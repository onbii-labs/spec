# 0029: Captured Audio Originals Are Compact, Not Lossless

Status: Accepted

Date: 2026-07-24

## Context

Onbii preserves the original source recording of an audio object (see
[0008](0008-preserve-original-sources.md)) so it can be transcribed and
reprocessed later — including future paralinguistic analysis such as intonation,
mood, or stress. "Preserve the original" left one thing implicit: whether that
original must be *lossless*.

In practice capture paths diverged: some recorded compressed AAC while others
captured uncompressed 16-bit linear PCM WAV. Uncompressed PCM is roughly 10–15×
larger (~5.5 MB/min versus ~0.4 MB/min for mono speech). That cost lands hardest
on the devices least able to bear it — wearables and phones that must transfer or
sync a recording before it is safely stored — which is exactly backwards.

Onbii does not require bit-exact originals. It requires a retained original that
is *good enough* to transcribe today and to reprocess with better tools later.
Small, uniform, and good-enough beats large and lossless.

## Decision

The retained audio original is a **compact, lossy, "good enough" encoding**, not
lossless, and it should be **uniform across an implementation's capture paths**
rather than varying per device. This is a project-wide principle, not specific to
one platform.

### Baseline recording specification

Every capture path targets this baseline for the preserved original:

- **Codec:** a modern lossy audio codec; AAC by default.
- **Container / media type:** MPEG-4 audio (`.m4a`), source media type
  `audio/mp4`.
- **Sample rate:** 44.1 kHz, and never below 24 kHz — the floor that keeps
  higher-frequency voice-quality cues available for later analysis.
- **Channels:** mono for single-speaker capture.
- **Quality:** approximately 64–96 kbps (equivalent to `AVAudioQuality.high`).
  A deliberate floor chosen to preserve prosody and voice-quality cues for future
  affect/paralinguistic reprocessing — not the minimum that would merely satisfy
  transcription.
- **No re-encoding:** derived processing reads from this original; it must never
  re-compress it (which would compound lossy artefacts).

### Apple realisation

iOS, macOS, and watchOS record identically through `AVAudioRecorder` with
`kAudioFormatMPEG4AAC`, 44.1 kHz, mono, and `AVAudioQuality.high`. Other platforms
should meet the same baseline with an equivalent compact codec.

## Consequences

- Recordings stay small, so transfer-constrained capture (watch, wearables,
  phones) reaches durable storage quickly — reinforcing capture certainty.
- Uniform originals give one provenance and processing story and simpler tooling.
- The retained original is lossy — an accepted trade for smaller files, faster
  transfer, and uniformity across devices.
- This refines [0008](0008-preserve-original-sources.md): "preserve the original"
  means retain a faithful, good-enough recording, not a bit-exact one. It does
  not affect the still-open shared package and media-type questions
  ([0025](0025-onbii-package-format-open.md)).
- A future capture *mode* that needs richer signal — e.g. spatial or
  multi-microphone capture to map who spoke where in a room — may define its own
  format for that mode without changing this default.

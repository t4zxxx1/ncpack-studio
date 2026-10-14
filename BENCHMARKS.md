# Benchmarks

How NCPack Studio was tested, and what came out. Every number here comes from our test runs of
September 2026. 🇮🇹 Italian summary at the end.

- [1. Fifteen videos "as in real life"](#1-fifteen-videos-as-in-real-life)
- [2. Accuracy of the size estimate](#2-accuracy-of-the-size-estimate)
- [3. SCORM Lightener on a real course](#3-scorm-lightener-on-a-real-course)
- [4. Why a WhatsApp video stays as it is](#4-why-a-whatsapp-video-stays-as-it-is)
- [How quality is measured](#how-quality-is-measured)

---

## 1. Fifteen videos "as in real life"

One video per typical situation, run through the app exactly as a user would (add, wait for the
estimate, compress, read the report) at the **High** level, **Fast** speed.

<details>
<summary><b>The 15 sources</b></summary>

Phone H.264 at 22 Mbps · iPhone HEVC 10-bit · vertical video with rotation · 5.1 audio · screen recording ·
film grain · simulated WhatsApp · YouTube VP9 · already AV1 · dimensions not multiple of 8 ·
ProRes 4:2:2 10-bit camera · MJPEG camera · old DVD (MPEG-2) · 1.5-second clip · a real WhatsApp video.

</details>

Each file is checked for: lighter than the original, VMAF ≥ 95 and 5th percentile ≥ 89, estimate within
±25%, and the same duration, frame count, audio channels and orientation as the original.

| | Result |
|:--|:--|
| Files that keep every promise | **15 / 15** |
| Compressed (lighter, at the promised quality) | 12 |
| Kept as the original, because AV1 couldn't make them lighter without losing quality | 3 |
| Files heavier than the original | **0** |
| Size estimate within ±25% | 12 / 12 (from −17% to +11%) |
| Duration, frames, audio channels, orientation identical to the original | 12 / 12 |

The finished file always beats the quality of the search samples: from +0.0 to +1.5 VMAF, median +0.7.

## 2. Accuracy of the size estimate

Before compressing, the app really compresses four 48-frame samples at several quality settings and
measures them, then predicts the size of the whole file for each level. Compared with the real
compressions:

| | |
|:--|:--:|
| 14 real videos, High level: **median error** | **2.6%** |
| same videos, within 15% | 13 / 14 |
| 18 videos, 23 sizes (High and Compact): within 10% | 17 / 23 |

The remaining misses are content the size model finds hard: simulated WhatsApp (−18%), a 6-second clip
full of cuts (−28%), heavy grain (−12%).

Analysis time: a 20 s 4K video in 54 s, a 29-minute video in 22 s.

## 3. SCORM Lightener on a real course

An Articulate Storyline–style course (SCORM 1.2: 4 videos, 2 narrations, images, scripts that reference
the videos by name), High level:

| File | Before | After | Result |
|:--|--:|--:|:--|
| intro.mp4 (1080p) | 35.9 MB | 6.62 MB | VMAF 97.2 (5th percentile 94.4) |
| docente.mp4 (720p) | 6.19 MB | 3.27 MB | VMAF 95.9 |
| lezione.mp4 (720p slides) | 3.90 MB | 2.64 MB | VMAF 96.0 |
| gia_leggero.mp4 | 0.41 MB | unchanged | can't get 5% lighter |
| narrazione.mp3 (256 kbps) | 0.64 MB | 0.32 MB | 128 kbps |
| effetto.mp3 (96 kbps) | 0.12 MB | unchanged | already under 160 kbps |
| **Package** | **46.9 MB** | **13.3 MB (−71.8%)** | free estimate beforehand: −71.1% |

Both packages were run on a simulated LMS exposing the SCORM 1.2 API: in Chrome and Safari all four videos
play and the course reports *completed* with score 100. Malformed packages (no manifest, manifest in a
subfolder, not a ZIP, paths escaping the folder) are refused with the reason.

## 4. Why a WhatsApp video stays as it is

A real WhatsApp video (1:30, 1024×576, H.264 Baseline at 776 kbps, video track 8.73 MB) at different AV1
settings:

| AV1 setting | Size | vs original | VMAF |
|:--|--:|--:|--:|
| CRF 34 | 24.5 MB | +181% | 96.7 |
| CRF 42 | 14.4 MB | +65% | 92.9 |
| CRF 48 | 10.1 MB | +16% | 89.5 |
| CRF 54 | 7.0 MB | −20% | 85.1 |

VMAF compares with what is in the file, WhatsApp's own artefacts included, and AV1 spends bits reproducing
them. At the original's size the quality is already down to VMAF 89. So NCPack Studio keeps the
original, and the estimate says so before you start.

## How quality is measured

- **VMAF** (Netflix) on every frame of the finished file against the original: mean, 5th percentile and
  worst frame. The target is checked on the file, not on samples.
- **Never heavier:** the AV1 file must weigh at most 95% of the original, or the original is kept.
- **Same content:** duration, frame count, audio channels and orientation are verified.
- Sources above 8-bit (10-bit phone HEVC, ProRes) become 10-bit AV1; 4:2:2 and 4:4:4 become 4:2:0.

---

### 🇮🇹 In breve

Su 15 video tipici (telefono, iPhone HEVC 10 bit, WhatsApp, ProRes, DVD, registrazioni dello schermo…)
al livello Alta: **15 su 15** rispettano ogni promessa, **0** file più pesanti dell'originale. La stima
del peso ha un **errore mediano del 2,6%** su 14 video reali. Un corso SCORM in stile Articulate passa da
**46,9 a 13,3 MB (−71,8%)** e funziona come prima in Chrome e Safari.

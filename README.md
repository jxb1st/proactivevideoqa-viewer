# ProactiveVideoQA Viewer

Case-by-case web viewer for [ProactiveVideoQA](https://github.com/yellow-binary-tree/ProactiveVideoQA) — ships with an 8-sample representative subset (2 per subset × 4 subsets).

**Live site:** https://jxb1st.github.io/proactivevideoqa-viewer/

## Subsets

- **WEB** — open-domain web videos. Single question at t=0; model must emit a time-aligned stream of descriptive responses as content unfolds.
- **EGO** — Ego4D-style first-person cooking/activity videos. Model narrates steps/substeps over time; each reply is tagged with a hierarchical type.
- **TV** — Friends / Big Bang Theory / House / Met clips with subtitle streams injected into the conversation. One factual question, answered at a specific moment.
- **VAD** — UCF-Crime-style surveillance footage. Model is expected to stay silent until an anomaly begins, then report it.

## Contents

- `index.html` — single-file viewer with timeline markers for related/reply timespans
- `<subset>/anno.json` — filtered to 2 samples per subset
- `<subset>/videos/` — re-encoded 480p mp4s (h264 CRF 28 / AAC 64k / faststart)
- `file_durations.json` — duration lookup
- `selection_report.md` — which videos were picked

## Local preview

```bash
cd proactivevideoqa-viewer
python3 -m http.server 8000
# open http://localhost:8000/
```

## Full benchmark

For the full dataset and evaluation code, see the [official ProactiveVideoQA repo](https://github.com/yellow-binary-tree/ProactiveVideoQA).

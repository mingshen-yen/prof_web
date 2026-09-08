---
title: Seismic Stress Drop Scaling Study
summary: "A waveform pipeline that reduced ~52 million raw records to 6,135 characterised earthquakes, then tested how stress drop scales with magnitude across Western Europe."
tag: Research
image: /images/stress-drop-fig8b.jpg
stack: [Python, SQL]
sourceUrl: https://doi.org/10.1007/s10950-023-10188-y
sourceKind: paper
liveUrl: https://beaded-tumble-185.notion.site/Earthquakes-Stress-Drop-Scaling-Study-38fe7c276c51816a9a4dd2d8f2c967a7?pvs=73
liveKind: notes
featured: true
order: 2
---

Stress drop is one of the parameters hazard models depend on, and estimating it means getting source, site, and path effects apart from one another across every record you have. This built the pipeline to do that at continental scale, then asked what the resulting catalogue says about scaling.

#### ***Data***

- ~52 million raw waveforms, Western Europe, January 1990 to May 2020
- Reduced to 220,000 high-quality records covering 6,135 shallow crustal events

#### ***Pipeline***

1. **Automated quality control** over the full raw archive — the step that takes 52 million records down to the 220,000 worth analysing
2. **Spectral decomposition** using the Generalized Inversion Technique (GIT), which separates source, site, and path contributions rather than letting them contaminate each other
3. **Source parameter estimation** per event: seismic moment, corner frequency, and stress drop derived from the ω²-source model

#### ***Validation***

Source spectra were checked against the standard ω²-model, which most conform to — the model fit is what makes the derived stress drops trustworthy rather than merely computed.

#### ***Outcome***

A catalogue of 6,135 characterised events, and from it: stress drop correlates positively with moment magnitude between Mw 3 and 4, self-similarity holds above Mw 4, and the mean stress drop across Western Europe is 13.8 MPa.

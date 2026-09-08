---
title: 52 Million Waveforms, 6,135 Earthquakes
summary: "A waveform pipeline that reduced ~52 million raw records to 6,135 characterised earthquakes, then tested how stress drop scales with magnitude across Western Europe."
tag: Research
image: /images/stress-drop-fig8b.jpg
stack: [Python, stream2segment, SQL]
sourceUrl: https://doi.org/10.1007/s10950-023-10188-y
sourceKind: paper
liveUrl: https://beaded-tumble-185.notion.site/Earthquakes-Stress-Drop-Scaling-Study-38fe7c276c51816a9a4dd2d8f2c967a7?pvs=73
liveKind: notes
featured: true
order: 2
---

Stress drop is one of the parameters hazard models depend on, and estimating it means getting source, site, and path effects apart from one another across every record you have. This built the pipeline to do that at continental scale, then asked what the resulting catalogue says about scaling.

#### ***Data***

- **~52 million single-component waveforms** — about 18 million three-component records — from January 1990 to May 2020
- Drawn from the European Integrated Data Archive across **~1,600 stations** in Germany, Italy, France and Poland
- Reduced to **220,000 high-quality spectra** covering **6,135 events**, M 1.0 to 6.5

#### ***Pipeline***

1. **Quality control, on explicit thresholds.** Signal-to-noise above 20, modified Z-score outlier rejection at ±3.5, and a multi-event detector to drop records contaminated by a second arrival. This is the stage that takes 52 million waveforms down to the 220,000 worth inverting.
2. **Spectral decomposition.** The Generalized Inversion Technique separates source, path attenuation and site amplification non-parametrically — a large linear system solved in the log-spectral domain, rather than three effects left to contaminate one another.
3. **Regionalised attenuation.** The study area is split along the Alps into Central Europe and Italy, with a separate attenuation function fitted to each, because one continental average biases both.
4. **Source parameters.** Each source spectrum is fitted to an ω² (Brune) model by least squares for corner frequency and seismic moment, and stress drop follows from those.

#### ***Validation***

- **100 bootstrap inversions per frequency point**, to show the decomposition is stable rather than merely convergent
- Results **benchmarked against independently published catalogues**, including Bindi et al. (2023a)
- The regionalisation was tested, not assumed: dropping it overestimates stress drop in Central Europe and underestimates it in Italy, which is what justifies the extra complexity

#### ***Outcome***

A catalogue of 6,135 characterised events, and from it: stress drop correlates positively with moment magnitude between M 3 and 4, self-similarity holds above M 4, and within that self-similar regime the mean stress drop is 13.8 MPa — consistently higher in Italy than in Central Europe. The resulting probability distributions calibrate stochastic ground-motion simulations for European hazard assessment, and fed into the EU H2020 URBASIS framework.

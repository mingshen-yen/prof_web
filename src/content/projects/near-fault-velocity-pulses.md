---
title: Near-Fault Velocity Pulses, Mw 6 to 7.8
summary: "80 velocity pulses extracted from five moderate earthquakes across three national networks, then 30 more from the 2023 Kahramanmaraş doublet — each tested against a simulation of the same rupture."
tag: Research
image: /images/velocity-pulses-moderate.jpg
stack: [Python, MATLAB]
sourceUrl: https://doi.org/10.1177/87552930241305012
sourceKind: paper
liveUrl: https://tec.earth.sinica.edu.tw/publication/newsletter/html/202412/46_06.html
liveKind: article
featured: false
order: 3
---

A velocity pulse concentrates a rupture's energy into one or two large swings, and it damages structures whose natural period matches it. Engineering practice predicts a pulse's period from magnitude alone. Two studies test that assumption from opposite ends of the magnitude range, and find it does not hold.

#### **_Data_**

- **Five moderate earthquakes, Mw 6.1–7.04**, across three national networks: 2016 Meinong and 2018 Hualien from TSMIP (Taiwan CWB, 200 Hz sampling), the 2016 Kumamoto foreshock and mainshock from K-NET, KiK-net and the JMA network (100 Hz), and 2010 Darfield from the GNS network
- **The 2023 Kahramanmaraş doublet**, Mw 7.8 Pazarcık and Mw 7.5 Elbistan, recorded by **349 and 288 strong-motion stations** (AFAD-TADAS) — raw records from AFAD, independently processed records from the Engineering Strong Motion database
- **Synthetic waveforms** from published 3D dynamic rupture models of the Mw 7.8 event, at two resolutions

#### **_Pipeline_**

1. **Separate the two things that look alike.** A permanent ground offset produces a one-sided pulse that a wavelet cannot distinguish from a directivity pulse. Every record passes through instrument-drift correction, segmented baseline estimation (ICBM), and a static-offset routine before any pulse is extracted — otherwise fling and directivity are counted as the same phenomenon.
2. **Extract.** Wavelet analysis over both horizontal components (Shahi & Baker, 2014; order-4 Daubechies), taking the largest-coefficient wavelet as the strongest pulse and recording its period, PGV and orientation.
3. **Classify.** The pulse indicator, computed from the PGV and energy ratios of residual to original motion; for the doublet, PGV > 20 cm/s as an entry criterion.
4. **Simulate.** Seven fault models solved with the frequency–wavenumber method: three dip angles (90°, 70°, 50°) and four asperity cases varying location and size (2.1 and 4.9 km), for an Mw 6.0 rupture carrying an Mw 5.8 asperity over a 13-layer velocity structure.
5. **Compare** observed against synthetic, station by station, and ask what the model fails to reproduce.

#### **_Validation_**

- Static-offset estimates were **validated against InSAR** before being trusted
- Extracted periods were checked against **244 pulses from NGA-West2**; for the Kumamoto mainshock the mean period is 5.2 s (σ 0.69) against an independent estimate of 5.5 s (σ 0.58–0.92)
- Pulse-detection rates were compared bin by bin — empirical **67% / 50% / 7%** at 0–10, 10–20 and 20–50 km against **58% / 25% / 7%** for the synthetics — bounding how many synthetic detections are artefacts of missing high frequencies

#### **_Findings_**

1. **Magnitude is a poor predictor.** Across 80 pulses from the five moderate events, period depends only weakly on magnitude between Mw 6 and 7.5, and the scatter within a single earthquake is large.
2. **Asperities govern it instead.** The simulations show pulse period and amplitude controlled by the location and size of the asperity: velocities rise near it, and an asperity far from the hypocentre produces stronger pulses than a near one of identical total slip.
3. **Standard practice overestimates reach.** Beyond 10 km, the empirical model — calibrated mainly on M > 6.5 events — predicts more pulses than moderate earthquakes actually produce.
4. **At Mw 7.8 the scatter widens.** Pulses appear at 23 of 50 stations for Pazarcık and 7 of 21 for Elbistan, with periods from 3 to 14 s. The standard deviation of log period is 1.19 for the Mw 7.8 against 0.64 for the Mw 7.5: variability itself scales with magnitude.
5. **Two stations 1.8 km apart disagree by 73°.** Orientations vary far more than directivity allows, and the dynamic rupture models — which align pulses with the fault-normal component — do not reproduce that spread. Stations 3.8 km apart differ on whether a pulse is there at all.
6. **The worst-hit city recorded the largest pulse.** 173–179 cm/s at Antakya, 1.5 km from the rupture but 130 km from the hypocentre.

#### **_Outcome_**

Directivity alone does not account for what near-fault stations record. Local slip heterogeneity, fault geometry and site response matter as much, which means a hazard assessment built on a magnitude-to-period relationship understates what an individual site can experience. Dynamic rupture models need more heterogeneous slip and geometry before they reproduce the variability that the instruments show.

#### **_Publications_**

- [Within- and between-event variabilities of strong-velocity pulses of moderate earthquakes within dense seismic arrays](https://doi.org/10.1785/0120200376), Bulletin of the Seismological Society of America, 2022
- [An analysis of directivity pulses using empirical data and dynamic rupture simulations of the 2023 Kahramanmaraş earthquake doublet](https://doi.org/10.1177/87552930241305012), Earthquake Spectra, 2025

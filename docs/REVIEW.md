# Review guide

[Project overview](../README.md) | [Original paper](../paper/vehicle-path-prediction-kim-et-al-2018.pdf) | [Download the presentation](https://github.com/yonatantamiru65-tech/vehicle-path-prediction-paper-review/releases/download/coursework-v1/Asfaw_YonatanTamiru_presentation.pptx)

This guide summarises the supplied coursework presentation. It does not add a new experimental study or claim implementation of the reviewed algorithm.

## 1. The problem studied

Adaptive Cruise Control (ACC) maintains a desired speed or a safe gap to a lead vehicle. The controller must first determine which detected vehicle lies in its predicted driving path: the Closest In-Path Vehicle (CIPV).

Slides 2-3 describe why prediction using constant yaw rate and speed can be inaccurate on curves with changing curvature. An incorrect CIPV selection can produce unnecessary braking.

## 2. The paper's proposed approach

Slides 4-9 explain the contributions attributed to Kim et al.:

- A clothoidal cubic polynomial predictor that incorporates curvature rate, using yaw acceleration as part of the path prediction.
- A Kalman filter based on a steering-to-yaw-rate state-space model to estimate yaw acceleration while handling noisy measurements.
- A multirate Kalman filter that estimates relative target states at the faster control rate between slower radar measurements.
- Integration of the estimates with path prediction, CIPV selection, and velocity/spacing control.

The architecture image in the repository is copied unchanged from the supplied PPTX (`ppt/media/image8.png`, slide 6). It reproduces Fig. 1 of the reviewed paper and remains credited to the research authors.

## 3. Evidence discussed in the slides

| Review slides | Evidence shown | How to interpret it |
|---|---|---|
| 10 | Test-road trajectory and path predictions at selected points | Comparison of the paper's proposed and conventional predictors |
| 11 | Lateral path-prediction error | Evidence reported by the original research, not a new measurement by the reviewer |
| 12 | Target selection near a curve inflection and ACC acceleration/velocity | Relationship between prediction, selected target and longitudinal response |

Slide 13 summarises the review's takeaways: yaw-acceleration information helps describe curvature transitions, improved prediction supports target selection, and multirate estimation supports faster control updates with reduced ripples. These statements summarise the paper and presentation; no independent benchmark was run for this repository.

## 4. What this assignment demonstrates

The material documents study and explanation of a vehicle-control research paper: identifying its motivation, following its estimation/control architecture, interpreting reported comparisons and communicating the findings in a presentation.

## 5. Reference map

The primary paper is cited on the title slide. The repository's [README](../README.md#citation-and-attribution) and [BibTeX file](../references.bib) provide its full citation.

The original presentation's final slide also lists:

- Moradi et al. (2020), *Exploring Fault Parameter Space Using Reinforcement Learning-based Fault Injection*, DOI: 10.1109/DSN-W50199.2020.00028.
- Olson et al. (2022), *Model-Based Design Approach for Validation of Vehicle Longitudinal Control Algorithm*, DOI: 10.47611/jsr.v11i2.1638.
- Houenou et al. (2013), *Vehicle Trajectory Prediction based on Motion Model and Maneuver Recognition*, DOI: 10.1109/IROS.2013.6696982.

These are recorded as references present in the supplied deck; they do not replace the primary Kim et al. paper reviewed in this assignment. The original presentation has not been edited.

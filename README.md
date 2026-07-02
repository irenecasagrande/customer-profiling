# Customer Profiling on Banking Data

Data-driven customer segmentation project built during my MSc coursework.
The goal is to identify distinct customer segments from behavioural banking
data and turn them into actionable profiles for targeted product offering.

# Approach
1. EDA & anomaly detection — flagged logical inconsistencies in the raw data.
2. Custom Gower-like distance. 
3. K-Medoids on the Gower distance — mathematically optimal at K = 4, but the
segments were hard to interpret, motivating a dimensionality-reduction step.
4. t-SNE (2D/3D) — visual inspection of the natural cluster structure.
5. FAMD — reduced the space to 3 interpretable components.
6. GLVQ (Generalised Learning Vector Quantization) — supervised prototype learning on
the FAMD space to test how much financial structure the 3 components actually capture.
7. Quadrant segmentation — the business-driven segmentation, cutting the
PC0 × PC1 plane into four named segments, enriched with two engineered composite scores
(ProductScore, StressScore).
8. K-Means validation — an unsupervised benchmark to check the quadrant structure is
not arbitrary.
## Key results
- ~5,000 customers, 17 mixed variables reduced to 3 FAMD dimensions.
- GLVQ key drivers: Gender (92%), Debt (73%), Income (71%), City Size (60%).
- Four actionable segments: Digital Investor, Digital Non-Investor, Traditional Investor, Traditional Passive.
- Financial risk ranges from 14% (Traditional Investor) to 40% (Traditional Passive) at risk.
- K-Means independently confirms the 4-cluster solution.

## Tech stack
Python · pandas · NumPy · SciPy · scikit-learn · kmedoids (K-Medoids) · prince (FAMD) ·
sklvq (GLVQ) · matplotlib · seaborn · plotly

## Notes
Developed in Google Colab. The dataset is not included for data-privacy reasons; the
notebook shows the full analysis with all outputs and plots saved, so it can be read
end-to-end without running it.

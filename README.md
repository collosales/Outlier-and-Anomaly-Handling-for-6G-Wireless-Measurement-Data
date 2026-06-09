A Systematic, Downstream-Centric Comparison of Statistical
Filters and Unsupervised Outlier Detectors for Tabular and
Time-Series 6G Network Measurements.

Links to datasets: - https://doi.org/10.5281/zenodo.6907619 - Time-Series
                   - https://dx.doi.org/10.21227/xtep-hv36 - Tabular

## Abstract

Machine-learning-driven management of next-generation (6G) networks depends on
measurements that are routinely corrupted by sensor noise, hardware imperfections,
bursty interference, and malicious activity, so outlier handling is widely assumed to be
a prerequisite for reliable downstream models. Whether, and which, cleaning methods
actually help, and whether this differs across data modalities, remains unclear. Us-
ing two real, labelled datasets with no synthetic contamination, attack traffic from a
functional 5G testbed (attack classification) and an operational web-latency KPI se-
ries (short-term forecasting), we systematically compare six outlier-handling methods,
namely interpretable statistical filters (robust Z-score replacement, IQR clipping, and
Savitzky–Golay smoothing) and unsupervised detectors (Isolation Forest, Local Out-
lier Factor, and PCA reconstruction), against a no-cleaning baseline. Hyperparameters
are tuned without access to held-out labels; each method is evaluated under both a
robust (Random Forest) and a noise-sensitive (k-NN) downstream model, with paired
significance tests and false-discovery-rate (FDR) correction, a detection diagnostic, and
runtime. The result is largely negative: after FDR correction, no method significantly
improves downstream performance on either modality. Savitzky–Golay smoothing gives
the only suggestive forecasting gain (≈17% lower error under Random Forest) but does
not survive correction; deletion- and clipping-based methods are neutral-to-harmful
(IQR significantly degrades classification); and the unsupervised detectors rank real
attacks barely above chance (ROC-AUC 0.54–0.60), even though a supervised model
separates the same classes at 0.86, statistical outlier detection is a poor proxy for the
anomalies of interest. As the slowest detectors are also the most harmful and exceed the
near-real-time control budget, we conclude that a generic outlier-handling stage offers
no reliable benefit for these tasks: its value must be demonstrated rather than assumed,
with lightweight smoothing the only candidate worth trying on noisy sequential signals.

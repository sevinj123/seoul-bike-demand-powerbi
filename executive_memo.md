# Executive memo — Seoul bike rental demand

**Decision:** Prioritize bike availability around the evening peak, especially in summer, while planning lower baseline capacity for rainy periods. Validate station-level patterns before changing allocation, because this dataset does not identify stations.

**Evidence.** In summer, average hourly rentals at 18:00 were 2,135.14 versus 1,418.60 at 08:00. The evening average was 50.51% higher relative to the morning average; each figure is based on 92 hourly observations. Overall, holiday hours averaged 499.76 rentals versus 715.23 in non-holiday hours, a 30.13% difference. Rainy hours averaged 163.46 rentals versus 739.31 in dry hours, a 77.89% lower average.

**Operational implication.** Use 18:00 as the first citywide planning checkpoint in summer and 08:00 as a secondary peak. Consider rainfall when preparing capacity, but retain flexibility: these comparisons describe historical averages, not a causal effect or a forecast.

**Important limits.** The dataset spans 365 dates from December 2017 through November 2018 and contains hourly citywide records rather than station-level demand. Temperature–season bins can be sparse: the autumn 30°C bin, for example, has only two hourly observations. Holiday patterns also vary by season. Check sample counts and relevant filters before applying a broad conclusion.

**Report delivery.** The two-page Power BI report includes date-range filters, reset buttons, page navigation, and tooltips with observation counts. A short silent demo is available in `demo.mp4`.

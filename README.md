# ACCESS-Volatility-Modeling-on-GSE
Volatility modeling of Access Bank Plc

Summary of Findings

- The dataset from the GSE contains several listed companies.
- After plotting companies like **GCB**, **MTN**, and **CAL Bank**, their **closing prices did not show any meaningful trends**.
- Only **ACCESS Bank** showed some **noticeable price movement**, which made it a reasonable candidate for further modeling.
- Daily returns (computed using `pct_change`) contained a large number of **zero values**, indicating **very few trades occur on a day-to-day basis**.
- The same issue remained when using **weekly returns**, and as a result, **stationarity tests (ADF) failed** due to lack of variation.
- We therefore switched to **monthly returns**, which showed enough variation and produced a **reasonable stationarity p-value** (ADF p-value ≈ 0.0469).
- A **GARCH(1,1)** model was initially fitted to the ACCESS monthly returns, but the **β parameter was approximately zero**, meaning **there was no persistence in volatility**.
- This implies that **GARCH is not appropriate** for this dataset.
- Instead, an **ARCH(1)** model was used, which is more suitable in situations where volatility appears as **isolated shocks** rather than persistent clusters.
- The conditional variance from the ARCH(1) model was estimated and **plotted** at the end of the analysis.


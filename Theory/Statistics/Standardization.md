In statistics and machine learning, **standardization** transforms data so that it has specific statistical properties (most commonly a mean of $0$ and a standard deviation of $1$).

Here are all the key formulas related to standardization across different contexts:

---

### 1. Z-Score Standardization (Standard Scaler)

Transforms data to have a mean ($\mu$) of $0$ and a standard deviation ($\sigma$) of $1$.

* **Population Z-score:**

$$z = \frac{x - \mu}{\sigma}$$

* $x$: raw value
* $\mu$: population mean
* $\sigma$: population standard deviation
* **Sample Z-score:**

$$z = \frac{x - \bar{x}}{s}$$

* $\bar{x} = \frac{1}{n}\sum_{i=1}^n x_i$ (sample mean)
* $s = \sqrt{\frac{\sum_{i=1}^n (x_i - \bar{x})^2}{n - 1}}$ (sample standard deviation)

---

### 2. Standardizing Sampling Distributions (Inferential Statistics)

Used in hypothesis testing and confidence intervals when dealing with sample estimates rather than individual data points.

* **Standardizing a Sample Mean (Known Population Variance - Z-test):**

$$Z = \frac{\bar{x} - \mu}{\frac{\sigma}{\sqrt{n}}}$$

* $\frac{\sigma}{\sqrt{n}}$: standard error of the mean ($SE$)
* **Standardizing a Sample Mean (Unknown Population Variance - One-Sample t-test):**

$$t = \frac{\bar{x} - \mu}{\frac{s}{\sqrt{n}}}$$

* **Standardizing a Sample Proportion:**

$$Z = \frac{\hat{p} - p_0}{\sqrt{\frac{p_0(1 - p_0)}{n}}}$$

* $\hat{p}$: sample proportion
* $p_0$: hypothesized population proportion
* **Standardizing the Difference Between Two Sample Means (Independent t-test):**

$$t = \frac{(\bar{x}_1 - \bar{x}_2) - (\mu_1 - \mu_2)}{SE_{(\bar{x}_1 - \bar{x}_2)}}$$

Where pooled standard error (assuming equal variances) is:

$$SE = s_p \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}, \quad s_p = \sqrt{\frac{(n_1 - 1)s_1^2 + (n_2 - 1)s_2^2}{n_1 + n_2 - 2}}$$

* **Standardizing Paired Differences (Paired t-test):**

$$t = \frac{\bar{d} - \mu_d}{\frac{s_d}{\sqrt{n}}}$$

* $\bar{d}$: mean of differences
* $s_d$: standard deviation of differences

---

### 3. Robust Standardization (Robust Scaler)

Used when data contains severe outliers, replacing the mean and standard deviation with median and interquartile range (IQR).

$$x_{\text{robust}} = \frac{x - \text{median}(X)}{\text{IQR}(X)}$$

* $\text{IQR} = Q_3 - Q_1$ ($75^{\text{th}}$ percentile minus $25^{\text{th}}$ percentile)

---

### 4. Multivariate Standardization (Mahalanobis Distance / Whitening)

For a multivariate random vector $\mathbf{x} \in \mathbb{R}^p$ with mean vector $\boldsymbol{\mu}$ and covariance matrix $\boldsymbol{\Sigma}$:

* **Standardized / Whitened Vector ($\mathbf{z}$):**

$$\mathbf{z} = \boldsymbol{\Sigma}^{-1/2} (\mathbf{x} - \boldsymbol{\mu})$$

*(Results in $\mathbb{E}[\mathbf{z}] = \mathbf{0}$ and $\text{Cov}(\mathbf{z}) = \mathbf{I}$)*

* **Standardized Distance (Mahalanobis Distance):**

$$D_M(\mathbf{x}) = \sqrt{(\mathbf{x} - \boldsymbol{\mu})^T \boldsymbol{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu})}$$

---

### 5. Deep Learning Standardization Formulas

Techniques used to stabilize and accelerate neural network training.

* **Batch Normalization (per feature across batch $B$):**

$$\hat{x}_i = \frac{x_i - \mu_B}{\sqrt{\sigma_B^2 + \epsilon}}$$

$$y_i = \gamma \hat{x}_i + \beta$$

* $\mu_B = \frac{1}{m} \sum_{i=1}^m x_i$
* $\sigma_B^2 = \frac{1}{m} \sum_{i=1}^m (x_i - \mu_B)^2$
* $\epsilon$: small constant for numerical stability (e.g., $10^{-5}$)
* $\gamma, \beta$: learnable scale and shift parameters
* **Layer Normalization (per sample across features $H$):**

$$\hat{x}_{i, j} = \frac{x_{i, j} - \mu_L}{\sqrt{\sigma_L^2 + \epsilon}}, \quad y = \gamma \hat{x} + \beta$$

* $\mu_L = \frac{1}{H} \sum_{j=1}^H x_{i, j}$
* $\sigma_L^2 = \frac{1}{H} \sum_{j=1}^H (x_{i, j} - \mu_L)^2$

---

### 6. Standardized Coefficients in Regression

Used to compare the relative importance of independent variables measured on different scales.

* **Standardized Beta Coefficient ($\beta_j^*$):**

$$\beta_j^* = \beta_j \times \left(\frac{s_{x_j}}{s_y}\right)$$

* $\beta_j$: unstandardized regression slope
* $s_{x_j}$: standard deviation of predictor $x_j$
* $s_y$: standard deviation of dependent variable $y$

---

### Summary Comparison of Scaler Types

| Scaler | Formula | Center | Spread / Scale | Handles Outliers? |
| --- | --- | --- | --- | --- |
| **Standard (Z-score)** | $\frac{x - \mu}{\sigma}$ | Mean ($0$) | Standard Deviation ($1$) | No |
| **Robust** | $\frac{x - \text{median}}{\text{IQR}}$ | Median ($0$) | Interquartile Range | Yes |
| **Min-Max (Normalization)** | $\frac{x - x_{\min}}{x_{\max} - x_{\min}}$ | Varies | Range $[0, 1]$ | No |

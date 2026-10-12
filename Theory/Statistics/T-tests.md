# Formulas

## Two-Tailed Test


### One-Sample t-Test

**Degrees of Freedom ($df$)**

$$df = n - 1$$

**Sample Standard Deviation ($s$)**

$$
s = \sqrt{\frac{\sum_{i=1}^{n}(x_i-\bar{x})^2}{n-1}}
$$

**Standard Error of the Mean ($SE$)**

$$SE = \frac{s}{\sqrt{n}}$$

**t-Statistic**

$$
t = \frac{\bar{x}-\mu_0}{\frac{s}{\sqrt{n}}} = \frac{\bar{x}-\mu_0}{SE}
$$

**Decision Rule**

$$|t_{\text{stat}}| > t_{\text{crit}} \implies \text{Reject } H_0$$

Otherwise, fail to reject $H_0$.

---

### Paired t-Test

Used when observations are paired (e.g., pre-test vs. post-test measurements for the same individuals), with difference $d_i = x_{2i} - x_{1i}$.

**Degrees of Freedom ($df$)**

$$df = n - 1$$

*(where $n$ is the number of pairs)*

**Mean Difference ($\bar{d}$)**

$$\bar{d} = \frac{\sum d_i}{n}$$

**Standard Deviation of Differences ($s_d$)**

$$s_d = \sqrt{\frac{\sum (d_i - \bar{d})^2}{n - 1}}$$

**Standard Error of the Mean Difference ($SE_d$)**

$$SE_d = \frac{s_d}{\sqrt{n}}$$

**t-Statistic**

$$t = \frac{\bar{d} - \mu_d}{\frac{s_d}{\sqrt{n}}} = \frac{\bar{d} - \mu_d}{SE_d}$$

*(typically $\mu_d = 0$ for testing whether differences exist)*

**Decision Rule**

$$|t_{\text{stat}}| > t_{\text{crit}} \implies \text{Reject } H_0$$

Otherwise, fail to reject $H_0$.

---

### Independent (Two-Sample) t-Test

Used when comparing means between two separate, independent groups.

**Degrees of Freedom ($df$)**

$$df = n_1 + n_2 - 2$$

**Sample Variances ($s_1^2, s_2^2$)**

$$s_1^2 = \frac{\sum_{i=1}^{n_1} (x_{1i} - \bar{x}_1)^2}{n_1 - 1}, \quad s_2^2 = \frac{\sum_{i=1}^{n_2} (x_{2i} - \bar{x}_2)^2}{n_2 - 1}$$

**Pooled Variance ($s_p^2$) (Equal Variances Assumed)**

$$s_p^2 = \frac{(n_1 - 1)s_1^2 + (n_2 - 1)s_2^2}{n_1 + n_2 - 2}$$

**Standard Error ($SE$)**

$$SE = \sqrt{s_p^2 \left(\frac{1}{n_1} + \frac{1}{n_2}\right)} = s_p \sqrt{\frac{1}{n_1} + \frac{1}{n_2}}$$

**t-Statistic**

$$t = \frac{(\bar{x}_1 - \bar{x}_2) - (\mu_1 - \mu_2)}{SE}$$

*(typically $\mu_1 - \mu_2 = 0$ when testing if group means are equal)*

**Decision Rule**

$$|t_{\text{stat}}| > t_{\text{crit}} \implies \text{Reject } H_0$$

Otherwise, fail to reject $H_0$.

> **Note (Unequal Variances - Welch's t-Test):**  
> If the assumption of equal variances does not hold:  
> $$SE = \sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}$$  
> with degrees of freedom calculated using the Welch–Satterthwaite equation.

---

## One-Tailed Test

In a one-tailed test, the test statistic formulas ($t$, $SE$, and $df$) are identical to the two-tailed tests, but the hypotheses and critical rejection regions are directional.

### 1. Right-Tailed (Upper-Tailed) Test

* **Hypotheses:**  
  * One-Sample: $H_0: \mu \le \mu_0 \quad \text{vs} \quad H_1: \mu > \mu_0$  
  * Paired: $H_0: \mu_d \le 0 \quad \text{vs} \quad H_1: \mu_d > 0$  
  * Independent: $H_0: \mu_1 \le \mu_2 \quad \text{vs} \quad H_1: \mu_1 > \mu_2$

* **Decision Rule:**

$$t_{\text{stat}} > t_{\text{crit}} \implies \text{Reject } H_0$$

Otherwise, fail to reject $H_0$.

---

### 2. Left-Tailed (Lower-Tailed) Test

* **Hypotheses:**  
  * One-Sample: $H_0: \mu \ge \mu_0 \quad \text{vs} \quad H_1: \mu < \mu_0$  
  * Paired: $H_0: \mu_d \ge 0 \quad \text{vs} \quad H_1: \mu_d < 0$  
  * Independent: $H_0: \mu_1 \ge \mu_2 \quad \text{vs} \quad H_1: \mu_1 < \mu_2$

* **Decision Rule:**

$$t_{\text{stat}} < -t_{\text{crit}} \implies \text{Reject } H_0$$

*(or $t_{\text{stat}} < t_{\text{crit}}$ where critical value is negative)*  
Otherwise, fail to reject $H_0$.

---

## Quick Reference Summary Table

| Test Type | Null Hypothesis ($H_0$) | Degrees of Freedom ($df$) | Standard Error ($SE$) | Test Statistic ($t$) |
| :--- | :--- | :--- | :--- | :--- |
| **One-Sample t-Test** | $\mu = \mu_0$ | $n - 1$ | $\frac{s}{\sqrt{n}}$ | $t = \frac{\bar{x} - \mu_0}{SE}$ |
| **Paired t-Test** | $\mu_d = 0$ | $n - 1$ | $\frac{s_d}{\sqrt{n}}$ | $t = \frac{\bar{d} - \mu_d}{SE_d}$ |
| **Independent t-Test** (Equal Variances) | $\mu_1 = \mu_2$ | $n_1 + n_2 - 2$ | $\sqrt{s_p^2 \left(\frac{1}{n_1} + \frac{1}{n_2}\right)}$ | $t = \frac{\bar{x}_1 - \bar{x}_2}{SE}$ |
| **Independent t-Test** (Unequal Variances) | $\mu_1 = \mu_2$ | Welch–Satterthwaite | $\sqrt{\frac{s_1^2}{n_1} + \frac{s_2^2}{n_2}}$ | $t = \frac{\bar{x}_1 - \bar{x}_2}{SE}$ |

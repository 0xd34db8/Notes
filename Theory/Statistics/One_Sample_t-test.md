**Q.** A university claims that the average time taken by students to complete an online examination is 60 minutes. A researcher randomly selects 10 students and records their completion times as 58, 62, 55, 64, 61, 57, 63, 59, 65, and 56 minutes.
At a 5% level of significance, perform a t-test to determine whether the average completion time of students is significantly different from 60 minutes.

**Ans.**: To determine whether the average completion time is significantly different from 60 minutes, we perform a two-tailed one-sample $t$-test.

---

### 1. State the Hypotheses

* **Null Hypothesis ($H_0$):** $\mu = 60$ (The true mean completion time is equal to 60 minutes)
* **Alternative Hypothesis ($H_1$):** $\mu \neq 60$ (The true mean completion time is significantly different from 60 minutes)

---

### 2. Sample Data and Descriptive Statistics

Sample values ($n = 10$):

$58, 62, 55, 64, 61, 57, 63, 59, 65, 56$

* **Sample Size ($n$):** $10$
* **Degrees of Freedom ($df$):** $n - 1 = 10 - 1 = 9$

#### Sample Mean ($\bar{x}$)

$$\bar{x} = \frac{\sum x_i}{n} = \frac{58 + 62 + 55 + 64 + 61 + 57 + 63 + 59 + 65 + 56}{10} = \frac{600}{10} = 60.0$$

#### Deviations from the Mean $(x_i - \bar{x})$ and Squared Deviations

* $(58 - 60)^2 = (-2)^2 = 4$
* $(62 - 60)^2 = (2)^2 = 4$
* $(55 - 60)^2 = (-5)^2 = 25$
* $(64 - 60)^2 = (4)^2 = 16$
* $(61 - 60)^2 = (1)^2 = 1$
* $(57 - 60)^2 = (-3)^2 = 9$
* $(63 - 60)^2 = (3)^2 = 9$
* $(59 - 60)^2 = (-1)^2 = 1$
* $(65 - 60)^2 = (5)^2 = 25$
* $(56 - 60)^2 = (-4)^2 = 16$

$$\sum (x_i - \bar{x})^2 = 4 + 4 + 25 + 16 + 1 + 9 + 9 + 1 + 25 + 16 = 110$$

#### Sample Standard Deviation ($s$)

$$s = \sqrt{\frac{\sum (x_i - \bar{x})^2}{n - 1}} = \sqrt{\frac{110}{9}} \approx \sqrt{12.222} \approx 3.496$$

---

### 3. Compute the Test Statistic ($t$)

The standard error of the mean ($SE$) is:

$$SE = \frac{s}{\sqrt{n}} = \frac{3.496}{\sqrt{10}} \approx \frac{3.496}{3.162} \approx 1.106$$

Now, compute the $t$-statistic:

$$t = \frac{\bar{x} - \mu_0}{\frac{s}{\sqrt{n}}} = \frac{60.0 - 60}{1.106} = \frac{0}{1.106} = 0.00$$

---

### 4. Critical Value and Decision Rule

* **Significance Level ($\alpha$):** $0.05$ (two-tailed)
* **Degrees of Freedom ($df$):** $9$

From the Student's $t$-distribution table, the critical value for a two-tailed test with $df = 9$ and $\alpha = 0.05$ is:

$$t_{\text{critical}} = \pm 2.262$$

* **Decision Rule:** Reject $H_0$ if $\vert{}t\vert{} > 2.262$. Otherwise, fail to reject $H_0$.

---

### 5. Conclusion

Since $\vert{}t\vert{} = 0.00 < 2.262$ (and $p\text{-value} = 1.0 > 0.05\(), we fail to reject the null hypothesis (\)H_0$).

There is no statistically significant evidence at the 5% level of significance to conclude that the average completion time differs from 60 minutes. The sample mean is exactly equal to the claimed population mean.

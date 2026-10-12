**Q.** A data science boot camp claims that introducing a new AI-assisted coding environment helps students finish a data analysis assessment faster. To test this claim, an instructor records the completion times (in minutes) of 8 students working under the standard environment as 54, 58, 52, 56, 59, 53, 57, and 55, and 8 students working under the new AI-assisted environment as 48, 51, 46, 50, 49, 47, 52, and 49. At a 5% level of significance, perform a $t$-test to determine whether students using the AI-assisted environment complete the assessment significantly faster than students using the standard environment.

**Ans.**:
To determine whether students using the AI-assisted environment finish the assessment significantly faster than those using the standard environment, an **independent two-sample $t$-test** (**one-tailed / left-tailed**) is performed.

---

### 1. State the Hypotheses

* **Null Hypothesis ($H_0$):** $\mu_1 \le \mu_2$ (The mean completion time with the AI-assisted environment is greater than or equal to that of the standard environment)
* **Alternative Hypothesis ($H_1$):** $\mu_1 < \mu_2$ (The mean completion time with the AI-assisted environment is significantly less than that of the standard environment)

*(where $\mu_1$ is the population mean for the AI-assisted environment and $\mu_2$ is the population mean for the standard environment)*

---

### 2. Sample Data and Descriptive Statistics

#### **Group 1: AI-Assisted Environment ($n_1 = 8$)**

Data: $48, 51, 46, 50, 49, 47, 52, 49$

* **Mean ($\bar{x}_1$):**

$$\bar{x}_1 = \frac{48 + 51 + 46 + 50 + 49 + 47 + 52 + 49}{8} = \frac{392}{8} = 49.0$$

* **Sum of Squared Deviations ($\sum (x_{1i} - \bar{x}_1)^2$):**
* $(48 - 49.0)^2 = (-1.0)^2 = 1.0$
* $(51 - 49.0)^2 = (2.0)^2 = 4.0$
* $(46 - 49.0)^2 = (-3.0)^2 = 9.0$
* $(50 - 49.0)^2 = (1.0)^2 = 1.0$
* $(49 - 49.0)^2 = (0.0)^2 = 0.0$
* $(47 - 49.0)^2 = (-2.0)^2 = 4.0$
* $(52 - 49.0)^2 = (3.0)^2 = 9.0$
* $(49 - 49.0)^2 = (0.0)^2 = 0.0$

$$\sum (x_{1i} - \bar{x}_1)^2 = 28.0$$

* **Sample Variance ($s_1^2$):**

$$s_1^2 = \frac{28.0}{8 - 1} = \frac{28.0}{7} = 4.0$$

---

#### **Group 2: Standard Environment ($n_2 = 8$)**

Data: $54, 58, 52, 56, 59, 53, 57, 55$

* **Mean ($\bar{x}_2$):**

$$\bar{x}_2 = \frac{54 + 58 + 52 + 56 + 59 + 53 + 57 + 55}{8} = \frac{444}{8} = 55.5$$

* **Sum of Squared Deviations ($\sum (x_{2i} - \bar{x}_2)^2$):**
* $(54 - 55.5)^2 = (-1.5)^2 = 2.25$
* $(58 - 55.5)^2 = (2.5)^2 = 6.25$
* $(52 - 55.5)^2 = (-3.5)^2 = 12.25$
* $(56 - 55.5)^2 = (0.5)^2 = 0.25$
* $(59 - 55.5)^2 = (3.5)^2 = 12.25$
* $(53 - 55.5)^2 = (-2.5)^2 = 6.25$
* $(57 - 55.5)^2 = (1.5)^2 = 2.25$
* $(55 - 55.5)^2 = (-0.5)^2 = 0.25$

$$\sum (x_{2i} - \bar{x}_2)^2 = 42.0$$

* **Sample Variance ($s_2^2$):**

$$s_2^2 = \frac{42.0}{8 - 1} = \frac{42.0}{7} = 6.0$$

---

### 3. Compute the Test Statistic ($t$)

#### **Pooled Variance ($s_p^2$)**

$$s_p^2 = \frac{(n_1 - 1)s_1^2 + (n_2 - 1)s_2^2}{n_1 + n_2 - 2} = \frac{28.0 + 42.0}{8 + 8 - 2} = \frac{70.0}{14} = 5.0$$

#### **Standard Error ($SE$)**

$$SE = \sqrt{s_p^2 \left(\frac{1}{n_1} + \frac{1}{n_2}\right)} = \sqrt{5.0 \left(\frac{1}{8} + \frac{1}{8}\right)} = \sqrt{5.0 \times 0.25} = \sqrt{1.25} \approx 1.1180$$

#### **$t$-Value**

$$t = \frac{\bar{x}_1 - \bar{x}_2}{SE} = \frac{49.0 - 55.5}{1.1180} = \frac{-6.5}{1.1180} \approx -5.814$$

---

### 4. Critical Value and Decision Rule

* **Significance Level ($\alpha$):** $0.05$ (one-tailed / left-tailed)
* **Degrees of Freedom ($df$):** $n_1 + n_2 - 2 = 8 + 8 - 2 = 14$

From the Student's $t$-distribution table:

$$t_{\text{critical}} = -1.761$$

* **Decision Rule:** Reject $H_0$ if $t < -1.761$. Otherwise, fail to reject $H_0$.

---

### 5. Conclusion

Since $t = -5.814$ is much less than the critical value $-1.761$ ($p < 0.0001$), we **reject the null hypothesis ($H_0$)**.

There is statistically significant evidence at the 5% level to conclude that students using the AI-assisted environment complete the assessment significantly faster (mean of 49.0 minutes) than students using the standard environment (mean of 55.5 minutes).

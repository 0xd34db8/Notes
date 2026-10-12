**Q.** A researcher wants to investigate whether there is a significant difference in the average time taken to complete a data science task by students using Python and R. The completion times (in minutes) for 10 students using Python are 42, 38, 45, 40, 43, 39, 41, 44, 37, and 40, while the completion times for 10 students using R are 48, 51, 46, 50, 49, 47, 52, 45, 50, and 48. At a 5% level of significance, perform an t-test to determine whether there is a significant difference in the average completion time between students using Python and R. 

**Ans.**:
To determine whether there is a significant difference in the average completion time between students using Python and R, an **independent two-sample $t$-test** (two-tailed) is performed.

---

### 1. State the Hypotheses

* **Null Hypothesis ($H_0$):** $\mu_1 = \mu_2$ (There is no significant difference in the average completion time between Python and R users)
* **Alternative Hypothesis ($H_1$):** $\mu_1 \neq \mu_2$ (There is a significant difference in the average completion time between Python and R users)

---

### 2. Sample Data and Descriptive Statistics

#### **Group 1: Python ($n_1 = 10$)**

Data: $42, 38, 45, 40, 43, 39, 41, 44, 37, 40$

* **Mean ($\bar{x}_1$):**

$$\bar{x}_1 = \frac{42 + 38 + 45 + 40 + 43 + 39 + 41 + 44 + 37 + 40}{10} = \frac{409}{10} = 40.9$$

* **Sum of Squared Deviations ($\sum (x_{1i} - \bar{x}_1)^2$):**
* $(42 - 40.9)^2 = (1.1)^2 = 1.21$
* $(38 - 40.9)^2 = (-2.9)^2 = 8.41$
* $(45 - 40.9)^2 = (4.1)^2 = 16.81$
* $(40 - 40.9)^2 = (-0.9)^2 = 0.81$
* $(43 - 40.9)^2 = (2.1)^2 = 4.41$
* $(39 - 40.9)^2 = (-1.9)^2 = 3.61$
* $(41 - 40.9)^2 = (0.1)^2 = 0.01$
* $(44 - 40.9)^2 = (3.1)^2 = 9.61$
* $(37 - 40.9)^2 = (-3.9)^2 = 15.21$
* $(40 - 40.9)^2 = (-0.9)^2 = 0.81$



$$\sum (x_{1i} - \bar{x}_1)^2 = 50.9$$

* **Sample Variance ($s_1^2$):**

$$s_1^2 = \frac{50.9}{10 - 1} = \frac{50.9}{9} \approx 5.6556$$

---

#### **Group 2: R ($n_2 = 10$)**

Data: $48, 51, 46, 50, 49, 47, 52, 45, 50, 48$

* **Mean ($\bar{x}_2$):**

$$\bar{x}_2 = \frac{48 + 51 + 46 + 50 + 49 + 47 + 52 + 45 + 50 + 48}{10} = \frac{486}{10} = 48.6$$

* **Sum of Squared Deviations ($\sum (x_{2i} - \bar{x}_2)^2$):**
* $(48 - 48.6)^2 = (-0.6)^2 = 0.36$
* $(51 - 48.6)^2 = (2.4)^2 = 5.76$
* $(46 - 48.6)^2 = (-2.6)^2 = 6.76$
* $(50 - 48.6)^2 = (1.4)^2 = 1.96$
* $(49 - 48.6)^2 = (0.4)^2 = 0.16$
* $(47 - 48.6)^2 = (-1.6)^2 = 2.56$
* $(52 - 48.6)^2 = (3.4)^2 = 11.56$
* $(45 - 48.6)^2 = (-3.6)^2 = 12.96$
* $(50 - 48.6)^2 = (1.4)^2 = 1.96$
* $(48 - 48.6)^2 = (-0.6)^2 = 0.36$



$$\sum (x_{2i} - \bar{x}_2)^2 = 44.4$$

* **Sample Variance ($s_2^2$):**

$$s_2^2 = \frac{44.4}{10 - 1} = \frac{44.4}{9} \approx 4.9333$$

---

### 3. Compute the Test Statistic ($t$)

#### **Pooled Variance ($s_p^2$)**

$$s_p^2 = \frac{(n_1 - 1)s_1^2 + (n_2 - 1)s_2^2}{n_1 + n_2 - 2} = \frac{50.9 + 44.4}{10 + 10 - 2} = \frac{95.3}{18} \approx 5.2944$$

#### **Standard Error ($SE$)**

$$SE = \sqrt{s_p^2 \left(\frac{1}{n_1} + \frac{1}{n_2}\right)} = \sqrt{5.2944 \left(\frac{1}{10} + \frac{1}{10}\right)} = \sqrt{5.2944 \times 0.2} = \sqrt{1.05889} \approx 1.0290$$

#### **$t$-Value**

$$t = \frac{\bar{x}_1 - \bar{x}_2}{SE} = \frac{40.9 - 48.6}{1.0290} = \frac{-7.7}{1.0290} \approx -7.483$$

---

### 4. Critical Value and Decision Rule

* **Significance Level ($\alpha$):** $0.05$ (two-tailed)
* **Degrees of Freedom ($df$):** $n_1 + n_2 - 2 = 10 + 10 - 2 = 18$

From the Student's $t$-distribution table:

$$t_{\text{critical}} = \pm 2.101$$

* **Decision Rule:** Reject $H_0$ if $\vert{}t\vert{} > 2.101$. Otherwise, fail to reject $H_0$.

---

### 5. Conclusion

Since $\vert{}t\vert{} = 7.483$ is significantly greater than the critical value $2.101$ ($p < 0.0001$), we **reject the null hypothesis ($H_0$)**.

There is statistically significant evidence at the 5% level to conclude that the average completion time differs significantly between students using Python and R, with students using Python completing the task significantly faster on average (40.9 minutes vs. 48.6 minutes).

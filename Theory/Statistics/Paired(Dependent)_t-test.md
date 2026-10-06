**Q.** A teacher wants to determine whether a training program has significantly improved the programming skills of students. The programming test scores of 10 students before and after the training program are recorded as follows: Before training: 55, 62, 58, 65, 60, 57, 63, 59, 61, and 56. After training: 62, 68, 64, 70, 65, 63, 69, 64, 67, and 61.
At a 5% level of significance, perform t-test to determine whether there is a significant difference between the students' scores before and after the training program.

**Ans.**:
To determine whether there is a significant difference between the students' scores before and after the training program, a **paired two-sample $t$-test** (two-tailed) is performed because the measurements are taken from the same 10 students.

---

### 1. State the Hypotheses

* **Null Hypothesis ($H_0$):** $\mu_d = 0$ (There is no significant difference between the scores before and after the training program)
* **Alternative Hypothesis ($H_1$):** $\mu_d \neq 0$ (There is a significant difference between the scores before and after the training program)

*(where $\mu_d$ is the mean difference: $d = \text{After} - \text{Before}$)*

---

### 2. Paired Differences and Descriptive Statistics

Let $d_i = \text{After}_i - \text{Before}_i$:

| Student | Before ($X_1$) | After ($X_2$) | Difference ($d = X_2 - X_1$) | Deviation ($d - \bar{d}$) | $(d - \bar{d})^2$ |
| --- | --- | --- | --- | --- | --- |
| 1 | 55 | 62 | +7 | $+1.1$ | 1.21 |
| 2 | 62 | 68 | +6 | $+0.1$ | 0.01 |
| 3 | 58 | 64 | +6 | $+0.1$ | 0.01 |
| 4 | 65 | 70 | +5 | $-0.9$ | 0.81 |
| 5 | 60 | 65 | +5 | $-0.9$ | 0.81 |
| 6 | 57 | 63 | +6 | $+0.1$ | 0.01 |
| 7 | 63 | 69 | +6 | $+0.1$ | 0.01 |
| 8 | 59 | 64 | +5 | $-0.9$ | 0.81 |
| 9 | 61 | 67 | +6 | $+0.1$ | 0.01 |
| 10 | 56 | 61 | +5 | $-0.9$ | 0.81 |
| **Sum** |  |  | **$\sum d = 59$** |  | **$\sum (d - \bar{d})^2 = 4.5$** |

* **Sample Size ($n$):** $10$
* **Degrees of Freedom ($df$):** $n - 1 = 9$

#### Mean Difference ($\bar{d}$)

$$\bar{d} = \frac{\sum d_i}{n} = \frac{59}{10} = 5.9$$

#### Standard Deviation of Differences ($s_d$)

$$s_d = \sqrt{\frac{\sum (d_i - \bar{d})^2}{n - 1}} = \sqrt{\frac{4.5}{9}} = \sqrt{0.5} \approx 0.7071$$

---

### 3. Compute the Test Statistic ($t$)

The standard error of the mean difference ($SE_d$) is:

$$SE_d = \frac{s_d}{\sqrt{n}} = \frac{0.7071}{\sqrt{10}} \approx \frac{0.7071}{3.1623} \approx 0.2236$$

Now, compute the $t$-statistic:

$$t = \frac{\bar{d} - 0}{SE_d} = \frac{5.9}{0.2236} \approx 26.39$$

---

### 4. Critical Value and Decision Rule

* **Significance Level ($\alpha$):** $0.05$ (two-tailed)
* **Degrees of Freedom ($df$):** $9$

From the Student's $t$-distribution table:

$$t_{\text{critical}} = \pm 2.262$$

* **Decision Rule:** Reject $H_0$ if $\vert{}t\vert{} > 2.262$. Otherwise, fail to reject $H_0$.

---

### 5. Conclusion

Since $\vert{}t\vert{} = 26.39$ is vastly greater than the critical value $2.262$ ($p < 0.0001$), we **reject the null hypothesis ($H_0$)**.

There is a statistically significant difference between the students' scores before and after the training program at the 5% significance level. On average, students improved their scores by **5.9 points** following the training.

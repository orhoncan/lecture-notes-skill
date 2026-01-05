# Econometrics Topic Guide

Reference for common econometrics lecture topics with key concepts, formulas, and practical examples.

## 1. Simple Linear Regression / Basit Doğrusal Regresyon

**Key Concepts:**
- Population vs sample regression
- OLS estimation
- Interpretation of coefficients
- Goodness of fit

**Core Formulas:**

Population model:
$$
Y_i = \beta_0 + \beta_1 X_i + u_i
$$

OLS estimators:
$$
\hat{\beta}_1 = \frac{\sum(X_i - \bar{X})(Y_i - \bar{Y})}{\sum(X_i - \bar{X})^2} = \frac{Cov(X,Y)}{Var(X)}
$$

$$
\hat{\beta}_0 = \bar{Y} - \hat{\beta}_1 \bar{X}
$$

R-squared:
$$
R^2 = 1 - \frac{SSR}{SST} = \frac{ESS}{SST}
$$

**Daily-Life Examples:**
- Education years and wage
- Study hours and exam scores
- Advertising spending and sales
- Temperature and ice cream sales

---

## 2. Multiple Regression / Çoklu Regresyon

**Key Concepts:**
- Holding other variables constant
- Omitted variable bias
- Adjusted R-squared
- Multicollinearity

**Core Formulas:**

Model:
$$
Y_i = \beta_0 + \beta_1 X_{1i} + \beta_2 X_{2i} + \cdots + \beta_k X_{ki} + u_i
$$

Adjusted R-squared:
$$
\bar{R}^2 = 1 - \frac{SSR/(n-k-1)}{SST/(n-1)}
$$

Omitted variable bias:
$$
\hat{\beta}_1^{short} = \beta_1 + \beta_2 \cdot \tilde{\delta}_1
$$

where $\tilde{\delta}_1$ is from regressing omitted variable on included variable.

**Daily-Life Examples:**
- Wage = f(education, experience, gender)
- House price = f(size, location, age, rooms)
- GPA = f(study hours, attendance, sleep)

---

## 3. Hypothesis Testing / Hipotez Testi

**Key Concepts:**
- Null and alternative hypotheses
- t-test for individual coefficients
- F-test for joint significance
- p-values and significance levels

**Core Formulas:**

t-statistic:
$$
t = \frac{\hat{\beta}_j - \beta_{j,0}}{SE(\hat{\beta}_j)}
$$

Standard error:
$$
SE(\hat{\beta}_1) = \sqrt{\frac{\hat{\sigma}^2}{\sum(X_i - \bar{X})^2}}
$$

F-statistic (restricted vs unrestricted):
$$
F = \frac{(SSR_r - SSR_{ur})/q}{SSR_{ur}/(n-k-1)}
$$

**Interpretation Guide:**

| p-value | Conclusion |
|---------|------------|
| p < 0.01 | Reject $H_0$ at 1% (***) |
| p < 0.05 | Reject $H_0$ at 5% (**) |
| p < 0.10 | Reject $H_0$ at 10% (*) |
| p ≥ 0.10 | Fail to reject $H_0$ |

---

## 4. Dummy Variables / Kukla Değişkenler

**Key Concepts:**
- Binary variables
- Dummy variable trap
- Interaction terms
- Difference-in-differences

**Core Formulas:**

Basic dummy model:
$$
Y_i = \beta_0 + \beta_1 D_i + u_i
$$

Interpretation:
- $\beta_0$ = mean for $D=0$ group
- $\beta_1$ = difference between groups

Interaction model:
$$
Y_i = \beta_0 + \beta_1 X_i + \beta_2 D_i + \beta_3 (X_i \times D_i) + u_i
$$

**Daily-Life Examples:**
- Gender wage gap analysis
- Before/after policy effects
- Urban vs rural differences
- Seasonal effects in sales

---

## 5. Heteroscedasticity / Değişen Varyans

**Key Concepts:**
- Violation of constant variance assumption
- Consequences for OLS
- Detection methods
- Robust standard errors

**Core Formulas:**

Homoscedasticity assumption:
$$
Var(u_i | X_i) = \sigma^2 \quad \forall i
$$

Heteroscedasticity:
$$
Var(u_i | X_i) = \sigma_i^2
$$

White test statistic:
$$
nR^2 \sim \chi^2_q
$$

**Detection Methods:**
1. Plot residuals vs fitted values
2. Breusch-Pagan test
3. White test

**Solution:** Use heteroscedasticity-robust (White) standard errors

---

## 6. Autocorrelation / Otokorelasyon

**Key Concepts:**
- Serial correlation in time series
- AR(1) process
- Durbin-Watson test
- HAC standard errors

**Core Formulas:**

AR(1) error process:
$$
u_t = \rho u_{t-1} + e_t
$$

Durbin-Watson statistic:
$$
DW = \frac{\sum_{t=2}^{n}(\hat{u}_t - \hat{u}_{t-1})^2}{\sum_{t=1}^{n}\hat{u}_t^2} \approx 2(1-\hat{\rho})
$$

**Decision Rules:**
- DW ≈ 2: No autocorrelation
- DW < 2: Positive autocorrelation
- DW > 2: Negative autocorrelation

---

## 7. Instrumental Variables / Araç Değişkenler

**Key Concepts:**
- Endogeneity problem
- IV requirements (relevance, exogeneity)
- Two-stage least squares (2SLS)
- Weak instruments

**Core Formulas:**

Endogenous model:
$$
Y_i = \beta_0 + \beta_1 X_i + u_i \quad \text{where } Cov(X_i, u_i) \neq 0
$$

IV estimator:
$$
\hat{\beta}_1^{IV} = \frac{Cov(Z,Y)}{Cov(Z,X)}
$$

2SLS procedure:
1. First stage: $X_i = \pi_0 + \pi_1 Z_i + v_i$
2. Second stage: $Y_i = \beta_0 + \beta_1 \hat{X}_i + u_i$

**IV Requirements:**
- Relevance: $Cov(Z,X) \neq 0$
- Exogeneity: $Cov(Z,u) = 0$

**Classic Examples:**
- Returns to education: use quarter of birth as IV
- Supply/demand estimation: use weather as IV for supply
- Effect of institutions: use settler mortality as IV

---

## 8. Panel Data / Panel Veri

**Key Concepts:**
- Fixed effects vs random effects
- Within and between variation
- Hausman test
- Clustered standard errors

**Core Formulas:**

Panel model:
$$
Y_{it} = \beta_0 + \beta_1 X_{it} + \alpha_i + u_{it}
$$

Fixed effects (within transformation):
$$
(Y_{it} - \bar{Y}_i) = \beta_1 (X_{it} - \bar{X}_i) + (u_{it} - \bar{u}_i)
$$

Hausman test:
$$
H = (\hat{\beta}_{FE} - \hat{\beta}_{RE})'[Var(\hat{\beta}_{FE}) - Var(\hat{\beta}_{RE})]^{-1}(\hat{\beta}_{FE} - \hat{\beta}_{RE})
$$

**Daily-Life Examples:**
- Firm productivity across years
- Individual wages over career
- Country-level growth comparisons
- School performance tracking

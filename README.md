# econ5200-lab12-instrumental-variables
# Instrumental Variables: Weak Instruments, Compliers and the Exclusion Restriction

## Objective

I used simulations and the Card (1995) college-proximity example to study how instrument strength, treatment-effect heterogeneity, and violations of the exclusion restriction affect instrumental-variables estimates.

## Methodology

- Simulated an endogenous treatment with a known true effect of 1.0 and instruments of different strengths.
- Compared OLS and 2SLS as the first stage became weaker.
- Examined how weak instruments affect both point estimates and statistical inference.
- Replicated Card's college-proximity instrument for schooling using `nearc4`.
- Compared the OLS return to schooling with the 2SLS estimate.
- Studied the interpretation of IV as a Local Average Treatment Effect for compliers.
- Simulated direct effects of the instrument on the outcome to study violations of the exclusion restriction.
- Wrote my own `iv_by_hand()` function using two OLS regressions and checked it against `linearmodels`.
- Used `src/iv_tools.py` to report IV estimates together with first-stage diagnostics.

## Key Findings

In the weak-instrument simulation, when the median first-stage F fell to 0.5, the median 2SLS estimate was 2.038, compared with a median OLS estimate of 1.998 and a true effect of 1.0. Weak instruments can therefore produce misleading estimates and unreliable inference.

In the Card (1995) application, the first-stage F was 16.7. The OLS estimated return to schooling was 0.0740, while the 2SLS estimate was 0.1323. The IV estimate should be interpreted as a local effect for people whose schooling is changed by proximity to a four-year college, rather than as the average effect for everyone.

The exclusion-restriction sensitivity exercise showed that even a small direct effect of the instrument can substantially change the IV estimate. In the Card application, allowing a direct effect of 0.02 reduced the estimate from 0.1323 to 0.0730.

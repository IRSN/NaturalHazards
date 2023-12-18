This doc repository is dedicated to Natural Hazards tools developped by the SCAN department at IRSN.

## Extreme values modelling

| Name | Short description | Location | Supports unsteady data | Processing historical data | Sampling type | Distribution laws | Confidence interval type | Other tool features |
| :--- | :------------------- | :--- | :--- | :--- | :--- | :--- | :--- | :------------- |
| Renext | Statistical tool for estimating extreme values in a frequentist framework with many methods | CRAN + [IRSN GitHub](https://github.com/IRSN/Renext) | <span style="color:red">✘</span>| <span style="color:green">✔</span> | POT block maxima r-LOS | GPD, expo, GEV, gumbel, mixed expo, log normal, Weibull, gamma | Delta | Various anova statistical tests | SRI CGB |
| NSGEV | Statistical tool for estimating extreme values in an unsteady frequentist framework based on annual maxima | [IRSN GitHub](https://github.com/IRSN/NSGEV) | <span style="color:green">✔</span> | <span style="color:red">✘</span>| maximum block | GEV, gumbel | Delta Likelihood Profile Bootstrap | Various anova statistical tests | RP4 1300 |
| potomax | Statistical tool for estimating extreme values with a new sampling method (MA censoring threshold) | [IRSN GitHub](https://github.com/IRSN/potomax) | <span style="color:red">✘</span>| <span style="color:green">✔</span> | POT block maximum | GPD, expo, GEV, gumbel | Delta Likelihood Profile | Validation method to check the convergence of results (argument check=TRUE) | SRI CGB |
| SpatialExtremes | Fork of the CRAN package by Mathieu Ribatet. Modification of the package by Yves Deville, in particular of the spatgev class in order to take into account temporal covariates (possibility of using this class with NSGEV) | [Y. Deville GitHub](https://github.com/yvesdeville/SpatialExtremes) | <span style="color:green">✔</span> (using it with NSGEV) | <span style="color:red">✘</span>| maximum block | GEV, gumbel | Delta Likelihood Profile Bootstrap | Package to extrapolate temperatures in places where there is| <span style="color:red">✘</span>data (spatial covariates) | RP4 1300 |
| bever | Statistical tool for estimating extreme values in a Bayesian framework (with focus on Markov chain Monte-Carlo) | [IRSN GitHub](https://github.com/IRSN/bever) | <span style="color:red">✘</span>| <span style="color:green">✔</span> | POT block maximum | GPD, expo, GEV, gumbel | Credibility intervals with HPD and equal tails methods | Calculation of the predictive distribution | PFHA Belleville |
| beverstan | Rstan statistical tool, dependent on NSGEV and bever, for the estimation of extreme values in a Bayesian framework | [IRSN GitHub](https://github.com/IRSN/beverstan) | <span style="color:green">✔</span> | <span style="color:green">✔</span> | maximum block | GEV, gumbel | Credibility intervals with HPD and equal tails methods | | |
| dailymet | Tool for analyzing daily weather series (mainly temperatures) using POT methods | [IRSN GitHub](https://github.com/IRSN/dailymet) | <span style="color:green">✔</span> | <span style="color:red">✘</span>| POT | GPD, exhibition | | Functions to describe seasonality and annual trend | |
| SeaLev | Estimation of extreme sea levels by combining tide and surge | [IRSN GitHub](https://github.com/IRSN/SeaLev) | <span style="color:red">✘</span>| <span style="color:green">✔</span> (with Renext) | POT or maximum block (premiums) | Renext laws | Delta | Theoretical tide distribution | PFHA Gravelines |

Theses tools are available through R using:

  * `install.packages('...')` for CRAN packages (Renext, SpatialExtremes, ...),
  * `install.packages('https://github.com/IRSN/.../releases/download/....tgz|zip|tar.gz', repos=NULL, type='binary')` for packages available on GitHub (potomax, bever, beverstan, dailymet, SeaLev) , precompiled for Linux (x86), Windows, or MacOSX
  * `devtools::install_github('IRSN/...')` (asuming devtools & Rtools for windows are available on yout system)
  
## Flood modelling

* Telemac2D v8p3r0 docker image `docker run -v `echo $PWD`:/workdir irsn/telemac-mascaret:latest telemac2d.py --ncsize=10 input.cas`
* [Funz](https://funz.github.io)-Telemac for parametric studies:
  * Python: `pip install Funz`, then `import Funz`, `Funz.installModel('Telemac')`
  * R: `remotes::install_github('Funz/Funz.R'); libary(Funz); Funz::installModel('Telemac')`
  * bash/cmd.exe: [Standalone dist](https://github.com/Funz/plugin-Telemac/releases/latest)

  

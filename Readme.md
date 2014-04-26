# R in Insurance
## Cass Business School, London, 14 July 2014

9:00  - 10:00 Opening keynote:  
Montserrat Guillen and Leo Guelman: New trends in predictive modelling - the uplift models success story 

10:00 - 11:00 Session 1: Reserving (20 min. each)

 1. Munir Hiabu: RBNS preserving double chain ladder
 2. Els Godecharle: Reserving by conditioning on markers of individual
 claims: a case study using historical simulation 
 3. Brian Fannin: Multivariate regression models for reserving

11:00 - 11:30 Coffee

11:30 - 12:30: Lightning talks (10 min each)

 1. Roel Verbelen: Loss modelling with mixtures of Erlang distributions
 2. Nicolas Baradel: R Program GUI Manager
 3. Karl-Kuno Kunze: Time Series Data Quality Analysis
 4. Ed Tredger: Integrating R with existing software in the London Market
 5. Wim Konings: Estimating the duration of non-maturing liabilities
 in a user friendly Shiny web application 
 6. Markus Gesmann: End User Computing with R under Solvency II

12:30 - 13:30 Lunch

13:30 - 14:30 Session 2: Pricing (20 min. each)

 1. Giorgio Spedicato: R data mining for insurance retention modelling
 2. Bernhard Kübler: Assessing exploration risk for geothermal wells
 3. Xavier Marechal: Geographical ratemaking with R


14:30 - 15:00 Panel discussion: How to improve communication between
academics and practitioners   
Moderator: Jens Nielsen. Potential panellist: Montserrat Guillen,
Katrien Antonio, Kristina Barnett (RSA), Mango 

15:00 - 15:30: Coffee

15:30 - 16:30 Session 3: Life / Using R in a production environment
(20 min. each) 

 1. Ana Debon: Modelling trends and inequality of longevity in
 European Union countries 
 2. Kate Hanley: Dynamic Report Generation in R: LaTeX vs. Markdown
 3. Matthew Dowle: Introduction to `data.table`

16:30 - 17:30 Closing keynote:  
Arthur Charpentier: Going Bayesian with R - a non-Bayesian perspective

18:00 - XY:00 The conference will be followed by a drinks and networking reception at Cass and the conference dinner (venue tbc).

# Abstracts

## Reserving

### RBNS preserving double chain ladder
#### Munir Hiabu, Cass Business School
 
The single most important number in the accounts of a non-life company
is often the so called reserve. The reserve is estimated based on a
statistical analysis combining past paid claims and so called RBNS
claims estimates. RBNS means "reported but not settled" and is a
number set for any incurred claim in an insurance company. The
statistical analysis in insurance companies is often done in practice
via the classical chain ladder on so called incurred data.  

This approach involves a statistical modelling and forecasting of RBNS
estimates implying that expert opinion from the claims department is
changed in the reserving department. Our motivation for developing
this new RBNS preserving double chain ladder approach is to ensure
that expert opinion of individual claims reserving is not changed in
the modelling process.  We take advantage of the flexibility of the
double chain ladder method and develop a reserving technique that does
not change RBNS estimates via  modelling and forecasting. Full
stochastic cash flows of the RBNS reserve, the IBNR reserve and the
reserving tail are provided.   Programmes are available via the double
chain ladder
([DCL](http://cran.r-project.org/web/packages/DCL/index.html))
R-package. 


### Reserving by conditioning on markers of individual claims: a case study using historical simulation
#### Els Godecharle, KU Leuven


Our research explores the use of claim specific characteristics, so-called claim markers, for loss reserving with individual claims. Starting from the approach of Rosenlund (2012) we develop a stochastic Reserve by Detailed Conditioning ('RDC') method which is applicable to a micro-level data set with detailed information on individual claims. 

We use historical simulation to construct the predictive distribution of the outstanding loss reserve by simulating payments of a claim, given its claim markers. We explore how to incorporate different types of claim specific information when simulating outstanding loss reserves, and evaluate the impact of the set of markers and their specification on the predictive distribution of the outstanding reserve.  

The stochastic RDC method is implemented in R and the code is made available [online](http://www.econ.kuleuven.be/els.godecharle). We demonstrate the performance of the method on a portfolio of general liability insurance policies for private individuals from a European insurance company.

### Multivariate Regression Models for Reserving
#### Brian Fannin, Redwoods Group

MRMR - Multivariate Regression Models for Reserving is an R package
for loss reserving. The emphasis is on the treatment of loss reserving
as a multilevel linear regression problem. MRMR supports S4 classes
for storage of reserving data and reserving models. A `Triangle`
object is composed of smaller objects which represent `OriginPeriod,
StaticMeasure` and `StochasticMeasure`. The stochastic feature of the
`StochasticMeasure` object refers to the fact that the measure may
change over time. In effect, a `StochasticMeasure` is a traditional
loss triangle. However, the data may be augmented by use of a
`StaticMeasure` object to store data which is fixed in time, such as
written premium or other exposure elements. The OriginPeriod and
measure classes support implementation of basic functionality such as
`rbind`, `c`, comparison, assignment and extraction in a natural way
consistent with common R objects. This enables one to easily update
information as part of routine studies, join to other data sources or
examine particular subsets of reserving data.
 
The Triangle object features basic visualisation for exploratory
analysis to aid the actuary in selecting model variables. The
TriangleModel object stores information regarding a fit model. One may
have more than one model for the same Triangle object. When
constructing a model, the development lag generally acts as a
categorical parameter, though others may also be introduced. The
structure of the Triangle object permits multilevel linear models so
that, for example, one may view results for a particular line
segmented by territory or other dimensional variables such as customer
size, customer industry or urban vs. rural risks. This is effectively
a wrapper around calls to the `lme4` package. Finally, a
TriangleProjection object stores projection of a TriangleModel to any
arbitrary future time period. The `Triangle`, `TriangleModel` and
`TriangleProjection` classes are roughly analogous to a data frame,
the result from an `lm` function and the result from a `predict`
function, respectively.

## Lightning Talks

### Loss modelling with mixtures of Erlang distributions
#### Roel Verbelen, KU Leuven

Modelling data on claim sizes is crucial when pricing insurance products. Such loss models require on the one hand the flexibility of nonparametric density estimation techniques to describe the insurance losses and on the other hand the feasibility to analytically quantify the risk. Mixtures of Erlang distributions with a common scale are very versatile as they are dense in the space of positive continuous distributions (Tijms (1994, p. 163)). At the same time, it is possible to work analytically with this kind of distributions. Closed-form expressions of quantities of interest, such as the Value-at-Risk (VaR) and the Tail-Value-at-Risk (TVaR), can be derived as well as appealing closure properties (Lee and Lin (2010), Willmot and Lin (2011) and Klugman et al. (2012)). In particular, using these distributions in aggregate loss models leads to an analytical form of the corresponding aggregate loss distribution which avoids the need for simulations to evaluate the model. 

In actuarial science, claim severity data is often censored and/or truncated due to policy modifications such as deductibles and policy limits. Lee and Lin (2010) formulate a calibration technique based on the EM algorithm for fitting mixtures of Erlangs with a common scale parameter to complete data. Here, we construct an adjusted EM algorithm which is able to deal with censored and truncated data, inspired by McLachlan and Peel (2001) and Lee and Scott (2012). Using the developed R program, we demonstrate the approximation strength of mixtures of Erlangs and model e.g. the left truncated Secura Re data from Beirlant et al. (2004), and use the mixtures of Erlangs approach to price an excess-of-loss reinsurance contract.


###### References
 
Beirlant, J., Goegebeur, Y., Segers, J., Teugels, J., De Waal, D., and Ferro, C. (2004). Statistics of Extremes: Theory and Applications. Wiley Series in Probability and Statistics. Wiley.

Klugman, S. A., Panjer, H. H., and Willmot, G. E. (2012). Loss models: from data to decisions, volume 715. Wiley.

Lee, G. and Scott, C. (2012). EM algorithms for multivariate Gaussian mixture models with truncated and censored data. Computational Statistics & Data Analysis, 56(9):2816 ñ 2829.

Lee, S. C. and Lin, X. S. (2010). Modeling and evaluating insurance losses via mixtures of Erlang distributions. North American Actuarial Journal, 14(1):107.

McLachlan, G. and Peel, D. (2001). Finite mixture models. Wiley.

Tijms, H. C. (1994). Stochastic models: an algorithmic approach. Wiley.

Willmot, G. E. and Lin, X. S. (2011). Risk modelling with the mixed Erlang distribution. Applied Stochastic Models in Business and Industry, 27(1):2-16.

### R Program GUI Manager
#### Nicolas Baradel and William Jouot, PGM Solutions

R is known to be a great programming language. However, we believe
that it lacks two important features: creating graphical interfaces
and generating reports. RPGM is a new brand software, standing for "R
Program GUI Manager". This tool enables any programmer to easily make
R programs, to create user-friendly interfaces and powerful report
generation abilities, that can export results as PDF files or as Excel
spreadsheets. 

Indeed, RPGM contains a powerful IDE, the Editor, with an R script
editor with strong keywords coloration, function auto-completion, and
a quick and easy access to the R help pages by just pressing F1 when
the cursor is on a function. As TCL/TK, users can create graphical
interfaces, but without a single line of code and without having to
learn a new language. All common widgets types can be inserted such as
text/number inputs, file/folder choosers, check boxes, dropdown lists,
images... 

Furthermore, RPGM also contains a "Client" software, aimed for end
users, which executes programs made with the Editor. Most of the time,
end user does not know and does not have to now about R and the given
implemented feature. R is completely hidden, as the user will
communicate with R through the user friendly generated client
interface, yet the R console can be displayed for debugging purposes.  

RPGM can also generate PDF reports using the powerful LaTeX
language. No need to know how LaTeX works for using it thanks to the
Report Editor, although raw LaTeX code can also be inserted. Excel
spreadsheets can also be generated, based on an already existing Excel
file with formulas and graphics. RPGM will add results from R in the
spreadsheet in a specific cell name. For more information and
screenshots, visit www.pgm-solutions.com. 

### Time Series Data Quality Analysis
#### Prof. Dr. Karl-Kuno Kunze, RStudio and Fractional View

Usually, time series analysis in finance, insurance, and other fields
of interest starts from the premise that data quality is checked: all
data is in place and in order. However, all too often data is either
missing or wrong. Reports exist that time series have even been
switched by market data providers at times. The package 'Time Series
Data Quality' (TSDQ) provides an easily accessible tool to check time
series data prior to further processing. Two main applications are in
focus: analysis of historical series where the full history is checked
for plausibility, as well as a 'golden copy' mode where newly incoming
data is analysed and checked, for example in overnight risk
calculations. In the second case, the checked data is the newest
available information for the particular time series. 

We present some features of the package as will be available for
download from [www.fractionalview.com](www.fractionalview.com). In
addition, we will walk the audience through an online application
provided by [www.fractionalview.com](www.fractionalview.com) fuelled
by package TSDQ and the Shiny framework developed and provided by
[RStudio](www.rstudio.com). The application consists of three major
parts: 

1. Missing Data Analysis
2. Outlier Analysis
3. Corrected Data Imputation

The steps are accompanied by Conspicuous & Corrected Data reports. 

Although high flexibility of methods is in focus, a standard mode with
both robust and easy to use methods aims at a large non-specialist
community as outlier detection and the like are concerned. The online
tool shall integrate seamlessly into existing analyses and help avoid
pitfalls that may result from mere data quality issues. 


### Integrating R with existing software in the London Market
#### Ed Tredger and Dan Thompson, UMACS

Whilst the vast majority of us know spreadsheets are incredibly
useful, there are things that they simply can not cope with. Our talk
will focus on what R enables Actuaries to do beyond what existing
software can handle, using example from the London Insurance
Market. All of this talk is based on practical experience of using R
in real-world examples and draws from the presenters’ personal
experiences. 

There are three distinct sections to the talk:

1. The limitations of spreadsheets, now and in the future
2. Why is R the solution?
3. Practical examples of R integrating with Excel

The first section of the talk discusses why increasing volumes of
data, demand for MI and reporting and the increasingly complex nature
of reserving, pricing and capital modelling will push current software
beyond their limits.  

The second part of our talk discusses why we believe R is particularly
well placed to go beyond the limitation of spreadsheets and manage the
integration of other pieces of software. 

The third part will discuss different implementations of R we have
found have added significant end-user value. This part of the talk
will use examples of how R has been successfully used in pricing,
reporting and capital modelling. 


### Estimating the duration of non-maturing liabilities in a user friendly Shiny web application
#### Wim Konings, Reacfin 

One of the challenges in the risk management of non-maturing
liabilities (e.g. saving accounts) is the estimation of the interest
rate sensitivity (or duration) of these instruments. The aim of our
talk is double: 
 
* First a replicating portfolio approach will be presented for this
  problem. This approach consists of testing a large number of random
  investment strategies over a historical time horizon in order to
  select this strategy that replicates best the interest rate
  evolution of the saving account. In practice the replicating
  portfolio is chosen to be the strategy that minimises the variance
  of the margin between the saving account rate and replicating
  portfolio rate. By testing a large number of portfolios we are also
  able to construct a risk-return plane that can be used for
  optimising the investment strategy. 
 
* Second, we will present how such a model can be turned into a user
  friendly web application using the Shiny package. 


### End User Computing with R under Solvency II
#### Markus Gesmann, Lloyd's

As R is used more and more in insurance companies, often by
individuals who commission their own work, e.g. for cat modelling,
pricing, reserving and capital modelling.  

Under the Solvency II regime insurance companies have to demonstrate
that applications built outside an IT controlled environments have an
appropriate control framework in place, if they are used as part of
the internal capital model. 

Open source communities had to overcome those challenges in the past
already: How do you organise work across multiple teams? How do you
define interfaces? How do you deal with security, incident management,
documentation, testing, roll out, etc.?  
The R documentation on writing R extensions answers those questions
and offers a blue print and framework for end user computing. Over
5000 packages on CRAN demonstrate the success of this approach.  

This talk will illustrate how the R package development standards map
to the Solvency II requirements for end user computing. 



## Pricing

### R data mining for insurance retention modelling
#### Giorgio Spedicato

Retention analysis is a very important task that insurers do when
perform tariff revisions. Retention and conversion represent the two
blocks of price optimisation that is currently among the most
sophisticated pricing analyses carried by actuaries working on
personal lines.  

However, academic literature has given few attention to this
topic. The use of predictive modelling techniques, like classification
trees, random forests, SVM, neural networks, knn, as long as
time-to-event modelling has been deeply explored and actively used by
data scientist and practitioners in other industries, like marketing,
healthcare, banking etc.  

The almost uniquely used model in actuarial practice and the only
model implemented in standard pricing software is logistic
regression. The aim of this paper is twofold: 

* First, some data mining techniques (among the most used) will be
  applied on a real data set and their predictive performance will
  compared with standard logistic regression results.  

* Second,the optimal renewal premium decision will be determined
  within all different methodology and results in term of underlying
  probability will be performed. 

The analysis will be performed by the use of R statistical software (R
Core Team, 2013) and specialised predictive modelling package, in
particular the `caret` package (Kuhn, 2008). 


### Assessing Exploration Risk for Geothermal Wells
#### Bernhard Kübler, Fraunhofer Institute for Industrial Mathematics 

In the course of Germany’s 'energy transition' alternative power 
sources are being extensively investigated. A particular form of these 
renewable energies is geothermics whose resources in Germany are 
estimated to 1200 EJ (Exajoules). As the power of a geothermal 
installation is proportional to the product of water temperature *T* 
and flow rate *Q*, a geothermal well is said to be successful if the 
crucial parameters *T* and *Q* exceed some critical thresholds fixed by 
the investor. The hazard that the drilling yields lower values than those 
required by the investor is referred to as exploration risk.

Typically, investors transfer exploration risk to a reinsurance company. 
Therefore, not only investors but also insurance and reinsurance 
companies seek for an accurate assessment of exploration risk.
Also, low interest rates and regulatory standards (Solvency II) trigger 
insurers to consider new asset classes like alternative investments. 
Due to generating stable cash flows, investing in renewable energies and 
infrastructure is seen to be an eligible strategy for insurers. 
Within this context, risk management and reporting purposes call for a 
thorough assessment of the associated risk.

Besides the classical Kriging approach, we particularly employ Support 
Vector Machine Regression (SVR) to measure exploration risk. To our 
knowledge, up to now SVR has not been used in the context of geothermics. 
The major advantage of a Machine Learning based approach is its ability 
to model even quite complex nonlinear relationships appropriately. 
We also address estimation risk by deriving statements concerning the 
reliability of (point) estimates gained by SVR.

Our first results based on real data indicate that the Machine Learning 
tools yield forecasts being more precise than Kriging. This should enable 
investors and insurers to enhance their assessment of exploration risk, 
with corresponding potentials to realise cost savings.


### Geographical ratemaking with R
#### Xavier Marechal, Reacfin

In motor insurance, most companies have adopted a risk classification
according to the geographical zone where the policyholder lives (urban
/ non urban for instance, or a more accurate splitting of the country
according to Zip codes). The aim of this talk is to introduce in the
tariff a new explanatory variable based on the policyholder’s district
taking into account the other explanatory variables already present in
the technical tariff.  

It is usually better to take into account both the frequency and the
mean cost as behaviour can be quite different but a lot of companies
concentrate on the frequency in order to establish their geographical
ratemaking. 

We will briefly present different solutions to define a categorical
geographical variable but we will focus on the use of GAM for the case
study in R. The `readShapeSpatial` function will be introduced to plot
country maps. 

## Life insurance

### Modelling trends and inequality of longevity in European Union countries
#### Ana Debon, Universitat Politècnica de València and Steve Haberman, Cass Business School

Comparisons of differential survival by country are useful in many
domains. In the area of public policy, they help policymakers and
analysts assess how much various groups benefit from public programs,
such as Social Security and health care. In financial markets and
especially for actuaries, they are important for designing annuities
and life insurance.  

In this study, we present a method for clustering information about
differential survival by country and reviews mortality indicators to
study inequalities and trends on mortality. Then we use this approach
to group mortality surfaces for European Union
countries. Additionally, the indicators allow us to characterize each
group.  All these statistical analyses were performed using the R
environment for statistical computing. 

## Using R in a production environment

### Dynamic Report Generation in R: LaTeX vs. Markdown
#### Kate Hanley, Mango Solutions

Dynamic document generation allows for the seamless integration of R
code and document templates when generating reports. Changes in the R
code are filtered through to the document, reducing the possibility of
errors and discrepancies between the R code and final report, and
minimising the burden of quality control procedures. 

The `knitr` package provides excellent tools to facilitate this
process, and allows documents to be generated directly from
R. However, there is often uncertainty concerning which mark-up
language to use to create the report templates, and the choice often
depends on a variety of factors. 

This presentation focuses on two widely-used mark-up languages, LaTeX
and markdown. Code examples are used to illustrate the differences
between the two languages, allowing for a discussion of the pros and
cons of each in terms of learning curve, flexibility and ease of use. 

### Introduction to `data.table` 
#### Matthew Dowle, data.table-project

The data.table package inherits from data.frame and aims to reduce two
types of time: 

1. programming time (fewer function calls, less variable name repetition) 
2. compute time on large data (e.g. 64bit with 8GB+ RAM)

The general form, including chaining is:

	DT[where, select|update, group by][order by][ ... ]...[ ... ]

The presentation covers the essential syntax illustrated with examples.

- Creating a `data.table`
- Fast and friendly file reading with `fread`
- Basic query syntax
- Keys (`setkey`)
- Update by reference (:= and set*)
- Ordered joins forwards, backwards, limited and nearest
- Why R?
- Recent new features
- Future directions
- Quality assurance (over 1,000 tests, release procedures)
- A review of online help (1,200 Q&A on Stack Overflow's data.table tag)


### Going Bayesian with R - a non-Bayesian perspective 
#### Arthur Charpentier, Université du Québec à Montréal, Professor


 Bayesian philosophy has a long history in actuarial science. Liu et
 al. (1996) claim that "Statistical methods with a Bayesian flavour
 [...] have long been used in the insurance industry." If actuarial
 students discover Bayesian statistics with credibility, the Bayesian
 philosophy can be extremely powerful. Not only to quantify
 uncertainty when only a few observations have been observed (and
 asymptotic results cannot be invoked) but also to make computations
 possible when a lot of observations are available (and classical
 computations will be too complex). With the perspective of a muggle,
 I will try to explain the power of Bayesian techniques (usually seen
 as a magical black box by non-Bayesians).
 

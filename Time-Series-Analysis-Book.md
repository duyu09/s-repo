# Time Series Analysis

![](images/e69a641be1f8dd333aabc852feb59560174ef93c0db9e7445ab91bb9b03b13cb.jpg)  
James D. Hamilton

# Time Series Analysis

# Time Series Analysis

James D. Hamilton

PRINCETON UNIVERSITY PRESS

PRINCETON, NEW JERSEY

Copyright © 1994 by Princeton University Press  
Published by Princeton University Press, 41 William St., Princeton, New Jersey 08540  
In the United Kingdom: Princeton University Press, Chichester, West Sussex

All Rights Reserved

Library of Congress Cataloging-in-Publication Data Hamilton, James D. (James Douglas), (1954-) Time series analysis / James D. Hamilton. p. cm. Includes bibliographical references and indexes.

ISBN-13: 978-0-691-04289-3 (cloth)  
ISBN-10: 0-691-04289-6 (cloth)

1. Time-series analysis. I. Title. QA280.H264 1994  
519.5'5---dc20 93-4958 CIP

This book has been composed in Times Roman.

Princeton University Press books are printed on acid-free paper and meet the guidelines for permanence and durability of the Committee on Production Guidelines for Book Longevity of the Council on Library Resources.

http://pup.princeton.edu

Printed in the United States of America

20 19 18 17 16 15

# Contents

PREFACE xiii

1 Difference Equations 1

1.1. First-Order Difference Equations 1   
1.2. $p$ th-Order Difference Equations 7

APPENDIX 1.A. Proofs of Chapter 1 Propositions 21  
References 24

2 Lag Operators 25

2.1. Introduction 25   
2.2. First-Order Difference Equations 27   
2.3. Second-Order Difference Equations 29   
2.4. $p$ th-Order Difference Equations 33   
2.5. Initial Conditions and Unbounded Sequences 36

References 42

3 Stationary ARMA Processes 43

3.1. Expectations, Stationarity, and Ergodicity 43   
3.2. White Noise 47   
3.3. Moving Average Processes 48   
3.4. Autoregressive Processes 53   
3.5. Mixed Autoregressive Moving Average Processes 59

3.6. The Autocovariance-Generating Function 61   
3.7. Invertibility 64

APPENDIX 3.A. Convergence Results for Infinite-Order Moving Average Processes 69

Exercises 70

# 4 Forecasting

72

4.1. Principles of Forecasting 72   
4.2. Forecasts Based on an Infinite Number of Observations 77   
4.3. Forecasts Based on a Finite Number of Observations 85   
4.4. The Triangular Factorization of a Positive Definite Symmetric Matrix 87   
4.5. Updating a Linear Projection 92   
4.6. Optimal Forecasts for Gaussian Processes 100   
4.7. Sums of ARMA Processes 102   
4.8. Wold's Decomposition and the Box-Jenkins Modeling Philosophy 108

APPENDIX 4.A. Parallel Between OLS Regression and Linear Projection 113  
APPENDIX 4.B. Triangular Factorization of the Covariance Matrix for an MA(1) Process 114  
Exercises 115 References 116

# 5 Maximum Likelihood Estimation

117

5.1. Introduction 117   
5.2. The Likelihood Function for a Gaussian $AR(1)$ Process 118   
5.3. The Likelihood Function for a Gaussian $AR(p)$ Process 123   
5.4. The Likelihood Function for a Gaussian $MA(1)$ Process 127   
5.5. The Likelihood Function for a Gaussian $MA(q)$ Process 130   
5.6. The Likelihood Function for a Gaussian $ARMA(p, q)$ Process 132   
5.7. Numerical Optimization 133

# vi Contents

5.8. Statistical Inference with Maximum Likelihood Estimation 142   
5.9. Inequality Constraints 146

APPENDIX 5.A. Proofs of Chapter 5 Propositions 148

Exercises 150

6 Spectral Analysis 152

6.1. The Population Spectrum 152   
6.2. The Sample Periodogram 158   
6.3. Estimating the Population Spectrum 163   
6.4. Uses of Spectral Analysis 167

APPENDIX 6.A. Proofs of Chapter 6 Propositions 172

Exercises 178

7 Asymptotic Distribution Theory 180

7.1. Review of Asymptotic Distribution Theory 180   
7.2. Limit Theorems for Serially Dependent Observations 186

APPENDIX 7.A. Proofs of Chapter 7 Propositions 195

Exercises 198 References 199

8 Linear Regression Models 200

8.1. Review of Ordinary Least Squares with Deterministic Regressors and i.i.d. Gaussian Disturbances 200   
8.2. Ordinary Least Squares Under More General Conditions 207   
8.3. Generalized Least Squares 220

APPENDIX 8.A. Proofs of Chapter 8 Propositions 228

Exercises 230

9 Linear Systems of Simultaneous Equations 233

9.1. Simultaneous Equations Bias 233   
9.2. Instrumental Variables and Two-Stage Least Squares 238

9.3. Identification 243   
9.4. Full-Information Maximum Likelihood Estimation 247   
9.5. Estimation Based on the Reduced Form 250   
9.6. Overview of Simultaneous Equations Bias 252

APPENDIX 9.A. Proofs of Chapter 9 Proposition 253

Exercise 255

# 10 Covariance-Stationary Vector Processes 257

10.1. Introduction to Vector Autoregressions 257   
10.2. Autocovariances and Convergence Results for Vector Processes 261   
10.3. The Autocovariance-Generating Function for Vector Processes 266   
10.4. The Spectrum for Vector Processes 268   
10.5. The Sample Mean of a Vector Process 279

APPENDIX 10.A. Proofs of Chapter 10 Propositions 285

Exercises 290

# 11 Vector Autoregressions 291

11.1. Maximum Likelihood Estimation and Hypothesis Testing for an Unrestricted Vector Autoregression 291   
11.2. Bivariate Granger Causality Tests 302   
11.3. Maximum Likelihood Estimation of Restricted Vector Autoregressions 309   
11.4. The Impulse-Response Function 318   
11.5. Variance Decomposition 323   
11.6. Vector Autoregressions and Structural Econometric Models 324   
11.7. Standard Errors for Impulse-Response Functions 336

APPENDIX 11.A. Proofs of Chapter 11 Propositions 340

APPENDIX 11.B. Calculation of Analytic Derivatives 344

Exercises 348 References 349

12 Bayesian Analysis

12.1. Introduction to Bayesian Analysis 351   
12.2. Bayesian Analysis of Vector Autoregressions 360   
12.3. Numerical Bayesian Methods 362

APPENDIX 12.A. Proofs of Chapter 12 Propositions 366

Exercise 370

13 The Kalman Filter

13.1. The State-Space Representation of a Dynamic System 372   
13.2. Derivation of the Kalman Filter 377   
13.3. Forecasts Based on the State-Space Representation 381   
13.4. Maximum Likelihood Estimation of Parameters 385   
13.5. The Steady-State Kalman Filter 389   
13.6.Smoothing 394   
13.7. Statistical Inference with the Kalman Filter 397   
13.8. Time-Varying Parameters 399

APPENDIX 13.A. Proofs of Chapter 13 Propositions 403  
Exercises 406 References 407

14 Generalized Method of Moments

14.1. Estimation by the Generalized Method of Moments 409   
14.2. Examples 415   
14.3. Extensions 424   
14.4. GMM and Maximum Likelihood Estimation 427

APPENDIX 14.A. Proofs of Chapter 14 Propositions 431 Exercise 432 References 433

15 Models of Nonstationary Time Series

15.1. Introduction 435   
15.2. Why Linear Time Trends and Unit Roots? 438

15.3. Comparison of Trend-Stationary and Unit Root Processes 438   
15.4. The Meaning of Tests for Unit Roots 444   
15.5. Other Approaches to Trended Time Series 447

APPENDIX 15.A. Derivation of Selected Equations for Chapter 15 451  
References 452

# 16 Processes with Deterministic Time Trends 454

16.1. Asymptotic Distribution of OLS Estimates of the Simple Time Trend Model 454   
16.2. Hypothesis Testing for the Simple Time Trend Model 461   
16.3. Asymptotic Inference for an Autoregressive Process Around a Deterministic Time Trend 463

APPENDIX 16.A. Derivation of Selected Equations for Chapter 16 472  
Exercises 474 References 474

# 17 Univariate Processes with Unit Roots 475

17.1. Introduction 475   
17.2. Brownian Motion 477   
17.3. The Functional Central Limit Theorem 479   
17.4. Asymptotic Properties of a First-Order Autoregression when the True Coefficient Is Unity 486   
17.5. Asymptotic Results for Unit Root Processes with General Serial Correlation 504   
17.6. Phillips-Perron Tests for Unit Roots 506   
17.7. Asymptotic Properties of a $p$ th-Order Autoregression and the Augmented Dickey-Fuller Tests for Unit Roots 516   
17.8. Other Approaches to Testing for Unit Roots 531   
17.9. Bayesian Analysis and Unit Roots 532

APPENDIX 17.A. Proofs of Chapter 17 Propositions 534  
Exercises 537 References 541

X Contents

18 Unit Roots in Multivariate Time Series 544

18.1. Asymptotic Results for Nonstationary Vector Processes 544   
18.2. Vector Autoregressions Containing Unit Roots 549   
18.3. Spurious Regressions 557

APPENDIX 18.A. Proofs of Chapter 18 Propositions 562

Exercises 568

19 Cointegration 571

19.1. Introduction 571   
19.2. Testing the Null Hypothesis of No Cointegration 582   
19.3. Testing Hypotheses About the Cointegrating Vector 601

APPENDIX 19.A. Proofs of Chapter 19 Propositions 618

Exercises 625

20 Full-Information Maximum Likelihood Analysis of Cointegrated Systems 630

20.1. Canonical Correlation 630   
20.2. Maximum Likelihood Estimation 635   
20.3. Hypothesis Testing 645   
20.4. Overview of Unit Roots-To Difference or Not to Difference? 651

APPENDIX 20.A. Proofs of Chapter 20 Propositions 653

Exercises 655

21 Time Series Models of Heteroskedasticity 657

21.1. Autoregressive Conditional Heteroskedasticity (ARCH) 657   
21.2. Extensions 665

APPENDIX 21.A. Derivation of Selected Equations

for Chapter 21 673

References 674

22 Modeling Time Series with Changes in Regime 677

22.1. Introduction 677   
22.2. Markov Chains 678   
22.3. Statistical Analysis of i.i.d. Mixture Distributions 685   
22.4. Time Series Models of Changes in Regime 690

APPENDIX 22.A. Derivation of Selected Equations for Chapter 22 699

Exercise 702

A Mathematical Review 704

A.1. Trigonometry 704   
A.2. Complex Numbers 708   
A.3. Calculus 711   
A.4. Matrix Algebra 721   
A.5. Probability and Statistics 739

References 750

B Statistical Tables 751   
C Answers to Selected Exercises 769   
D Greek Letters and Mathematical Symbols 786 Used in the Text

AUTHOR INDEX 789

SUBJECT INDEX 792

# Preface

Much of economics is concerned with modeling dynamics. There has been an explosion of research in this area in the last decade, as "time series econometrics" has practically come to be synonymous with "empirical macroeconomics."

Several texts provide good coverage of the advances in the economic analysis of dynamic systems, while others summarize the earlier literature on statistical inference for time series data. There seemed a use for a text that could integrate the theoretical and empirical issues as well as incorporate the many advances of the last decade, such as the analysis of vector autoregressions, estimation by generalized method of moments, and statistical inference for nonstationary data. This is the goal of Time Series Analysis.

A principal anticipated use of the book would be as a textbook for a graduate econometrics course in time series analysis. The book aims for maximum flexibility through what might be described as an integrated modular structure. As an example of this, the first three sections of Chapter 13 on the Kalman filter could be covered right after Chapter 4, if desired. Alternatively, Chapter 13 could be skipped altogether without loss of comprehension. Despite this flexibility, state-space ideas are fully integrated into the text beginning with Chapter 1, where a state-space representation is used (without any jargon or formalism) to introduce the key results concerning difference equations. Thus, when the reader encounters the formal development of the state-space framework and the Kalman filter in Chapter 13, the notation and key ideas should already be quite familiar.

Spectral analysis (Chapter 6) is another topic that could be covered at a point of the reader's choosing or skipped altogether. In this case, the integrated modular structure is achieved by the early introduction and use of autocovariance-generating functions and filters. Wherever possible, results are described in terms of these rather than the spectrum.

Although the book is designed with an econometrics course in time series methods in mind, the book should be useful for several other purposes. It is completely self-contained, starting from basic principles accessible to first-year graduate students and including an extensive math review appendix. Thus the book would be quite suitable for a first-year graduate course in macroeconomics or dynamic methods that has no econometric content. Such a course might use Chapters 1 and 2, Sections 3.1 through 3.5, and Sections 4.1 and 4.2.

Yet another intended use for the book would be in a conventional econometrics course without an explicit time series focus. The popular econometrics texts do not have much discussion of such topics as numerical methods; asymptotic results for serially dependent, heterogeneously distributed observations; estimation of models with distributed lags; autocorrelation- and heteroskedasticity-consistent

standard errors; Bayesian analysis; or generalized method of moments. All of these topics receive extensive treatment in Time Series Analysis. Thus, an econometrics course without an explicit focus on time series might make use of Sections 3.1 through 3.5, Chapters 7 through 9, and Chapter 14, and perhaps any of Chapters 5, 11, and 12 as well. Again, the text is self-contained, with a fairly complete discussion of conventional simultaneous equations methods in Chapter 9. Indeed, a very important goal of the text is to develop the parallels between (1) the traditional econometric approach to simultaneous equations and (2) the current popularity of vector autoregressions and generalized method of moments estimation.

Finally, the book attempts to provide a rigorous motivation for the methods and yet still be accessible for researchers with purely applied interests. This is achieved by relegation of many details to mathematical appendixes at the ends of chapters, and by inclusion of numerous examples that illustrate exactly how the theoretical results are used and applied in practice.

The book developed out of my lectures at the University of Virginia. I am grateful first and foremost to my many students over the years whose questions and comments have shaped the course of the manuscript. I also have an enormous debt to numerous colleagues who have kindly offered many useful suggestions, and would like to thank in particular Donald W. K. Andrews, Jushan Bai, Peter Bearse, Stephen R. Blough, John Cochrane, George Davis, Michael Dotsey, John Elder, Robert Engle, T. Wake Epps, Marjorie Flavin, John Geweke, Eric Ghysels, Carlo Giannini, Clive W. J. Granger, Alastair Hall, Bruce E. Hansen, Kevin Hassett, Tomoo Inoue, Ravi Jagannathan, Kenneth F. Kroner, Jaime Marquez, Rocco Mosconi, Edward Nelson, Masao Ogaki, Adrian Pagan, Peter C. B. Phillips, Peter Rappoport, Glenn Rudebusch, Raul Susmel, Mark Watson, Kenneth D. West, Halbert White, and Jeffrey M. Wooldridge. I would also like to thank Pok-sang Lam and John Rogers for graciously sharing their data. Thanks also go to Keith Sill and Christopher Stomberg for assistance with the figures, to Rita Chen for assistance with the statistical tables in Appendix B, and to Richard Mickey for a superb job of copy editing.

James D. Hamilton

# Time Series Analysis

1

# Difference Equations

# 1.1. First-Order Difference Equations

This book is concerned with the dynamic consequences of events over time. Let's say we are studying a variable whose value at date $t$ is denoted $y_{t}$ . Suppose we are given a dynamic equation relating the value $y$ takes on at date $t$ to another variable $w_{t}$ and to the value $y$ took on in the previous period:

$$
y _ {t} = \phi y _ {t - 1} + w _ {t}. \tag {1.1.1}
$$

Equation [1.1.1] is a linear first-order difference equation. A difference equation is an expression relating a variable $y_{t}$ to its previous values. This is a first-order difference equation because only the first lag of the variable $(y_{t - 1})$ appears in the equation. Note that it expresses $y_{t}$ as a linear function of $y_{t - 1}$ and $w_{t}$ .

An example of [1.1.1] is Goldfeld's (1973) estimated money demand function for the United States. Goldfeld's model related the log of the real money holdings of the public $(m_t)$ to the log of aggregate real income $(I_t)$ , the log of the interest rate on bank accounts $(r_{bt})$ , and the log of the interest rate on commercial paper $(r_{ct})$ :

$$
m _ {t} = 0. 2 7 + 0. 7 2 m _ {t - 1} + 0. 1 9 I _ {t} - 0. 0 4 5 r _ {b t} - 0. 0 1 9 r _ {c t}. \tag {1.1.2}
$$

This is a special case of [1.1.1] with $y_{t} = m_{t}$ , $\phi = 0.72$ , and

$$
w _ {t} = 0. 2 7 + 0. 1 9 I _ {t} - 0. 0 4 5 r _ {b t} - 0. 0 1 9 r _ {c t}.
$$

For purposes of analyzing the dynamics of such a system, it simplifies the algebra a little to summarize the effects of all the input variables $(I_{t},r_{bt},$ and $r_{ct})$ in terms of a scalar $w_{t}$ as here.

In Chapter 3 the input variable $w_{t}$ will be regarded as a random variable, and the implications of [1.1.1] for the statistical properties of the output series $y_{t}$ will be explored. In preparation for this discussion, it is necessary first to understand the mechanics of difference equations. For the discussion in Chapters 1 and 2, the values for the input variable $\{w_{1}, w_{2}, \ldots\}$ will simply be regarded as a sequence of deterministic numbers. Our goal is to answer the following question: If a dynamic system is described by [1.1.1], what are the effects on $y$ of changes in the value of $w$ ?

# Solving a Difference Equation by Recursive Substitution

The presumption is that the dynamic equation [1.1.1] governs the behavior of $y$ for all dates $t$ . Thus, for each date we have an equation relating the value of

$y$ for that date to its previous value and the current value of $w$ :

<table><tr><td>Date</td><td>Equation</td><td></td></tr><tr><td>0</td><td>y0 = φy-1 + w0</td><td>[1.1.3]</td></tr><tr><td>1</td><td>y1 = φy0 + w1</td><td>[1.1.4]</td></tr><tr><td>2</td><td>y2 = φy1 + w2</td><td>[1.1.5]</td></tr><tr><td>:</td><td>:</td><td></td></tr><tr><td>t</td><td>yt = φyt-1 + wt.</td><td>[1.1.6]</td></tr></table>

If we know the starting value of $y$ for date $t = -1$ and the value of $w$ for dates $t = 0, 1, 2, \ldots$ , then it is possible to simulate this dynamic system to find the value of $y$ for any date. For example, if we know the value of $y$ for $t = -1$ and the value of $w$ for $t = 0$ , we can calculate the value of $y$ for $t = 0$ directly from [1.1.3]. Given this value of $y_0$ and the value of $w$ for $t = 1$ , we can calculate the value of $y$ for $t = 1$ from [1.1.4]:

$$
y _ {1} = \phi y _ {0} + w _ {1} = \phi \left(\phi y _ {- 1} + w _ {0}\right) + w _ {1},
$$

or

$$
y _ {1} = \phi^ {2} y _ {- 1} + \phi w _ {0} + w _ {1}.
$$

Given this value of $y_{1}$ and the value of $w$ for $t = 2$ , we can calculate the value of $y$ for $t = 2$ from [1.1.5]:

$$
y _ {2} = \phi y _ {1} + w _ {2} = \phi \left(\phi^ {2} y _ {- 1} + \phi w _ {0} + w _ {1}\right) + w _ {2},
$$

or

$$
y _ {2} = \phi^ {3} y _ {- 1} + \phi^ {2} w _ {0} + \phi w _ {1} + w _ {2}.
$$

Continuing recursively in this fashion, the value that $y$ takes on at date $t$ can be described as a function of its initial value $y_{-1}$ and the history of $w$ between date 0 and date $t$ :

$$
y _ {t} = \phi^ {t + 1} y _ {- 1} + \phi^ {t} w _ {0} + \phi^ {t - 1} w _ {1} + \phi^ {t - 2} w _ {2} + \dots + \phi w _ {t - 1} + w _ {t}. \tag {1.1.7}
$$

This procedure is known as solving the difference equation [1.1.1] by recursive substitution.

# Dynamic Multipliers

Note that [1.1.7] expresses $y_{t}$ as a linear function of the initial value $y_{-1}$ and the historical values of $w$ . This makes it very easy to calculate the effect of $w_{0}$ on $y_{t}$ . If $w_{0}$ were to change with $y_{-1}$ and $w_{1}, w_{2}, \ldots, w_{t}$ taken as unaffected, the effect on $y_{t}$ would be given by

$$
\frac {\partial y _ {t}}{\partial w _ {0}} = \phi^ {t}. \tag {1.1.8}
$$

Note that the calculations would be exactly the same if the dynamic simulation were started at date $t$ (taking $y_{t-1}$ as given); then $y_{t+j}$ could be described as a

function of $y_{t - 1}$ and $w_{t},w_{t + 1},\ldots ,w_{t + j}$

$$
\begin{array}{l} y _ {t + j} = \phi^ {j + 1} y _ {t - 1} + \phi^ {j} w _ {t} + \phi^ {j - 1} w _ {t + 1} + \phi^ {j - 2} w _ {t + 2} \tag {1.1.9} \\ + \dots + \phi w _ {t + j - 1} + w _ {t + j}. \\ \end{array}
$$

The effect of $w_{t}$ on $y_{t + f}$ is given by

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = \phi^ {j}. \tag {1.1.10}
$$

Thus the dynamic multiplier [1.1.10] depends only on $j$ , the length of time separating the disturbance to the input $(w_{t})$ and the observed value of the output $(y_{t + j})$ . The multiplier does not depend on $t$ ; that is, it does not depend on the dates of the observations themselves. This is true of any linear difference equation.

As an example of calculating a dynamic multiplier, consider again Goldfeld's money demand specification [1.1.2]. Suppose we want to know what will happen to money demand two quarters from now if current income $I_{t}$ were to increase by one unit today with future income $I_{t+1}$ and $I_{t+2}$ unaffected:

$$
\frac {\partial m _ {t + 2}}{\partial I _ {t}} = \frac {\partial m _ {t + 2}}{\partial w _ {t}} \times \frac {\partial w _ {t}}{\partial I _ {t}} = \phi^ {2} \times \frac {\partial w _ {t}}{\partial I _ {t}}.
$$

From [1.1.2], a one-unit increase in $I_{t}$ will increase $w_{t}$ by 0.19 units, meaning that $\partial w_{t} / \partial I_{t} = 0.19$ . Since $\phi = 0.72$ , we calculate

$$
\frac {\partial m _ {t + 2}}{\partial I _ {t}} = (0. 7 2) ^ {2} (0. 1 9) = 0. 0 9 8.
$$

Because $I_{t}$ is the log of income, an increase in $I_{t}$ of 0.01 units corresponds to a $1\%$ increase in income. An increase in $m_{t}$ of (0.01)-(0.098) $\cong 0.001$ corresponds to a $0.1\%$ increase in money holdings. Thus the public would be expected to increase its money holdings by a little less than $0.1\%$ two quarters following a $1\%$ increase in income.

Different values of $\phi$ in [1.1.1] can produce a variety of dynamic responses of $y$ to $w$ . If $0 < \phi < 1$ , the multiplier $\partial y_{t+j} / \partial w_t$ in [1.1.10] decays geometrically toward zero. Panel (a) of Figure 1.1 plots $\phi^j$ as a function of $j$ for $\phi = 0.8$ . If $-1 < \phi < 0$ , the multiplier $\partial y_{t+j} / \partial w_t$ will alternate in sign as in panel (b). In this case an increase in $w_t$ will cause $y_t$ to be higher, $y_{t+1}$ to be lower, $y_{t+2}$ to be higher, and so on. Again the absolute value of the effect decays geometrically toward zero. If $\phi > 1$ , the dynamic multiplier increases exponentially over time as in panel (c). A given increase in $w_t$ has a larger effect the farther into the future one goes. For $\phi < -1$ , the system [1.1.1] exhibits explosive oscillation as in panel (d).

Thus, if $|\phi| < 1$ , the system is stable; the consequences of a given change in $w_{t}$ will eventually die out. If $|\phi| > 1$ , the system is explosive. An interesting possibility is the borderline case, $\phi = 1$ . In this case, the solution [1.1.9] becomes

$$
y _ {t + j} = y _ {t - 1} + w _ {t} + w _ {t + 1} + w _ {t + 2} + \dots + w _ {t + j - 1} + w _ {t + j}. \tag {1.1.11}
$$

Here the output variable $y$ is the sum of the historical inputs $w$ . A one-unit increase in $w$ will cause a permanent one-unit increase in $y$ :

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = 1 \quad \text {f o r} j = 0, 1, \dots .
$$

We might also be interested in the effect of $w$ on the present value of the stream of future realizations of $y$ . For a given stream of future values $y_{t}, y_{t+1}$ ,

![](images/832faabd0357e89666e5692127734b25a145b6ad4735f37dfb8535a384c02d0c.jpg)  
(a) $\phi = 0.8$

![](images/0743d9b54536cc73399624763320a762f48873445fa34a23cc2e4daac64c56f4.jpg)  
(b) $\phi = -0.8$

![](images/c91a0c9b5b2d6d1a2893a6c4a42c490830e540c6046620018fbe35bcc9fdfb9b.jpg)  
(c) $\phi = 1.1$

![](images/297ebe75ebce9b8f2cbf48dcb0b87f4e7857cd96c67c36c1510f513b9018dd10.jpg)  
(d) $\phi = -1.1$   
FIGURE 1.1 Dynamic multiplier for first-order difference equation for different values of $\phi$ (plot of $\partial y_{t+j} / \partial w_t = \phi^j$ as a function of the lag $j$ ).

$y_{t + 2},\ldots$ and a constant interest rate $r > 0$ , the present value of the stream at time $t$ is given by

$$
y _ {t} + \frac {y _ {t + 1}}{1 + r} + \frac {y _ {t + 2}}{(1 + r) ^ {2}} + \frac {y _ {t + 3}}{(1 + r) ^ {3}} + \dots . \tag {1.1.12}
$$

Let $\beta$ denote the discount factor:

$$
\beta \equiv 1 / (1 + r).
$$

Note that $0 < \beta < 1$ . Then the present value [1.1.12] can be written as

$$
\sum_ {j = 0} ^ {\infty} \beta^ {j} y _ {t + j}. \tag {1.1.13}
$$

Consider what would happen if there were a one-unit increase in $w_{t}$ with $w_{t+1}, w_{t+2}, \ldots$ unaffected. The consequences of this change for the present value of $y$ are found by differentiating [1.1.13] with respect to $w_{t}$ and then using [1.1.10]

The interest rate is measured here as a fraction of 1; thus $r = 0.1$ corresponds to a $10\%$ interest rate.

to evaluate each derivative:

$$
\sum_ {j = 0} ^ {\infty} \beta^ {j} \frac {\partial y _ {t + j}}{\partial w _ {t}} = \sum_ {j = 0} ^ {\infty} \beta^ {j} \phi^ {j} = 1 / (1 - \beta \phi), \tag {1.1.14}
$$

provided that $|\beta \phi| < 1$ .

In calculating the dynamic multipliers [1.1.10] or [1.1.14], we were asking what would happen if $w_{t}$ were to increase by one unit with $w_{t+1}, w_{t+2}, \ldots, w_{t+j}$ unaffected. We were thus finding the effect of a purely transitory change in $w$ . Panel (a) of Figure 1.2 shows the time path of $w$ associated with this question, and panel (b) shows the implied path for $y$ . Because the dynamic multiplier [1.1.10] calculates the response of $y$ to a single impulse in $w$ , it is also referred to as the impulse-response function.

![](images/7f20fca0352adae7ede0414e3fa9a95feccb645bb8107e1aaad18f7d5f2814eb.jpg)  
(a) Value of $w$

![](images/aa1e37b6073bae27423a281269a7f5e1fcac2925f53e575aff3355f5855cc2fb.jpg)  
(b) Value of $y$   
FIGURE 1.2 Paths of input variable $(w_{t})$ and output variable $(y_{t})$ assumed for dynamic multiplier and present-value calculations.

Sometimes we might instead be interested in the consequences of a permanent change in $w$ . A permanent change in $w$ means that $w_{t}, w_{t+1}, \ldots,$ and $w_{t+j}$ would all increase by one unit, as in Figure 1.3. From formula [1.1.10], the effect on $y_{t+j}$ of a permanent change in $w$ beginning in period $t$ is given by

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} + \frac {\partial y _ {t + j}}{\partial w _ {t + 1}} + \frac {\partial y _ {t + j}}{\partial w _ {t + 2}} + \dots + \frac {\partial y _ {t + j}}{\partial w _ {t + j}} = \phi^ {j} + \phi^ {j - 1} + \phi^ {j - 2} + \dots + \phi + 1.
$$

When $|\phi| < 1$ , the limit of this expression as $j$ goes to infinity is sometimes described as the "long-run" effect of $w$ on $y$ :

$$
\begin{array}{l} \lim  _ {j \rightarrow \infty} \left[ \frac {\partial y _ {t + j}}{\partial w _ {t}} + \frac {\partial y _ {t + j}}{\partial w _ {t + 1}} + \frac {\partial y _ {t + j}}{\partial w _ {t + 2}} + \dots + \frac {\partial y _ {t + j}}{\partial w _ {t + j}} \right] = 1 + \phi + \phi^ {2} + \dots \tag {1.1.15} \\ = 1 / (1 - \phi). \\ \end{array}
$$

![](images/690519e3a928250838b8615d82fd07b25fdc74bfd5673b5946a406eda41e8fdf.jpg)  
(a) Value of $w$

![](images/11211359a45087a3f0fcba0d32cf648cd297075c6b948ea65c502a28953c8b93.jpg)  
(b) Value of $y$   
FIGURE 1.3 Paths of input variable $(w_{t})$ and output variable $(y_{t})$ assumed for long-run effect calculations.

For example, the long-run income elasticity of money demand in the system [1.1.2] is given by

$$
\frac {0 . 1 9}{1 - 0 . 7 2} = 0. 6 8.
$$

A permanent $1\%$ increase in income will eventually lead to a $0.68\%$ increase in money demand.

Another related question concerns the cumulative consequences for $y$ of a one-time change in $w$ . Here we consider a transitory disturbance to $w$ as in panel (a) of Figure 1.2, but wish to calculate the sum of the consequences for all future values of $y$ . Another way to think of this is as the effect on the present value of $y$ [1.1.13] with the discount rate $\beta = 1$ . Setting $\beta = 1$ in [1.1.14] shows this cumulative effect to be equal to

$$
\sum_ {j = 0} ^ {\infty} \frac {\partial y _ {t + j}}{\partial w _ {t}} = 1 / (1 - \phi), \tag {1.1.16}
$$

provided that $|\phi| < 1$ . Note that the cumulative effect on $y$ of a transitory change in $w$ (expression [1.1.16]) is the same as the long-run effect on $y$ of a permanent change in $w$ (expression [1.1.15]).

# 1.2. pth-Order Difference Equations

Let us now generalize the dynamic system [1.1.1] by allowing the value of $y$ at date $t$ to depend on $p$ of its own lags along with the current value of the input variable $w_{t}$ :

$$
y _ {t} = \phi_ {1} y _ {t - 1} + \phi_ {2} y _ {t - 2} + \dots + \phi_ {p} y _ {t - p} + w _ {t}. \tag {1.2.1}
$$

Equation [1.2.1] is a linear $p$ th-order difference equation.

It is often convenient to rewrite the $p$ th-order difference equation [1.2.1] in the scalar $y_{t}$ as a first-order difference equation in a vector $\xi_{t}$ . Define the $(p \times 1)$ vector $\xi_{t}$ by

$$
\boldsymbol {\xi} _ {t} \equiv \left[ \begin{array}{c} y _ {t} \\ y _ {t - 1} \\ y _ {t - 2} \\ \vdots \\ y _ {t - p + 1} \end{array} \right]. \tag {1.2.2}
$$

That is, the first element of the vector $\xi$ at date $t$ is the value $y$ took on at date $t$ . The second element of $\xi_{t}$ is the value $y$ took on at date $t - 1$ , and so on. Define the $(p \times p)$ matrix $\mathbf{F}$ by

$$
\mathbf {F} \equiv \left[ \begin{array}{c c c c c c} \phi_ {1} & \phi_ {2} & \phi_ {3} & \dots & \phi_ {p - 1} & \phi_ {p} \\ 1 & 0 & 0 & \dots & 0 & 0 \\ 0 & 1 & 0 & \dots & 0 & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & 1 & 0 \end{array} \right]. \tag {1.2.3}
$$

For example, for $p = 4$ , $\mathbf{F}$ refers to the following $4 \times 4$ matrix:

$$
\mathbf {F} = \left[ \begin{array}{c c c c} \phi_ {1} & \phi_ {2} & \phi_ {3} & \phi_ {4} \\ 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \end{array} \right].
$$

For $p = 1$ (the first-order difference equation [1.1.1]), $\mathbf{F}$ is just the scalar $\phi$ . Finally, define the $(p \times 1)$ vector $\mathbf{v}_t$ by

$$
\mathbf {v} _ {t} \equiv \left[ \begin{array}{c} w _ {t} \\ 0 \\ 0 \\ \vdots \\ 0 \end{array} \right]. \tag {1.2.4}
$$

Consider the following first-order vector difference equation:

$$
\boldsymbol {\xi} _ {t} = \mathbf {F} \boldsymbol {\xi} _ {t - 1} + \mathbf {v} _ {t}, \tag {1.2.5}
$$

or

$$
\left[ \begin{array}{c} y _ {t} \\ y _ {t - 1} \\ y _ {t - 2} \\ \vdots \\ y _ {t - p + 1} \end{array} \right] = \left[ \begin{array}{c c c c c c} \phi_ {1} & \phi_ {2} & \phi_ {3} & \dots & \phi_ {p - 1} & \phi_ {p} \\ 1 & 0 & 0 & \dots & 0 & 0 \\ 0 & 1 & 0 & \dots & 0 & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & 1 & 0 \end{array} \right] \left[ \begin{array}{c} y _ {t - 1} \\ y _ {t - 2} \\ y _ {t - 3} \\ \vdots \\ y _ {t - p} \end{array} \right] + \left[ \begin{array}{c} w _ {t} \\ 0 \\ 0 \\ \vdots \\ 0 \end{array} \right].
$$

This is a system of $p$ equations. The first equation in this system is identical to equation [1.2.1]. The second equation is simply the identity

$$
y _ {t - 1} = y _ {t - 1},
$$

owing to the fact that the second element of $\xi_{t}$ is the same as the first element of $\xi_{t - 1}$ . The third equation in [1.2.5] states that $y_{t - 2} = y_{t - 2}$ ; the $p$ th equation states that $y_{t - p + 1} = y_{t - p + 1}$ .

Thus, the first-order vector system [1.2.5] is simply an alternative representation of the $p$ th-order scalar system [1.2.1]. The advantage of rewriting the $p$ th-order system [1.2.1] in the form of a first-order system [1.2.5] is that first-order systems are often easier to work with than $p$ th-order systems.

A dynamic multiplier for [1.2.5] can be found in exactly the same way as was done for the first-order scalar system of Section 1.1. If we knew the value of the vector $\xi$ for date $t = -1$ and of $\mathbf{v}$ for date $t = 0$ , we could find the value of $\xi$ for date 0 from

$$
\boldsymbol {\xi} _ {0} = \mathbf {F} \boldsymbol {\xi} _ {- 1} + \mathbf {v} _ {0}.
$$

The value of $\pmb{\xi}$ for date 1 is

$$
\boldsymbol {\xi} _ {1} = \mathbf {F} \boldsymbol {\xi} _ {0} + \mathbf {v} _ {1} = \mathbf {F} (\mathbf {F} \boldsymbol {\xi} _ {- 1} + \mathbf {v} _ {0}) + \mathbf {v} _ {1} = \mathbf {F} ^ {2} \boldsymbol {\xi} _ {- 1} + \mathbf {F} \mathbf {v} _ {0} + \mathbf {v} _ {1}.
$$

Proceeding recursively in this fashion produces a generalization of [1.1.7]:

$$
\boldsymbol {\xi} _ {t} = \mathbf {F} ^ {t + 1} \boldsymbol {\xi} _ {- 1} + \mathbf {F} ^ {t} \mathbf {v} _ {0} + \mathbf {F} ^ {t - 1} \mathbf {v} _ {1} + \mathbf {F} ^ {t - 2} \mathbf {v} _ {2} + \dots + \mathbf {F} \mathbf {v} _ {t - 1} + \mathbf {v} _ {t}. \quad [ 1. 2. 6 ]
$$

Writing this out in terms of the definitions of $\pmb{\xi}$ and $\mathbf{v}$ ,

$$
\begin{array}{l} \left[ \begin{array}{c} y _ {t} \\ y _ {t - 1} \\ y _ {t - 2} \\ \vdots \\ y _ {t - p + 1} \end{array} \right] = \mathbf {F} ^ {t + 1} \left[ \begin{array}{c} y _ {- 1} \\ y _ {- 2} \\ y _ {- 3} \\ \vdots \\ y _ {- p} \end{array} \right] + \mathbf {F} ^ {t} \left[ \begin{array}{c} w _ {0} \\ 0 \\ 0 \\ \vdots \\ 0 \end{array} \right] + \mathbf {F} ^ {t - 1} \left[ \begin{array}{c} w _ {1} \\ 0 \\ 0 \\ \vdots \\ 0 \end{array} \right] + \dots \tag {1.2.7} \\ + \mathbf {F} ^ {1} \left[ \begin{array}{c} w _ {t - 1} \\ 0 \\ 0 \\ \vdots \\ 0 \end{array} \right] + \left[ \begin{array}{c} w _ {t} \\ 0 \\ 0 \\ \vdots \\ 0 \end{array} \right]. \\ \end{array}
$$

Consider the first equation of this system, which characterizes the value of $y_{t}$ . Let $f_{11}^{(t)}$ denote the (1, 1) element of $\mathbf{F}^t$ , $f_{12}^{(t)}$ the (1, 2) element of $\mathbf{F}^t$ , and so on. Then the first equation of [1.2.7] states that

$$
\begin{array}{l} y _ {t} = f _ {1 1} ^ {(t + 1)} y _ {- 1} + f _ {1 2} ^ {(t + 1)} y _ {- 2} + \dots + f _ {1 p} ^ {(t + 1)} y _ {- p} + f _ {1 1} ^ {(t)} w _ {0} \tag {1.2.8} \\ + f _ {1 1} ^ {(t - 1)} w _ {1} + \dots + f _ {1 1} ^ {(1)} w _ {t - 1} + w _ {t}. \\ \end{array}
$$

This describes the value of $y$ at date $t$ as a linear function of $p$ initial values of $y$ ( $y_{-1}, y_{-2}, \ldots, y_{-p}$ ) and the history of the input variable $w$ since time 0 ( $w_0, w_1, \ldots, w_t$ ). Note that whereas only one initial value for $y$ (the value $y_{-1}$ ) was needed in the case of a first-order difference equation, $p$ initial values for $y$ (the values $y_{-1}, y_{-2}, \ldots, y_{-p}$ ) are needed in the case of a $p$ th-order difference equation.

The obvious generalization of [1.1.9] is

$$
\begin{array}{r l} \xi_ {t + j} & = \mathbf {F} ^ {j + 1} \xi_ {t - 1} + \mathbf {F} ^ {j} \mathbf {v} _ {t} + \mathbf {F} ^ {j - 1} \mathbf {v} _ {t + 1} + \mathbf {F} ^ {j - 2} \mathbf {v} _ {t + 2} + \dots \\ & + \mathbf {F} \mathbf {v} _ {t + j - 1} + \mathbf {v} _ {t + j} \end{array} \tag {1.2.9}
$$

from which

$$
\begin{array}{l} y _ {t + j} = f _ {1 1} ^ {(j + 1)} y _ {t - 1} + f _ {1 2} ^ {(j + 1)} y _ {t - 2} + \dots + f _ {1 p} ^ {(j + 1)} y _ {t - p} + f _ {1 1} ^ {(j)} w _ {t} \tag {1.2.10} \\ + f _ {1 1} ^ {(j - 1)} w _ {t + 1} + f _ {1 1} ^ {(j - 2)} w _ {t + 2} + \dots + f _ {1 1} ^ {(1)} w _ {t + j - 1} + w _ {t + j}. \\ \end{array}
$$

Thus, for a $p$ th-order difference equation, the dynamic multiplier is given by

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = f _ {1 1} ^ {(j)} \tag {1.2.11}
$$

where $f_{11}^{(j)}$ denotes the (1, 1) element of $\mathbf{F}^j$ . For $j = 1$ , this is simply the (1, 1) element of $\mathbf{F}$ , or the parameter $\phi_1$ . Thus, for any $p$ th-order system, the effect on $y_{t+1}$ of a one-unit increase in $w_t$ is given by the coefficient relating $y_t$ to $y_{t-1}$ in equation [1.2.1]:

$$
\frac {\partial y _ {t + 1}}{\partial w _ {t}} = \phi_ {1}.
$$

Direct multiplication of [1.2.3] reveals that the $(1,1)$ element of $\mathbf{F}^2$ is $(\phi_1^2 + \phi_2)$ , so

$$
\frac {\partial y _ {t + 2}}{\partial w _ {t}} = \phi_ {1} ^ {2} + \phi_ {2}
$$

in a $p$ th-order system.

For larger values of $j$ , an easy way to obtain a numerical value for the dynamic multiplier $\partial y_{t+j} / \partial w_t$ is to simulate the system. This is done as follows. Set $y_{-1} = y_{-2} = \dots = y_{-p} = 0$ , $w_0 = 1$ , and set the value of $w$ for all other dates to 0. Then use [1.2.1] to calculate the value of $y_t$ for $t = 0$ (namely, $y_0 = 1$ ). Next substitute this value along with $y_{t-1}, y_{t-2}, \ldots, y_{t-p+1}$ back into [1.2.1] to calculate $y_{t+1}$ , and continue recursively in this fashion. The value of $y$ at step $t$ gives the effect of a one-unit change in $w_0$ on $y_t$ .

Although numerical simulation may be adequate for many circumstances, it is also useful to have a simple analytical characterization of $\partial y_{t+j} / \partial w_t$ , which, we know from [1.2.11], is given by the $(1,1)$ element of $\mathbf{F}^j$ . This is fairly easy to obtain in terms of the eigenvalues of the matrix $\mathbf{F}$ . Recall that the eigenvalues of a matrix $\mathbf{F}$ are those numbers $\lambda$ for which

$$
\left| \mathbf {F} - \lambda \mathbf {I} _ {p} \right| = 0. \tag {1.2.12}
$$

For example, for $p = 2$ the eigenvalues are the solutions to

$$
\left| \left[ \begin{array}{c c} \phi_ {1} & \phi_ {2} \\ 1 & 0 \end{array} \right] - \left[ \begin{array}{c c} \lambda & 0 \\ 0 & \lambda \end{array} \right] \right| = 0
$$

or

$$
\left| \begin{array}{c c} (\phi_ {1} - \lambda) & \phi_ {2} \\ 1 & - \lambda \end{array} \right| = \lambda^ {2} - \phi_ {1} \lambda - \phi_ {2} = 0. \tag {1.2.13}
$$

The two eigenvalues of $\mathbf{F}$ for a second-order difference equation are thus given by

$$
\lambda_ {1} = \frac {\phi_ {1} + \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}}}{2} \tag {1.2.14}
$$

$$
\lambda_ {2} = \frac {\phi_ {1} - \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}}}{2}. \tag {1.2.15}
$$

For a general $p$ th-order system, the determinant in [1.2.12] is a $p$ th-order polynomial in $\lambda$ whose $p$ solutions characterize the $p$ eigenvalues of $\mathbf{F}$ . This polynomial turns out to take a very similar form to [1.2.13]. The following result is proved in Appendix 1.A at the end of this chapter.

Proposition 1.1: The eigenvalues of the matrix $\mathbf{F}$ defined in equation [1.2.3] are the values of $\lambda$ that satisfy

$$
\lambda^ {p} - \phi_ {1} \lambda^ {p - 1} - \phi_ {2} \lambda^ {p - 2} - \dots - \phi_ {p - 1} \lambda - \phi_ {p} = 0. \qquad [ 1. 2. 1 6 ]
$$

Once we know the eigenvalues, it is straightforward to characterize the dynamic behavior of the system. First we consider the case when the eigenvalues of $\mathbf{F}$ are distinct; for example, we require that $\lambda_{1}$ and $\lambda_{2}$ in [1.2.14] and [1.2.15] be different numbers.

# General Solution of a pth-Order Difference Equation with Distinct Eigenvalues

Recall² that if the eigenvalues of a $(p \times p)$ matrix $\mathbf{F}$ are distinct, there exists a nonsingular $(p \times p)$ matrix $\mathbf{T}$ such that

$$
\mathbf {F} = \mathbf {T} \boldsymbol {\Lambda} \mathbf {T} ^ {- 1} \tag {1.2.17}
$$

where $\Lambda$ is a $(p\times p)$ matrix with the eigenvalues of $\mathbf{F}$ along the principal diagonal and zeros elsewhere:

$$
\boldsymbol {\Lambda} = \left[ \begin{array}{c c c c c} \lambda_ {1} & 0 & 0 & \dots & 0 \\ 0 & \lambda_ {2} & 0 & \dots & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots \\ 0 & 0 & 0 & \dots & \lambda_ {p} \end{array} \right]. \tag {1.2.18}
$$

This enables us to characterize the dynamic multiplier (the $(1,1)$ element of $\mathbf{F}^j$ in [1.2.11]) very easily. For example, from [1.2.17] we can write $\mathbf{F}^2$ as

$$
\begin{array}{l} \mathbf {F} ^ {2} = \mathbf {T} \boldsymbol {\Lambda} \mathbf {T} ^ {- 1} \times \mathbf {T} \boldsymbol {\Lambda} \mathbf {T} ^ {- 1} \\ = \mathbf {T} \times \boldsymbol {\Lambda} \times (\mathbf {T} ^ {- 1} \mathbf {T}) \times \boldsymbol {\Lambda} \times \mathbf {T} ^ {- 1} \\ = \mathbf {T} \times \boldsymbol {\Lambda} \times \mathbf {I} _ {p} \times \boldsymbol {\Lambda} \times \mathbf {T} ^ {- 1} \\ = \mathbf {T} \boldsymbol {\Lambda} ^ {2} \mathbf {T} ^ {- 1}. \\ \end{array}
$$

The diagonal structure of $\Lambda$ implies that $\Lambda^2$ is also a diagonal matrix whose elements are the squares of the eigenvalues of $\mathbf{F}$ :

$$
\boldsymbol {\Lambda} ^ {2} = \left[ \begin{array}{c c c c c} \lambda_ {1} ^ {2} & 0 & 0 & \dots & 0 \\ 0 & \lambda_ {2} ^ {2} & 0 & \dots & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots \\ 0 & 0 & 0 & \dots & \lambda_ {p} ^ {2} \end{array} \right].
$$

More generally, we can characterize $\mathbf{F}^j$ in terms of the eigenvalues of $\mathbf{F}$ as

$$
\begin{array}{l} \mathbf {F} ^ {j} = \underbrace {\mathbf {T A T} ^ {- 1} \times \mathbf {T A T} ^ {- 1} \times \cdots \times \mathbf {T A T} ^ {- 1}} _ {j \text {t e r m s}} \\ = \mathbf {T} \times \boldsymbol {\Lambda} \times (\mathbf {T} ^ {- 1} \mathbf {T}) \times \boldsymbol {\Lambda} \times (\mathbf {T} ^ {- 1} \mathbf {T}) \times \dots \times \boldsymbol {\Lambda} \times \mathbf {T} ^ {- 1}, \\ \end{array}
$$

which simplifies to

$$
\mathbf {F} ^ {j} = \mathbf {T} \boldsymbol {\Lambda} ^ {j} \mathbf {T} ^ {- 1} \tag {1.2.19}
$$

where

$$
\boldsymbol {\Lambda} ^ {j} = \left[ \begin{array}{c c c c c} \lambda_ {1} ^ {i} & 0 & 0 & \dots & 0 \\ 0 & \lambda_ {2} ^ {i} & 0 & \dots & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots \\ 0 & 0 & 0 & \dots & \lambda_ {p} ^ {j} \end{array} \right].
$$

See equation [A.4.24] in the Mathematical Review (Appendix A) at the end of the book.

Let $t_{ij}$ denote the row $i$ , column $j$ element of $\mathbf{T}$ and let $t^{ij}$ denote the row $i$ , column $j$ element of $\mathbf{T}^{-1}$ . Equation [1.2.19] written out explicitly becomes

$$
\begin{array}{l} \mathbf {F} ^ {j} = \left[ \begin{array}{c c c c} t _ {1 1} & t _ {1 2} & \dots & t _ {1 p} \\ t _ {2 1} & t _ {2 2} & \dots & t _ {2 p} \\ \vdots & \vdots & \dots & \vdots \\ t _ {p 1} & t _ {p 2} & \dots & t _ {p p} \end{array} \right] \left[ \begin{array}{c c c c c} \lambda_ {1} ^ {j} & 0 & 0 & \dots & 0 \\ 0 & \lambda_ {2} ^ {j} & 0 & \dots & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots \\ 0 & 0 & 0 & \dots & \lambda_ {p} ^ {j} \end{array} \right] \left[ \begin{array}{c c c c c} t ^ {1 1} & t ^ {1 2} & \dots & t ^ {1 p} \\ t ^ {2 1} & t ^ {2 2} & \dots & t ^ {2 p} \\ \vdots & \vdots & \dots & \vdots \\ t ^ {p 1} & t ^ {p 2} & \dots & t ^ {p p} \end{array} \right] \\ = \left[ \begin{array}{c c c c} t _ {1 1} \lambda_ {1} ^ {j} & t _ {1 2} \lambda_ {2} ^ {j} & \dots & t _ {1 p} \lambda_ {p} ^ {j} \\ t _ {2 1} \lambda_ {1} ^ {j} & t _ {2 2} \lambda_ {2} ^ {j} & \dots & t _ {2 p} \lambda_ {p} ^ {j} \\ \vdots & \vdots & \dots & \vdots \\ t _ {p 1} \lambda_ {1} ^ {j} & t _ {p 2} \lambda_ {2} ^ {j} & \dots & t _ {p p} \lambda_ {p} ^ {j} \end{array} \right] \left[ \begin{array}{c c c c} t ^ {1 1} & t ^ {1 2} & \dots & t ^ {1 p} \\ t ^ {2 1} & t ^ {2 2} & \dots & t ^ {2 p} \\ \vdots & \vdots & \dots & \vdots \\ t ^ {p 1} & t ^ {p 2} & \dots & t ^ {p p} \end{array} \right] \\ \end{array}
$$

from which the $(1,1)$ element of $\mathbf{F}^j$ is given by

$$
f _ {1 1} ^ {(j)} = \left[ t _ {1 1} t ^ {1 1} \right] \lambda_ {1} ^ {j} + \left[ t _ {1 2} t ^ {2 1} \right] \lambda_ {2} ^ {j} + \dots + \left[ t _ {1 p} t ^ {p 1} \right] \lambda_ {p} ^ {j}
$$

or

$$
f _ {1 1} ^ {(j)} = c _ {1} \lambda_ {1} ^ {i} + c _ {2} \lambda_ {2} ^ {j} + \dots + c _ {p} \lambda_ {p} ^ {j} \tag {1.2.20}
$$

where

$$
c _ {i} = \left[ t _ {1 i} t ^ {t 1} \right]. \tag {1.2.21}
$$

Note that the sum of the $c_{i}$ terms has the following interpretation:

$$
c _ {1} + c _ {2} + \dots + c _ {p} = \left[ t _ {1 1} t ^ {1 1} \right] + \left[ t _ {1 2} t ^ {2 1} \right] + \dots + \left[ t _ {1 p} t ^ {p 1} \right], \quad [ 1. 2. 2 2 ]
$$

which is the $(1,1)$ element of $\mathbf{T} \cdot \mathbf{T}^{-1}$ . Since $\mathbf{T} \cdot \mathbf{T}^{-1}$ is just the $(p \times p)$ identity matrix, [1.2.22] implies that the $c_{i}$ terms sum to unity:

$$
c _ {1} + c _ {2} + \dots + c _ {p} = 1. \tag {1.2.23}
$$

Substituting [1.2.20] into [1.2.11] gives the form of the dynamic multiplier for a $p$ th-order difference equation:

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = c _ {1} \lambda_ {1} ^ {j} + c _ {2} \lambda_ {2} ^ {j} + \dots + c _ {p} \lambda_ {p} ^ {j}. \tag {1.2.24}
$$

Equation [1.2.24] characterizes the dynamic multiplier as a weighted average of each of the $p$ eigenvalues raised to the $j$ th power.

The following result provides a closed-form expression for the constants $(c_{1}, c_{2}, \ldots, c_{p})$ .

Proposition 1.2: If the eigenvalues $(\lambda_1, \lambda_2, \ldots, \lambda_p)$ of the matrix $\mathbf{F}$ in [1.2.3] are distinct, then the magnitude $c_i$ in [1.2.21] can be written

$$
c_{i} = \frac{\lambda_{i}^{p - 1}}{\prod\limits_{\substack{k = 1\\ k\neq i}}^{p}\left(\lambda_{i} - \lambda_{k}\right)}. \tag{[1.2.25]}
$$

To summarize, the $p$ th-order difference equation [1.2.1] implies that

$$
\begin{array}{l} y _ {t + j} = f _ {1 1} ^ {(j + 1)} y _ {t - 1} + f _ {1 2} ^ {(j + 1)} y _ {t - 2} + \dots + f _ {1 p} ^ {(j + 1)} y _ {t - p} \tag {1.2.26} \\ + w _ {t + j} + \psi_ {1} w _ {t + j - 1} + \psi_ {2} w _ {i + j - 2} + \dots + \psi_ {j - 1} w _ {t + 1} + \psi_ {j} w _ {t}. \\ \end{array}
$$

The dynamic multiplier

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = \psi_ {j} \tag {1.2.27}
$$

is given by the $(1,1)$ element of $\mathbf{F}^j$ :

$$
\psi_ {j} = f _ {1 1} ^ {(j)}. \tag {1.2.28}
$$

A closed-form expression for $\psi_{j}$ can be obtained by finding the eigenvalues of $\mathbf{F}$ , or the values of $\lambda$ satisfying [1.2.16]. Denoting these $p$ values by $(\lambda_1,\lambda_2,\dots ,\lambda_p)$ and assuming them to be distinct, the dynamic multiplier is given by

$$
\psi_ {j} = c _ {1} \lambda_ {1} ^ {j} + c _ {2} \lambda_ {2} ^ {j} + \dots + c _ {p} \lambda_ {p} ^ {j} \tag {1.2.29}
$$

where $(c_{1}, c_{2}, \ldots, c_{p})$ is a set of constants summing to unity given by expression [1.2.25].

For a first-order system $(p = 1)$ , this rule would have us solve [1.2.16],

$$
\lambda - \phi_ {1} = 0,
$$

which has the single solution

$$
\lambda_ {1} = \phi_ {1}. \tag {1.2.30}
$$

According to [1.2.29], the dynamic multiplier is given by

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = c _ {1} \lambda_ {1} ^ {j}. \tag {1.2.31}
$$

From [1.2.23], $c_{1} = 1$ . Substituting this and [1.2.30] into [1.2.31] gives

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = \phi_ {1} ^ {i},
$$

or the same result found in Section 1.1.

For higher-order systems, [1.2.29] allows a variety of more complicated dynamics. Suppose first that all the eigenvalues of $\mathbf{F}$ (or solutions to [1.2.16]) are real. This would be the case, for example, if $p = 2$ and $\phi_1^2 +4\phi_2 > 0$ in the solutions [1.2.14] and [1.2.15] for the second-order system. If, furthermore, all of the eigenvalues are less than 1 in absolute value, then the system is stable, and its dynamics are represented as a weighted average of decaying exponentials or decaying exponentials oscillating in sign. For example, consider the following second-order difference equation:

$$
y _ {t} = 0. 6 y _ {t - 1} + 0. 2 y _ {t - 2} + w _ {t}.
$$

From equations [1.2.14] and [1.2.15], the eigenvalues of this system are given by

$$
\lambda_ {1} = \frac {0 . 6 + \sqrt {(0 . 6) ^ {2} + 4 (0 . 2)}}{2} = 0. 8 4
$$

$$
\lambda_ {2} = \frac {0 . 6 - \sqrt {(0 . 6) ^ {2} + 4 (0 . 2)}}{2} = - 0. 2 4.
$$

From [1.2.25], we have

$$
c _ {1} = \lambda_ {1} / (\lambda_ {1} - \lambda_ {2}) = 0. 7 7 8
$$

$$
c _ {2} = \lambda_ {2} / (\lambda_ {2} - \lambda_ {1}) = 0. 2 2 2.
$$

The dynamic multiplier for this system,

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = c _ {1} \lambda_ {1} ^ {j} + c _ {2} \lambda_ {2} ^ {j},
$$

is plotted as a function of $j$ in panel (a) of Figure 1.4. Note that as $j$ becomes larger, the pattern is dominated by the larger eigenvalue $(\lambda_1)$ , approximating a simple geometric decay at rate $\lambda_1$ .

If the eigenvalues (the solutions to [1.2.16]) are real but at least one is greater than unity in absolute value, the system is explosive. If $\lambda_{1}$ denotes the eigenvalue that is largest in absolute value, the dynamic multiplier is eventually dominated by an exponential function of that eigenvalue:

$$
\lim  _ {j \rightarrow \infty} \frac {\partial y _ {t + j}}{\partial w _ {t}} \cdot \frac {1}{\lambda_ {1} ^ {j}} = c _ {1}.
$$

Other interesting possibilities arise if some of the eigenvalues are complex. Whenever this is the case, they appear as complex conjugates. For example, if $p = 2$ and $\phi_1^2 + 4\phi_2 < 0$ , then the solutions $\lambda_1$ and $\lambda_2$ in [1.2.14] and [1.2.15] are complex conjugates. Suppose that $\lambda_1$ and $\lambda_2$ are complex conjugates, written as

$$
\lambda_ {1} = a + b i \tag {1.2.32}
$$

$$
\lambda_ {2} = a - b i. \tag {1.2.33}
$$

For the $p = 2$ case of [1.2.14] and [1.2.15], we would have

$$
a = \phi_ {1} / 2 \tag {1.2.34}
$$

$$
b = (1 / 2) \sqrt {- \phi_ {1} ^ {2} - 4 \phi_ {2}}. \tag {1.2.35}
$$

Our goal is to characterize the contribution to the dynamic multiplier $c_{1}\lambda_{1}^{j}$ when $\lambda_{1}$ is a complex number as in [1.2.32]. Recall that to raise a complex number to a power, we rewrite [1.2.32] in polar coordinate form:

$$
\lambda_ {1} = R \cdot [ \cos (\theta) + i \cdot \sin (\theta) ], \tag {1.2.36}
$$

where $\theta$ and $R$ are defined in terms of $a$ and $b$ by the following equations:

$$
R = \sqrt {a ^ {2} + b ^ {2}}
$$

$$
\cos (\theta) = a / R
$$

$$
\sin (\theta) = b / R.
$$

Note that $R$ is equal to the modulus of the complex number $\lambda_{1}$ .

The eigenvalue $\lambda_{1}$ in [1.2.36] can be written as

$$
\lambda_ {1} = R \left[ e ^ {i \theta^ {\prime}} \right],
$$

and so

$$
\lambda_ {1} ^ {i} = R ^ {j} \left[ e ^ {i \theta j} \right] = R ^ {j} \left[ \cos (\theta j) + i \cdot \sin (\theta j) \right]. \tag {1.2.37}
$$

Analogously, if $\lambda_{2}$ is the complex conjugate of $\lambda_{1}$ , then

$$
\lambda_ {2} = R [ \cos (\theta) - i \cdot \sin (\theta) ],
$$

which can be written

$$
\lambda_ {2} = R \left[ e ^ {- i \theta} \right].
$$

Thus

$$
\lambda_ {2} ^ {j} = R ^ {j} \left[ e ^ {- i \theta j} \right] = R ^ {j} \left[ \cos (\theta j) - i \cdot \sin (\theta j) \right]. \tag {1.2.38}
$$

<sup>3</sup>Again, if one's purpose is solely to generate a numerical plot as in Figure 1.4, the easiest approach is numerical simulation of the system.

4See equation [A.3.25] in the Mathematical Review (Appendix A) at the end of the book.

See equation [A.3.26].

![](images/d6558ae77dbc34e5c26582d7dc3e74e324c86b510d875c29a634c3bec418871b.jpg)  
(a) $\phi_1 = 0.6, \phi_2 = 0.2$

![](images/cbfb4fccde6aeb03ed9ef7d32e254cea08583abc1db8c8cf02771666075b46eb.jpg)  
(b) $\phi_1 = 0.5, \phi_2 = -0.8$   
FIGURE 1.4 Dynamic multiplier for second-order difference equation for different values of $\phi_{1}$ and $\phi_{2}$ (plot of $\partial y_{t+j} / \partial w_{t}$ as a function of the lag $j$ ).

Substituting [1.2.37] and [1.2.38] into [1.2.29] gives the contribution of the complex conjugates to the dynamic multiplier $\partial y_{t+j} / \partial w_t$ :

$$
\begin{array}{l} c _ {1} \lambda_ {1} ^ {j} + c _ {2} \lambda_ {2} ^ {j} = c _ {1} R ^ {j} [ \cos (\theta j) + i \cdot \sin (\theta j) ] + c _ {2} R ^ {j} [ \cos (\theta j) - i \cdot \sin (\theta j) ] \\ = \left[ c _ {1} + c _ {2} \right] \cdot R ^ {j} \cdot \cos (\theta j) + i \cdot \left[ c _ {1} - c _ {2} \right] \cdot R ^ {j} \cdot \sin (\theta j). \\ \end{array}
$$

The appearance of the imaginary number $i$ in [1.2.39] may seem a little troubling. After all, this calculation was intended to give the effect of a change in the real-valued variable $w_{t}$ on the real-valued variable $y_{t + f}$ as predicted by the real-valued system [1.2.1], and it would be odd indeed if the correct answer involved the imaginary number $i!$ . Fortunately, it turns out from [1.2.25] that if $\lambda_{1}$ and $\lambda_{2}$ are complex conjugates, then $c_{1}$ and $c_{2}$ are complex conjugates; that is, they can

be written as

$$
c _ {1} = \alpha + \beta i
$$

$$
c _ {2} = \alpha - \beta i
$$

for some real numbers $\alpha$ and $\beta$ . Substituting these expressions into [1.2.39] yields

$$
\begin{array}{l} c _ {1} \lambda_ {1} ^ {i} + c _ {2} \lambda_ {2} ^ {i} = [ (\alpha + \beta i) + (\alpha - \beta i) ] \cdot R ^ {j} \cos (\theta j) + i \cdot [ (\alpha + \beta i) - (\alpha - \beta i) ] \cdot R ^ {j} \sin (\theta j) \\ = [ 2 \alpha ] \cdot R ^ {j} \cos (\theta j) + i \cdot [ 2 \beta i ] \cdot R ^ {j} \sin (\theta j) \\ = 2 \alpha R ^ {j} \cos (\theta j) - 2 \beta R ^ {j} \sin (\theta j), \\ \end{array}
$$

which is strictly real.

Thus, when some of the eigenvalues are complex, they contribute terms proportional to $R^j \cos(\theta j)$ and $R^j \sin(\theta j)$ to the dynamic multiplier $\partial y_{t+j} / \partial w_t$ . Note that if $R = 1$ —that is, if the complex eigenvalues have unit modulus—the multipliers are periodic sine and cosine functions of $j$ . A given increase in $w_t$ increases $y_{t+j}$ for some ranges of $j$ and decreases $y_{t+j}$ over other ranges, with the impulse never dying out as $j \to \infty$ . If the complex eigenvalues are less than 1 in modulus $(R < 1)$ , the impulse again follows a sinusoidal pattern though its amplitude decays at the rate $R^j$ . If the complex eigenvalues are greater than 1 in modulus $(R > 1)$ , the amplitude of the sinusoids explodes at the rate $R^j$ .

For an example of dynamic behavior characterized by decaying sinusoids, consider the second-order system

$$
y _ {t} = 0. 5 y _ {t - 1} - 0. 8 y _ {t - 2} + w _ {t}.
$$

The eigenvalues for this system are given from [1.2.14] and [1.2.15]:

$$
\lambda_ {1} = \frac {0 . 5 + \sqrt {(0 . 5) ^ {2} - 4 (0 . 8)}}{2} = 0. 2 5 + 0. 8 6 i
$$

$$
\lambda_ {2} = \frac {0 . 5 - \sqrt {(0 . 5) ^ {2} - 4 (0 . 8)}}{2} = 0. 2 5 - 0. 8 6 i,
$$

with modulus

$$
R = \sqrt {(0 . 2 5) ^ {2} + (0 . 8 6) ^ {2}} = 0. 9.
$$

Since $R < 1$ , the dynamic multiplier follows a pattern of damped oscillation plotted in panel (b) of Figure 1.4. The frequency<sup>6</sup> of these oscillations is given by the parameter $\theta$ in [1.2.39], which was defined implicitly by

$$
\cos (\theta) = a / R = (0. 2 5) / (0. 9) = 0. 2 8
$$

or

$$
\theta = 1. 2 9.
$$

The cycles associated with the dynamic multiplier function [1.2.39] thus have a period of

$$
\frac {2 \pi}{\theta} = \frac {(2) (3 . 1 4 1 5 9)}{1 . 2 9} = 4. 9;
$$

that is, the peaks in the pattern in panel (b) of Figure 1.4 appear about five periods apart.

See Section A.1 of the Mathematical Review (Appendix A) at the end of the book for a discussion of the frequency and period of a sinusoidal function.

# Solution of a Second-Order Difference Equation with Distinct Eigenvalues

The second-order difference equation $(p = 2)$ comes up sufficiently often that it is useful to summarize the properties of the solution as a general function of $\phi_{1}$ and $\phi_{2}$ , which we now do.

The eigenvalues $\lambda_{1}$ and $\lambda_{2}$ in [1.2.14] and [1.2.15] are complex whenever

$$
\phi_ {1} ^ {2} + 4 \phi_ {2} <   0,
$$

or whenever $(\phi_1, \phi_2)$ lies below the parabola indicated in Figure 1.5. For the case of complex eigenvalues, the modulus $R$ satisfies

$$
R ^ {2} = a ^ {2} + b ^ {2},
$$

or, from [1.2.34] and [1.2.35],

$$
R ^ {2} = (\phi_ {1} / 2) ^ {2} - (\phi_ {1} ^ {2} + 4 \phi_ {2}) / 4 = - \phi_ {2}.
$$

Thus, a system with complex eigenvalues is explosive whenever $\phi_2 < -1$ . Also, when the eigenvalues are complex, the frequency of oscillations is given by

$$
\theta = \cos^ {- 1} (a / R) = \cos^ {- 1} \left[ \phi_ {1} / \left(2 \sqrt {- \phi_ {2}}\right) \right],
$$

where $\cos^{-1}(x)$ denotes the inverse of the cosine function, or the radian measure of an angle whose cosine is $x$ .

![](images/f394f8ecd0b23310a1ab88a719c73499cde42c8585c7bcfce2445f8205f97d52.jpg)  
FIGURE 1.5 Summary of dynamics for a second-order difference equation.

This discussion closely follows Sargent (1987, pp. 188-89).

For the case of real eigenvalues, the arithmetically larger eigenvalue $(\lambda_{1})$ will be greater than unity whenever

$$
\frac {\phi_ {1} + \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}}}{2} > 1
$$

or

$$
\sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}} > 2 - \phi_ {1}.
$$

Assuming that $\lambda_{1}$ is real, the left side of this expression is a positive number and the inequality would be satisfied for any value of $\phi_1 > 2$ . If, on the other hand, $\phi_1 < 2$ , we can square both sides to conclude that $\lambda_{1}$ will exceed unity whenever

$$
\phi_ {1} ^ {2} + 4 \phi_ {2} > 4 - 4 \phi_ {1} + \phi_ {1} ^ {2}
$$

or

$$
\phi_ {2} > 1 - \phi_ {1}.
$$

Thus, in the real region, $\lambda_{1}$ will be greater than unity either if $\phi_1 > 2$ or if $(\phi_1,\phi_2)$ lies northeast of the line $\phi_2 = 1 - \phi_1$ in Figure 1.5. Similarly, with real eigenvalues, the arithmetically smaller eigenvalue $(\lambda_{2})$ will be less than $-1$ whenever

$$
\begin{array}{l} \frac {\phi_ {1} - \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}}}{2} <   - 1 \\ - \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}} <   - 2 - \phi_ {1} \\ \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}} > 2 + \phi_ {1}. \\ \end{array}
$$

Again, if $\phi_1 < -2$ , this must be satisfied, and in the case when $\phi_1 > -2$ , we can square both sides:

$$
\begin{array}{l} \phi_ {1} ^ {2} + 4 \phi_ {2} > 4 + 4 \phi_ {1} + \phi_ {1} ^ {2} \\ \phi_ {2} > 1 + \phi_ {1}. \\ \end{array}
$$

Thus, in the real region, $\lambda_{2}$ will be less than $-1$ if either $\phi_1 < -2$ or $(\phi_1,\phi_2)$ lies to the northwest of the line $\phi_{2} = 1 + \phi_{1}$ in Figure 1.5.

The system is thus stable whenever $(\phi_1, \phi_2)$ lies within the triangular region of Figure 1.5.

# General Solution of a pth-Order Difference Equation with Repeated Eigenvalues

In the more general case of a difference equation for which $\mathbf{F}$ has repeated eigenvalues and $s < p$ linearly independent eigenvectors, result [1.2.17] is generalized by using the Jordan decomposition,

$$
\mathbf {F} = \mathbf {M J M} ^ {- 1} \tag {1.2.40}
$$

where $\mathbf{M}$ is a $(p\times p)$ matrix and $\mathbf{J}$ takes the form

$$
\mathbf {J} = \left[ \begin{array}{c c c c} \mathbf {J} _ {1} & \mathbf {0} & \dots & \mathbf {0} \\ \mathbf {0} & \mathbf {J} _ {2} & \dots & \mathbf {0} \\ \vdots & \vdots & \dots & \vdots \\ \mathbf {0} & \mathbf {0} & \dots & \mathbf {J} _ {s} \end{array} \right]
$$

with

$$
\mathbf {J} _ {i} = \left[ \begin{array}{c c c c c c} \lambda_ {i} & 1 & 0 & \dots & 0 & 0 \\ 0 & \lambda_ {i} & 1 & \dots & 0 & 0 \\ 0 & 0 & \lambda_ {i} & \dots & 0 & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & \lambda_ {i} & 1 \\ 0 & 0 & 0 & \dots & 0 & \lambda_ {i} \end{array} \right] \tag {1.2.41}
$$

for $\lambda_{i}$ an eigenvalue of $\mathbf{F}$ . If [1.2.17] is replaced by [1.2.40], then equation [1.2.19] generalizes to

$$
\mathbf {F} ^ {j} = \mathbf {M J} ^ {j} \mathbf {M} ^ {- 1} \tag {1.2.42}
$$

where

$$
\mathbf {J} ^ {j} = \left[ \begin{array}{c c c c} \mathbf {J} _ {1} ^ {j} & \mathbf {0} & \dots & \mathbf {0} \\ \mathbf {0} & \mathbf {J} _ {2} ^ {j} & \dots & \mathbf {0} \\ \vdots & \vdots & \dots & \vdots \\ \mathbf {0} & \mathbf {0} & \dots & \mathbf {J} _ {s} ^ {j} \end{array} \right].
$$

Moreover, from [1.2.41], if $\mathbf{J}_i$ is of dimension $(n_i\times n_i)$ , then

$$
\mathbf {J} _ {i} ^ {j} = \left[ \begin{array}{c c c c c} \lambda_ {i} ^ {j} & (i) \lambda_ {i} ^ {j - 1} & (j) \lambda_ {i} ^ {j - 2} & \dots & \left(n _ {i} - j _ {1}\right) \lambda_ {i} ^ {j - n _ {i} + 1} \\ 0 & \lambda_ {i} ^ {j} & (j) \lambda_ {i} ^ {j - 1} & \dots & \left(n _ {i} - j _ {2}\right) \lambda_ {i} ^ {j - n _ {i} + 2} \\ \vdots & \vdots & \vdots & \dots & \vdots \\ 0 & 0 & 0 & \dots & \lambda_ {i} ^ {j} \end{array} \right] \tag {1.2.43}
$$

where

$$
\binom {j} {n} \equiv \left\{ \begin{array}{l l} \frac {j (j - 1) (j - 2) \cdots (j - n + 1)}{n (n - 1) \cdots 3 \cdot 2 \cdot 1} & \text {f o r} j \geq n \\ 0 & \text {o t h e r w i s e .} \end{array} \right.
$$

Equation [1.2.43] may be verified by induction by multiplying [1.2.41] by [1.2.43] and noticing that $\binom{j}{n} + \binom{j}{n-1} = \binom{j+1}{n}$ .

For example, consider again the second-order difference equation, this time with repeated roots. Then

$$
\mathbf {F} ^ {j} = \mathbf {M} \left[ \begin{array}{c c} \lambda^ {j} & j \lambda^ {j - 1} \\ 0 & \lambda^ {j} \end{array} \right] \mathbf {M} ^ {- 1},
$$

so that the dynamic multiplier takes the form

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = f _ {1 1} ^ {(j)} = k _ {1} \lambda^ {j} + k _ {2} j \lambda^ {j - 1}.
$$

# Long-Run and Present-Value Calculations

If the eigenvalues are all less than 1 in modulus, then $\mathbf{F}^j$ in [1.2.9] goes to zero as $j$ becomes large. If all values of $w$ and $y$ are taken to be bounded, we can

This expression is taken from Chiang (1980, p. 444).

think of a "solution" of $y_{t}$ in terms of the infinite history of $w$ ,

$$
y _ {t} = w _ {t} + \psi_ {1} w _ {t - 1} + \psi_ {2} w _ {t - 2} + \psi_ {3} w _ {t - 3} + \dots , \tag {1.2.44}
$$

where $\psi_{j}$ is given by the $(1,1)$ element of $\mathbf{F}^j$ and takes the particular form of [1.2.29] in the case of distinct eigenvalues.

It is also straightforward to calculate the effect on the present value of $y$ of a transitory increase in $w$ . This is simplest to find if we first consider the slightly more general problem of the hypothetical consequences of a change in any element of the vector $\mathbf{v}_t$ on any element of $\xi_{t+j}$ in a general system of the form of [1.2.5]. The answer to this more general problem can be inferred immediately from [1.2.9]:

$$
\frac {\partial \boldsymbol {\xi} _ {t + j}}{\partial \mathbf {v} _ {t} ^ {\prime}} = \mathbf {F} ^ {j}. \tag {1.2.45}
$$

The true dynamic multiplier of interest, $\partial y_{t+j} / \partial w_t$ , is just the $(1,1)$ element of the $(p \times p)$ matrix in [1.2.45]. The effect on the present value of $\xi$ of a change in $\mathbf{v}$ is given by

$$
\frac {\partial \sum_ {j = 0} ^ {\infty} \beta^ {j} \boldsymbol {\xi} _ {t + j}}{\partial \mathbf {v} _ {t} ^ {\prime}} = \sum_ {j = 0} ^ {\infty} \beta^ {j} \mathbf {F} ^ {j} = (\mathbf {I} _ {p} - \beta \mathbf {F}) ^ {- 1}, \tag {1.2.46}
$$

provided that the eigenvalues of $\mathbf{F}$ are all less than $\beta^{-1}$ in modulus. The effect on the present value of $y$ of a change in $w$ ,

$$
\frac {\partial \sum_ {j = 0} ^ {\infty} \beta^ {j} y _ {t + j}}{\partial w _ {t}},
$$

is thus the $(1, 1)$ element of the $(p \times p)$ matrix in [1.2.46]. This value is given by the following proposition.

Proposition 1.3: If the eigenvalues of the $(p\times p)$ matrix $\mathbf{F}$ defined in [1.2.3] are all less than $\beta^{-1}$ in modulus, then the matrix $(\mathbf{I}_p - \beta \mathbf{F})^{-1}$ exists and the effect of $w$ on the present value of $y$ is given by its $(1,1)$ element:

$$
1 / (1 - \phi_ {1} \beta - \phi_ {2} \beta^ {2} - \dots - \phi_ {p - 1} \beta^ {p - 1} - \phi_ {p} \beta^ {p}).
$$

Note that Proposition 1.3 includes the earlier result for a first-order system (equation [1.1.14]) as a special case.

The cumulative effect of a one-time change in $w_{t}$ on $y_{t}, y_{t+1}, \ldots$ can be considered a special case of Proposition 1.3 with no discounting. Setting $\beta = 1$ in Proposition 1.3 shows that, provided the eigenvalues of $\mathbf{F}$ are all less than 1 in modulus, the cumulative effect of a one-time change in $w$ on $y$ is given by

$$
\sum_ {j = 0} ^ {\infty} \frac {\partial y _ {t + j}}{\partial w _ {t}} = 1 / (1 - \phi_ {1} - \phi_ {2} - \dots - \phi_ {p}). \tag {1.2.47}
$$

Notice again that [1.2.47] can alternatively be interpreted as giving the eventual long-run effect on $y$ of a permanent change in $w$ :

$$
\lim  _ {j \to \infty} \frac {\partial y _ {t + j}}{\partial w _ {t}} + \frac {\partial y _ {t + j}}{\partial w _ {t + 1}} + \frac {\partial y _ {t + j}}{\partial w _ {t + 2}} + \dots + \frac {\partial y _ {t + j}}{\partial w _ {t + j}} = 1 / (1 - \phi_ {1} - \phi_ {2} - \dots - \phi_ {p}).
$$

# APPENDIX 1.A. Proofs of Chapter 1 Propositions

Proof of Proposition 1.1. The eigenvalues of $\mathbf{F}$ satisfy

$$
\left| \mathbf {F} - \lambda \mathbf {I} _ {p} \right| = 0. \tag {1.A.1}
$$

For the matrix $\mathbf{F}$ defined in equation [1.2.3], this determinant would be

$$
\begin{array}{l} \left| \left[ \begin{array}{c c c c c c} \phi_ {1} & \phi_ {2} & \phi_ {3} & \dots & \phi_ {p - 1} & \phi_ {p} \\ 1 & 0 & 0 & \dots & 0 & 0 \\ 0 & 1 & 0 & \dots & 0 & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & 1 & 0 \end{array} \right] - \left[ \begin{array}{c c c c c c} \lambda & 0 & 0 & \dots & 0 & 0 \\ 0 & \lambda & 0 & \dots & 0 & 0 \\ 0 & 0 & \lambda & \dots & 0 & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & 0 & \lambda \end{array} \right] \right| \\ = \left| \begin{array}{c c c c c c} \left(\phi_ {1} - \lambda\right) & \phi_ {2} & \phi_ {3} & \dots & \phi_ {p - 1} & \phi_ {p} \\ 1 & - \lambda & 0 & \dots & 0 & 0 \\ 0 & 1 & - \lambda & \dots & 0 & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & 1 & - \lambda \end{array} \right|. \quad [ 1. A. 2 ] \\ \end{array}
$$

Recall that if we multiply a column of a matrix by a constant and add the result to another column, the determinant of the matrix is unchanged. If we multiply the $p$ th column of the matrix in [1.A.2] by $(1 / \lambda)$ and add the result to the $(p - 1)$ th column, the result is a matrix with the same determinant as that in [1.A.2]:

$$
\left| \mathbf {F} - \lambda \mathbf {I} _ {p} \right| = \left| \begin{array}{c c c c c c c} \phi_ {1} - \lambda & \phi_ {2} & \phi_ {3} & \dots & \phi_ {p - 2} & \phi_ {p - 1} + (\phi_ {p} / \lambda) & \phi_ {p} \\ 1 & - \lambda & 0 & \dots & 0 & 0 & 0 \\ 0 & 1 & - \lambda & \dots & 0 & 0 & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & 1 & - \lambda & 0 \\ 0 & 0 & 0 & \dots & 0 & 0 & - \lambda \end{array} \right|.
$$

Next, multiply the $(p - 1)$ th column by $(1 / \lambda)$ and add the result to the $(p - 2)$ th column: $|\mathbf{F} - \lambda \mathbf{I}_p|$

$$
= \left| \begin{array}{c c c c c c c c} \phi_ {1} - \lambda & \phi_ {2} & \phi_ {3} & \dots & \phi_ {p - 2} + \phi_ {p - 1} / \lambda + \phi_ {p} / \lambda^ {2} & \phi_ {p - 1} + \phi_ {p} / \lambda & \phi_ {p} \\ 1 & - \lambda & 0 & \dots & 0 & 0 & 0 \\ 0 & 1 & - \lambda & \dots & 0 & 0 & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & 0 & - \lambda & 0 \\ 0 & 0 & 0 & \dots & 0 & 0 & - \lambda \end{array} \right|.
$$

Continuing in this fashion shows [1.A.1] to be equivalent to the determinant of the following upper triangular matrix:

$$
\begin{array}{l} \left| \mathbf {F} - \lambda \mathbf {I} _ {p} \right| \\ = \left| \begin{array}{c c c c c} \phi_ {1} - \lambda + \phi_ {2} / \lambda + \phi_ {3} / \lambda^ {2} + \dots + \phi_ {p} / \lambda^ {p - 1} & \phi_ {2} + \phi_ {3} / \lambda + \phi_ {4} / \lambda^ {2} + \dots + \phi_ {p} / \lambda^ {p - 2} & \dots & \phi_ {p - 1} + \phi_ {p} / \lambda & \phi_ {p} \\ 0 & - \lambda & \dots & 0 & 0 \\ 0 & 0 & \dots & 0 & 0 \\ \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & \dots & - \lambda & 0 \\ 0 & 0 & \dots & 0 & - \lambda \end{array} \right| \\ \end{array}
$$

But the determinant of an upper triangular matrix is simply the product of the terms along the principal diagonal:

$$
\begin{array}{l} \left| \mathbf {F} - \lambda \mathbf {I} _ {p} \right| = \left[ \phi_ {1} - \lambda + \phi_ {2} / \lambda + \phi_ {3} / \lambda^ {2} + \dots + \phi_ {p} / \lambda^ {p - 1} \right] \cdot [ - \lambda ] ^ {p - 1} \tag {1.A.3} \\ = (- 1) ^ {p} \cdot \left[ \lambda^ {p} - \phi_ {1} \lambda^ {p - 1} - \phi_ {2} \lambda^ {p - 2} - \dots - \phi_ {p} \right]. \\ \end{array}
$$

The eigenvalues of $\mathbf{F}$ are thus the values of $\lambda$ for which [1.A.3] is zero, or for which

$$
\lambda^ {p} - \phi_ {1} \lambda^ {p - 1} - \phi_ {2} \lambda^ {p - 2} - \dots - \phi_ {p} = 0,
$$

as asserted in Proposition 1.1.

Proof of Proposition 1.2. Assuming that the eigenvalues $(\lambda_1, \lambda_2, \ldots, \lambda_p)$ are distinct, the matrix $\mathbf{T}$ in equation [1.2.17] can be constructed from the eigenvectors of $\mathbf{F}$ . Let $\mathbf{t}_i$ denote the following $(p \times 1)$ vector,

$$
\mathbf {t} _ {i} = \left[ \begin{array}{c} \lambda_ {i} ^ {p - 1} \\ \lambda_ {i} ^ {p - 2} \\ \lambda_ {i} ^ {p - 3} \\ \vdots \\ \lambda_ {i} ^ {1} \\ 1 \end{array} \right], \tag {1.A.4}
$$

where $\lambda_{i}$ denotes the $i$ th eigenvalue of $\mathbf{F}$ . Notice

$$
\begin{array}{l} \mathbf {F} \mathbf {t} _ {i} = \left[ \begin{array}{c c c c c c} \phi_ {1} & \phi_ {2} & \phi_ {3} & \dots & \phi_ {p - 1} & \phi_ {p} \\ 1 & 0 & 0 & \dots & 0 & 0 \\ 0 & 1 & 0 & \dots & 0 & 0 \\ \vdots & \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & 0 & \dots & 1 & 0 \end{array} \right] \left[ \begin{array}{c} \lambda_ {i} ^ {p - 1} \\ \lambda_ {i} ^ {p - 2} \\ \lambda_ {i} ^ {p - 3} \\ \vdots \\ \vdots \\ \lambda_ {i} ^ {1} \\ 1 \end{array} \right] \tag {1.A.5} \\ = \left[ \begin{array}{c} \phi_ {1} \lambda_ {i} ^ {p - 1} + \phi_ {2} \lambda_ {i} ^ {p - 2} + \phi_ {3} \lambda_ {i} ^ {p - 3} + \dots + \phi_ {p - 1} \lambda_ {i} + \phi_ {p} \\ \lambda_ {i} ^ {p - 1} \\ \lambda_ {i} ^ {p - 2} \\ \vdots \\ \lambda_ {i} ^ {2} \\ \lambda_ {i} \end{array} \right]. \\ \end{array}
$$

Since $\lambda_{i}$ is an eigenvalue of $\mathbf{F}$ , it satisfies [1.2.16]:

$$
\lambda_ {i} ^ {p} - \phi_ {1} \lambda_ {i} ^ {p - 1} - \phi_ {2} \lambda_ {i} ^ {p - 2} - \dots - \phi_ {p - 1} \lambda_ {i} - \phi_ {p} = 0. \tag {1.A.6}
$$

Substituting [1.A.6] into [1.A.5] reveals

$$
\mathbf {F t} _ {i} = \left[ \begin{array}{c} \lambda_ {i} ^ {p} \\ \lambda_ {i} ^ {p - 1} \\ \lambda_ {i} ^ {p - 2} \\ \vdots \\ \lambda_ {i} ^ {2} \\ \lambda_ {i} \end{array} \right] = \lambda_ {i} \left[ \begin{array}{c} \lambda_ {i} ^ {p - 1} \\ \lambda_ {i} ^ {p - 2} \\ \lambda_ {i} ^ {p - 3} \\ \vdots \\ \lambda_ {i} ^ {1} \\ 1 \end{array} \right]
$$

or

$$
\mathbf {F} \mathbf {t} _ {i} = \lambda_ {i} \mathbf {t} _ {i}. \tag {1.A.7}
$$

Thus $\mathbf{t}_i$ is an eigenvector of $\mathbf{F}$ associated with the eigenvalue $\lambda_i$ .

We can calculate the matrix $\mathbf{T}$ by combining the eigenvectors $(\mathbf{t}_1, \mathbf{t}_2, \ldots, \mathbf{t}_p)$ into a $(p \times p)$ matrix

$$
\mathbf {T} = \left[ \begin{array}{l l l l} \mathbf {t} _ {1} & \mathbf {t} _ {2} & \dots & \mathbf {t} _ {p} \end{array} \right]. \tag {1.A.8}
$$

To calculate the particular values for $c_{i}$ in equation [1.2.21], recall that $\mathbf{T}^{-1}$ is characterized by

$$
\mathbf {T} \mathbf {T} ^ {- 1} = \mathbf {I} _ {p}, \tag {1.A.9}
$$

where $\mathbf{T}$ is given by [1.A.4] and [1.A.8]. Writing out the first column of the matrix system of equations [1.A.9] explicitly, we have

$$
\left[ \begin{array}{c c c c} \lambda_ {1} ^ {p - 1} & \lambda_ {2} ^ {p - 1} & \dots & \lambda_ {p} ^ {p - 1} \\ \lambda_ {1} ^ {p - 2} & \lambda_ {2} ^ {p - 2} & \dots & \lambda_ {p} ^ {p - 2} \\ \lambda_ {1} ^ {p - 3} & \lambda_ {2} ^ {p - 3} & \dots & \lambda_ {p} ^ {p - 3} \\ \vdots & \vdots & \dots & \vdots \\ \lambda_ {1} ^ {1} & \lambda_ {2} ^ {1} & \dots & \lambda_ {p} ^ {1} \\ 1 & 1 & \dots & 1 \end{array} \right] \left[ \begin{array}{c} t ^ {1 1} \\ t ^ {2 1} \\ t ^ {3 1} \\ \vdots \\ t ^ {p - 1, 1} \\ t ^ {p 1} \end{array} \right] = \left[ \begin{array}{c} 1 \\ 0 \\ 0 \\ \vdots \\ 0 \\ 0 \end{array} \right].
$$

This gives a system of $p$ linear equations in the $p$ unknowns $(t^{11}, t^{21}, \ldots, t^{p1})$ . Provided that the $\lambda_i$ are all distinct, the solution can be shown to be<sup>9</sup>

$$
t ^ {1 1} = \frac {1}{\left(\lambda_ {1} - \lambda_ {2}\right) \left(\lambda_ {1} - \lambda_ {3}\right) \cdots \left(\lambda_ {1} - \lambda_ {p}\right)}
$$

$$
t ^ {2 1} = \frac {1}{\left(\lambda_ {2} - \lambda_ {1}\right) \left(\lambda_ {2} - \lambda_ {3}\right) \cdots \left(\lambda_ {2} - \lambda_ {p}\right)}
$$

![](images/04768382ae70497b40dff5f64772eb84dcc6cb46a235584706e714af682b2597.jpg)

$$
t ^ {p 1} = \frac {1}{\left(\lambda_ {p} - \lambda_ {1}\right) \left(\lambda_ {p} - \lambda_ {2}\right) \cdots \left(\lambda_ {p} - \lambda_ {p - 1}\right)}.
$$

Substituting these values into [1.2.21] gives equation [1.2.25].

Proof of Proposition 1.3. The first claim in this proposition is that if the eigenvalues of $\mathbf{F}$ are less than $\beta^{-1}$ in modulus, then the inverse of $(\mathbf{I}_p - \beta \mathbf{F})$ exists. Suppose the inverse of $(\mathbf{I}_p - \beta \mathbf{F})$ did not exist. Then the determinant $|\mathbf{I}_p - \beta \mathbf{F}|$ would have to be zero. But

$$
\left| \mathbf {I} _ {p} - \beta \mathbf {F} \right| = | - \boldsymbol {\beta} \cdot \left[ \mathbf {F} - \boldsymbol {\beta} ^ {- 1} \mathbf {I} _ {p} \right] | = (- \boldsymbol {\beta}) ^ {p} \left| \mathbf {F} - \boldsymbol {\beta} ^ {- 1} \mathbf {I} _ {p} \right|,
$$

so that $|\mathbf{F} - \beta^{-1}\mathbf{I}_p|$ would have to be zero whenever the inverse of $(\mathbf{I}_p - \beta \mathbf{F})$ fails to exist. But this would mean that $\beta^{-1}$ is an eigenvalue of $\mathbf{F}$ , which is ruled out by the assumption that all eigenvalues of $\mathbf{F}$ are strictly less than $\beta^{-1}$ in modulus. Thus, the matrix $\mathbf{I}_p - \beta \mathbf{F}$ must be nonsingular.

Since $\left[\mathbf{I}_p - \beta \mathbf{F}\right]^{-1}$ exists, it satisfies the equation

$$
\left[ \mathbf {I} _ {p} - \beta \mathbf {F} \right] ^ {- 1} \left[ \mathbf {I} _ {p} - \beta \mathbf {F} \right] = \mathbf {I} _ {p}. \tag {1.A.10}
$$

Let $x_{ij}$ denote the row $i$ , column $j$ element of $[\mathbf{I}_p - \beta \mathbf{F}]^{-1}$ , and write [1.A.10] as

$$
\begin{array}{l} \left[ \begin{array}{c c c c} x _ {1 1} & x _ {1 2} & \dots & x _ {1 p} \\ x _ {2 1} & x _ {2 2} & \dots & x _ {2 p} \\ \vdots & \vdots & \dots & \vdots \\ x _ {p 1} & x _ {p 2} & \dots & x _ {p p} \end{array} \right] \left[ \begin{array}{c c c c c} 1 - \beta \phi_ {1} & - \beta \phi_ {2} & \dots & - \beta \phi_ {p - 1} & - \beta \phi_ {p} \\ - \beta & 1 & \dots & 0 & 0 \\ \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & \dots & - \beta & 1 \end{array} \right] \tag {1.A.11} \\ = \left[ \begin{array}{c c c c} 1 & 0 & \dots & 0 \\ 0 & 1 & \dots & 0 \\ \vdots & \vdots & \dots & \vdots \\ 0 & 0 & \dots & 1 \end{array} \right]. \\ \end{array}
$$

The task is then to find the $(1,1)$ element of $[\mathbf{I}_p - \beta \mathbf{F}]^{\prime}$ , that is, to find the value of $x_{11}$ . To do this we need only consider the first row of equations in [1.A.11]:

$$
\begin{array}{l} \left[ \begin{array}{l l l l} x _ {1 1} & x _ {1 2} & \dots & x _ {1 p} \end{array} \right] \left[ \begin{array}{c c c c c} 1 - \beta \phi_ {1} & - \beta \phi_ {2} & \dots & - \beta \phi_ {p - 1} & - \beta \phi_ {p} \\ - \beta & 1 & \dots & 0 & 0 \\ \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & \dots & - \beta & 1 \end{array} \right] \\ = \left[ \begin{array}{l l l l l} 1 & 0 & \dots & 0 & 0 \end{array} \right]. \quad [ 1. A. 1 2 ] \\ \end{array}
$$

9See Lemma 2 of Chiang (1980, p. 144).

Consider postmultiplying this system of equations by a matrix with 1s along the principal diagonal, $\beta$ in the row $p$ , column $p - 1$ position, and 0s elsewhere:

$$
\left[ \begin{array}{c c c c c} 1 & 0 & \dots & 0 & 0 \\ 0 & 1 & \dots & 0 & 0 \\ \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & \dots & \beta & 1 \end{array} \right].
$$

The effect of this operation is to multiply the $p$ th column of a matrix by $\beta$ and add the result to the $(p - 1)$ th column:

$$
\left[ \begin{array}{l l} x _ {1 1} & x _ {1 2} \dots x _ {1 p} \end{array} \right] \left[ \begin{array}{c c c c c} 1 - \beta \phi_ {1} & - \beta \phi_ {2} & \dots & - \beta \phi_ {p - 1} - \beta^ {2} \phi_ {p} & - \beta \phi_ {p} \\ - \beta & 1 & \dots & 0 & 0 \\ \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & \dots & 0 & 1 \end{array} \right] = \left[ \begin{array}{l l l l} 1 & 0 \cdot \cdot \cdot 0 & 0 \end{array} \right].
$$

Next multiply the $(p - 1)$ th column by $\beta$ and add the result to the $(p - 2)$ th column. Proceeding in this fashion, we arrive at

$$
\left[ \begin{array}{c c c c} x _ {1 1} & x _ {1 2} & \dots & x _ {1 p} \end{array} \right] \times
$$

$$
\begin{array}{l} \left[ \begin{array}{c c c c c} 1 - \beta \phi_ {1} - \beta^ {2} \phi_ {2} - \dots - \beta^ {p - 1} \phi_ {p - 1} - \beta^ {p} \phi_ {p} & - \beta \phi_ {2} - \beta^ {2} \phi_ {3} - \dots - \beta^ {p - 1} \phi_ {p} & \dots & - \beta \phi_ {p - 1} - \beta^ {2} \phi_ {p} & - \beta \phi_ {p} \\ 0 & 1 & \dots & 0 & 0 \\ \vdots & \vdots & \dots & \vdots & \vdots \\ 0 & 0 & \dots & 0 & 1 \end{array} \right] \\ = \left[ \begin{array}{c c c c c} 1 & 0 & \dots & 0 & 0 \end{array} \right]. \quad [ 1. A. 1 3 ] \\ \end{array}
$$

The first equation in [1.A.13] states that

$$
x _ {1 1} \cdot \left(1 - \beta \phi_ {1} - \beta^ {2} \phi_ {2} - \dots - \beta^ {p - 1} \phi_ {p - 1} - \beta^ {p} \phi_ {p}\right) = 1
$$

or

$$
x _ {1 1} = 1 / \left(1 - \beta \phi_ {1} - \beta^ {2} \phi_ {2} - \dots - \beta^ {p} \phi_ {p}\right),
$$

as claimed in Proposition 1.3.

# Chapter 1 References

Chiang, Chin Long. 1980. An Introduction to Stochastic Processes and Their Applications. Huntington, N.Y.: Krieger.

Goldfeld, Stephen M. 1973. "The Demand for Money Revisited," Brookings Papers on Economic Activity 3:577-638.

Sargent, Thomas J. 1987. *Macroeconomic Theory*, 2d ed. Boston: Academic Press.

# 2 Lag Operators

# 2.1. Introduction

The previous chapter analyzed the dynamics of linear difference equations using matrix algebra. This chapter develops some of the same results using time series operators. We begin with some introductory remarks on some useful time series operators.

A time series is a collection of observations indexed by the date of each observation. Usually we have collected data beginning at some particular date (say, $t = 1$ ) and ending at another (say, $t = T$ ):

$$
\left(y _ {1}, y _ {2}, \dots , y _ {T}\right).
$$

We often imagine that we could have obtained earlier observations $(y_0, y_{-1}, y_{-2}, \ldots)$ or later observations $(y_{T+1}, y_{T+2}, \ldots)$ had the process been observed for more time. The observed sample $(y_1, y_2, \ldots, y_T)$ could then be viewed as a finite segment of a doubly infinite sequence, denoted $\{y_t\}_{t= -\infty}$ :

$$
\{y _ {t} \} _ {t = - \infty} ^ {\infty} = \{\dots , y _ {- 1}, y _ {0}, \underbrace {y _ {1} , y _ {2} , \dots , y _ {T}} _ {\text {o b s e r v e d s a m p l e}}, y _ {T + 1}, y _ {T + 2}, \dots \}.
$$

Typically, a time series $\{y_{t}\}_{t = -\infty}^{\infty}$ is identified by describing the $t$ th element. For example, a time trend is a series whose value at date $t$ is simply the date of the observation:

$$
y _ {t} = t.
$$

We could also consider a time series in which each element is equal to a constant $c$ , regardless of the date of the observation $t$ :

$$
y _ {t} = c.
$$

Another important time series is a Gaussian white noise process, denoted

$$
y _ {t} = \varepsilon_ {t},
$$

where $\{\varepsilon_{t} \}_{t = -\infty}^{\infty}$ is a sequence of independent random variables each of which has a $N(0, \sigma^2)$ distribution.

We are used to thinking of a function such as $y = f(x)$ or $y = g(x, w)$ as an operation that accepts as input a number $(x)$ or group of numbers $(x, w)$ and produces the output $(y)$ . A time series operator transforms one time series or group

of time series into a new time series. It accepts as input a sequence such as $\{x_{t}\}_{t = -\infty}^{\infty}$ or a group of sequences such as $(\{x_{t}\}_{t = -\infty},\{w_{t}\}_{t = -\infty})$ and has as output a new sequence $\{y_{t}\}_{t = -\infty}^{\infty}$ . Again, the operator is summarized by describing the value of a typical element of $\{y_t\}_{t = -\infty}^{\infty}$ in terms of the corresponding elements of $\{x_{t}\}_{t = -\infty}^{\infty}$ .

An example of a time series operator is the multiplication operator, represented as

$$
y _ {t} = \beta x _ {t}. \tag {2.1.1}
$$

Although it is written exactly the same way as simple scalar multiplication, equation [2.1.1] is actually shorthand for an infinite sequence of multiplications, one for each date $t$ . The operator multiplies the value $x$ takes on at any date $t$ by some constant $\beta$ to generate the value of $y$ for that date.

Another example of a time series operator is the addition operator:

$$
y _ {t} = x _ {t} + w _ {t}.
$$

Here the value of $y$ at any date $t$ is the sum of the values that $x$ and $w$ take on for that date.

Since the multiplication or addition operators amount to element-by-element multiplication or addition, they obey all the standard rules of algebra. For example, if we multiply each observation of $\{x_{t}\}_{t = -\infty}^{\infty}$ by $\beta$ and each observation of $\{w_{t}\}_{t = -\infty}^{\infty}$ by $\beta$ and add the results,

$$
\beta x _ {t} + \beta w _ {t},
$$

the outcome is the same as if we had first added $\{x_{t}\}_{t = -\infty}^{\infty}$ to $\{w_t\}_{t = -\infty}^{\infty}$ and then multiplied each element of the resulting series by $\beta$

$$
\beta \left(x _ {t} + w _ {t}\right).
$$

A highly useful operator is the lag operator. Suppose that we start with a sequence $\{x_{t}\}_{t = -\infty}^{\infty}$ and generate a new sequence $\{y_{t}\}_{t = -\infty}^{\infty}$ , where the value of $y$ for date $t$ is equal to the value $x$ took on at date $t - 1$ :

$$
y _ {t} = x _ {t - 1}. \tag {2.1.2}
$$

This is described as applying the lag operator to $\{x_{t}\}_{t = -\infty}^{\infty}$ . The operation is represented by the symbol $L$ :

$$
L x _ {t} \equiv x _ {t - 1}. \tag {2.1.3}
$$

Consider the result of applying the lag operator twice to a series:

$$
L \left(L x _ {t}\right) = L \left(x _ {t - 1}\right) = x _ {t - 2}.
$$

Such a double application of the lag operator is indicated by $L^2$ :

$$
L ^ {2} x _ {t} = x _ {t - 2}.
$$

In general, for any integer $k$ ,

$$
L ^ {k} x _ {t} = x _ {t - k}. \tag {2.1.4}
$$

Notice that if we first apply the multiplication operator and then the lag operator, as in

$$
x _ {t} \rightarrow \beta x _ {t} \rightarrow \beta x _ {t - 1},
$$

the result will be exactly the same as if we had applied the lag operator first and then the multiplication operator:

$$
x _ {t} \rightarrow x _ {t - 1} \rightarrow \beta x _ {t - 1}.
$$

Thus the lag operator and multiplication operator are commutative:

$$
L \left(\beta x _ {t}\right) = \beta \cdot L x _ {t}.
$$

Similarly, if we first add two series and then apply the lag operator to the result,

$$
\left(x _ {t}, w _ {t}\right)\rightarrow x _ {t} + w _ {t} \rightarrow x _ {t - 1} + w _ {t - 1},
$$

the result is the same as if we had applied the lag operator before adding:

$$
\left(x _ {t}, w _ {t}\right)\rightarrow \left(x _ {t - 1}, w _ {t - 1}\right)\rightarrow x _ {t - 1} + w _ {t - 1}.
$$

Thus, the lag operator is distributive over the addition operator:

$$
L \left(x _ {t} + w _ {t}\right) = L x _ {t} + L w _ {t}.
$$

We thus see that the lag operator follows exactly the same algebraic rules as the multiplication operator. For this reason, it is tempting to use the expression "multiply $y_{t}$ by $L$ " rather than "operate on $\{y_{t}\}_{t = -\infty}^{\infty}$ by $L$ ." Although the latter expression is technically more correct, this text will often use the former shorthand expression to facilitate the exposition.

Faced with a time series defined in terms of compound operators, we are free to use the standard commutative, associative, and distributive algebraic laws for multiplication and addition to express the compound operator in an alternative form. For example, the process defined by

$$
y _ {t} = (a + b L) L x _ {t}
$$

is exactly the same as

$$
y _ {t} = \left(a L + b L ^ {2}\right) x _ {t} = a x _ {t - 1} + b x _ {t - 2}.
$$

To take another example,

$$
\begin{array}{l} (1 - \lambda_ {1} L) (1 - \lambda_ {2} L) x _ {t} = (1 - \lambda_ {1} L - \lambda_ {2} L + \lambda_ {1} \lambda_ {2} L ^ {2}) x _ {t} \\ = \left(1 - \left[ \lambda_ {1} + \lambda_ {2} \right] L + \lambda_ {1} \lambda_ {2} L ^ {2}\right) x _ {t} \tag {2.1.5} \\ = x _ {t} - \left(\lambda_ {1} + \lambda_ {2}\right) x _ {t - 1} + \left(\lambda_ {1} \lambda_ {2}\right) x _ {t - 2}. \\ \end{array}
$$

An expression such as $(aL + bL^2)$ is referred to as a polynomial in the lag operator. It is algebraically similar to a simple polynomial $(az + bz^2)$ where $z$ is a scalar. The difference is that the simple polynomial $(az + bz^2)$ refers to a particular number, whereas a polynomial in the lag operator $(aL + bL^2)$ refers to an operator that would be applied to one time series $\{x_{t}\}_{t = -\infty}^{\infty}$ to produce a new time series $\{y_t\}_{t = -\infty}^{\infty}$ .

Notice that if $\{x_{t|t = -\infty}^{\mathrm{X}}$ is just a series of constants,

$$
x _ {t} = c \quad \text {f o r a l l} t,
$$

then the lag operator applied to $x_{t}$ produces the same series of constants:

$$
L x _ {t} = x _ {t - 1} = c.
$$

Thus, for example,

$$
\left(\alpha L + \beta L ^ {2} + \gamma L ^ {3}\right) c = (\alpha + \beta + \gamma) \cdot c. \tag {2.1.6}
$$

# 2.2. First-Order Difference Equations

Let us now return to the first-order difference equation analyzed in Section 1.1:

$$
y _ {t} = \phi y _ {t - 1} + w _ {t}. \tag {2.2.1}
$$

Equation [2.2.1] can be rewritten using the lag operator [2.1.3] as

$$
y _ {t} = \phi L y _ {t} + w _ {t}.
$$

This equation, in turn, can be rearranged using standard algebra,

$$
y _ {t} - \phi L y _ {t} = w _ {t},
$$

or

$$
(1 - \phi L) y _ {t} = w _ {t}. \tag {2.2.2}
$$

Next consider "multiplying" both sides of [2.2.2] by the following operator:

$$
(1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {\prime} L ^ {\prime}). \tag {2.2.3}
$$

The result would be

$$
\begin{array}{l} (1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {\prime} L ^ {\prime}) (1 - \phi L) y _ {t} \\ = (1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {t} L ^ {t}) w _ {t}. \tag {2.2.4} \\ \end{array}
$$

Expanding out the compound operator on the left side of [2.2.4] results in

$$
\begin{array}{l} (1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {\prime} L ^ {\prime}) (1 - \phi L) \\ = \left(1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {\prime} L ^ {\prime}\right) \\ - \left(1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {t} L ^ {t}\right) \phi L \\ = \left(1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {\prime} L ^ {\prime}\right) \\ - \left(\phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {\prime} L ^ {\prime} + \phi^ {\prime + 1} L ^ {\prime + 1}\right) \\ = \left(1 - \phi^ {t + 1} L ^ {t + 1}\right). \\ \end{array}
$$

Substituting [2.2.5] into [2.2.4] yields

$$
\left(1 - \phi^ {t + 1} L ^ {t + 1}\right) y _ {t} = \left(1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {t} L ^ {t}\right) w _ {t}. \quad [ 2. 2. 6 ]
$$

Writing [2.2.6] out explicitly using [2.1.4] produces

$$
y _ {t} - \phi^ {t + 1} y _ {t - (t + 1)} = w _ {t} + \phi w _ {t - 1} + \phi^ {2} w _ {t - 2} + \phi^ {3} w _ {t - 3} + \dots + \phi^ {t} w _ {t - t}
$$

or

$$
y _ {t} = \phi^ {t + 1} y _ {- 1} + w _ {t} + \phi w _ {t - 1} + \phi^ {2} w _ {t - 2} + \phi^ {3} w _ {t - 3} + \dots + \phi^ {\prime} w _ {0}. \tag {2.2.7}
$$

Notice that equation [2.2.7] is identical to equation [1.1.7]. Applying the operator [2.2.3] is performing exactly the same set of recursive substitutions that were employed in the previous chapter to arrive at [1.1.7].

It is interesting to reflect on the nature of the operator [2.2.3] as $t$ becomes large. We saw in [2.2.5] that

$$
(1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {\prime} L ^ {\prime}) (1 - \phi L) y _ {t} = y _ {t} - \phi^ {t + 1} y _ {- 1}.
$$

That is, $(1 + \phi L + \phi^2 L^2 + \phi^3 L^3 + \dots + \phi' L') (1 - \phi L) y_t$ differs from $y_t$ by the term $\phi^{t+1} y_{-1}$ . If $|\phi| < 1$ and if $y_{-1}$ is a finite number, this residual $\phi'^{t+1} y_{-1}$ will become negligible as $t$ becomes large:

$$
(1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {\prime} L ^ {\prime}) (1 - \phi L) y _ {t} \cong y _ {t} \quad \text {f o r} t \text {l a r g e}.
$$

A sequence $\{y_t\}_{t = -\infty}^{\infty}$ is said to be bounded if there exists a finite number $\overline{y}$ such that

$$
\left| y _ {t} \right| <   \bar {y} \quad \text {f o r a l l} t.
$$

Thus, when $|\phi| < 1$ and when we are considering applying an operator to a bounded sequence, we can think of

$$
\left(1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {j} L ^ {j}\right)
$$

as approximating the inverse of the operator $(1 - \phi L)$ , with this approximation made arbitrarily accurate by choosing $j$ sufficiently large:

$$
\left(1 - \phi L\right) ^ {- 1} = \lim  _ {j \rightarrow \infty} \left(1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots + \phi^ {j} L ^ {j}\right). \quad [ 2. 2. 8 ]
$$

This operator $(1 - \phi L)^{-1}$ has the property

$$
(1 - \phi L) ^ {- 1} (1 - \phi L) = 1,
$$

where "1" denotes the identity operator:

$$
1 y _ {t} = y _ {t}.
$$

The following chapter discusses stochastic sequences rather than the deterministic sequences studied here. There we will speak of mean square convergence and stationary stochastic processes in place of limits of bounded deterministic sequences, though the practical meaning of [2.2.8] will be little changed.

Provided that $|\phi| < 1$ and we restrict ourselves to bounded sequences or stationary stochastic processes, both sides of [2.2.2] can be "divided" by $(1 - \phi L)$ to obtain

$$
y _ {t} = (1 - \phi L) ^ {- 1} w _ {t}
$$

or

$$
y _ {t} = w _ {t} + \phi w _ {t - 1} + \phi^ {2} w _ {t - 2} + \phi^ {3} w _ {t - 3} + \dots . \tag {2.2.9}
$$

It should be emphasized that if we were not restricted to considering bounded sequences or stationary stochastic processes $\{w_{t} \}_{t = -\infty}^{\infty}$ and $\{y_t \}_{t = -\infty}^{\infty}$ , then expression [2.2.9] would not be a necessary implication of [2.2.1]. Equation [2.2.9] is consistent with [2.2.1], but adding a term $a_{o} \phi^{t}$ ,

$$
y _ {t} = a _ {o} \phi^ {t} + w _ {t} + \phi w _ {t - 1} + \phi^ {2} w _ {t - 2} + \phi^ {3} w _ {t - 3} + \dots , \tag {2.2.10}
$$

produces another series consistent with [2.2.1] for any constant $a_{o}$ . To verify that [2.2.10] is consistent with [2.2.1], multiply [2.2.10] by $(1 - \phi L)$ :

$$
\begin{array}{l} (1 - \phi L) y _ {t} = (1 - \phi L) a _ {o} \phi^ {\prime} + (1 - \phi L) (1 - \phi L) ^ {- 1} w _ {t} \\ = a _ {o} \phi^ {t} - \phi \cdot a _ {o} \phi^ {t - 1} + w _ {t} \\ = w _ {t}, \\ \end{array}
$$

so that [2.2.10] is consistent with [2.2.1] for any constant $a_{o}$ .

Although any process of the form of [2.2.10] is consistent with the difference equation [2.2.1], notice that since $|\phi| < 1$ ,

$$
\left| a _ {o} \phi^ {t} \right|\rightarrow \infty \quad \text {a s} \quad t \rightarrow - \infty .
$$

Thus, even if $\{w_{t}\}_{t = -\infty}^{\infty}$ is a bounded sequence, the solution $\{y_{t}\}_{t = -\infty}^{\infty}$ given by [2.2.10] is unbounded unless $a_{o} = 0$ in [2.2.10]. Thus, there was a particular reason for defining the operator [2.2.8] to be the inverse of $(1 - \phi L)$ —namely, $(1 - \phi L)^{-1}$ defined in [2.2.8] is the unique operator satisfying

$$
(1 - \phi L) ^ {- 1} (1 - \phi L) = 1
$$

that maps a bounded sequence $\{w_{t}\}_{t = -\infty}^{\infty}$ into a bounded sequence $\{y_t\}_{t = -\infty}^x$

The nature of $(1 - \phi L)^{-1}$ when $|\phi| \geq 1$ will be discussed in Section 2.5.

# 2.3. Second-Order Difference Equations

Consider next a second-order difference equation:

$$
y _ {t} = \phi_ {1} y _ {t - 1} + \phi_ {2} y _ {t - 2} + w _ {t}. \tag {2.3.1}
$$

Rewriting this in lag operator form produces

$$
(1 - \phi_ {1} L - \phi_ {2} L ^ {2}) y _ {t} = w _ {t}. \tag {2.3.2}
$$

The left side of [2.3.2] contains a second-order polynomial in the lag operator $L$ . Suppose we factor this polynomial, that is, find numbers $\lambda_{1}$ and $\lambda_{2}$ such that

$$
\left(1 - \phi_ {1} L - \phi_ {2} L ^ {2}\right) = \left(1 - \lambda_ {1} L\right) \left(1 - \lambda_ {2} L\right) = \left(1 - \left[ \lambda_ {1} + \lambda_ {2} \right] L + \lambda_ {1} \lambda_ {2} L ^ {2}\right). \tag {2.3.3}
$$

This is just the operation in [2.1.5] in reverse. Given values for $\phi_1$ and $\phi_2$ , we seek numbers $\lambda_1$ and $\lambda_2$ with the properties that

$$
\lambda_ {1} + \lambda_ {2} = \phi_ {1}
$$

and

$$
\lambda_ {1} \lambda_ {2} = - \phi_ {2}.
$$

For example, if $\phi_1 = 0.6$ and $\phi_2 = -0.08$ , then we should choose $\lambda_1 = 0.4$ and $\lambda_2 = 0.2$ :

$$
(1 - 0. 6 L + 0. 0 8 L ^ {2}) = (1 - 0. 4 L) (1 - 0. 2 L). \tag {2.3.4}
$$

It is easy enough to see that these values of $\lambda_{1}$ and $\lambda_{2}$ work for this numerical example, but how are $\lambda_{1}$ and $\lambda_{2}$ found in general? The task is to choose $\lambda_{1}$ and $\lambda_{2}$ so as to make sure that the operator on the right side of [2.3.3] is identical to that on the left side. This will be true whenever the following represent the identical functions of $z$ :

$$
\left(1 - \phi_ {1} z - \phi_ {2} z ^ {2}\right) = \left(1 - \lambda_ {1} z\right) \left(1 - \lambda_ {2} z\right). \tag {2.3.5}
$$

This equation simply replaces the lag operator $L$ in [2.3.3] with a scalar $z$ . What is the point of doing so? With [2.3.5], we can now ask, For what values of $z$ is the right side of [2.3.5] equal to zero? The answer is, if either $z = \lambda_1^{-1}$ or $z = \lambda_2^{-1}$ , then the right side of [2.3.5] would be zero. It would not have made sense to ask an analogous question of [2.3.3]— $L$ denotes a particular operator, not a number, and $L = \lambda_1^{-1}$ is not a sensible statement.

Why should we care that the right side of [2.3.5] is zero if $z = \lambda_1^{-1}$ or if $z = \lambda_2^{-1}$ ? Recall that the goal was to choose $\lambda_1$ and $\lambda_2$ so that the two sides of [2.3.5] represented the identical polynomial in $z$ . This means that for any particular value $z$ the two functions must produce the same number. If we find a value of $z$ that sets the right side to zero, that same value of $z$ must set the left side to zero as well. But the values of $z$ that set the left side to zero,

$$
(1 - \phi_ {1} z - \phi_ {2} z ^ {2}) = 0, \tag {2.3.6}
$$

are given by the quadratic formula:

$$
z _ {1} = \frac {\phi_ {1} - \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}}}{- 2 \phi_ {2}} \tag {2.3.7}
$$

$$
z _ {2} = \frac {\phi_ {1} + \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}}}{- 2 \phi_ {2}}. \tag {2.3.8}
$$

Setting $z = z_{1}$ or $z_{2}$ makes the left side of [2.3.5] zero, while $z = \lambda_{1}^{-1}$ or $\lambda_{2}^{-1}$ sets the right side of [2.3.5] to zero. Thus

$$
\lambda_ {1} ^ {- 1} = z _ {1} \tag {2.3.9}
$$

$$
\lambda_ {2} ^ {- 1} = z _ {2}. \tag {2.3.10}
$$

Returning to the numerical example [2.3.4] in which $\phi_1 = 0.6$ and $\phi_2 = -0.08$ , we would calculate

$$
z _ {1} = \frac {0 . 6 - \sqrt {(0 . 6) ^ {2} - 4 (0 . 0 8)}}{2 (0 . 0 8)} = 2. 5
$$

$$
z _ {2} = \frac {0 . 6 + \sqrt {(0 . 6) ^ {2} - 4 (0 . 0 8)}}{2 (0 . 0 8)} = 5. 0,
$$

and so

$$
\lambda_ {1} = 1 / (2. 5) = 0. 4
$$

$$
\lambda_ {2} = 1 / (5. 0) = 0. 2,
$$

as was found in [2.3.4].

When $\phi_1^2 + 4\phi_2 < 0$ , the values $z_1$ and $z_2$ are complex conjugates, and their reciprocals $\lambda_1$ and $\lambda_2$ can be found by first writing the complex number in polar coordinate form. Specifically, write

$$
z _ {1} = a + b i
$$

as

$$
z _ {1} = R \cdot [ \cos (\theta) + i \cdot \sin (\theta) ] = R \cdot e ^ {i \theta}.
$$

Then

$$
z _ {1} ^ {- 1} = R ^ {- 1} \cdot e ^ {- i \theta} = R ^ {- 1} \cdot [ \cos (\theta) - i \cdot \sin (\theta) ].
$$

Actually, there is a more direct method for calculating the values of $\lambda_{1}$ and $\lambda_{2}$ from $\phi_{1}$ and $\phi_{2}$ . Divide both sides of [2.3.5] by $z^{2}$ :

$$
\left(z ^ {- 2} - \phi_ {1} z ^ {- 1} - \phi_ {2}\right) = \left(z ^ {- 1} - \lambda_ {1}\right) \left(z ^ {- 1} - \lambda_ {2}\right) \tag {2.3.11}
$$

and define $\lambda$ to be the variable $z^{-1}$ :

$$
\lambda \equiv z ^ {- 1}. \tag {2.3.12}
$$

Substituting [2.3.12] into [2.3.11] produces

$$
\left(\lambda^ {2} - \phi_ {1} \lambda - \phi_ {2}\right) = (\lambda - \lambda_ {1}) (\lambda - \lambda_ {2}). \tag {2.3.13}
$$

Again, [2.3.13] must hold for all values of $\lambda$ in order for the two sides of [2.3.5] to represent the same polynomial. The values of $\lambda$ that set the right side to zero are $\lambda = \lambda_{1}$ and $\lambda = \lambda_{2}$ . These same values must set the left side of [2.3.13] to zero as well:

$$
\left(\lambda^ {2} - \phi_ {1} \lambda - \phi_ {2}\right) = 0. \tag {2.3.14}
$$

Thus, to calculate the values of $\lambda_{1}$ and $\lambda_{2}$ that factor the polynomial in [2.3.3], we can find the roots of [2.3.14] directly from the quadratic formula:

$$
\lambda_ {1} = \frac {\phi_ {1} + \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}}}{2} \tag {2.3.15}
$$

$$
\lambda_ {2} = \frac {\phi_ {1} - \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}}}{2}. \tag {2.3.16}
$$

For the example of [2.3.4], we would thus calculate

$$
\lambda_ {1} = \frac {0 . 6 + \sqrt {(0 . 6) ^ {2} - 4 (0 . 0 8)}}{2} = 0. 4
$$

$$
\lambda_ {2} = \frac {0 . 6 - \sqrt {(0 . 6) ^ {2} - 4 (0 . 0 8)}}{2} = 0. 2.
$$

It is instructive to compare these results with those in Chapter 1. There the dynamics of the second-order difference equation [2.3.1] were summarized by calculating the eigenvalues of the matrix $\mathbf{F}$ given by

$$
\mathbf {F} = \left[ \begin{array}{l l} \phi_ {1} & \phi_ {2} \\ 1 & 0 \end{array} \right]. \tag {2.3.17}
$$

The eigenvalues of $\mathbf{F}$ were seen to be the two values of $\lambda$ that satisfy equation [1.2.13]:

$$
\left(\lambda^ {2} - \phi_ {1} \lambda - \phi_ {2}\right) = 0.
$$

But this is the same calculation as in [2.3.14]. This finding is summarized in the following proposition.

Proposition 2.1: Factoring the polynomial $(1 - \phi_1L - \phi_2L^2)$ as

$$
\left(1 - \phi_ {1} L - \phi_ {2} L ^ {2}\right) = \left(1 - \lambda_ {1} L\right) \left(1 - \lambda_ {2} L\right) \tag {2.3.18}
$$

is the same calculation as finding the eigenvalues of the matrix $\mathbf{F}$ in [2.3.17]. The eigenvalues $\lambda_{1}$ and $\lambda_{2}$ of $\mathbf{F}$ are the same as the parameters $\lambda_{1}$ and $\lambda_{2}$ in [2.3.18], and are given by equations [2.3.15] and [2.3.16].

The correspondence between calculating the eigenvalues of a matrix and factoring a polynomial in the lag operator is very instructive. However, it introduces one minor source of possible semantic confusion about which we have to be careful. Recall from Chapter 1 that the system [2.3.1] is stable if both $\lambda_{1}$ and $\lambda_{2}$ are less than 1 in modulus and explosive if either $\lambda_{1}$ or $\lambda_{2}$ is greater than 1 in modulus. Sometimes this is described as the requirement that the roots of

$$
\left(\lambda^ {2} - \phi_ {1} \lambda - \phi_ {2}\right) = 0 \tag {2.3.19}
$$

lie inside the unit circle. The possible confusion is that it is often convenient to work directly with the polynomial in the form in which it appears in [2.3.2],

$$
(1 - \phi_ {1} z - \phi_ {2} z ^ {2}) = 0, \tag {2.3.20}
$$

whose roots, we have seen, are the reciprocals of those of [2.3.19]. Thus, we could say with equal accuracy that "the difference equation [2.3.1] is stable whenever the roots of [2.3.19] lie inside the unit circle" or that "the difference equation [2.3.1] is stable whenever the roots of [2.3.20] lie outside the unit circle." The two statements mean exactly the same thing. Some scholars refer simply to the "roots of the difference equation [2.3.1]," though this raises the possibility of confusion between [2.3.19] and [2.3.20]. This book will follow the convention of using the term "eigenvalues" to refer to the roots of [2.3.19]. Wherever the term "roots" is used, we will indicate explicitly the equation whose roots are being described.

From here on in this section, it is assumed that the second-order difference equation is stable, with the eigenvalues $\lambda_{1}$ and $\lambda_{2}$ distinct and both inside the unit circle. Where this is the case, the inverses

$$
\left(1 - \lambda_ {1} L\right) ^ {- 1} = 1 + \lambda_ {1} ^ {1} L + \lambda_ {1} ^ {2} L ^ {2} + \lambda_ {1} ^ {3} L ^ {3} + \dots
$$

$$
\left(1 - \lambda_ {2} L\right) ^ {- 1} = 1 + \lambda_ {2} ^ {1} L + \lambda_ {2} ^ {2} L ^ {2} + \lambda_ {2} ^ {3} L ^ {3} + \dots
$$

are well defined for bounded sequences. Write [2.3.2] in factored form:

$$
(1 - \lambda_ {1} L) (1 - \lambda_ {2} L) y _ {t} = w _ {t}
$$

and operate on both sides by $(1 - \lambda_{1}L)^{-1}(1 - \lambda_{2}L)^{-1}$

$$
y _ {t} = \left(1 - \lambda_ {1} L\right) ^ {- 1} \left(1 - \lambda_ {2} L\right) ^ {- 1} w _ {t}. \tag {2.3.21}
$$

Following Sargent (1987, p. 184), when $\lambda_1 \neq \lambda_2$ , we can use the following operator:

$$
\left. \left(\lambda_ {1} - \lambda_ {2}\right) ^ {- 1} \left\{\frac {\lambda_ {1}}{1 - \lambda_ {1} L} - \frac {\lambda_ {2}}{1 - \lambda_ {2} L} \right\}. \right. \tag {2.3.22}
$$

Notice that this is simply another way of writing the operator in [2.3.21]:

$$
\begin{array}{l} \left(\lambda_ {1} - \lambda_ {2}\right) ^ {- 1} \left\{\frac {\lambda_ {1}}{1 - \lambda_ {1} L} - \frac {\lambda_ {2}}{1 - \lambda_ {2} L} \right\} \\ = \left(\lambda_ {1} - \lambda_ {2}\right) ^ {- 1} \left\{\frac {\lambda_ {1} \left(1 - \lambda_ {2} L\right) - \lambda_ {2} \left(1 - \lambda_ {1} L\right)}{\left(1 - \lambda_ {1} L\right) \cdot \left(1 - \lambda_ {2} L\right)} \right\} \\ = \frac {1}{\left(1 - \lambda_ {1} L\right) \cdot \left(1 - \lambda_ {2} L\right)}. \\ \end{array}
$$

Thus, [2.3.21] can be written as

$$
\begin{array}{l} y _ {t} = \left(\lambda_ {1} - \lambda_ {2}\right) ^ {- 1} \left\{\frac {\lambda_ {1}}{1 - \lambda_ {1} L} - \frac {\lambda_ {2}}{1 - \lambda_ {2} L} \right\} w _ {t} \\ = \left\{\frac {\lambda_ {1}}{\lambda_ {1} - \lambda_ {2}} \left[ 1 + \lambda_ {1} L + \lambda_ {1} ^ {2} L ^ {2} + \lambda_ {1} ^ {3} L ^ {3} + \dots \right] \right. \\ \left. - \frac {\lambda_ {2}}{\lambda_ {1} - \lambda_ {2}} \left[ 1 + \lambda_ {2} L + \lambda_ {2} ^ {2} L ^ {2} + \lambda_ {2} ^ {3} L ^ {3} + \dots \right] \right\} w _ {t} \\ \end{array}
$$

or

$$
\begin{array}{l} \begin{array}{l} y _ {t} = \left[ c _ {1} + c _ {2} \right] w _ {t} + \left[ c _ {1} \lambda_ {1} + c _ {2} \lambda_ {2} \right] w _ {t - 1} + \left[ c _ {1} \lambda_ {1} ^ {2} + c _ {2} \lambda_ {2} ^ {2} \right] w _ {t - 2} \\ + \left[ c _ {1} \lambda^ {3} + c _ {2} \lambda^ {3} \right] w _ {t - 1} + \dots . \end{array} \tag {2.3.23} \\ + \left[ c _ {1} \lambda_ {1} ^ {3} + c _ {2} \lambda_ {2} ^ {3} \right] w _ {t - 3} + \dots , \\ \end{array}
$$

where

$$
c _ {1} = \lambda_ {1} / \left(\lambda_ {1} - \lambda_ {2}\right) \tag {2.3.24}
$$

$$
c _ {2} = - \lambda_ {2} / \left(\lambda_ {1} - \lambda_ {2}\right). \tag {2.3.25}
$$

From [2.3.23] the dynamic multiplier can be read off directly as

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = c _ {1} \lambda_ {1} ^ {j} + c _ {2} \lambda_ {2} ^ {j},
$$

the same result arrived at in equations [1.2.24] and [1.2.25].

# 2.4. pth-Order Difference Equations

These techniques generalize in a straightforward way to a $p$ th-order difference equation of the form

$$
y _ {t} = \phi_ {1} y _ {t - 1} + \phi_ {2} y _ {t - 2} + \dots + \phi_ {p} y _ {t - p} + w _ {t}. \tag {2.4.1}
$$

Write [2.4.1] in terms of lag operators as

$$
(1 - \phi_ {1} L - \phi_ {2} L ^ {2} - \dots - \phi_ {p} L ^ {p}) y _ {t} = w _ {t}. \tag {2.4.2}
$$

Factor the operator on the left side of [2.4.2] as

$$
\left(1 - \phi_ {1} L - \phi_ {2} L ^ {2} - \dots - \phi_ {p} L ^ {p}\right) = \left(1 - \lambda_ {1} L\right) \left(1 - \lambda_ {2} L\right) \cdot \cdot \cdot \left(1 - \lambda_ {p} L\right). \quad [ 2. 4. 3 ]
$$

This is the same as finding the values of $(\lambda_1, \lambda_2, \ldots, \lambda_p)$ such that the following polynomials are the same for all $z$ :

$$
(1 - \phi_ {1} z - \phi_ {2} z ^ {2} - \dots - \phi_ {p} z ^ {p}) = (1 - \lambda_ {1} z) (1 - \lambda_ {2} z) \dots (1 - \lambda_ {p} z).
$$

As in the second-order system, we multiply both sides of this equation by $z^{-p}$ and define $\lambda \equiv z^{-1}$ :

$$
\begin{array}{l} \left(\lambda^ {p} - \phi_ {1} \lambda^ {p - 1} - \phi_ {2} \lambda^ {p - 2} - \dots - \phi_ {p - 1} \lambda - \phi_ {p}\right) \\ = (\lambda - \lambda_ {1}) (\lambda - \lambda_ {2}) \dots (\lambda - \lambda_ {p}). \tag {2.4.4} \\ \end{array}
$$

Clearly, setting $\lambda = \lambda_{i}$ for $i = 1,2,\ldots ,$ or $p$ causes the right side of [2.4.4] to equal zero. Thus the values $(\lambda_1,\lambda_2,\dots ,\lambda_p)$ must be the numbers that set the left side of expression [2.4.4] to zero as well:

$$
\lambda^ {p} - \phi_ {1} \lambda^ {p - 1} - \phi_ {2} \lambda^ {p - 2} - \dots - \phi_ {p - 1} \lambda - \phi_ {p} = 0. \tag {2.4.5}
$$

This expression again is identical to that given in Proposition 1.1, which characterized the eigenvalues $(\lambda_1,\lambda_2,\dots ,\lambda_p)$ of the matrix $\mathbf{F}$ defined in equation [1.2.3]. Thus, Proposition 2.1 readily generalizes.

Proposition 2.2: Factoring a pth-order polynomial in the lag operator,

$$
(1 - \phi_ {1} L - \phi_ {2} L ^ {2} - \dots - \phi_ {p} L ^ {p}) = (1 - \lambda_ {1} L) (1 - \lambda_ {2} L) \dots (1 - \lambda_ {p} L),
$$

is the same calculation as finding the eigenvalues of the matrix $\mathbf{F}$ defined in [1.2.3]. The eigenvalues $(\lambda_1, \lambda_2, \ldots, \lambda_p)$ of $\mathbf{F}$ are the same as the parameters $(\lambda_1, \lambda_2, \ldots, \lambda_p)$ in [2.4.3] and are given by the solutions to equation [2.4.5].

The difference equation [2.4.1] is stable if the eigenvalues (the roots of [2.4.5]) lie inside the unit circle, or equivalently if the roots of

$$
1 - \phi_ {1} z - \phi_ {2} z ^ {2} - \dots - \phi_ {\rho} z ^ {p} = 0 \tag {2.4.6}
$$

lie outside the unit circle.

Assuming that the eigenvalues are inside the unit circle and that we are restricting ourselves to considering bounded sequences, the inverses $(1 - \lambda_1L)^{-1}$ , $(1 - \lambda_2L)^{-1},\ldots ,(1 - \lambda_pL)^{-1}$ all exist, permitting the difference equation

$$
(1 - \lambda_ {1} L) (1 - \lambda_ {2} L) \dots (1 - \lambda_ {p} L) y _ {t} = w _ {t}
$$

to be written as

$$
y _ {t} = (1 - \lambda_ {1} L) ^ {- 1} (1 - \lambda_ {2} L) ^ {- 1} \dots (1 - \lambda_ {p} L) ^ {- 1} w _ {t}. \tag {2.4.7}
$$

Provided further that the eigenvalues $(\lambda_1, \lambda_2, \dots, \lambda_p)$ are all distinct, the polynomial associated with the operator on the right side of [2.4.7] can again be expanded with partial fractions:

$$
\begin{array}{l} \frac {1}{(1 - \lambda_ {1} z) (1 - \lambda_ {2} z) \cdots (1 - \lambda_ {p} z)} \\ = \frac {c _ {1}}{(1 - \lambda_ {1} z)} + \frac {c _ {2}}{(1 - \lambda_ {2} z)} + \dots + \frac {c _ {p}}{(1 - \lambda_ {p} z)}. \tag {2.4.8} \\ \end{array}
$$

Following Sargent (1987, pp. 192-93), the values of $(c_{1}, c_{2}, \ldots, c_{p})$ that make [2.4.8] true can be found by multiplying both sides by $(1 - \lambda_{1}z)(1 - \lambda_{2}z) \cdots (1 - \lambda_{p}z)$ :

$$
\begin{array}{l} 1 = c _ {1} (1 - \lambda_ {2} z) (1 - \lambda_ {3} z) \dots (1 - \lambda_ {p} z) \\ + c _ {2} \left(1 - \lambda_ {1} z\right) \left(1 - \lambda_ {3} z\right) \dots \left(1 - \lambda_ {p} z\right) + \dots \tag {2.4.9} \\ + c _ {p} (1 - \lambda_ {1} z) (1 - \lambda_ {2} z) \dots (1 - \lambda_ {p - 1} z). \\ \end{array}
$$

Equation [2.4.9] has to hold for all values of $z$ . Since it is a $(p - 1)$ th-order polynomial, if $(c_{1}, c_{2}, \ldots, c_{p})$ are chosen so that [2.4.9] holds for $p$ particular

distinct values of $z$ , then [2.4.9] must hold for all $z$ . To ensure that [2.4.9] holds at $z = \lambda_1^{-1}$ requires that

$$
1 = c _ {1} \left(1 - \lambda_ {2} \lambda_ {1} ^ {- 1}\right) \left(1 - \lambda_ {3} \lambda_ {1} ^ {- 1}\right) \dots \left(1 - \lambda_ {p} \lambda_ {1} ^ {- 1}\right)
$$

or

$$
c _ {1} = \frac {\lambda_ {1} ^ {p - 1}}{(\lambda_ {1} - \lambda_ {2}) (\lambda_ {1} - \lambda_ {3}) \cdots (\lambda_ {1} - \lambda_ {p})}. \tag {2.4.10}
$$

For [2.4.9] to hold for $z = \lambda_2^{-1},\lambda_3^{-1},\dots ,\lambda_p^{-1}$ requires

$$
c _ {2} = \frac {\lambda_ {2} ^ {p - 1}}{(\lambda_ {2} - \lambda_ {1}) (\lambda_ {2} - \lambda_ {3}) \cdots (\lambda_ {2} - \lambda_ {p})} \tag {2.4.11}
$$

$$
\begin{array}{c} \vdots \\ \vdots \end{array}
$$

$$
c _ {p} = \frac {\lambda_ {p} ^ {p - 1}}{(\lambda_ {p} - \lambda_ {1}) (\lambda_ {p} - \lambda_ {2}) \cdots (\lambda_ {p} - \lambda_ {p - 1})}. \tag {2.4.12}
$$

Note again that these are identical to expression [1.2.25] in Chapter 1. Recall from the discussion there that $c_{1} + c_{2} + \dots + c_{p} = 1$ .

To conclude, [2.4.7] can be written

$$
\begin{array}{l} y _ {t} = \frac {c _ {1}}{(1 - \lambda_ {1} L)} w _ {t} + \frac {c _ {2}}{(1 - \lambda_ {2} L)} w _ {t} + \dots + \frac {c _ {p}}{(1 - \lambda_ {p} L)} w _ {t} \\ = c _ {1} \left(1 + \lambda_ {1} L + \lambda_ {1} ^ {2} L ^ {2} + \lambda_ {1} ^ {3} L ^ {3} + \dots\right) w _ {t} + c _ {2} \left(1 + \lambda_ {2} L + \lambda_ {2} ^ {2} L ^ {2} + \lambda_ {2} ^ {3} L ^ {3} + \dots\right) w _ {t} \\ + \dots + c _ {p} \left(1 + \lambda_ {p} L + \lambda_ {p} ^ {2} L ^ {2} + \lambda_ {p} ^ {3} L ^ {3} + \dots\right) w _ {t} \\ \end{array}
$$

or

$$
\begin{array}{l} y _ {t} = \left[ c _ {1} + c _ {2} + \dots + c _ {p} \right] w _ {t} + \left[ c _ {1} \lambda_ {1} + c _ {2} \lambda_ {2} + \dots + c _ {p} \lambda_ {p} \right] w _ {t - 1} \\ + \left[ c _ {1} \lambda_ {1} ^ {2} + c _ {2} \lambda_ {2} ^ {2} + \dots + c _ {p} \lambda_ {p} ^ {2} \right] w _ {t - 2} \tag {2.4.13} \\ + \left[ c _ {1} \lambda_ {1} ^ {3} + c _ {2} \lambda_ {2} ^ {3} + \dots + c _ {p} \lambda_ {p} ^ {3} \right] w _ {t - 3} + \dots \\ \end{array}
$$

where $(c_{1}, c_{2}, \ldots, c_{p})$ are given by equations [2.4.10] through [2.4.12]. Again, the dynamic multiplier can be read directly off [2.4.13]:

$$
\frac {\partial y _ {t + j}}{\partial w _ {t}} = \left[ c _ {1} \lambda_ {1} ^ {j} + c _ {2} \lambda_ {2} ^ {j} + \dots + c _ {p} \lambda_ {p} ^ {j} \right], \tag {2.4.14}
$$

reproducing the result from Chapter 1.

There is a very convenient way to calculate the effect of $w$ on the present value of $y$ using the lag operator representation. Write [2.4.13] as

$$
y _ {t} = \psi_ {0} w _ {t} + \psi_ {1} w _ {t - 1} + \psi_ {2} w _ {t - 2} + \psi_ {3} w _ {t - 3} + \dots \tag {2.4.15}
$$

where

$$
\psi_ {j} = \left[ c _ {1} \lambda_ {1} ^ {i} + c _ {2} \lambda_ {2} ^ {j} + \dots + c _ {p} \lambda_ {p} ^ {j} \right]. \tag {2.4.16}
$$

Next rewrite [2.4.15] in lag operator notation as

$$
y _ {t} = \psi (L) w _ {t}, \tag {2.4.17}
$$

where $\psi (L)$ denotes an infinite-order polynomial in the lag operator:

$$
\psi (L) = \psi_ {0} + \psi_ {1} L + \psi_ {2} L ^ {2} + \psi_ {3} L ^ {3} + \dots .
$$

Notice that $\psi_{j}$ is the dynamic multiplier [2.4.14]. The effect of $w_{t}$ on the present value of $y$ is given by

$$
\begin{array}{l} \frac {\partial \sum_ {j = 0} ^ {\infty} \beta^ {j} y _ {t + j}}{\partial w _ {t}} = \sum_ {j = 0} ^ {\infty} \beta^ {j} \frac {\partial y _ {t + j}}{\partial w _ {t}} \tag {2.4.18} \\ = \sum_ {j = 0} ^ {\infty} \beta^ {j} \psi_ {j}. \\ \end{array}
$$

Thinking of $\psi (z)$ as a polynomial in a real number $z$

$$
\psi (z) = \psi_ {0} + \psi_ {1} z + \psi_ {2} z ^ {2} + \psi_ {3} z ^ {3} + \dots ,
$$

it appears that the multiplier [2.4.18] is simply this polynomial evaluated at $z = \beta$ :

$$
\frac {\partial \sum_ {j = 0} ^ {\infty} \beta^ {j} y _ {t + j}}{\partial w _ {t}} = \psi (\beta) = \psi_ {0} + \psi_ {1} \beta + \psi_ {2} \beta^ {2} + \psi_ {3} \beta^ {3} + \dots . \tag {2.4.19}
$$

But comparing [2.4.17] with [2.4.7], it is apparent that

$$
\psi (L) = \left[ \left(1 - \lambda_ {1} L\right) \left(1 - \lambda_ {2} L\right) \dots \left(1 - \lambda_ {p} L\right) \right] ^ {- 1},
$$

and from [2.4.3] this means that

$$
\psi (L) = \left[ 1 - \phi_ {1} L - \phi_ {2} L ^ {2} - \dots - \phi_ {p} L ^ {p} \right] ^ {- 1}.
$$

We conclude that

$$
\psi (z) = \left[ 1 - \phi_ {1} z - \phi_ {2} z ^ {2} - \dots - \phi_ {p} z ^ {p} \right] ^ {- 1}
$$

for any value of $z$ , so, in particular,

$$
\psi (\beta) = [ 1 - \phi_ {1} \beta - \phi_ {2} \beta^ {2} - \dots - \phi_ {p} \beta^ {p} ] ^ {- 1}. \tag {2.4.20}
$$

Substituting [2.4.20] into [2.4.19] reveals that

$$
\frac {\partial \sum_ {j = 0} ^ {\infty} \beta^ {j} y _ {t + j}}{\partial w _ {t}} = \frac {1}{1 - \phi_ {1} \beta - \phi_ {2} \beta^ {2} - \cdots - \phi_ {p} \beta^ {p}}, \tag {2.4.21}
$$

reproducing the claim in Proposition 1.3. Again, the long-run multiplier obtains as the special case of [2.4.21] with $\beta = 1$ :

$$
\lim  _ {j \rightarrow \infty} \left[ \frac {\partial y _ {t + j}}{\partial w _ {t}} + \frac {\partial y _ {t + j}}{\partial w _ {t + 1}} + \dots + \frac {\partial y _ {t + j}}{\partial w _ {t + j}} \right] = \frac {1}{1 - \phi_ {1} - \phi_ {2} - \cdots - \phi_ {p}}.
$$

# 2.5. Initial Conditions and Unbounded Sequences

Section 1.2 analyzed the following problem. Given a $p$ th-order difference equation

$$
y _ {t} = \phi_ {1} y _ {t - 1} + \phi_ {2} y _ {t - 2} + \dots + \phi_ {p} y _ {t - p} + w _ {t}, \tag {2.5.1}
$$

$p$ initial values of $y$ ,

$$
y _ {- 1}, y _ {- 2}, \dots , y _ {- p}, \tag {2.5.2}
$$

and a sequence of values for the input variable $w$ ,

$$
\left\{w _ {0}, w _ {1}, \dots , w _ {t} \right\}, \tag {2.5.3}
$$

we sought to calculate the sequence of values for the output variable $y$ :

$$
\left\{y _ {0}, y _ {1}, \dots , y _ {t} \right\}.
$$

Certainly there are systems where the question is posed in precisely this form. We may know the equation of motion for the system [2.5.1] and its current state [2.5.2] and wish to characterize the values that $\{y_0, y_1, \ldots, y_t\}$ might take on for different specifications of $\{w_0, w_1, \ldots, w_t\}$ .

However, there are many examples in economics and finance in which a theory specifies just the equation of motion [2.5.1] and a sequence of driving variables [2.5.3]. Clearly, these two pieces of information alone are insufficient to determine the sequence $\{y_0, y_1, \ldots, y_d\}$ , and some additional theory beyond that contained in the difference equation [2.5.1] is needed to describe fully the dependence of $y$ on $w$ . These additional restrictions can be of interest in their own right and also help give some insight into some of the technical details of manipulating difference equations. For these reasons, this section discusses in some depth an example of the role of initial conditions and their implications for solving difference equations.

Let $P_{t}$ denote the price of a stock and $D_{t}$ its dividend payment. If an investor buys the stock at date $t$ and sells it at $t + 1$ , the investor will earn a yield of $D_{t} / P_{t}$ from the dividend and a yield of $(P_{t + 1} - P_{t}) / P_{t}$ in capital gains. The investor's total return $(r_{t + 1})$ is thus

$$
r _ {t + 1} = \left(P _ {t + 1} - P _ {t}\right) / P _ {t} + D _ {t} / P _ {t}.
$$

A very simple model of the stock market posits that the return investors earn on stocks is constant across time periods:

$$
r = \left(P _ {t + 1} - P _ {t}\right) / P _ {t} + D _ {t} / P _ {t} \quad r > 0. \tag {2.5.4}
$$

Equation [2.5.4] may seem too simplistic to be of much practical interest; it assumes among other things that investors have perfect foresight about future stock prices and dividends. However, a slightly more realistic model in which expected stock returns are constant involves a very similar set of technical issues. The advantage of the perfect-foresight model [2.5.4] is that it can be discussed using the tools already in hand to gain some further insight into using lag operators to solve difference equations.

Multiply [2.5.4] by $P_{t}$ to arrive at

$$
r P _ {t} = P _ {t + 1} - P _ {t} + D _ {t}
$$

or

$$
P _ {t + 1} = (1 + r) P _ {t} - D _ {t}. \tag {2.5.5}
$$

Equation [2.5.5] will be recognized as a first-order difference equation of the form of [1.1.1] with $y_{t} = P_{t + 1}$ , $\phi = (1 + r)$ , and $w_{t} = -D_{t}$ . From [1.1.7], we know that [2.5.5] implies that

$$
\begin{array}{l} P _ {t + 1} = (1 + r) ^ {t + 1} P _ {0} - (1 + r) ^ {t} D _ {0} - (1 + r) ^ {t - 1} D _ {1} - (1 + r) ^ {t - 2} D _ {2} \quad [ 2. 5. 6 ] \\ - \dots - (1 + r) D _ {t - 1} - D _ {t}. \\ \end{array}
$$

If the sequence $\{D_0, D_1, \ldots, D_t\}$ and the value of $P_0$ were given, then [2.5.6] could determine the values of $\{P_1, P_2, \ldots, P_{t+1}\}$ . But if only the values $\{D_0, D_1, \ldots, D_t\}$ are given, then equation [2.5.6] would not be enough to pin down $\{P_1, P_2, \ldots, P_{t+1}\}$ . There are an infinite number of possible sequences $\{P_1, P_2, \ldots, P_{t+1}\}$ consistent with [2.5.5] and with a given $\{D_0, D_1, \ldots, D_t\}$ . This infinite number of possibilities is indexed by the initial value $P_0$ .

A further simplifying assumption helps clarify the nature of these different paths for $\{P_1, P_2, \ldots, P_{t+1}\}$ . Suppose that dividends are constant over time:

$$
D _ {t} = D \quad \text {f o r a l l} t.
$$

Then [2.5.6] becomes

$$
\begin{array}{l} P _ {t + 1} = (1 + r) ^ {t + 1} P _ {0} - \left[ (1 + r) ^ {t} + (1 + r) ^ {t - 1} \right. \\ + \dots + (1 + r) + 1 ] D \\ = (1 + r) ^ {t + 1} P _ {0} - \frac {1 - (1 + r) ^ {t + 1}}{1 - (1 + r)} D \tag {2.5.7} \\ = (1 + r) ^ {t + 1} \left[ P _ {0} - (D / r) \right] + (D / r). \\ \end{array}
$$

Consider first the solution in which $P_0 = D / r$ . If the initial stock price should happen to take this value, then [2.5.7] implies that

$$
P _ {t} = D / r \tag {2.5.8}
$$

for all $t$ . In this solution, dividends are constant at $D$ and the stock price is constant at $D / r$ . With no change in stock prices, investors never have any capital gains or losses, and their return is solely the dividend yield $D / P = r$ . In a world with no changes in dividends this seems to be a sensible expression of the theory represented by [2.5.4]. Equation [2.5.8] is sometimes described as the "market fundamentals" solution to [2.5.4] for the case of constant dividends.

However, even with constant dividends, equation [2.5.8] is not the only result consistent with [2.5.4]. Suppose that the initial price exceeded $D / r$ :

$$
P _ {0} > D / r.
$$

Investors seem to be valuing the stock beyond the potential of its constant dividend stream. From [2.5.7] this could be consistent with the asset pricing theory [2.5.4] provided that $P_{1}$ exceeds $D / r$ by an even larger amount. As long as investors all believe that prices will continue to rise over time, each will earn the required return $r$ from the realized capital gain and [2.5.4] will be satisfied. This scenario has reminded many economists of a speculative bubble in stock prices.

If such bubbles are to be ruled out, additional knowledge about the process for $\{P_t\}_{t = -\infty}^{\infty}$ is required beyond that contained in the theory of [2.5.4]. For example, we might argue that finite world resources put an upper limit on feasible stock prices, as in

$$
\left| P _ {t} \right| <   \bar {P} \quad \text {f o r a l l} t. \tag {2.5.9}
$$

Then the only sequence for $\{P_{t}^{\infty}\}_{t = -\infty}$ consistent with both [2.5.4] and [2.5.9] would be the market fundamentals solution [2.5.8].

Let us now relax the assumption that dividends are constant and replace it with the assumption that $\{D_{t|t = -\infty}^{\infty}$ is a bounded sequence. What path for $\{P_{t|t = -\infty}^{\infty}$ in [2.5.6] is consistent with [2.5.9] in this case? The answer can be found by returning to the difference equation [2.5.5]. We arrived at the form [2.5.6] by recursively substituting this equation backward. That is, we used the fact that [2.5.5] held for dates $t, t - 1, t - 2, \ldots, 0$ and recursively substituted to arrive at [2.5.6] as a logical implication of [2.5.5]. Equation [2.5.5] could equally well be solved recursively forward. To do so, equation [2.5.5] is written as

$$
P _ {t} = \frac {1}{1 + r} \left[ P _ {t + 1} + D _ {t} \right]. \tag {2.5.10}
$$

An analogous equation must hold for date $t + 1$ :

$$
P _ {t + 1} = \frac {1}{1 + r} \left[ P _ {t + 2} + D _ {t + 1} \right]. \tag {2.5.11}
$$

Substitute [2.5.11] into [2.5.10] to deduce

$$
\begin{array}{l} P _ {t} = \frac {1}{1 + r} \left[ \frac {1}{1 + r} \left[ P _ {t + 2} + D _ {t + 1} \right] + D _ {t} \right] \tag {2.5.12} \\ = \left[ \frac {1}{1 + r} \right] ^ {2} P _ {t + 2} + \left[ \frac {1}{1 + r} \right] ^ {2} D _ {t + 1} + \left[ \frac {1}{1 + r} \right] D _ {t}. \\ \end{array}
$$

Using [2.5.10] for date $t + 2$

$$
P _ {t + 2} = \frac {1}{1 + r} [ P _ {t + 3} + D _ {t + 2} ],
$$

and substituting into [2.5.12] gives

$$
P _ {t} = \left[ \frac {1}{1 + r} \right] ^ {3} P _ {t + 3} + \left[ \frac {1}{1 + r} \right] ^ {3} D _ {t + 2} + \left[ \frac {1}{1 + r} \right] ^ {2} D _ {t + 1} + \left[ \frac {1}{1 + r} \right] D _ {t}.
$$

Continuing in this fashion $T$ periods into the future produces

$$
\begin{array}{l} P _ {t} = \left[ \frac {1}{1 + r} \right] ^ {T} P _ {t + T} + \left[ \frac {1}{1 + r} \right] ^ {T} D _ {t + T - 1} + \left[ \frac {1}{1 + r} \right] ^ {T - 1} D _ {t + T - 2} \tag {2.5.13} \\ + \dots + \left[ \frac {1}{1 + r} \right] ^ {2} D _ {t + 1} + \left[ \frac {1}{1 + r} \right] D _ {t}. \\ \end{array}
$$

If the sequence $\{P_{t}\}_{t = -\infty}^{\infty}$ is to satisfy [2.5.9], then

$$
\lim  _ {T \rightarrow \infty} \left[ \frac {1}{1 + r} \right] ^ {T} P _ {t + T} = 0.
$$

If $\{D_{\theta}T\}_{\theta = -\infty}$ is likewise a bounded sequence, then the following limit exists:

$$
\lim  _ {T \rightarrow \infty} \sum_ {j = 0} ^ {T} \left[ \frac {1}{1 + r} \right] ^ {j + 1} D _ {t + j}.
$$

Thus, if $\{P_{t}\}_{t = -\infty}^{\infty}$ is to be a bounded sequence, then we can take the limit of [2.5.13] as $T\to \infty$ to conclude

$$
P _ {t} = \sum_ {j = 0} ^ {\infty} \left[ \frac {1}{1 + r} \right] ^ {j + 1} D _ {t + j}, \tag {2.5.14}
$$

which is referred to as the "market fundamentals" solution of [2.5.5] for the general case of time-varying dividends. Notice that [2.5.14] produces [2.5.8] as a special case when $D_{t} = D$ for all $t$ .

Describing the value of a variable at time $t$ as a function of future realizations of another variable as in [2.5.14] may seem an artifact of assuming a perfect-foresight model of stock prices. However, an analogous set of operations turns out to be appropriate in a system similar to [2.5.4] in which expected returns are constant.<sup>1</sup> In such systems [2.5.14] generalizes to

$$
P _ {t} = \sum_ {j = 0} ^ {\infty} \left[ \frac {1}{1 + r} \right] ^ {j + 1} E _ {t} D _ {t + j},
$$

See Sargent (1987) and Whiteman (1983) for an introduction to the manipulation of difference equations involving expectations.

where $E_{t}$ denotes an expectation of an unknown future quantity based on information available to investors at date $t$ .

Expression [2.5.14] determines the particular value for the initial price $P_0$ that is consistent with the boundedness condition [2.5.9]. Setting $t = 0$ in [2.5.14] and substituting into [2.5.6] produces

$$
\begin{array}{l} P _ {t + 1} = (1 + r) ^ {t + 1} \left\{\left[ \frac {1}{1 + r} \right] D _ {0} + \left[ \frac {1}{1 + r} \right] ^ {2} D _ {1} + \left[ \frac {1}{1 + r} \right] ^ {3} D _ {2} \right. \\ + \dots + \left[ \frac {1}{1 + r} \right] ^ {t + 1} D _ {t} + \left[ \frac {1}{1 + r} \right] ^ {t + 2} D _ {t + 1} + \dots \Bigg \} - (1 + r) ^ {t} D _ {0} \\ - (1 + r) ^ {t - 1} D _ {1} - (1 + r) ^ {t - 2} D _ {2} - \dots - (1 + r) D _ {t - 1} - D _ {t} \\ = \left[ \frac {1}{1 + r} \right] D _ {t + 1} + \left[ \frac {1}{1 + r} \right] ^ {2} D _ {t + 2} + \left[ \frac {1}{1 + r} \right] ^ {3} D _ {t + 3} + \dots . \\ \end{array}
$$

Thus, setting the initial condition $P_0$ to satisfy [2.5.14] is sufficient to ensure that it holds for all $t$ . Choosing $P_0$ equal to any other value would cause the consequences of each period's dividends to accumulate over time so as to lead to a violation of [2.5.9] eventually.

It is useful to discuss these same calculations from the perspective of lag operators. In Section 2.2 the recursive substitution backward that led from [2.5.5] to [2.5.6] was represented by writing [2.5.5] in terms of lag operators as

$$
[ 1 - (1 + r) L ] P _ {t + 1} = - D _ {t} \tag {2.5.15}
$$

and multiplying both sides of [2.5.15] by the following operator:

$$
[ 1 + (1 + r) L + (1 + r) ^ {2} L ^ {2} + \dots + (1 + r) ^ {t} L ^ {t} ]. \tag {2.5.16}
$$

If $(1 + r)$ were less than unity, it would be natural to consider the limit of [2.5.16] as $t\to \infty$ :

$$
[ 1 - (1 + r) L ] ^ {- 1} = 1 + (1 + r) L + (1 + r) ^ {2} L ^ {2} + \dots .
$$

In the case of the theory of stock returns discussed here, however, $r > 0$ and this operator is not defined. In this case, a lag operator representation can be sought for the recursive substitution forward that led from [2.5.5] to [2.5.13]. This is accomplished using the inverse of the lag operator,

$$
L ^ {- 1} w _ {t} = w _ {t + 1},
$$

which extends result [2.1.4] to negative values of $k$ . Note that $L^{-1}$ is indeed the inverse of the operator $L$ :

$$
L ^ {- 1} \left(L w _ {t}\right) = L ^ {- 1} w _ {t - 1} = w _ {t}.
$$

In general,

$$
L ^ {- k} L ^ {j} = L ^ {j - k},
$$

with $L^0$ defined as the identity operator:

$$
L ^ {0} w _ {t} \equiv w _ {t}.
$$

Now consider multiplying [2.5.15] by

$$
\begin{array}{l} \left[ 1 + (1 + r) ^ {- 1} L ^ {- 1} + (1 + r) ^ {- 2} L ^ {- 2} + \dots + (1 + r) ^ {- (T - 1)} L ^ {- (T - 1)} \right] \\ \times \left[ - (1 + r) ^ {- 1} L ^ {- 1} \right] \quad [ 2. 5. 1 7 ] \\ \end{array}
$$

to obtain

$$
\begin{array}{l} \left[ 1 + (1 + r) ^ {- 1} L ^ {- 1} + (1 + r) ^ {- 2} L ^ {- 2} + \dots + (1 + r) ^ {- (T - 1)} L ^ {- (T - 1)} \right] \\ \times [ 1 - (1 + r) ^ {- 1} L ^ {- 1} ] P _ {t + 1} \\ = [ 1 + (1 + r) ^ {- 1} L ^ {- 1} + (1 + r) ^ {- 2} L ^ {- 2} + \dots \\ \left. + (1 + r) ^ {- (T - 1)} L ^ {- (T - 1)} \right] \times (1 + r) ^ {- 1} D _ {t + 1} \\ \end{array}
$$

or

$$
\begin{array}{l} [ 1 - (1 + r) ^ {- T} L ^ {- T} ] P _ {t + 1} = \left[ \frac {1}{1 + r} \right] D _ {t + 1} + \left[ \frac {1}{1 + r} \right] ^ {2} D _ {t + 2} \\ + \left[ \frac {1}{1 + r} \right] ^ {3} D _ {t + 3} + \dots + \left[ \frac {1}{1 + r} \right] ^ {T} D _ {t + T}, \\ \end{array}
$$

which is identical to [2.5.13] with $t$ in [2.5.13] replaced with $t + 1$ .

When $r > 0$ and $\{P_{t}^{\infty}\}_{t = -\infty}$ is a bounded sequence, the left side of the preceding equation will approach $P_{t + 1}$ as $T$ becomes large. Thus, when $r > 0$ and $\{P_{t}\}_{t = -\infty}^{\infty}$ and $\{D_{t}\}_{t = -\infty}^{\infty}$ are bounded sequences, the limit of the operator in [2.5.17] exists and could be viewed as the inverse of the operator on the left side of [2.5.15]:

$$
\begin{array}{l} [ 1 - (1 + r) L ] ^ {- 1} = - (1 + r) ^ {- 1} L ^ {- 1} \\ \times [ 1 + (1 + r) ^ {- 1} L ^ {- 1} + (1 + r) ^ {- 2} L ^ {- 2} + \dots ]. \\ \end{array}
$$

Applying this limiting operator to [2.5.15] amounts to solving the difference equation forward as in [2.5.14] and selecting the market fundamentals solution among the set of possible time paths for $\{P_{t}\}_{t = -\infty}^{\infty}$ given a particular time path for dividends $\{D_{t}\}_{t = -\infty}^{\infty}$ .

Thus, given a first-order difference equation of the form

$$
(1 - \phi L) y _ {t} = w _ {t}, \tag {2.5.18}
$$

Sargent's (1987) advice was to solve the equation "backward" when $|\phi| < 1$ by multiplying by

$$
[ 1 - \phi L ] ^ {- 1} = [ 1 + \phi L + \phi^ {2} L ^ {2} + \phi^ {3} L ^ {3} + \dots ] \tag {2.5.19}
$$

and to solve the equation "forward" when $|\phi| > 1$ by multiplying by

$$
\begin{array}{l} [ 1 - \phi L ] ^ {- 1} = \frac {- \phi^ {- 1} L ^ {- 1}}{1 - \phi^ {- 1} L ^ {- 1}} \\ = - \phi^ {- 1} L ^ {- 1} \left[ 1 + \phi^ {- 1} L ^ {- 1} + \phi^ {- 2} L ^ {- 2} + \phi^ {- 3} L ^ {- 3} + \dots \right]. \\ \end{array}
$$

Defining the inverse of $[1 - \phi L]$ in this way amounts to selecting an operator $[1 - \phi L]^{-1}$ with the properties that

$$
[ 1 - \phi L ] ^ {- 1} \times [ 1 - \phi L ] = 1 \quad (\text {t h e i d e n t i t y o p e r a t o r})
$$

and that, when it is applied to a bounded sequence $\{w_{t}^{f}\}_{t = -\infty}$

$$
[ 1 - \phi L ] ^ {- 1} w _ {t},
$$

the result is another bounded sequence.

The conclusion from this discussion is that in applying an operator such as $[1 - \phi L]^{-1}$ , we are implicitly imposing a boundedness assumption that rules out

phenomena such as the speculative bubbles of equation [2.5.7] a priori. Where that is our intention, so much the better, though we should not apply the rules [2.5.19] or [2.5.20] without some reflection on their economic content.

# Chapter 2 References

Sargent, Thomas J. 1987. *Macroeconomic Theory*, 2d ed. Boston: Academic Press.

Whiteman, Charles H. 1983. Linear Rational Expectations Models: A User's Guide. Minneapolis: University of Minnesota Press.

3

# Stationary ARMA Processes

This chapter introduces univariate ARMA processes, which provide a very useful class of models for describing the dynamics of an individual time series. The chapter begins with definitions of some of the key concepts used in time series analysis. Sections 3.2 through 3.5 then investigate the properties of various ARMA processes. Section 3.6 introduces the autocovariance-generating function, which is useful for analyzing the consequences of combining different time series and for an understanding of the population spectrum. The chapter concludes with a discussion of invertibility (Section 3.7), which can be important for selecting the ARMA representation of an observed time series that is appropriate given the uses to be made of the model.

# 3.1. Expectations, Stationarity, and Ergodicity

Expectations and Stochastic Processes

Suppose we have observed a sample of size $T$ of some random variable $Y_{t}$ :

$$
\left\{y _ {1}, y _ {2}, \dots , y _ {T} \right\}. \tag {3.1.1}
$$

For example, consider a collection of $T$ independent and identically distributed (i.i.d.) variables $\varepsilon_{t}$ ,

$$
\left\{\varepsilon_ {1}, \varepsilon_ {2}, \dots , \varepsilon_ {T} \right\}, \tag {3.1.2}
$$

with

$$
\varepsilon_ {t} \sim N (0, \sigma^ {2}).
$$

This is referred to as a sample of size $T$ from a Gaussian white noise process.

The observed sample [3.1.1] represents $T$ particular numbers, but this set of $T$ numbers is only one possible outcome of the underlying stochastic process that generated the data. Indeed, even if we were to imagine having observed the process for an infinite period of time, arriving at the sequence

$$
\left\{y _ {t} \right\} _ {t = - \infty} ^ {\infty} = \left\{\dots , y _ {- 1}, y _ {0}, y _ {1}, y _ {2}, \dots , y _ {T}, y _ {T + 1}, y _ {T + 2}, \dots \right\},
$$

the infinite sequence $\{y_{t}\}_{t = -\infty}^{\infty}$ would still be viewed as a single realization from a time series process. For example, we might set one computer to work generating an infinite sequence of i.i.d. $N(0,\sigma^2)$ variates, $\{\varepsilon_t^{(1)}\}_{t = -\infty}^{\infty}$ , and a second computer generating a separate sequence, $\{\varepsilon_t^{(2)}\}_{t = -\infty}^{\infty}$ . We would then view these as two independent realizations of a Gaussian white noise process.

Imagine a battery of $l$ such computers generating sequences $\{y_t^{(1)}\}_{t = -\infty}^{\infty}, \{y_t^{(2)}\}_{t = -\infty}^{\infty}, \dots, \{y_t^{(l)}\}_{t = -\infty}^{\infty}$ , and consider selecting the observation associated with date $t$ from each sequence:

$$
\left\{y _ {t} ^ {(1)}, y _ {t} ^ {(2)}, \dots , y _ {t} ^ {(J)} \right\}.
$$

This would be described as a sample of $I$ realizations of the random variable $Y_{t}$ . This random variable has some density, denoted $f_{Y_t}(y_t)$ , which is called the unconditional density of $Y_{t}$ . For example, for the Gaussian white noise process, this density is given by

$$
f _ {Y _ {t}} \left(y _ {t}\right) = \frac {1}{\sqrt {2 \pi} \sigma} \exp \left[ \frac {- y _ {t} ^ {2}}{2 \sigma^ {2}} \right].
$$

The expectation of the $t$ th observation of a time series refers to the mean of this probability distribution, provided it exists:

$$
E \left(Y _ {t}\right) \equiv \int_ {- \infty} ^ {\infty} y _ {t} f _ {Y _ {t}} \left(y _ {t}\right) d y _ {t}. \tag {3.1.3}
$$

We might view this as the probability limit of the ensemble average:

$$
E \left(Y _ {t}\right) = \operatorname * {p l i m} _ {I \rightarrow \infty} (1 / I) \sum_ {i = 1} ^ {I} Y _ {t} ^ {(i)}. \tag {3.1.4}
$$

For example, if $\{Y_{t}\}_{t = -\infty}^{\infty}$ represents the sum of a constant $\mu$ plus a Gaussian white noise process $\{\varepsilon_t\}_{t = -\infty}^{\infty}$ ,

$$
Y _ {t} = \mu + \varepsilon_ {t}, \tag {3.1.5}
$$

then its mean is

$$
E \left(Y _ {t}\right) = \mu + E \left(\varepsilon_ {t}\right) = \mu . \tag {3.1.6}
$$

If $Y_{t}$ is a time trend plus Gaussian white noise,

$$
Y _ {t} = \beta t + \varepsilon_ {t}, \tag {3.1.7}
$$

then its mean is

$$
E \left(Y _ {t}\right) = \beta t. \tag {3.1.8}
$$

Sometimes for emphasis the expectation $E(Y_{t})$ is called the unconditional mean of $Y_{t}$ . The unconditional mean is denoted $\mu_t$ :

$$
E \left(Y _ {t}\right) = \mu_ {t}.
$$

Note that this notation allows the general possibility that the mean can be a function of the date of the observation $t$ . For the process [3.1.7] involving the time trend, the mean [3.1.8] is a function of time, whereas for the constant plus Gaussian white noise, the mean [3.1.6] is not a function of time.

The variance of the random variable $Y_{t}$ (denoted $\gamma_{0t}$ ) is similarly defined as

$$
\gamma_ {0 t} \equiv E \left(Y _ {t} - \mu_ {t}\right) ^ {2} = \int_ {- \infty} ^ {\infty} \left(y _ {t} - \mu_ {t}\right) ^ {2} f _ {Y _ {t}} \left(y _ {t}\right) d y _ {t}. \tag {3.1.9}
$$

For example, for the process [3.1.7], the variance is

$$
\gamma_ {0 t} = E \left(Y _ {t} - \beta t\right) ^ {2} = E \left(\varepsilon_ {t} ^ {2}\right) = \sigma^ {2}.
$$

# Autocovariance

Given a particular realization such as $\{y_{t}^{(1)}\}_{t = -\infty}^{\infty}$ on a time series process, consider constructing a vector $\mathbf{x}_t^{(1)}$ associated with date $t$ . This vector consists of the $[j + 1]$ most recent observations on $y$ as of date $t$ for that realization:

$$
\mathbf {x} _ {t} ^ {(1)} \equiv \left[ \begin{array}{c} y _ {t} ^ {(1)} \\ y _ {t - 1} ^ {(1)} \\ \vdots \\ y _ {t - j} ^ {(1)} \end{array} \right].
$$

We think of each realization $\{y_{t}\}_{t = -\infty}^{\infty}$ as generating one particular value of the vector $\mathbf{x}_t$ and want to calculate the probability distribution of this vector $\mathbf{x}_t^{(i)}$ across realizations $i$ . This distribution is called the joint distribution of $(Y_{t}, Y_{t-1}, \ldots, Y_{t-j})$ . From this distribution we can calculate the $j$ th autocovariance of $Y_{t}$ (denoted $\gamma_{jt}$ ):

$$
\begin{array}{l} \gamma_ {j t} = \int_ {- \infty} ^ {\infty} \int_ {- \infty} ^ {\infty} \dots \int_ {- \infty} ^ {\infty} \left(y _ {t} - \mu_ {t}\right) \left(y _ {t - j} - \mu_ {t - j}\right) \\ \times f _ {Y _ {t}, Y _ {t - 1}, \dots , Y _ {t - j}} \left(y _ {t}, y _ {t - 1}, \dots , y _ {t - j}\right) d y _ {t} d y _ {t - 1} \dots d y _ {t - j} \quad [ 3. 1. 1 0 ] \\ = E \left(Y _ {t} - \mu_ {t}\right) \left(Y _ {t - j} - \mu_ {t - j}\right). \\ \end{array}
$$

Note that [3.1.10] has the form of a covariance between two variables $X$ and $Y$ :

$$
\operatorname {C o v} (X, Y) = E \left(X - \mu_ {X}\right) \left(Y - \mu_ {Y}\right).
$$

Thus [3.1.10] could be described as the covariance of $Y_{t}$ with its own lagged value; hence, the term "autocovariance." Notice further from [3.1.10] that the 0th autocovariance is just the variance of $Y_{t}$ , as anticipated by the notation $\gamma_{0t}$ in [3.1.9].

The autocovariance $\gamma_{jt}$ can be viewed as the $(1,j + 1)$ element of the variance-covariance matrix of the vector $\mathbf{x}_t$ . For this reason, the autocovariances are described as the second moments of the process for $Y_{t}$ .

Again it may be helpful to think of the $j$ th autocovariance as the probability limit of an ensemble average:

$$
\gamma_ {j t} = \operatorname * {p l i m} _ {I \rightarrow \infty} (1 / I) \sum_ {i = 1} ^ {I} \left[ Y _ {t} ^ {(i)} - \mu_ {t} \right] \cdot \left[ Y _ {t - j} ^ {(i)} - \mu_ {t - j} \right]. \tag {3.1.11}
$$

As an example of calculating autocovariances, note that for the process in [3.1.5] the autocovariances are all zero for $j \neq 0$ :

$$
\gamma_ {j t} = E \left(Y _ {t} - \mu\right) \left(Y _ {t - j} - \mu\right) = E \left(\varepsilon_ {t} \varepsilon_ {t - j}\right) = 0 \quad \text {f o r} j \neq 0.
$$

# Stationarity

If neither the mean $\mu_t$ nor the autocovariances $\gamma_{jt}$ depend on the date $t$ , then the process for $Y_t$ is said to be covariance-stationary or weakly stationary:

$$
E \left(Y _ {t}\right) = \mu \quad \text {f o r a l l} t
$$

$$
E \left(Y _ {t} - \mu\right) \left(Y _ {t - j} - \mu\right) = \gamma_ {j} \quad \text {f o r a l l} t \text {a n d a n y} j.
$$

For example, the process in [3.1.5] is covariance-stationary:

$$
E \left(Y _ {t}\right) = \mu
$$

$$
E (Y _ {t} - \mu) (Y _ {t - j} - \mu) = \left\{ \begin{array}{l l} \sigma^ {2} & \text {f o r} j = 0 \\ 0 & \text {f o r} j \neq 0. \end{array} \right.
$$

By contrast, the process of [3.1.7] is not covariance-stationary, because its mean, $\beta t$ , is a function of time.

Notice that if a process is covariance-stationary, the covariance between $Y_{t}$ and $Y_{t - j}$ depends only on $j$ , the length of time separating the observations, and not on $t$ , the date of the observation. It follows that for a covariance-stationary process, $\gamma_{j}$ and $\gamma_{-j}$ would represent the same magnitude. To see this, recall the definition

$$
\gamma_ {j} = E \left(Y _ {t} - \mu\right) \left(Y _ {t - j} - \mu\right). \tag {3.1.12}
$$

If the process is covariance-stationary, then this magnitude is the same for any value of $t$ we might have chosen; for example, we can replace $t$ with $t + j$ :

$$
\gamma_ {j} = E \left(Y _ {t + j} - \mu\right) \left(Y _ {[ t + j ] - j} - \mu\right) = E \left(Y _ {t + j} - \mu\right) \left(Y _ {t} - \mu\right) = E \left(Y _ {t} - \mu\right) \left(Y _ {t + j} - \mu\right).
$$

But referring again to the definition [3.1.12], this last expression is just the definition of $\gamma_{-j}$ . Thus, for any covariance-stationary process,

$$
\gamma_ {j} = \gamma_ {- j} \quad \text {f o r a l l i n t e g e r s} j. \tag {3.1.13}
$$

A different concept is that of strict stationarity. A process is said to be strictly stationary if, for any values of $j_1, j_2, \ldots, j_n$ , the joint distribution of $(Y_t, Y_{t+j_1}, Y_{t+j_2}, \ldots, Y_{t+j_n})$ depends only on the intervals separating the dates $(j_1, j_2, \ldots, j_n)$ and not on the date itself $(t)$ . Notice that if a process is strictly stationary with finite second moments, then it must be covariance-stationary—if the densities over which we are integrating in [3.1.3] and [3.1.10] do not depend on time, then the moments $\mu_t$ and $\gamma_{jt}$ will not depend on time. However, it is possible to imagine a process that is covariance-stationary but not strictly stationary; the mean and autocovariances could not be functions of time, but perhaps higher moments such as $E(Y_t^3)$ are.

In this text the term "stationary" by itself is taken to mean "covariance-stationary."

A process $\{Y_t\}$ is said to be Gaussian if the joint density

$$
f _ {Y _ {t}, Y _ {t + j _ {1}}, \dots , Y _ {t + j _ {n}}} (y _ {t}, y _ {t + j _ {1}}, \dots , y _ {t + j _ {n}})
$$

is Gaussian for any $j_1, j_2, \ldots, j_n$ . Since the mean and variance are all that are needed to parameterize a multivariate Gaussian distribution completely, a covariance-stationary Gaussian process is strictly stationary.

# Ergodicity

We have viewed expectations of a time series in terms of ensemble averages such as [3.1.4] and [3.1.11]. These definitions may seem a bit contrived, since usually all one has available is a single realization of size $T$ from the process, which we earlier denoted $\{y_1^{(1)}, y_2^{(1)}, \ldots, y_T^{(1)}\}$ . From these observations we would calculate the sample mean $\overline{y}$ . This, of course, is not an ensemble average but rather a time average:

$$
\bar {y} \equiv (1 / T) \sum_ {t = 1} ^ {T} y _ {t} ^ {(1)}. \tag {3.1.14}
$$

Whether time averages such as [3.1.14] eventually converge to the ensemble concept $E(Y_{t})$ for a stationary process has to do with ergodicity. A covariance-stationary process is said to be ergodic for the mean if [3.1.14] converges in probability to $E(Y_{t})$ as $T \to \infty$ .<sup>1</sup> A process will be ergodic for the mean provided that the autocovariance $\gamma_{j}$ goes to zero sufficiently quickly as $j$ becomes large. In Chapter 7 we will see that if the autocovariances for a covariance-stationary process satisfy

$$
\sum_ {j = 0} ^ {\infty} \left| \gamma_ {j} \right| <   \infty , \tag {3.1.15}
$$

then $\{Y_t\}$ is ergodic for the mean.

Similarly, a covariance-stationary process is said to be ergodic for second moments if

$$
[ 1 / (T - j) ] \sum_ {t = j + 1} ^ {T} (Y _ {t} - \mu) (Y _ {t - j} - \mu) \xrightarrow {p} \gamma_ {j}
$$

for all $j$ . Sufficient conditions for second-moment ergodicity will be presented in Chapter 7. In the special case where $\{Y_{t}\}$ is a stationary Gaussian process, condition [3.1.15] is sufficient to ensure ergodicity for all moments.

For many applications, stationarity and ergodicity turn out to amount to the same requirements. For purposes of clarifying the concepts of stationarity and ergodicity, however, it may be helpful to consider an example of a process that is stationary but not ergodic. Suppose the mean $\mu^{(i)}$ for the $i$ th realization $\{y_t^{(i)}\}_{t = -\infty}^{\infty}$ is generated from a $N(0,\lambda^2)$ distribution, say

$$
Y _ {t} ^ {(i)} = \mu^ {(i)} + \varepsilon_ {t}. \tag {3.1.16}
$$

Here $\{\varepsilon_{i}\}$ is a Gaussian white noise process with mean zero and variance $\sigma^2$ that is independent of $\mu^{(i)}$ . Notice that

$$
\mu_ {t} = E \left(\mu^ {(i)}\right) + E \left(\varepsilon_ {t}\right) = 0.
$$

Also,

$$
\gamma_ {0 t} = E \left(\mu^ {(i)} + \varepsilon_ {t}\right) ^ {2} = \lambda^ {2} + \sigma^ {2}
$$

and

$$
\gamma_ {j t} = E \left(\mu^ {(i)} + \varepsilon_ {t}\right) \left(\mu^ {(i)} + \varepsilon_ {t - j}\right) = \lambda^ {2} \quad \text {f o r} j \neq 0.
$$

Thus the process of [3.1.16] is covariance-stationary. It does not satisfy the sufficient condition [3.1.15] for ergodicity for the mean, however, and indeed, the time average

$$
(1 / T) \sum_ {t = 1} ^ {T} Y _ {t} ^ {(i)} = (1 / T) \sum_ {t = 1} ^ {T} \left(\mu^ {(i)} + \varepsilon_ {t}\right) = \mu^ {(i)} + (1 / T) \sum_ {t = 1} ^ {T} \varepsilon_ {t}
$$

converges to $\mu^{(i)}$ rather than to zero, the mean of $Y_{t}$

# 3.2. White Noise

The basic building block for all the processes considered in this chapter is a sequence $\{\varepsilon_{t}\}_{t = -\infty}^{\infty}$ whose elements have mean zero and variance $\sigma^2$

$$
E \left(\varepsilon_ {t}\right) = 0 \tag {3.2.1}
$$

$$
E \left(\varepsilon_ {t} ^ {2}\right) = \sigma^ {2}, \tag {3.2.2}
$$

and for which the $\varepsilon$ 's are uncorrelated across time:

$$
E \left(\varepsilon_ {t} \varepsilon_ {\tau}\right) = 0 \quad \text {f o r} t \neq \tau . \tag {3.2.3}
$$

A process satisfying [3.2.1] through [3.2.3] is described as a white noise process.

We shall on occasion wish to replace [3.2.3] with the slightly stronger condition that the $\varepsilon$ 's are independent across time:

$$
\varepsilon_ {t}, \varepsilon_ {\tau} \text {i n d e p e n d e n t f o r} t \neq \tau . \tag {3.2.4}
$$

Notice that [3.2.4] implies [3.2.3] but [3.2.3] does not imply [3.2.4]. A process satisfying [3.2.1] through [3.2.4] is called an independent white noise process.

Finally, if [3.2.1] through [3.2.4] hold along with

$$
\varepsilon_ {t} \sim N (0, \sigma^ {2}), \tag {3.2.5}
$$

then we have the Gaussian white noise process.

# 3.3. Moving Average Processes

The First-Order Moving Average Process

Let $\{\varepsilon_t\}$ be white noise as in [3.2.1] through [3.2.3], and consider the process

$$
Y _ {t} = \mu + \varepsilon_ {t} + \theta \varepsilon_ {t - 1}, \tag {3.3.1}
$$

where $\mu$ and $\theta$ could be any constants. This time series is called a first-order moving average process, denoted $MA(1)$ . The term "moving average" comes from the fact that $Y_{t}$ is constructed from a weighted sum, akin to an average, of the two most recent values of $\varepsilon$ .

The expectation of $Y_{t}$ is given by

$$
E \left(Y _ {t}\right) = E \left(\mu + \varepsilon_ {t} + \theta \varepsilon_ {t - 1}\right) = \mu + E \left(\varepsilon_ {t}\right) + \theta \cdot E \left(\varepsilon_ {t - 1}\right) = \mu . \tag {3.3.2}
$$

We used the symbol $\mu$ for the constant term in [3.3.1] in anticipation of the result that this constant term turns out to be the mean of the process.

The variance of $Y_{t}$ is

$$
\begin{array}{l} E \left(Y _ {t} - \mu\right) ^ {2} = E \left(\varepsilon_ {t} + \theta \varepsilon_ {t - 1}\right) ^ {2} \\ = E \left(\varepsilon_ {t} ^ {2} + 2 \theta \varepsilon_ {t} \varepsilon_ {t - 1} + \theta^ {2} \varepsilon_ {t - 1} ^ {2}\right) \tag {3.3.3} \\ = \sigma^ {2} + 0 + \theta^ {2} \sigma^ {2} \\ = (1 + \theta^ {2}) \sigma^ {2}. \\ \end{array}
$$

The first autocovariance is

$$
\begin{array}{l} E \left(Y _ {t} - \mu\right) \left(Y _ {t - 1} - \mu\right) = E \left(\varepsilon_ {t} + \theta \varepsilon_ {t - 1}\right) \left(\varepsilon_ {t - 1} + \theta \varepsilon_ {t - 2}\right) \\ = E \left(\varepsilon_ {t} \varepsilon_ {t - 1} + \theta \varepsilon_ {t - 1} ^ {2} + \theta \varepsilon_ {t} \varepsilon_ {t - 2} + \theta^ {2} \varepsilon_ {t - 1} \varepsilon_ {t - 2}\right) \tag {3.3.4} \\ = 0 + \theta \sigma^ {2} + 0 + 0. \\ \end{array}
$$

Higher autocovariances are all zero:

$$
E \left(Y _ {t} - \mu\right) \left(Y _ {t - j} - \mu\right) = E \left(\varepsilon_ {t} + \theta \varepsilon_ {t - 1}\right) \left(\varepsilon_ {t - j} + \theta \varepsilon_ {t - j - 1}\right) = 0 \quad \text {f o r} j > 1. \tag {3.3.5}
$$

Since the mean and autocovariances are not functions of time, an $MA(1)$ process is covariance-stationary regardless of the value of $\theta$ . Furthermore, [3.1.15] is clearly satisfied:

$$
\sum_ {j = 0} ^ {\infty} \left| \gamma_ {j} \right| = (1 + \theta^ {2}) \sigma^ {2} + \left| \theta \sigma^ {2} \right|.
$$

Thus, if $\{\varepsilon_t\}$ is Gaussian white noise, then the $MA(1)$ process [3.3.1] is ergodic for all moments.

The $j$ th autocorrelation of a covariance-stationary process (denoted $\rho_{j}$ ) is defined as its $j$ th autocovariance divided by the variance:

$$
\rho_ {j} \equiv \gamma_ {j} / \gamma_ {0}. \tag {3.3.6}
$$

Again the terminology arises from the fact that $\rho_{j}$ is the correlation between $Y_{t}$ and $Y_{t - j}$ :

$$
\operatorname {C o r r} \left(Y _ {t}, Y _ {t - j}\right) = \frac {\operatorname {C o v} \left(Y _ {t} , Y _ {t - j}\right)}{\sqrt {\operatorname {V a r} \left(Y _ {t}\right)} \sqrt {\operatorname {V a r} \left(Y _ {t - j}\right)}} = \frac {\gamma_ {j}}{\sqrt {\gamma_ {0}} \sqrt {\gamma_ {0}}} = \rho_ {j}.
$$

Since $\rho_{j}$ is a correlation, $|\rho_j| \leq 1$ for all $j$ , by the Cauchy-Schwarz inequality. Notice also that the 0th autocorrelation $\rho_0$ is equal to unity for any covariance-stationary process by definition.

From [3.3.3] and [3.3.4], the first autocorrelation for an $MA(1)$ process is given by

$$
\rho_ {1} = \frac {\theta \sigma^ {2}}{(1 + \theta^ {2}) \sigma^ {2}} = \frac {\theta}{(1 + \theta^ {2})}. \tag {3.3.7}
$$

Higher autocorrelations are all zero.

The autocorrelation $\rho_{j}$ can be plotted as a function of $j$ as in Figure 3.1. Panel (a) shows the autocorrelation function for white noise, while panel (b) gives the autocorrelation function for the $MA(1)$ process:

$$
Y _ {t} = \varepsilon_ {t} + 0. 8 \varepsilon_ {t - 1}.
$$

For different specifications of $\theta$ we would obtain different values for the first autocorrelation $\rho_{1}$ in [3.3.7]. Positive values of $\theta$ induce positive autocorrelation in the series. In this case, an unusually large value of $Y_{t}$ is likely to be followed by a larger-than-average value for $Y_{t + 1}$ , just as a smaller-than-average $Y_{t}$ may well be followed by a smaller-than-average $Y_{t + 1}$ . By contrast, negative values of $\theta$ imply negative autocorrelation—a large $Y_{t}$ might be expected to be followed by a small value for $Y_{t + 1}$ .

The values for $\rho_{1}$ implied by different specifications of $\theta$ are plotted in Figure 3.2. Notice that the largest possible value for $\rho_{1}$ is 0.5; this occurs if $\theta = 1$ . The smallest value for $\rho_{1}$ is -0.5, which occurs if $\theta = -1$ . For any value of $\rho_{1}$ between -0.5 and 0.5, there are two different values of $\theta$ that could produce that autocorrelation. This is because the value of $\theta / (1 + \theta^2)$ is unchanged if $\theta$ is replaced by $1 / \theta$ :

$$
\rho_ {1} = \frac {(1 / \theta)}{1 + (1 / \theta) ^ {2}} = \frac {\theta^ {2} \cdot (1 / \theta)}{\theta^ {2} [ 1 + (1 / \theta) ^ {2} ]} = \frac {\theta}{\theta^ {2} + 1}.
$$

For example, the processes

$$
Y _ {t} = \varepsilon_ {t} + 0. 5 \varepsilon_ {t - 1}
$$

and

$$
Y _ {t} = \varepsilon_ {t} + 2 \varepsilon_ {t - 1}
$$

would have the same autocorrelation function:

$$
\rho_ {1} = \frac {2}{(1 + 2 ^ {2})} = \frac {0 . 5}{(1 + 0 . 5 ^ {2})} = 0. 4.
$$

We will have more to say about the relation between two $MA(1)$ processes that share the same autocorrelation function in Section 3.7.

![](images/e01858ff2b466f810cd76a1790876f757064b85c79136be1b54ac1cf748fe16b.jpg)  
(a) White noise: $Y_{t} = \varepsilon_{t}$

![](images/4ed8d92420a03483bfb374c4a733ec3509c3d093d8a4e58a3c1691acd09f1ff7.jpg)  
(b) $MA(1): Y_{t} = \varepsilon_{t} + 0.8\varepsilon_{t - 1}$

![](images/af26846df50d49ff6c9a986889f5b2d583bd1f50c5983cce9ca8eba73675230d.jpg)  
(c) $MA(4): Y_{t} = \varepsilon_{t} - 0.6\varepsilon_{t-1} + 0.3\varepsilon_{t-2} - 0.5\varepsilon_{t-3} + 0.5\varepsilon_{t-4}$

![](images/58a379fc79817e559c0299365fb4da2eb83db40faf3102bf8d883d89e851e4ec.jpg)  
(d) $AR(1):Y_{t} = 0.8Y_{t - 1} + \varepsilon_{t}$

![](images/5b1f9c387a675b22e79ea1029fcfb53b4d0cfc62cbb01eac9a34963a3d7b210c.jpg)  
(e) $AR(1):Y_{t} = -0.8Y_{t - 1} + \varepsilon_{t}$   
FIGURE 3.1 Autocorrelation functions for assorted ARMA processes.

The qth-Order Moving Average Process

A qth-order moving average process, denoted $MA(q)$ , is characterized by

$$
Y _ {t} = \mu + \varepsilon_ {t} + \theta_ {1} \varepsilon_ {t - 1} + \theta_ {2} \varepsilon_ {t - 2} + \dots + \theta_ {q} \varepsilon_ {t - q}, \tag {3.3.8}
$$

where $\{\varepsilon_t\}$ satisfies [3.2.1] through [3.2.3] and $(\theta_1, \theta_2, \ldots, \theta_q)$ could be any real numbers. The mean of [3.3.8] is again given by $\mu$ :

$$
E (Y _ {t}) = \mu + E (\varepsilon_ {t}) + \theta_ {1} \cdot E (\varepsilon_ {t - 1}) + \theta_ {2} \cdot E (\varepsilon_ {t - 2}) + \dots + \theta_ {q} \cdot E (\varepsilon_ {t - q}) = \mu .
$$

The variance of an $MA(q)$ process is

$$
\gamma_ {0} = E \left(Y _ {t} - \mu\right) ^ {2} = E \left(\varepsilon_ {t} + \theta_ {1} \varepsilon_ {t - 1} + \theta_ {2} \varepsilon_ {t - 2} + \dots + \theta_ {q} \varepsilon_ {t - q}\right) ^ {2}. \tag {3.3.9}
$$

![](images/cb4fda8dbfc1fe7fcdbb0678d428cf6d5de9c468ccc9a7e89afdbe8d84718371.jpg)  
FIGURE 3.2 The first autocorrelation $(\rho_{1})$ for an $MA(1)$ process possible for different values of $\theta$ .

Since the $\varepsilon$ 's are uncorrelated, the variance [3.3.9] is<sup>2</sup>

$$
\gamma_ {0} = \sigma^ {2} + \theta_ {1} ^ {2} \sigma^ {2} + \theta_ {2} ^ {2} \sigma^ {2} + \dots + \theta_ {q} ^ {2} \sigma^ {2} = (1 + \theta_ {1} ^ {2} + \theta_ {2} ^ {2} + \dots + \theta_ {q} ^ {2}) \sigma^ {2}. \quad [ 3. 3. 1 0 ]
$$

For $j = 1,2,\dots ,q$

$$
\begin{array}{l} \gamma_ {j} = E \left[ \left(\varepsilon_ {t} + \theta_ {1} \varepsilon_ {t - 1} + \theta_ {2} \varepsilon_ {t - 2} + \dots + \theta_ {q} \varepsilon_ {t - q}\right) \right. \\ \times \left(\varepsilon_ {t - j} + \theta_ {1} \varepsilon_ {t - j - 1} + \theta_ {2} \varepsilon_ {t - j - 2} + \dots + \theta_ {q} \varepsilon_ {t - j - q}\right) ] \tag {3.3.11} \\ = E \left[ \theta_ {j} \varepsilon_ {t - j} ^ {2} + \theta_ {j + 1} \theta_ {1} \varepsilon_ {t - j - 1} ^ {2} + \theta_ {j + 2} \theta_ {2} \varepsilon_ {t - j - 2} ^ {2} + \dots + \theta_ {q} \theta_ {q - j} \varepsilon_ {t - q} ^ {2} \right]. \\ \end{array}
$$

Terms involving $\varepsilon$ 's at different dates have been dropped because their product has expectation zero, and $\theta_0$ is defined to be unity. For $j > q$ , there are no $\varepsilon$ 's with common dates in the definition of $\gamma_j$ , and so the expectation is zero. Thus,

$$
\gamma_ {j} = \left\{ \begin{array}{l l} {\left[ \theta_ {j} + \theta_ {j + 1} \theta_ {1} + \theta_ {j + 2} \theta_ {2} + \dots + \theta_ {q} \theta_ {q - j} \right] \cdot \sigma^ {2}} & {\text {f o r} j = 1, 2, \dots , q} \\ 0 & {\text {f o r} j > q.} \end{array} \right.
$$

For example, for an $MA(2)$ process,

$$
\gamma_ {0} = \left[ 1 + \theta_ {1} ^ {2} + \theta_ {2} ^ {2} \right] \cdot \sigma^ {2}
$$

$$
\gamma_ {1} = \left[ \theta_ {1} + \theta_ {2} \theta_ {1} \right] \cdot \sigma^ {2}
$$

$$
\gamma_ {2} = \left[ \theta_ {2} \right] \cdot \sigma^ {2}
$$

$$
\gamma_ {3} = \gamma_ {4} = \dots = 0.
$$

For any values of $(\theta_{1},\theta_{2},\ldots ,\theta_{q})$ , the $MA(q)$ process is thus covariance-stationary. Condition [3.1.15] is satisfied, so for Gaussian $\varepsilon_{t}$ the $MA(q)$ process is also ergodic for all moments. The autocorrelation function is zero after $q$ lags, as in panel (c) of Figure 3.1.

# The Infinite-Order Moving Average Process

The $MA(q)$ process can be written

$$
Y _ {t} = \mu + \sum_ {j = 0} ^ {q} \theta_ {j} \varepsilon_ {t - j}
$$

2See equation [A.5.18] in Appendix A at the end of the book.

with $\theta_0\equiv 1$ . Consider the process that results as $q\to \infty$ ..

$$
Y _ {t} = \mu + \sum_ {j = 0} ^ {\infty} \psi_ {j} \varepsilon_ {t - j} = \mu + \psi_ {0} \varepsilon_ {t} + \psi_ {1} \varepsilon_ {t - 1} + \psi_ {2} \varepsilon_ {t - 2} + \dots . \tag {3.3.13}
$$

This could be described as an $MA(\infty)$ process. To preserve notational flexibility later, we will use $\psi$ 's for the coefficients of an infinite-order moving average process and $\theta$ 's for the coefficients of a finite-order moving average process.

Appendix 3.A to this chapter shows that the infinite sequence in [3.3.13] generates a well defined covariance-stationary process provided that

$$
\sum_ {j = 0} ^ {\infty} \psi_ {j} ^ {2} <   \infty . \tag {3.3.14}
$$

It is often convenient to work with a slightly stronger condition than [3.3.14]:

$$
\sum_ {j = 0} ^ {\infty} | \psi_ {j} | <   \infty . \tag {3.3.15}
$$

A sequence of numbers $\{\psi_j\}_{j=0}^{\infty}$ satisfying [3.3.14] is said to be square summable, whereas a sequence satisfying [3.3.15] is said to be absolutely summable. Absolute summability implies square-summability, but the converse does not hold—there are examples of square-summable sequences that are not absolutely summable (again, see Appendix 3.A).

The mean and autocovariances of an $MA(\infty)$ process with absolutely summable coefficients can be calculated from a simple extrapolation of the results for an $MA(q)$ process:

$$
\begin{array}{l} E \left(Y _ {t}\right) = \lim  _ {T \rightarrow \infty} E \left(\mu + \psi_ {0} \varepsilon_ {t} + \psi_ {1} \varepsilon_ {t - 1} + \psi_ {2} \varepsilon_ {t - 2} + \dots + \psi_ {T} \varepsilon_ {t - T}\right) \tag {3.3.16} \\ = \mu \\ \end{array}
$$

$$
\begin{array}{l} \gamma_ {0} = E \left(Y _ {t} - \mu\right) ^ {2} \\ = \lim  _ {T \rightarrow \infty} E \left(\psi_ {0} \varepsilon_ {t} + \psi_ {1} \varepsilon_ {t - 1} + \psi_ {2} \varepsilon_ {t - 2} + \dots + \psi_ {T} \varepsilon_ {t - T}\right) ^ {2} \tag {3.3.17} \\ = \lim  _ {T \rightarrow \infty} \left(\psi_ {0} ^ {2} + \psi_ {1} ^ {2} + \psi_ {2} ^ {2} + \dots + \psi_ {T} ^ {2}\right) \cdot \sigma^ {2} \\ \end{array}
$$

$$
\begin{array}{l} \gamma_ {j} = E \left(Y _ {t} - \mu\right) \left(Y _ {t - j} - \mu\right) \tag {3.3.18} \\ = \sigma^ {2} \left(\psi_ {j} \psi_ {0} + \psi_ {j + 1} \psi_ {1} + \psi_ {j + 2} \psi_ {2} + \psi_ {j + 3} \psi_ {3} + \dots\right). \\ \end{array}
$$

Moreover, an $MA(\infty)$ process with absolutely summable coefficients has absolutely summable autocovariances:

$$
\sum_ {j = 0} ^ {\infty} \left| \gamma_ {j} \right| <   \infty . \tag {3.3.19}
$$

Hence, an $MA(\infty)$ process satisfying [3.3.15] is ergodic for the mean (see Appendix 3.A). If the $\varepsilon$ 's are Gaussian, then the process is ergodic for all moments.

3Absolute summability of $\{\psi_j\}_{j = 0}^{\infty}$ and existence of the second moment $E(\varepsilon_t^2)$ are sufficient conditions to permit interchanging the order of integration and summation. Specifically, if $\{X_T\}_{T = 1}^{\infty}$ is a sequence of random variables such that

$$
\sum_ {T = 1} ^ {\infty} E \left| X _ {T} \right| <   \infty ,
$$

then

$$
E \left\{\sum_ {T = 1} ^ {\infty} X _ {T} \right\} = \sum_ {T = 1} ^ {\infty} E (X _ {T}).
$$

See Rao (1973, p. 111).

# 3.4. Autoregressive Processes

# The First-Order Autoregressive Process

A first-order autoregression, denoted $AR(1)$ , satisfies the following difference equation:

$$
Y _ {t} = c + \phi Y _ {t - 1} + \varepsilon_ {t}. \tag {3.4.1}
$$

Again, $\{\varepsilon_t\}$ is a white noise sequence satisfying [3.2.1] through [3.2.3]. Notice that [3.4.1] takes the form of the first-order difference equation [1.1.1] or [2.2.1] in which the input variable $w_{t}$ is given by $w_{t} = c + \varepsilon_{t}$ . We know from the analysis of first-order difference equations that if $|\phi |\geq 1$ , the consequences of the $\varepsilon$ ’s for $Y$ accumulate rather than die out over time. It is thus perhaps not surprising that when $|\phi |\geq 1$ , there does not exist a covariance-stationary process for $Y_{t}$ with finite variance that satisfies [3.4.1]. In the case when $|\phi | < 1$ , there is a covariance-stationary process for $Y_{t}$ satisfying [3.4.1]. It is given by the stable solution to [3.4.1] characterized in [2.2.9]:

$$
\begin{array}{l} Y _ {t} = \left(c + \varepsilon_ {t}\right) + \phi \cdot \left(c + \varepsilon_ {t - 1}\right) + \phi^ {2} \cdot \left(c + \varepsilon_ {t - 2}\right) + \phi^ {3} \cdot \left(c + \varepsilon_ {t - 3}\right) + \dots \\ = \left[ c / (1 - \phi) \right] + \varepsilon_ {t} + \phi \varepsilon_ {t - 1} + \phi^ {2} \varepsilon_ {t - 2} + \phi^ {3} \varepsilon_ {t - 3} + \dots . \tag {3.4.2} \\ \end{array}
$$

This can be viewed as an $MA(\infty)$ process as in [3.3.13] with $\psi_j$ given by $\phi^j$ . When $|\phi| < 1$ , condition [3.3.15] is satisfied:

$$
\sum_ {j = 0} ^ {\infty} \left| \psi_ {j} \right| = \sum_ {j = 0} ^ {\infty} \left| \phi \right| ^ {j},
$$

which equals $1 / (1 - |\phi|)$ provided that $|\phi| < 1$ . The remainder of this discussion of first-order autoregressive processes assumes that $|\phi| < 1$ . This ensures that the $MA(\infty)$ representation exists and can be manipulated in the obvious way, and that the $AR(1)$ process is ergodic for the mean.

Taking expectations of [3.4.2], we see that

$$
E (Y _ {t}) = [ c / (1 - \phi) ] + 0 + 0 + \dots ,
$$

so that the mean of a stationary $AR(1)$ process is

$$
\mu = c / (1 - \phi). \tag {3.4.3}
$$

The variance is

$$
\begin{array}{l} \gamma_ {0} = E \left(Y _ {t} - \mu\right) ^ {2} \\ = E \left(\varepsilon_ {t} + \phi \varepsilon_ {t - 1} + \phi^ {2} \varepsilon_ {t - 2} + \phi^ {3} \varepsilon_ {t - 3} + \dots\right) ^ {2} \tag {3.4.4} \\ = \left(1 + \phi^ {2} + \phi^ {4} + \phi^ {6} + \dots\right) \cdot \sigma^ {2} \\ = \sigma^ {2} / (1 - \phi^ {2}), \\ \end{array}
$$

while the $j$ th autocovariance is

$$
\begin{array}{l} \gamma_ {j} = E \left(Y _ {t} - \mu\right) \left(Y _ {t - j} - \mu\right) \\ = E \left[ \varepsilon_ {t} + \phi \varepsilon_ {t - 1} + \phi^ {2} \varepsilon_ {t - 2} + \dots + \phi^ {j} \varepsilon_ {t - j} + \phi^ {j + 1} \varepsilon_ {t - j - 1} \right. \\ + \phi^ {j + 2} \varepsilon_ {t - j - 2} + \dots \cdot ] \times [ \varepsilon_ {t - j} + \phi \varepsilon_ {t - j - 1} + \phi^ {2} \varepsilon_ {t - j - 2} + \dots ] \quad [ 3. 4. 5 ] \\ = \left[ \phi^ {j} + \phi^ {j + 2} + \phi^ {j + 4} + \dots \cdot \right] \cdot \sigma^ {2} \\ = \phi^ {j} \left[ 1 + \phi^ {2} + \phi^ {4} + \dots \right] \cdot \sigma^ {2} \\ = \left[ \phi^ {j} / \left(1 - \phi^ {2}\right) \right] \cdot \sigma^ {2}. \\ \end{array}
$$

It follows from [3.4.4] and [3.4.5] that the autocorrelation function,

$$
\rho_ {j} = \gamma_ {j} / \gamma_ {0} = \phi^ {j}, \tag {3.4.6}
$$

follows a pattern of geometric decay as in panel (d) of Figure 3.1. Indeed, the autocorrelation function [3.4.6] for a stationary $AR(1)$ process is identical to the dynamic multiplier or impulse-response function [1.1.10]; the effect of a one-unit increase in $\varepsilon_{t}$ on $Y_{t+j}$ is equal to the correlation between $Y_{t}$ and $Y_{t+j}$ . A positive value of $\phi$ , like a positive value of $\theta$ for an $MA(1)$ process, implies positive correlation between $Y_{t}$ and $Y_{t+1}$ . A negative value of $\phi$ implies negative first-order but positive second-order autocorrelation, as in panel (e) of Figure 3.1.

Figure 3.3 shows the effect on the appearance of the time series $\{y_{t}\}$ of varying the parameter $\phi$ . The panels show realizations of the process in [3.4.1] with $c = 0$ and $\varepsilon_{t} \sim N(0, 1)$ for different values of the autoregressive parameter $\phi$ . Panel (a) displays white noise ( $\phi = 0$ ). A series with no autocorrelation looks choppy and patternless to the eye; the value of one observation gives no information about the value of the next observation. For $\phi = 0.5$ (panel (b)), the series seems smoother, with observations above or below the mean often appearing in clusters of modest duration. For $\phi = 0.9$ (panel (c)), departures from the mean can be quite prolonged; strong shocks take considerable time to die out.

The moments for a stationary $AR(1)$ were derived above by viewing it as an $MA(\infty)$ process. A second way to arrive at the same results is to assume that the process is covariance-stationary and calculate the moments directly from the difference equation [3.4.1]. Taking expectations of both sides of [3.4.1],

$$
E \left(Y _ {t}\right) = c + \phi \cdot E \left(Y _ {t - 1}\right) + E \left(\varepsilon_ {t}\right). \tag {3.4.7}
$$

Assuming that the process is covariance-stationary,

$$
E \left(Y _ {t}\right) = E \left(Y _ {t - 1}\right) = \mu . \tag {3.4.8}
$$

Substituting [3.4.8] into [3.4.7],

$$
\mu = c + \phi \mu + 0
$$

or

$$
\mu = c / (1 - \phi), \tag {3.4.9}
$$

reproducing the earlier result [3.4.3].

Notice that formula [3.4.9] is clearly not generating a sensible statement if $|\phi| \geq 1$ . For example, if $c > 0$ and $\phi > 1$ , then $Y_{t}$ in [3.4.1] is equal to a positive constant plus a positive number times its lagged value plus a mean-zero random variable. Yet [3.4.9] seems to assert that $Y_{t}$ would be negative on average for such a process! The reason that formula [3.4.9] is not valid when $|\phi| \geq 1$ is that we assumed in [3.4.8] that $Y_{t}$ is covariance-stationary, an assumption which is not correct when $|\phi| \geq 1$ .

To find the second moments of $Y_{t}$ in an analogous manner, use [3.4.3] to rewrite [3.4.1] as

$$
Y _ {t} = \mu (1 - \phi) + \phi Y _ {t - 1} + \varepsilon_ {t}
$$

or

$$
(Y _ {t} - \mu) = \phi \left(Y _ {t - 1} - \mu\right) + \varepsilon_ {t}. \tag {3.4.10}
$$

Now square both sides of [3.4.10] and take expectations:

$$
E \left(Y _ {t} - \mu\right) ^ {2} = \phi^ {2} E \left(Y _ {t - 1} - \mu\right) ^ {2} + 2 \phi E \left[ \left(Y _ {t - 1} - \mu\right) \varepsilon_ {t} \right] + E \left(\varepsilon_ {t} ^ {2}\right). \tag {3.4.11}
$$

![](images/cf72edf2da9cb199c181bae81f429bfa4861b50b0d00d24300770775e80e1264.jpg)  
(a) $\phi = 0$ (white noise)

![](images/db064347e496f5999719feee427c80f3e9a498cea87d17809f33807bff58b380.jpg)  
(b) $\phi = 0.5$

![](images/56badad677005d74e1ff02e4dafd067940a7188ab53baac480e55ab6e6a4c736.jpg)  
(c) $\phi = 0.9$   
FIGURE 3.3 Realizations of an $AR(1)$ process, $Y_{t} = \phi Y_{t - 1} + \varepsilon_{t}$ , for alternative values of $\phi$ .

Recall from [3.4.2] that $(Y_{t - 1} - \mu)$ is a linear function of $\varepsilon_{t - 1},\varepsilon_{t - 2},\ldots$

$$
(Y _ {t - 1} - \mu) = \varepsilon_ {t - 1} + \phi \varepsilon_ {t - 2} + \phi^ {2} \varepsilon_ {t - 3} + \dots .
$$

But $\varepsilon_{t}$ is uncorrelated with $\varepsilon_{t - 1},\varepsilon_{t - 2},\ldots$ , so $\varepsilon_{t}$ must be uncorrelated with $(Y_{t - 1} - \mu)$ . Thus the middle term on the right side of [3.4.11] is zero:

$$
E \left[ \left(Y _ {t - 1} - \mu\right) \varepsilon_ {t} \right] = 0. \tag {3.4.12}
$$

Again, assuming covariance-stationarity, we have

$$
E \left(Y _ {t} - \mu\right) ^ {2} = E \left(Y _ {t - 1} - \mu\right) ^ {2} = \gamma_ {0}. \tag {3.4.13}
$$

Substituting [3.4.13] and [3.4.12] into [3.4.11],

$$
\gamma_ {0} = \phi^ {2} \gamma_ {0} + 0 + \sigma^ {2}
$$

or

$$
\gamma_ {0} = \sigma^ {2} / (1 - \phi^ {2}),
$$

reproducing [3.4.4].

Similarly, we could multiply [3.4.10] by $(Y_{t - j} - \mu)$ and take expectations:

$$
E \left[ \left(Y _ {t} - \mu\right) \left(Y _ {t - j} - \mu\right) \right]
$$

$$
= \phi \cdot E \left[ \left(Y _ {t - 1} - \mu\right) \left(Y _ {t - j} - \mu\right) \right] + E \left[ \varepsilon_ {t} \left(Y _ {t - j} - \mu\right) \right]. \tag {3.4.14}
$$

But the term $(Y_{t - j} - \mu)$ will be a linear function of $\varepsilon_{t - j}, \varepsilon_{t - j - 1}, \varepsilon_{t - j - 2}, \ldots$ , which, for $j > 0$ , will be uncorrelated with $\varepsilon_t$ . Thus, for $j > 0$ , the last term on the right side in [3.4.14] is zero. Notice, moreover, that the expression appearing in the first term on the right side of [3.4.14],

$$
E \left[ \left(Y _ {t - 1} - \mu\right) \left(Y _ {t - j} - \mu\right) \right],
$$

is the autocovariance of observations on $Y$ separated by $j - 1$ periods:

$$
E \left[ \left(Y _ {t - 1} - \mu\right) \left(Y _ {[ t - 1 ] - [ j - 1 ]} - \mu\right) \right] = \gamma_ {j - 1}.
$$

Thus, for $j > 0$ , [3.4.14] becomes

$$
\gamma_ {j} = \phi \gamma_ {j - 1}. \tag {3.4.15}
$$

Equation [3.4.15] takes the form of a first-order difference equation,

$$
y _ {t} = \phi y _ {t - 1} + w _ {t},
$$

in which the autocovariance $\gamma$ takes the place of the variable $y$ and in which the subscript $j$ (which indexes the order of the autocovariance) replaces $t$ (which indexes time). The input $w_{t}$ in [3.4.15] is identically equal to zero. It is easy to see that the difference equation [3.4.15] has the solution

$$
\gamma_ {j} = \phi^ {j} \gamma_ {0},
$$

which reproduces [3.4.6]. We now see why the impulse-response function and autocorrelation function for an $AR(1)$ process coincide—they both represent the solution to a first-order difference equation with autoregressive parameter $\phi$ , an initial value of unity, and no subsequent shocks.

The Second-Order Autoregressive Process

A second-order autoregression, denoted $AR(2)$ , satisfies

$$
Y _ {t} = c + \phi_ {1} Y _ {t - 1} + \phi_ {2} Y _ {t - 2} + \varepsilon_ {t}, \tag {3.4.16}
$$

or, in lag operator notation,

$$
\left(1 - \phi_ {1} L - \phi_ {2} L ^ {2}\right) Y _ {t} = c + \varepsilon_ {t}. \tag {3.4.17}
$$

The difference equation [3.4.16] is stable provided that the roots of

$$
(1 - \phi_ {1} z - \phi_ {2} z ^ {2}) = 0 \tag {3.4.18}
$$

lie outside the unit circle. When this condition is satisfied, the $AR(2)$ process turns out to be covariance-stationary, and the inverse of the autoregressive operator in [3.4.17] is given by

$$
\psi (L) = \left(1 - \phi_ {1} L - \phi_ {2} L ^ {2}\right) ^ {- 1} = \psi_ {0} + \psi_ {1} L + \psi_ {2} L ^ {2} + \psi_ {3} L ^ {3} + \dots . \tag {3.4.19}
$$

Recalling [1.2.44], the value of $\psi_{j}$ can be found from the (1, 1) element of the matrix $\mathbf{F}$ raised to the $j$ th power, as in expression [1.2.28]. Where the roots of [3.4.18] are distinct, a closed-form expression for $\psi_{j}$ is given by [1.2.29] and [1.2.25]. Exercise 3.3 at the end of this chapter discusses alternative algorithms for calculating $\psi_{j}$ .

Multiplying both sides of [3.4.17] by $\psi (L)$ gives

$$
Y _ {t} = \psi (L) c + \psi (L) \varepsilon_ {t}. \tag {3.4.20}
$$

It is straightforward to show that

$$
\psi (L) c = c / \left(1 - \phi_ {1} - \phi_ {2}\right) \tag {3.4.21}
$$

and

$$
\sum_ {j = 0} ^ {\infty} \left| \psi_ {j} \right| <   \infty ; \tag {3.4.22}
$$

the reader is invited to prove these claims in Exercises 3.4 and 3.5. Since [3.4.20] is an absolutely summable $MA(\infty)$ process, its mean is given by the constant term:

$$
\mu = c / \left(1 - \phi_ {1} - \phi_ {2}\right). \tag {3.4.23}
$$

An alternative method for calculating the mean is to assume that the process is covariance-stationary and take expectations of [3.4.16] directly:

$$
E \left(Y _ {t}\right) = c + \phi_ {1} E \left(Y _ {t - 1}\right) + \phi_ {2} E \left(Y _ {t - 2}\right) + E \left(\varepsilon_ {t}\right),
$$

implying

$$
\mu = c + \phi_ {1} \mu + \phi_ {2} \mu + 0,
$$

reproducing [3.4.23].

To find second moments, write [3.4.16] as

$$
Y _ {t} = \mu \cdot \left(1 - \phi_ {1} - \phi_ {2}\right) + \phi_ {1} Y _ {t - 1} + \phi_ {2} Y _ {t - 2} + \varepsilon_ {t}
$$

or

$$
(Y _ {t} - \mu) = \phi_ {1} \left(Y _ {t - 1} - \mu\right) + \phi_ {2} \left(Y _ {t - 2} - \mu\right) + \varepsilon_ {t}. \tag {3.4.24}
$$

Multiplying both sides of [3.4.24] by $(Y_{t - j} - \mu)$ and taking expectations produces

$$
\gamma_ {j} = \phi_ {1} \gamma_ {j - 1} + \phi_ {2} \gamma_ {j - 2} \quad \text {f o r} j = 1, 2, \dots . \tag {3.4.25}
$$

Thus, the autocovariances follow the same second-order difference equation as does the process for $Y_{t}$ , with the difference equation for $\gamma_{j}$ indexed by the lag $j$ . The autocovariances therefore behave just as the solutions to the second-order difference equation analyzed in Section 1.2. An $AR(2)$ process is covariance-stationary provided that $\phi_{1}$ and $\phi_{2}$ lie within the triangular region of Figure 1.5.

When $\phi_1$ and $\phi_2$ lie within the triangular region but above the parabola in that figure, the autocovariance function $\gamma_j$ is the sum of two decaying exponential functions of $j$ . When $\phi_1$ and $\phi_2$ fall within the triangular region but below the parabola, $\gamma_j$ is a damped sinusoidal function.

The autocorrelations are found by dividing both sides of [3.4.25] by $\gamma_0$ :

$$
\rho_ {j} = \phi_ {1} \rho_ {j - 1} + \phi_ {2} \rho_ {j - 2} \quad \text {f o r} j = 1, 2, \dots . \tag {3.4.26}
$$

In particular, setting $j = 1$ produces

$$
\rho_ {1} = \phi_ {1} + \phi_ {2} \rho_ {1}
$$

or

$$
\rho_ {1} = \phi_ {1} / (1 - \phi_ {2}). \tag {3.4.27}
$$

For $j = 2$

$$
\rho_ {2} = \phi_ {1} \rho_ {1} + \phi_ {2}. \tag {3.4.28}
$$

The variance of a covariance-stationary second-order autoregression can be found by multiplying both sides of [3.4.24] by $(Y_{t} - \mu)$ and taking expectations:

$$
\begin{array}{l} E \left(Y _ {t} - \mu\right) ^ {2} = \phi_ {1} \cdot E \left(Y _ {t - 1} - \mu\right) \left(Y _ {t} - \mu\right) + \phi_ {2} \cdot E \left(Y _ {t - 2} - \mu\right) \left(Y _ {t} - \mu\right) \\ + E \left(\varepsilon_ {t}\right) \left(Y _ {t} - \mu\right), \\ \end{array}
$$

or

$$
\gamma_ {0} = \phi_ {1} \gamma_ {1} + \phi_ {2} \gamma_ {2} + \sigma^ {2}. \tag {3.4.29}
$$

The last term $(\sigma^2)$ in [3.4.29] comes from noticing that

$$
\begin{array}{l} E \left(\varepsilon_ {t}\right) \left(Y _ {t} - \mu\right) = E \left(\varepsilon_ {t}\right) \left[ \phi_ {1} \left(Y _ {t - 1} - \mu\right) + \phi_ {2} \left(Y _ {t - 2} - \mu\right) + \varepsilon_ {t} \right] \\ = \phi_ {1} \cdot 0 + \phi_ {2} \cdot 0 + \sigma^ {2}. \\ \end{array}
$$

Equation [3.4.29] can be written

$$
\gamma_ {0} = \phi_ {1} \rho_ {1} \gamma_ {0} + \phi_ {2} \rho_ {2} \gamma_ {0} + \sigma^ {2}. \tag {3.4.30}
$$

Substituting [3.4.27] and [3.4.28] into [3.4.30] gives

$$
\gamma_ {0} = \left[ \frac {\phi_ {1} ^ {2}}{(1 - \phi_ {2})} + \frac {\phi_ {2} \phi_ {1} ^ {2}}{(1 - \phi_ {2})} + \phi_ {2} ^ {2} \right] \gamma_ {0} + \sigma^ {2}
$$

or

$$
\gamma_ {0} = \frac {(1 - \phi_ {2}) \sigma^ {2}}{(1 + \phi_ {2}) [ (1 - \phi_ {2}) ^ {2} - \phi_ {1} ^ {2} ]}.
$$

The pth-Order Autoregressive Process

A pth-order autoregression, denoted $AR(p)$ , satisfies

$$
Y _ {t} = c + \phi_ {1} Y _ {t - 1} + \phi_ {2} Y _ {t - 2} + \dots + \phi_ {p} Y _ {t - p} + \varepsilon_ {t}. \tag {3.4.31}
$$

Provided that the roots of

$$
1 - \phi_ {1} z - \phi_ {2} z ^ {2} - \dots - \phi_ {p} z ^ {p} = 0 \tag {3.4.32}
$$

all lie outside the unit circle, it is straightforward to verify that a covariance-stationary representation of the form

$$
Y _ {t} = \mu + \psi (L) \varepsilon_ {t} \tag {3.4.33}
$$

exists where

$$
\psi (L) = \left(1 - \phi_ {1} L - \phi_ {2} L ^ {2} - \dots - \phi_ {p} L ^ {p}\right) ^ {- 1}
$$

and $\Sigma_{j=0}^{\infty} |\psi_j| < \infty$ . Assuming that the stationarity condition is satisfied, one way to find the mean is to take expectations of [3.4.31]:

$$
\mu = c + \phi_ {1} \mu + \phi_ {2} \mu + \dots + \phi_ {p} \mu ,
$$

or

$$
\mu = c / \left(1 - \phi_ {1} - \phi_ {2} - \dots - \phi_ {p}\right). \tag {3.4.34}
$$

Using [3.4.34], equation [3.4.31] can be written

$$
\begin{array}{r l} Y _ {t} - \mu & = \phi_ {1} \left(Y _ {t - 1} - \mu\right) + \phi_ {2} \left(Y _ {t - 2} - \mu\right) + \dots \\ & + \phi_ {p} \left(Y _ {t - p} - \mu\right) + \varepsilon_ {t}. \end{array} \tag {3.4.35}
$$

Autocovariances are found by multiplying both sides of [3.4.35] by $(Y_{t - j} - \mu)$ and taking expectations:

$$
\gamma_ {j} = \left\{ \begin{array}{l l} \phi_ {1} \gamma_ {j - 1} + \phi_ {2} \gamma_ {j - 2} + \dots + \phi_ {p} \gamma_ {j - p} & \text {f o r} j = 1, 2, \dots \\ \phi_ {1} \gamma_ {1} + \phi_ {2} \gamma_ {2} + \dots + \phi_ {p} \gamma_ {p} + \sigma^ {2} & \text {f o r} j = 0. \end{array} \right. \tag {3.4.36}
$$

Using the fact that $\gamma_{-j} = \gamma_j$ , the system of equations in [3.4.36] for $j = 0, 1, \ldots, p$ can be solved for $\gamma_0, \gamma_1, \ldots, \gamma_p$ as functions of $\sigma^2$ , $\phi_1, \phi_2, \ldots, \phi_p$ . It can be shown<sup>4</sup> that the $(p \times 1)$ vector $(\gamma_0, \gamma_1, \ldots, \gamma_{p-1})'$ is given by the first $p$ elements of the first column of the $(p^2 \times p^2)$ matrix $\sigma^2[\mathbf{I}_{p^2} - (\mathbf{F} \otimes \mathbf{F})]^{-1}$ where $\mathbf{F}$ is the $(p \times p)$ matrix defined in equation [1.2.3] and $\otimes$ indicates the Kronecker product.

Dividing [3.4.36] by $\gamma_0$ produces the Yule-Walker equations:

$$
\rho_ {j} = \phi_ {1} \rho_ {j - 1} + \phi_ {2} \rho_ {j - 2} + \dots + \phi_ {p} \rho_ {j - p} \quad \text {f o r} j = 1, 2, \dots . \tag {3.4.37}
$$

Thus, the autocovariances and autocorrelations follow the same $p$ th-order difference equation as does the process itself [3.4.31]. For distinct roots, their solutions take the form

$$
\gamma_ {j} = g _ {1} \lambda_ {1} ^ {j} + g _ {2} \lambda_ {2} ^ {j} + \dots + g _ {p} \lambda_ {p} ^ {j}, \tag {3.4.38}
$$

where the eigenvalues $(\lambda_1, \dots, \lambda_p)$ are the solutions to

$$
\lambda^ {p} - \phi_ {1} \lambda^ {p - 1} - \phi_ {2} \lambda^ {p - 2} - \dots - \phi_ {p} = 0.
$$

# 3.5. Mixed Autoregressive Moving Average Processes

An $ARMA(p, q)$ process includes both autoregressive and moving average terms:

$$
\begin{array}{l} Y _ {t} = c + \phi_ {1} Y _ {t - 1} + \phi_ {2} Y _ {t - 2} + \dots + \phi_ {p} Y _ {t - p} + \varepsilon_ {t} + \theta_ {1} \varepsilon_ {t - 1} \tag {3.5.1} \\ + \theta_ {2} \varepsilon_ {t - 2} + \dots + \theta_ {q} \varepsilon_ {t - q}, \\ \end{array}
$$

or, in lag operator form,

$$
\begin{array}{l} (1 - \phi_ {1} L - \phi_ {2} L ^ {2} - \dots - \phi_ {p} L ^ {p}) Y _ {t} (3.5.2) \\ = c + \left(1 + \theta_ {1} L + \theta_ {2} L ^ {2} + \dots + \theta_ {q} L ^ {q}\right) \varepsilon_ {t}. (3.5.2) \\ \end{array}
$$

Provided that the roots of

$$
1 - \phi_ {1} z - \phi_ {2} z ^ {2} - \dots - \phi_ {p} z ^ {p} = 0 \tag {3.5.3}
$$

The reader will be invited to prove this in Exercise 10.1 in Chapter 10.

lie outside the unit circle, both sides of [3.5.2] can be divided by $(1 - \phi_1L - \phi_2L^2 -\dots -\phi_pL^p)$ to obtain

$$
Y _ {t} = \mu + \psi (L) \varepsilon_ {t}
$$

where

$$
\psi (L) = \frac {\left(1 + \theta_ {1} L + \theta_ {2} L ^ {2} + \cdots + \theta_ {q} L ^ {q}\right)}{\left(1 - \phi_ {1} L - \phi_ {2} L ^ {2} - \cdots - \phi_ {p} L ^ {p}\right)}
$$

$$
\sum_ {j = 0} ^ {\infty} | \psi_ {j} | <   \infty
$$

$$
\mu = c / \left(1 - \phi_ {1} - \phi_ {2} - \dots - \phi_ {p}\right).
$$

Thus, stationarity of an ARMA process depends entirely on the autoregressive parameters $(\phi_1,\phi_2,\ldots ,\phi_p)$ and not on the moving average parameters $(\theta_{1},\theta_{2},$ $\dots ,\theta_q)$

It is often convenient to write the ARMA process [3.5.1] in terms of deviations from the mean:

$$
\begin{array}{l} Y _ {t} - \mu = \phi_ {1} \left(Y _ {t - 1} - \mu\right) + \phi_ {2} \left(Y _ {t - 2} - \mu\right) + \dots \tag {3.5.4} \\ + \phi_ {p} \left(Y _ {t - p} - \mu\right) + \varepsilon_ {t} + \theta_ {1} \varepsilon_ {t - 1} + \theta_ {2} \varepsilon_ {t - 2} + \dots + \theta_ {q} \varepsilon_ {t - q}. \\ \end{array}
$$

Autocovariances are found by multiplying both sides of [3.5.4] by $(Y_{t - j} - \mu)$ and taking expectations. For $j > q$ , the resulting equations take the form

$$
\gamma_ {j} = \phi_ {1} \gamma_ {j - 1} + \phi_ {2} \gamma_ {j - 2} + \dots + \phi_ {p} \gamma_ {j - p} \quad \text {f o r} j = q + 1, q + 2, \dots . \tag {3.5.5}
$$

Thus, after $q$ lags the autocovariance function $\gamma_{j}$ (and the autocorrelation function $\rho_{j}$ ) follow the $p$ th-order difference equation governed by the autoregressive parameters.

Note that [3.5.5] does not hold for $j \leq q$ , owing to correlation between $\theta_{j} \varepsilon_{t - j}$ and $Y_{t - j}$ . Hence, an $ARMA(p,q)$ process will have more complicated autocovariances for lags 1 through $q$ than would the corresponding $AR(p)$ process. For $j > q$ with distinct autoregressive roots, the autocovariances will be given by

$$
\gamma_ {j} = h _ {1} \lambda_ {1} ^ {j} + h _ {2} \lambda_ {2} ^ {j} + \dots + h _ {p} \lambda_ {p} ^ {j}. \tag {3.5.6}
$$

This takes the same form as the autocovariances for an $AR(p)$ process [3.4.38], though because the initial conditions $(\gamma_0, \gamma_1, \ldots, \gamma_q)$ differ for the ARMA and $AR$ processes, the parameters $h_k$ in [3.5.6] will not be the same as the parameters $g_k$ in [3.4.38].

There is a potential for redundant parameterization with ARMA processes. Consider, for example, a simple white noise process,

$$
Y _ {t} = \varepsilon_ {t}. \tag {3.5.7}
$$

Suppose both sides of [3.5.7] are multiplied by $(1 - \rho L)$ :

$$
(1 - \rho L) Y _ {t} = (1 - \rho L) \varepsilon_ {t}. \tag {3.5.8}
$$

Clearly, if [3.5.7] is a valid representation, then so is [3.5.8] for any value of $\rho$ . Thus, [3.5.8] might be described as an $ARMA(1, 1)$ process, with $\phi_1 = \rho$ and $\theta_1 = -\rho$ . It is important to avoid such a parameterization. Since any value of $\rho$ in [3.5.8] describes the data equally well, we will obviously get into trouble trying to estimate the parameter $\rho$ in [3.5.8] by maximum likelihood. Moreover, theoretical manipulations based on a representation such as [3.5.8] may overlook key cancellations. If we are using an $ARMA(1, 1)$ model in which $\theta_1$ is close to $-\phi_1$ , then the data might better be modeled as simple white noise.

A related overparameterization can arise with an $ARMA(p,q)$ model. Consider factoring the lag polynomial operators in [3.5.2] as in [2.4.3]:

$$
\begin{array}{l} (1 - \lambda_ {1} L) (1 - \lambda_ {2} L) \dots (1 - \lambda_ {p} L) (Y _ {t} - \mu) \\ = (1 - \eta_ {1} L) (1 - \eta_ {2} L) \dots (1 - \eta_ {q} L) \varepsilon_ {t}. \tag {3.5.9} \\ \end{array}
$$

We assume that $|\lambda_i| < 1$ for all $i$ , so that the process is covariance-stationary. If the autoregressive operator $(1 - \phi_1L - \phi_2L^2 - \dots - \phi_pL^p)$ and the moving average operator $(1 + \theta_1L + \theta_2L^2 + \dots + \theta_qL^q)$ have any roots in common, say, $\lambda_i = \eta_j$ for some $i$ and $j$ , then both sides of [3.5.9] can be divided by $(1 - \lambda_iL)$ :

$$
\prod_{\substack{k = 1\\ k\neq i}}^{p}(1 - \lambda_{k}L)(Y_{i} - \mu) = \prod_{\substack{k = 1\\ k\neq j}}^{q}(1 - \eta_{k}L)\varepsilon_{i},
$$

or

$$
\begin{array}{l} \left(1 - \phi_ {1} ^ {*} L - \phi_ {2} ^ {*} L ^ {2} - \dots - \phi_ {p - 1} ^ {*} L ^ {p - 1}\right) \left(Y _ {t} - \mu\right) \\ = \left(1 + \theta_ {1} ^ {*} L + \theta_ {2} ^ {*} L ^ {2} + \dots + \theta_ {q - 1} ^ {*} L ^ {q - 1}\right) \varepsilon_ {t}, \tag {3.5.10} \\ \end{array}
$$

where

$$
\begin{array}{l} \left(1 - \phi_ {1} ^ {*} L - \phi_ {2} ^ {*} L ^ {2} - \dots - \phi_ {p - 1} ^ {*} L ^ {p - 1}\right) \\ \equiv (1 - \lambda_ {1} L) (1 - \lambda_ {2} L) \dots (1 - \lambda_ {i - 1} L) (1 - \lambda_ {i + 1} L) \dots (1 - \lambda_ {p} L) \\ \end{array}
$$

$$
\begin{array}{l} \left(1 + \theta_ {1} ^ {*} L + \theta_ {2} ^ {*} L ^ {2} + \dots + \theta_ {q - 1} ^ {*} L ^ {q - 1}\right) \\ \equiv (1 - \eta_ {1} L) (1 - \eta_ {2} L) \dots (1 - \eta_ {j - 1} L) (1 - \eta_ {j + 1} L) \dots (1 - \eta_ {q} L). \\ \end{array}
$$

The stationary $ARMA(p, q)$ process satisfying [3.5.2] is clearly identical to the stationary $ARMA(p - 1, q - 1)$ process satisfying [3.5.10].

# 3.6. The Autocovariance-Generating Function

For each of the covariance-stationary processes for $Y_{t}$ considered so far, we calculated the sequence of autocovariances $\{\gamma_j\}_{j = -\infty}^{\infty}$ . If this sequence is absolutely summable, then one way of summarizing the autocovariances is through a scalar-valued function called the autocovariance-generating function:

$$
g _ {Y} (z) = \sum_ {j = - \infty} ^ {\infty} \gamma_ {j} z ^ {j}. \tag {3.6.1}
$$

This function is constructed by taking the $j$ th autocovariance and multiplying it by some number $z$ raised to the $j$ th power, and then summing over all the possible values of $j$ . The argument of this function $(z)$ is taken to be a complex scalar.

Of particular interest as an argument for the autocovariance-generating function is any value of $z$ that lies on the complex unit circle,

$$
z = \cos (\omega) - i \sin (\omega) = e ^ {- i \omega},
$$

where $i = \sqrt{-1}$ and $\omega$ is the radian angle that $z$ makes with the real axis. If the autocovariance-generating function is evaluated at $z = e^{-i\omega}$ and divided by $2\pi$ , the resulting function of $\omega$ ,

$$
s _ {Y} (\omega) = \frac {1}{2 \pi} g _ {Y} (e ^ {- i \omega}) = \frac {1}{2 \pi} \sum_ {j = - \infty} ^ {\infty} \gamma_ {j} e ^ {- i \omega j},
$$

is called the population spectrum of $Y$ . The population spectrum will be discussed

in detail in Chapter 6. There it will be shown that for a process with absolutely summable autocovariances, the function $s_{Y}(\omega)$ exists and can be used to calculate all of the autocovariances. This means that if two different processes share the same autocovariance-generating function, then the two processes exhibit the identical sequence of autocovariances.

As an example of calculating an autocovariance-generating function, consider the $MA(1)$ process. From equations [3.3.3] to [3.3.5], its autocovariance-generating function is

$$
g _ {Y} (z) = \left[ \theta \sigma^ {2} \right] z ^ {- 1} + \left\{\left(1 + \theta^ {2}\right) \sigma^ {2} \right] z ^ {0} + \left[ \theta \sigma^ {2} \right] z ^ {1} = \sigma^ {2} \cdot \left[ \theta z ^ {- 1} + \left(1 + \theta^ {2}\right) + \theta z \right].
$$

Notice that this expression could alternatively be written

$$
g _ {Y} (z) = \sigma^ {2} (1 + \theta z) (1 + \theta z ^ {- 1}). \tag {3.6.2}
$$

The form of expression [3.6.2] suggests that for the $MA(q)$ process,

$$
Y _ {t} = \mu + (1 + \theta_ {1} L + \theta_ {2} L ^ {2} + \dots + \theta_ {q} L ^ {q}) \varepsilon_ {t},
$$

the autocovariance-generating function might be calculated as

$$
\begin{array}{l} g _ {Y} (z) = \sigma^ {2} \left(1 + \theta_ {1} z + \theta_ {2} z ^ {2} + \dots + \theta_ {q} z ^ {q}\right) \tag {3.6.3} \\ \times \left(1 + \theta_ {1} z ^ {- 1} + \theta_ {2} z ^ {- 2} + \dots + \theta_ {q} z ^ {- q}\right). \\ \end{array}
$$

This conjecture can be verified by carrying out the multiplication in [3.6.3] and collecting terms by powers of $z$ :

$$
\begin{array}{l} \left(1 + \theta_ {1} z + \theta_ {2} z ^ {2} + \dots + \theta_ {q} z ^ {q}\right) \times \left(1 + \theta_ {1} z ^ {- 1} + \theta_ {2} z ^ {- 2} + \dots + \theta_ {q} z ^ {- q}\right) \\ = \left(\theta_ {q}\right) z ^ {q} + \left(\theta_ {q - 1} + \theta_ {q} \theta_ {1}\right) z ^ {(q - 1)} + \left(\theta_ {q - 2} + \theta_ {q - 1} \theta_ {1} + \theta_ {q} \theta_ {2}\right) z ^ {(q - 2)} \\ + \dots + \left(\theta_ {1} + \theta_ {2} \theta_ {1} + \theta_ {3} \theta_ {2} + \dots + \theta_ {q} \theta_ {q - 1}\right) z ^ {1} \tag {3.6.4} \\ + \left(1 + \theta_ {1} ^ {2} + \theta_ {2} ^ {2} + \dots + \theta_ {q} ^ {2}\right) z ^ {0} \\ + \left(\theta_ {1} + \theta_ {2} \theta_ {1} + \theta_ {3} \theta_ {2} + \dots + \theta_ {q} \theta_ {q - 1}\right) z ^ {- 1} + \dots + \left(\theta_ {q}\right) z ^ {- q}. \\ \end{array}
$$

Comparison of [3.6.4] with [3.3.10] or [3.3.12] confirms that the coefficient on $z^j$ in [3.6.3] is indeed the $j$ th autocovariance.

This method for finding $g_{Y}(z)$ extends to the $MA(\infty)$ case. If

$$
Y _ {t} = \mu + \psi (L) \varepsilon_ {t} \tag {3.6.5}
$$

with

$$
\psi (L) = \psi_ {0} + \psi_ {1} L + \psi_ {2} L ^ {2} + \dots \tag {3.6.6}
$$

and

$$
\sum_ {j = 0} ^ {\infty} | \psi_ {j} | <   \infty , \tag {3.6.7}
$$

then

$$
g _ {Y} (z) = \sigma^ {2} \psi (z) \psi \left(z ^ {- 1}\right). \tag {3.6.8}
$$

For example, the stationary $AR(1)$ process can be written as

$$
Y _ {t} - \mu = (1 - \phi L) ^ {- 1} \varepsilon_ {r},
$$

which is in the form of [3.6.5] with $\psi(L) = 1/(1 - \phi L)$ . The autocovariance-generating function for an $AR(1)$ process could therefore be calculated from

$$
g _ {Y} (z) = \frac {\sigma^ {2}}{(1 - \phi z) (1 - \phi z ^ {- 1})}. \tag {3.6.9}
$$

To verify this claim directly, expand out the terms in [3.6.9]:

$$
\begin{array}{l} \frac {\sigma^ {2}}{(1 - \phi z) (1 - \phi z ^ {- 1})} = \sigma^ {2} (1 + \phi z + \phi^ {2} z ^ {2} + \phi^ {3} z ^ {3} + \dots) \\ \times \left(1 + \phi z ^ {- 1} + \phi^ {2} z ^ {- 2} + \phi^ {3} z ^ {- 3} + \dots\right), \\ \end{array}
$$

from which the coefficient on $z^j$ is

$$
\sigma^ {2} \left(\phi^ {j} + \phi^ {j + 1} \phi + \phi^ {j + 2} \phi^ {2} + \dots\right) = \sigma^ {2} \phi^ {j} / (1 - \phi^ {2}).
$$

This indeed yields the $j$ th autocovariance as earlier calculated in equation [3.4.5].

The autocovariance-generating function for a stationary $ARMA(p,q)$ process can be written

$$
g _ {Y} (z) = \frac {\sigma^ {2} \left(1 + \theta_ {1} z + \theta_ {2} z ^ {2} + \cdots + \theta_ {q} z ^ {q}\right) \left(1 + \theta_ {1} z ^ {- 1} + \theta_ {2} z ^ {- 2} + \cdots + \theta_ {q} z ^ {- q}\right)}{\left(1 - \phi_ {1} z - \phi_ {2} z ^ {2} - \cdots - \phi_ {p} z ^ {p}\right) \left(1 - \phi_ {1} z ^ {- 1} - \phi_ {2} z ^ {- 2} - \cdots - \phi_ {p} z ^ {- p}\right)}. \tag {3.6.10}
$$

# Filters

Sometimes the data are filtered, or treated in a particular way before they are analyzed, and we would like to summarize the effects of this treatment on the autocovariances. This calculation is particularly simple using the autocovariance-generating function. For example, suppose that the original data $Y_{t}$ were generated from an $MA(1)$ process,

$$
Y _ {t} = (1 + \theta L) \varepsilon_ {t}, \tag {3.6.11}
$$

with autocovariance-generating function given by [3.6.2]. Let's say that the data as actually analyzed, $X_{t}$ , represent the change in $Y_{t}$ over its value the previous period:

$$
X _ {t} = Y _ {t} - Y _ {t - 1} = (1 - L) Y _ {t}. \tag {3.6.12}
$$

Substituting [3.6.11] into [3.6.12], the observed data can be characterized as the following $MA(2)$ process,

$$
X _ {t} = (1 - L) (1 + \theta L) \varepsilon_ {t} = [ 1 + (\theta - 1) L - \theta L ^ {2} ] \varepsilon_ {t} \equiv [ 1 + \theta_ {1} L + \theta_ {2} L ^ {2} ] \varepsilon_ {t}, \quad [ 3. 6. 1 3 ]
$$

with $\theta_{1} \equiv (\theta - 1)$ and $\theta_{2} \equiv -\theta$ . The autocovariance-generating function of the observed data $X_{t}$ can be calculated by direct application of [3.6.3]:

$$
g _ {X} (z) = \sigma^ {2} \left(1 + \theta_ {1} z + \theta_ {2} z ^ {2}\right) \left(1 + \theta_ {1} z ^ {- 1} + \theta_ {2} z ^ {- 2}\right). \tag {3.6.14}
$$

It is often instructive, however, to keep the polynomial $(1 + \theta_{1}z + \theta_{2}z^{2})$ in its factored form of the first line of [3.6.13],

$$
(1 + \theta_ {1} z + \theta_ {2} z ^ {2}) = (1 - z) (1 + \theta z),
$$

in which case [3.6.14] could be written

$$
\begin{array}{l} g _ {X} (z) = \sigma^ {2} (1 - z) (1 + \theta z) (1 - z ^ {- 1}) (1 + \theta z ^ {- 1}) \tag {3.6.15} \\ = (1 - z) \left(1 - z ^ {- 1}\right) \cdot g _ {Y} (z). \\ \end{array}
$$

Of course, [3.6.14] and [3.6.15] represent the identical function of $z$ , and which way we choose to write it is simply a matter of convenience. Applying the filter

$(1 - L)$ to $Y_{t}$ thus results in multiplying its autocovariance-generating function by $(1 - z)(1 - z^{-1})$

This principle readily generalizes. Suppose that the original data series $\{Y_{t}\}$ satisfies [3.6.5] through [3.6.7]. Let's say the data are filtered according to

$$
X _ {t} = h (L) Y _ {t} \tag {3.6.16}
$$

with

$$
h (L) = \sum_ {j = - \infty} ^ {\infty} h _ {j} L ^ {j}
$$

$$
\sum_ {j = - \infty} ^ {\infty} | h _ {j} | <   \infty .
$$

Substituting [3.6.5] into [3.6.16], the observed data $X_{t}$ are then generated by

$$
X _ {t} = h (1) \mu + h (L) \psi (L) \varepsilon_ {t} \equiv \mu^ {*} + \psi^ {*} (L) \varepsilon_ {t},
$$

where $\mu^{*} \equiv h(1)\mu$ and $\psi^{*}(L) \equiv h(L)\psi(L)$ . The sequence of coefficients associated with the compound operator $\{\psi_j^*\}_{j = -\infty}^{\infty}$ turns out to be absolutely summable, and the autocovariance-generating function of $X_{t}$ can accordingly be calculated as

$$
g _ {X} (z) = \sigma^ {2} \psi^ {*} (z) \psi^ {*} (z ^ {- 1}) = \sigma^ {2} h (z) \psi (z) \psi (z ^ {- 1}) h (z ^ {- 1}) = h (z) h (z ^ {- 1}) g _ {Y} (z). \tag {3.6.17}
$$

Applying the filter $h(L)$ to a series thus results in multiplying its autocovariance-generating function by $h(z)h(z^{-1})$ .

# 3.7. Invertibility

Invertibility for the MA(1) Process

Consider an $MA(1)$ process,

$$
Y _ {t} - \mu = (1 + \theta L) \varepsilon_ {t}, \tag {3.7.1}
$$

with

$$
E (\varepsilon_ {t} \varepsilon_ {\tau}) = \left\{ \begin{array}{l l} \sigma^ {2} & \text {f o r} t = \tau \\ 0 & \text {o t h e r w i s e .} \end{array} \right.
$$

${}^{5}$ Specifically,

$$
\begin{array}{l} \psi^ {*} (z) = \left(\sum_ {j = - \infty} ^ {\infty} h _ {j} z ^ {j}\right) \left(\sum_ {k = 0} ^ {\infty} \psi_ {k} z ^ {k}\right) \\ = \left(\dots + h _ {- j} z ^ {- j} + h _ {- j + 1} z ^ {- j + 1} + \dots + h _ {- 1} z ^ {- 1} + h _ {0} z ^ {0} + h _ {1} z ^ {1} + \dots \right. \\ + h _ {j} z ^ {j} + h _ {j + 1} z ^ {j + 1} + \dots) (\psi_ {0} z ^ {0}) + \psi_ {1} z ^ {1} + \psi_ {2} z ^ {2} + \dots), \\ \end{array}
$$

from which the coefficient on $z^j$ is

$$
\psi_ {j} ^ {*} = h _ {j} \psi_ {0} + h _ {j - 1} \psi_ {1} + h _ {j - 2} \psi_ {2} + \dots = \sum_ {\nu = 0} ^ {\infty} h _ {j - \nu} \psi_ {\nu}.
$$

Then

$$
\sum_ {j = - \infty} ^ {\infty} | \psi_ {j} ^ {*} | = \sum_ {j = - \infty} ^ {\infty} \left| \sum_ {\nu = 0} ^ {\infty} h _ {j - \nu} \psi_ {\nu} \right| \leq \sum_ {j = - \infty} ^ {\infty} \sum_ {\nu = 0} ^ {\infty} | h _ {j - \nu} \psi_ {\nu} | = \sum_ {\nu = 0} ^ {\infty} | \psi_ {\nu} | \sum_ {j = - \infty} ^ {\infty} | h _ {j - \nu} | = \sum_ {\nu = 0} ^ {\infty} | \psi_ {\nu} | \sum_ {j = - \infty} ^ {\infty} | h _ {j} | <   \infty .
$$
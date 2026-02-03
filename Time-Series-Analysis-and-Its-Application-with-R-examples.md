Robert H.Shumway

David S.Stoffer

# and

With R Examples

# Springer Texts in Statistics

Series Editors

G. Casella   
S. Fienberg   
I. Olkin

# Time Series Analysis and Its Applications

With R Examples

Third edition

Prof. Robert H. Shumway Department of Statistics University of California Davis, California USA

Prof. David S. Stoffer Department of Statistics University of Pittsburgh Pittsburgh, Pennsylvania USA

ISSN 1431-875X ISBN 978-1-4419-7864-6 e-ISBN 978-1-4419-7865-3 DOI 10.1007/978-1-4419-7865-3 Springer New York Dordrecht Heidelberg London

$\circledcirc$ Springer Science+Business Media, LLC 2011

All rights reserved. This work may not be translated or copied in whole or in part without the written permission of the publisher (Springer Science+Business Media, LLC, 233 Spring Street, New York, NY 10013, USA), except for brief excerpts in connection with reviews or scholarly analysis. Use in connection with any form of information storage and retrieval, electronic adaptation, computer software, or by similar or dissimilar methodology now known or hereafter developed is forbidden.

The use in this publication of trade names, trademarks, service marks, and similar terms, even if they are not identified as such, is not to be taken as an expression of opinion as to whether or not they are subject to proprietary rights.

Printed on acid-free paper

Springer is part of Springer Science+Business Media (www.springer.com)

To my wife, Ruth, for her support and joie de vivre, and to the memory of my thesis adviser, Solomon Kullback.

R.H.S.

To my family and friends, who constantly remind me what is important.

D.S.S.

# Preface to the Third Edition

The goals of this book are to develop an appreciation for the richness and versatility of modern time series analysis as a tool for analyzing data, and still maintain a commitment to theoretical integrity, as exemplified by the seminal works of Brillinger (1975) and Hannan (1970) and the texts by Brockwell and Davis (1991) and Fuller (1995). The advent of inexpensive powerful computing has provided both real data and new software that can take one considerably beyond the fitting of simple time domain models, such as have been elegantly described in the landmark work of Box and Jenkins (1970). This book is designed to be useful as a text for courses in time series on several different levels and as a reference work for practitioners facing the analysis of timecorrelated data in the physical, biological, and social sciences.

We have used earlier versions of the text at both the undergraduate and graduate levels over the past decade. Our experience is that an undergraduate course can be accessible to students with a background in regression analysis and may include 1.1– 1.6, 2.1– 2.3, the results and numerical parts of 3.1– 3.9, and briefly the results and numerical parts of 4.1– 4.6. At the advanced undergraduate or master’s level, where the students have some mathematical statistics background, more detailed coverage of the same sections, with the inclusion of 2.4 and extra topics from Chapter 5 or Chapter 6 can be used as a one-semester course. Often, the extra topics are chosen by the students according to their interests. Finally, a two-semester upper-level graduate course for mathematics, statistics, and engineering graduate students can be crafted by adding selected theoretical appendices. For the upper-level graduate course, we should mention that we are striving for a broader but less rigorous level of coverage than that which is attained by Brockwell and Davis (1991), the classic entry at this level.

The major difference between this third edition of the text and the second edition is that we provide R code for almost all of the numerical examples. In addition, we provide an R supplement for the text that contains the data and scripts in a compressed file called tsa3.rda; the supplement is available on the website for the third edition, http://www.stat.pitt.edu/stoffer/tsa3/,

or one of its mirrors. On the website, we also provide the code used in each example so that the reader may simply copy-and-paste code directly into R. Specific details are given in Appendix R and on the website for the text. Appendix R is new to this edition, and it includes a small R tutorial as well as providing a reference for the data sets and scripts included in tsa3.rda. So there is no misunderstanding, we emphasize the fact that this text is about time series analysis, not about R. R code is provided simply to enhance the exposition by making the numerical examples reproducible.

We have tried, where possible, to keep the problem sets in order so that an instructor may have an easy time moving from the second edition to the third edition. However, some of the old problems have been revised and there are some new problems. Also, some of the data sets have been updated. We added one section in Chapter 5 on unit roots and enhanced some of the presentations throughout the text. The exposition on state-space modeling, ARMAX models, and (multivariate) regression with autocorrelated errors in Chapter 6 have been expanded. In this edition, we use standard R functions as much as possible, but we use our own scripts (included in tsa3.rda) when we feel it is necessary to avoid problems with a particular R function; these problems are discussed in detail on the website for the text under R Issues.

We thank John Kimmel, Executive Editor, Springer Statistics, for his guidance in the preparation and production of this edition of the text. We are grateful to Don Percival, University of Washington, for numerous suggestions that led to substantial improvement to the presentation in the second edition, and consequently in this edition. We thank Doug Wiens, University of Alberta, for help with some of the R code in Chapters 4 and 7, and for his many suggestions for improvement of the exposition. We are grateful for the continued help and advice of Pierre Duchesne, University of Montreal, and Alexander Aue, University of California, Davis. We also thank the many students and other readers who took the time to mention typographical errors and other corrections to the first and second editions. Finally, work on the this edition was supported by the National Science Foundation while one of us (D.S.S.) was working at the Foundation under the Intergovernmental Personnel Act.

Davis, CA

Pittsburgh, PA

September 2010

Robert H. Shumway

David S. Stoffer

# Contents

Preface to the Third Edition . vii

# 1 Characteristics of Time Series 1

1.1 Introduction 1   
1.2 The Nature of Time Series Data . . . 3   
1.3 Time Series Statistical Models 11   
1.4 Measures of Dependence: Autocorrelation and Cross-Correlation . 17   
1.5 Stationary Time Series . . 22   
1.6 Estimation of Correlation . 28   
1.7 Vector-Valued and Multidimensional Series 33   
Problems 39

# 2 Time Series Regression and Exploratory Data Analysis . . . . 47

2.1 Introduction 47   
2.2 Classical Regression in the Time Series Context . . . . 48   
2.3 Exploratory Data Analysis. . 57   
2.4 Smoothing in the Time Series Context 70

Problems 78

# 3 ARIMA Models 83

3.1 Introduction 83   
3.2 Autoregressive Moving Average Models 84   
3.3 Difference Equations . 97   
3.4 Autocorrelation and Partial Autocorrelation . 102   
3.5 Forecasting . 108   
3.6 Estimation 121   
3.7 Integrated Models for Nonstationary Data . 141   
3.8 Building ARIMA Models . 144   
3.9 Multiplicative Seasonal ARIMA Models . . . 154

Problems . 162

# 4 Spectral Analysis and Filtering . . 173

4.1 Introduction . 173   
4.2 Cyclical Behavior and Periodicity . . . . 175   
4.3 The Spectral Density . 180   
4.4 Periodogram and Discrete Fourier Transform . . 187   
4.5 Nonparametric Spectral Estimation . . . . 196   
4.6 Parametric Spectral Estimation . 212   
4.7 Multiple Series and Cross-Spectra . . . 216   
4.8 Linear Filters . . 221   
4.9 Dynamic Fourier Analysis and Wavelets . . . 228   
4.10 Lagged Regression Models . . 242   
4.11 Signal Extraction and Optimum Filtering . . . . . . 247   
4.12 Spectral Analysis of Multidimensional Series . . . . 252   
Problems . 255

# 5 Additional Time Domain Topics . 267

5.1 Introduction . 267   
5.2 Long Memory ARMA and Fractional Differencing . . . . . . . 267   
5.3 Unit Root Testing . 277   
5.4 GARCH Models . 280   
5.5 Threshold Models . 289   
5.6 Regression with Autocorrelated Errors . 293   
5.7 Lagged Regression: Transfer Function Modeling . . . . . . 296   
5.8 Multivariate ARMAX Models . . . 301

Problems . 315

# 6 State-Space Models . . 319

6.1 Introduction . 319   
6.2 Filtering, Smoothing, and Forecasting . 325   
6.3 Maximum Likelihood Estimation . 335   
6.4 Missing Data Modifications . 344   
6.5 Structural Models: Signal Extraction and Forecasting . . . . . . . . 350   
6.6 State-Space Models with Correlated Errors . 354

6.6.1 ARMAX Models . 355   
6.6.2 Multivariate Regression with Autocorrelated Errors . . . . 356

6.7 Bootstrapping State-Space Models . 359   
6.8 Dynamic Linear Models with Switching . . . 365   
6.9 Stochastic Volatility . 378   
6.10 Nonlinear and Non-normal State-Space Models Using Monte Carlo Methods . 387

Problems . 398

# 7 Statistical Methods in the Frequency Domain . . 405

7.1 Introduction . 405   
7.2 Spectral Matrices and Likelihood Functions . . . . . 409   
7.3 Regression for Jointly Stationary Series . . . . 410   
7.4 Regression with Deterministic Inputs . . . . 420   
7.5 Random Coefficient Regression . 429   
7.6 Analysis of Designed Experiments . . 434   
7.7 Discrimination and Cluster Analysis . . . . 450   
7.8 Principal Components and Factor Analysis . . . . 468   
7.9 The Spectral Envelope . 485

Problems 501

# Appendix A: Large Sample Theory . . . . . 507

A.1 Convergence Modes . . 507   
A.2 Central Limit Theorems . . 515   
A.3 The Mean and Autocorrelation Functions . . . . 518

# Appendix B: Time Domain Theory . . . . 527

B.1 Hilbert Spaces and the Projection Theorem . . . . 527   
B.2 Causal Conditions for ARMA Models . . . 531   
B.3 Large Sample Distribution of the AR(p) Conditional Least Squares Estimators 533   
B.4 The Wold Decomposition . . 537

# Appendix C: Spectral Domain Theory . . 539

C.1 Spectral Representation Theorem . . 539   
C.2 Large Sample Distribution of the DFT and Smoothed Periodogram 543   
C.3 The Complex Multivariate Normal Distribution . . . . . . 554

# Appendix R: R Supplement . 559

R.1 First Things First . 559

R.1.1 Included Data Sets . . 560   
R.1.2 Included Scripts . . 562

R.2 Getting Started . 567   
R.3 Time Series Primer . . 571

# References . . 577

# Index . . 591

# Characteristics of Time Series

# 1.1 Introduction

The analysis of experimental data that have been observed at different points in time leads to new and unique problems in statistical modeling and inference. The obvious correlation introduced by the sampling of adjacent points in time can severely restrict the applicability of the many conventional statistical methods traditionally dependent on the assumption that these adjacent observations are independent and identically distributed. The systematic approach by which one goes about answering the mathematical and statistical questions posed by these time correlations is commonly referred to as time series analysis.

The impact of time series analysis on scientific applications can be partially documented by producing an abbreviated listing of the diverse fields in which important time series problems may arise. For example, many familiar time series occur in the field of economics, where we are continually exposed to daily stock market quotations or monthly unemployment figures. Social scientists follow population series, such as birthrates or school enrollments. An epidemiologist might be interested in the number of influenza cases observed over some time period. In medicine, blood pressure measurements traced over time could be useful for evaluating drugs used in treating hypertension. Functional magnetic resonance imaging of brain-wave time series patterns might be used to study how the brain reacts to certain stimuli under various experimental conditions.

Many of the most intensive and sophisticated applications of time series methods have been to problems in the physical and environmental sciences. This fact accounts for the basic engineering flavor permeating the language of time series analysis. One of the earliest recorded series is the monthly sunspot numbers studied by Schuster (1906). More modern investigations may center on whether a warming is present in global temperature measurements

or whether levels of pollution may influence daily mortality in Los Angeles. The modeling of speech series is an important problem related to the efficient transmission of voice recordings. Common features in a time series characteristic known as the power spectrum are used to help computers recognize and translate speech. Geophysical time series such as those produced by yearly depositions of various kinds can provide long-range proxies for temperature and rainfall. Seismic recordings can aid in mapping fault lines or in distinguishing between earthquakes and nuclear explosions.

The above series are only examples of experimental databases that can be used to illustrate the process by which classical statistical methodology can be applied in the correlated time series framework. In our view, the first step in any time series investigation always involves careful scrutiny of the recorded data plotted over time. This scrutiny often suggests the method of analysis as well as statistics that will be of use in summarizing the information in the data. Before looking more closely at the particular statistical methods, it is appropriate to mention that two separate, but not necessarily mutually exclusive, approaches to time series analysis exist, commonly identified as the time domain approach and the frequency domain approach.

The time domain approach is generally motivated by the presumption that correlation between adjacent points in time is best explained in terms of a dependence of the current value on past values. The time domain approach focuses on modeling some future value of a time series as a parametric function of the current and past values. In this scenario, we begin with linear regressions of the present value of a time series on its own past values and on the past values of other series. This modeling leads one to use the results of the time domain approach as a forecasting tool and is particularly popular with economists for this reason.

One approach, advocated in the landmark work of Box and Jenkins (1970; see also Box et al., 1994), develops a systematic class of models called autoregressive integrated moving average (ARIMA) models to handle timecorrelated modeling and forecasting. The approach includes a provision for treating more than one input series through multivariate ARIMA or through transfer function modeling. The defining feature of these models is that they are multiplicative models, meaning that the observed data are assumed to result from products of factors involving differential or difference equation operators responding to a white noise input.

A more recent approach to the same problem uses additive models more familiar to statisticians. In this approach, the observed data are assumed to result from sums of series, each with a specified time series structure; for example, in economics, assume a series is generated as the sum of trend, a seasonal effect, and error. The state-space model that results is then treated by making judicious use of the celebrated Kalman filters and smoothers, developed originally for estimation and control in space applications. Two relatively complete presentations from this point of view are in Harvey (1991) and Kitagawa and Gersch (1996). Time series regression is introduced in Chapter 2, and ARIMA

and related time domain models are studied in Chapter 3, with the emphasis on classical, statistical, univariate linear regression. Special topics on time domain analysis are covered in Chapter 5; these topics include modern treatments of, for example, time series with long memory and GARCH models for the analysis of volatility. The state-space model, Kalman filtering and smoothing, and related topics are developed in Chapter 6.

Conversely, the frequency domain approach assumes the primary characteristics of interest in time series analyses relate to periodic or systematic sinusoidal variations found naturally in most data. These periodic variations are often caused by biological, physical, or environmental phenomena of interest. A series of periodic shocks may influence certain areas of the brain; wind may affect vibrations on an airplane wing; sea surface temperatures caused by El Ni˜no oscillations may affect the number of fish in the ocean. The study of periodicity extends to economics and social sciences, where one may be interested in yearly periodicities in such series as monthly unemployment or monthly birth rates.

In spectral analysis, the partition of the various kinds of periodic variation in a time series is accomplished by evaluating separately the variance associated with each periodicity of interest. This variance profile over frequency is called the power spectrum. In our view, no schism divides time domain and frequency domain methodology, although cliques are often formed that advocate primarily one or the other of the approaches to analyzing data. In many cases, the two approaches may produce similar answers for long series, but the comparative performance over short samples is better done in the time domain. In some cases, the frequency domain formulation simply provides a convenient means for carrying out what is conceptually a time domain calculation. Hopefully, this book will demonstrate that the best path to analyzing many data sets is to use the two approaches in a complementary fashion. Expositions emphasizing primarily the frequency domain approach can be found in Bloomfield (1976, 2000), Priestley (1981), or Jenkins and Watts (1968). On a more advanced level, Hannan (1970), Brillinger (1981, 2001), Brockwell and Davis (1991), and Fuller (1996) are available as theoretical sources. Our coverage of the frequency domain is given in Chapters 4 and 7.

The objective of this book is to provide a unified and reasonably complete exposition of statistical methods used in time series analysis, giving serious consideration to both the time and frequency domain approaches. Because a myriad of possible methods for analyzing any particular experimental series can exist, we have integrated real data from a number of subject fields into the exposition and have suggested methods for analyzing these data.

# 1.2 The Nature of Time Series Data

Some of the problems and questions of interest to the prospective time series analyst can best be exposed by considering real experimental data taken

![](images/7040d079d187ff6077e55306436745f616248570660309a840f544c0ea4d5e13.jpg)  
Fig. 1.1. Johnson & Johnson quarterly earnings per share, 84 quarters, 1960-I to 1980-IV.

from different subject areas. The following cases illustrate some of the common kinds of experimental time series data as well as some of the statistical questions that might be asked about such data.

# Example 1.1 Johnson & Johnson Quarterly Earnings

Figure 1.1 shows quarterly earnings per share for the U.S. company Johnson & Johnson, furnished by Professor Paul Griffin (personal communication) of the Graduate School of Management, University of California, Davis. There are 84 quarters (21 years) measured from the first quarter of 1960 to the last quarter of 1980. Modeling such series begins by observing the primary patterns in the time history. In this case, note the gradually increasing underlying trend and the rather regular variation superimposed on the trend that seems to repeat over quarters. Methods for analyzing data such as these are explored in Chapter 2 (see Problem 2.1) using regression techniques and in Chapter 6, 6.5, using structural equation modeling.

To plot the data using the R statistical package, type the following:1

1 load("tsa3.rda") # SEE THE FOOTNOTE   
2 plot(jj, type="o", ylab="Quarterly Earnings per Share")

# Example 1.2 Global Warming

Consider the global temperature series record shown in Figure 1.2. The data are the global mean land–ocean temperature index from 1880 to 2009, with

![](images/b157cd0615c2abb048473c04a767074389310bde607895713ce62549da3c630b.jpg)  
Fig. 1.2. Yearly average global temperature deviations (1880–2009) in degrees centigrade.

the base period 1951-1980. In particular, the data are deviations, measured in degrees centigrade, from the 1951-1980 average, and are an update of Hansen et al. (2006). We note an apparent upward trend in the series during the latter part of the twentieth century that has been used as an argument for the global warming hypothesis. Note also the leveling off at about 1935 and then another rather sharp upward trend at about 1970. The question of interest for global warming proponents and opponents is whether the overall trend is natural or whether it is caused by some human-induced interface. Problem 2.8 examines 634 years of glacial sediment data that might be taken as a long-term temperature proxy. Such percentage changes in temperature do not seem to be unusual over a time period of 100 years. Again, the question of trend is of more interest than particular periodicities.

The R code for this example is similar to the code in Example 1.1: 1 plot(gtemp, type="o", ylab="Global Temperature Deviations")

# Example 1.3 Speech Data

More involved questions develop in applications to the physical sciences. Figure 1.3 shows a small .1 second (1000 point) sample of recorded speech for the phrase $a a a \cdots h h $ , and we note the repetitive nature of the signal and the rather regular periodicities. One current problem of great interest is computer recognition of speech, which would require converting this particular signal into the recorded phrase $a a a \cdots h h $ . Spectral analysis can be used in this context to produce a signature of this phrase that can be compared with signatures of various library syllables to look for a match.

![](images/1380c798d73f5feddbfcf90784855600639cc87029bca326cc8b6a6fe7df091f.jpg)  
Fig. 1.3. Speech recording of the syllable aaa · · · hhh sampled at 10,000 points per second with $n = 1 0 2 0$ points.

One can immediately notice the rather regular repetition of small wavelets. The separation between the packets is known as the pitch period and represents the response of the vocal tract filter to a periodic sequence of pulses stimulated by the opening and closing of the glottis.

In R, you can reproduce Figure 1.3 as follows:

1 plot(speech)

# Example 1.4 New York Stock Exchange

As an example of financial time series data, Figure 1.4 shows the daily returns (or percent change) of the New York Stock Exchange (NYSE) from February 2, 1984 to December 31, 1991. It is easy to spot the crash of October 19, 1987 in the figure. The data shown in Figure 1.4 are typical of return data. The mean of the series appears to be stable with an average return of approximately zero, however, the volatility (or variability) of data changes over time. In fact, the data show volatility clustering; that is, highly volatile periods tend to be clustered together. A problem in the analysis of these type of financial data is to forecast the volatility of future returns. Models such as ARCH and GARCH models (Engle, 1982; Bollerslev, 1986) and stochastic volatility models (Harvey, Ruiz and Shephard, 1994) have been developed to handle these problems. We will discuss these models and the analysis of financial data in Chapters 5 and 6. The R code for this example is similar to the previous examples:

1 plot(nyse, ylab="NYSE Returns")

![](images/9fb783df5bbc718121b36eebc17c79ef761e5f27a69bde78ef18fc302a1d8531.jpg)  
Fig. 1.4. Returns of the NYSE. The data are daily value weighted market returns from February 2, 1984 to December 31, 1991 (2000 trading days). The crash of October 19, 1987 occurs at $t = 9 3 8$ .

# Example 1.5 El Ni˜no and Fish Population

We may also be interested in analyzing several time series at once. Figure 1.5 shows monthly values of an environmental series called the Southern Oscillation Index (SOI) and associated Recruitment (number of new fish) furnished by Dr. Roy Mendelssohn of the Pacific Environmental Fisheries Group (personal communication). Both series are for a period of 453 months ranging over the years 1950–1987. The SOI measures changes in air pressure, related to sea surface temperatures in the central Pacific Ocean. The central Pacific warms every three to seven years due to the El Ni˜no effect, which has been blamed, in particular, for the 1997 floods in the midwestern portions of the United States. Both series in Figure 1.5 tend to exhibit repetitive behavior, with regularly repeating cycles that are easily visible. This periodic behavior is of interest because underlying processes of interest may be regular and the rate or frequency of oscillation characterizing the behavior of the underlying series would help to identify them. One can also remark that the cycles of the SOI are repeating at a faster rate than those of the Recruitment series. The Recruitment series also shows several kinds of oscillations, a faster frequency that seems to repeat about every 12 months and a slower frequency that seems to repeat about every 50 months. The study of the kinds of cycles and their strengths is the subject of Chapter 4. The two series also tend to be somewhat related; it is easy to imagine that somehow the fish population is dependent on the SOI. Perhaps even a lagged relation exists, with the SOI signaling changes in the fish population. This possibility

![](images/5bc4ddf700551b4900f13f4d53801e7963289771bd3cb0c70f903847966d1df1.jpg)

![](images/37115999a53fc5ec2bc48a77ac414a14d92c565d161288950be94d0761476ee6.jpg)  
Fig. 1.5. Monthly SOI and Recruitment (estimated new fish), 1950-1987.

suggests trying some version of regression analysis as a procedure for relating the two series. Transfer function modeling, as considered in Chapter 5, can be applied in this case to obtain a model relating Recruitment to its own past and the past values of the SOI.

The following R code will reproduce Figure 1.5:

1 par(mfrow = c(2,1)) # set up the graphics   
2 plot(soi, ylab="", xlab="", main $\varepsilon$ "Southern Oscillation Index")   
3 plot(rec, ylab="", xlab="", main="Recruitment")

# Example 1.6 fMRI Imaging

A fundamental problem in classical statistics occurs when we are given a collection of independent series or vectors of series, generated under varying experimental conditions or treatment configurations. Such a set of series is shown in Figure 1.6, where we observe data collected from various locations in the brain via functional magnetic resonance imaging (fMRI). In this example, five subjects were given periodic brushing on the hand. The stimulus was applied for 32 seconds and then stopped for 32 seconds; thus, the signal period is 64 seconds. The sampling rate was one observation every 2 seconds for 256 seconds ( $n = 1 2 8$ ). For this example, we averaged the results over subjects (these were evoked responses, and all subjects were in phase). The

![](images/9469179962c690f831c07e94704b07d41626a229c7133fa9c38dab234aa69de0.jpg)

![](images/0b942d4d9ce947c31bc0467e510f479accd5dc1527ba51b86bf52096533b6635.jpg)  
Fig. 1.6. fMRI data from various locations in the cortex, thalamus, and cerebellum; $n = 1 2 8$ points, one observation taken every 2 seconds.

series shown in Figure 1.6 are consecutive measures of blood oxygenationlevel dependent (bold) signal intensity, which measures areas of activation in the brain. Notice that the periodicities appear strongly in the motor cortex series and less strongly in the thalamus and cerebellum. The fact that one has series from different areas of the brain suggests testing whether the areas are responding differently to the brush stimulus. Analysis of variance techniques accomplish this in classical statistics, and we show in Chapter 7 how these classical techniques extend to the time series case, leading to a spectral analysis of variance.

The following R commands were used to plot the data:

1 par(mfrow=c(2,1), mar=c(3,2,1,0)+.5, mgp=c(1.6,.6,0))   
2 ts.plot(fmri1[,2:5], lty=c(1,2,4,5), ylab="BOLD", xlab="", main="Cortex")   
3 ts.plot(fmri1[,6:9], lty=c(1,2,4,5), ylab $=$ "BOLD", xlab="", main="Thalamus & Cerebellum")   
4 mtext("Time (1 pt = 2 sec)", side=1, line=2)

# Example 1.7 Earthquakes and Explosions

As a final example, the series in Figure 1.7 represent two phases or arrivals along the surface, denoted by P ( $t = 1 , \dots , 1 0 2 4 )$ and S ( $t = 1 0 2 5 , \dots , 2 0 4 8 )$ ,

![](images/1c7f85086aaeed4f7f84c6a0f1dcb3b6a9fc5243598d8a38ca33d3e9b2618ef3.jpg)

![](images/16f52b54c3204164fafbad70b3b40abdb1c98d41053a8be76055b47525987855.jpg)  
Fig. 1.7. Arrival phases from an earthquake (top) and explosion (bottom) at 40 points per second.

at a seismic recording station. The recording instruments in Scandinavia are observing earthquakes and mining explosions with one of each shown in Figure 1.7. The general problem of interest is in distinguishing or discriminating between waveforms generated by earthquakes and those generated by explosions. Features that may be important are the rough amplitude ratios of the first phase P to the second phase S, which tend to be smaller for earthquakes than for explosions. In the case of the two events in Figure 1.7, the ratio of maximum amplitudes appears to be somewhat less than .5 for the earthquake and about 1 for the explosion. Otherwise, note a subtle difference exists in the periodic nature of the S phase for the earthquake. We can again think about spectral analysis of variance for testing the equality of the periodic components of earthquakes and explosions. We would also like to be able to classify future P and S components from events of unknown origin, leading to the time series discriminant analysis developed in Chapter 7.

To plot the data as in this example, use the following commands in R:

1 par(mfrow=c(2,1))  
2 plot(EQ5, main="Earthquake")  
3 plot(EXP6, main="Explosion")

# 1.3 Time Series Statistical Models

The primary objective of time series analysis is to develop mathematical models that provide plausible descriptions for sample data, like that encountered in the previous section. In order to provide a statistical setting for describing the character of data that seemingly fluctuate in a random fashion over time, we assume a time series can be defined as a collection of random variables indexed according to the order they are obtained in time. For example, we may consider a time series as a sequence of random variables, $x _ { 1 } , x _ { 2 } , x _ { 3 } , \ldots$ , where the random variable $x _ { 1 }$ denotes the value taken by the series at the first time point, the variable $x _ { 2 }$ denotes the value for the second time period, $x _ { 3 }$ denotes the value for the third time period, and so on. In general, a collection of random variables, $\{ x _ { t } \}$ , indexed by $t$ is referred to as a stochastic process. In this text, $t$ will typically be discrete and vary over the integers $t = 0 , \pm 1 , \pm 2 , \ldots$ or some subset of the integers. The observed values of a stochastic process are referred to as a realization of the stochastic process. Because it will be clear from the context of our discussions, we use the term time series whether we are referring generically to the process or to a particular realization and make no notational distinction between the two concepts.

It is conventional to display a sample time series graphically by plotting the values of the random variables on the vertical axis, or ordinate, with the time scale as the abscissa. It is usually convenient to connect the values at adjacent time periods to reconstruct visually some original hypothetical continuous time series that might have produced these values as a discrete sample. Many of the series discussed in the previous section, for example, could have been observed at any continuous point in time and are conceptually more properly treated as continuous time series. The approximation of these series by discrete time parameter series sampled at equally spaced points in time is simply an acknowledgment that sampled data will, for the most part, be discrete because of restrictions inherent in the method of collection. Furthermore, the analysis techniques are then feasible using computers, which are limited to digital computations. Theoretical developments also rest on the idea that a continuous parameter time series should be specified in terms of finite-dimensional distribution functions defined over a finite number of points in time. This is not to say that the selection of the sampling interval or rate is not an extremely important consideration. The appearance of data can be changed completely by adopting an insufficient sampling rate. We have all seen wagon wheels in movies appear to be turning backwards because of the insufficient number of frames sampled by the camera. This phenomenon leads to a distortion called aliasing (see 4.2).

The fundamental visual characteristic distinguishing the different series shown in Examples 1.1–1.7 is their differing degrees of smoothness. One possible explanation for this smoothness is that it is being induced by the supposition that adjacent points in time are correlated, so the value of the series at time $t$ , say, $x _ { t }$ , depends in some way on the past values $x _ { t - 1 } , x _ { t - 2 } , . . . .$ This

model expresses a fundamental way in which we might think about generating realistic-looking time series. To begin to develop an approach to using collections of random variables to model time series, consider Example 1.8.

# Example 1.8 White Noise

A simple kind of generated series might be a collection of uncorrelated random variables, $w _ { t }$ , with mean 0 and finite variance $\sigma _ { w } ^ { 2 }$ . The time series generated from uncorrelated variables is used as a model for noise in engineering applications, where it is called white noise; we shall sometimes denote this process as $w _ { t } \sim w n ( 0 , \sigma _ { w } ^ { 2 } )$ . The designation white originates from the analogy with white light and indicates that all possible periodic oscillations are present with equal strength.

We will, at times, also require the noise to be independent and identically distributed (iid) random variables with mean 0 and variance $\sigma _ { w } ^ { 2 }$ . We shall distinguish this case by saying white independent noise, or by writing $w _ { t } \sim$ $\operatorname { i i d } ( 0 , \sigma _ { w } ^ { 2 } )$ . A particularly useful white noise series is Gaussian white noise, wherein the $w _ { t }$ are independent normal random variables, with mean 0 and variance $\sigma _ { w } ^ { 2 }$ ; or more succinctly, $w _ { t } \sim$ iid $\mathrm { N } ( 0 , \sigma _ { w } ^ { 2 } )$ . Figure 1.8 shows in the upper panel a collection of 500 such random variables, with $\sigma _ { w } ^ { 2 } = 1$ , plotted in the order in which they were drawn. The resulting series bears a slight resemblance to the explosion in Figure 1.7 but is not smooth enough to serve as a plausible model for any of the other experimental series. The plot tends to show visually a mixture of many different kinds of oscillations in the white noise series.

If the stochastic behavior of all time series could be explained in terms of the white noise model, classical statistical methods would suffice. Two ways of introducing serial correlation and more smoothness into time series models are given in Examples 1.9 and 1.10.

# Example 1.9 Moving Averages

We might replace the white noise series $w _ { t }$ by a moving average that smooths the series. For example, consider replacing $w _ { t }$ in Example 1.8 by an average of its current value and its immediate neighbors in the past and future. That is, let

$$
v _ {t} = \frac {1}{3} \left(w _ {t - 1} + w _ {t} + w _ {t + 1}\right), \tag {1.1}
$$

which leads to the series shown in the lower panel of Figure 1.8. Inspecting the series shows a smoother version of the first series, reflecting the fact that the slower oscillations are more apparent and some of the faster oscillations are taken out. We begin to notice a similarity to the SOI in Figure 1.5, or perhaps, to some of the fMRI series in Figure 1.6.

To reproduce Figure 1.8 in R use the following commands. A linear combination of values in a time series such as in (1.1) is referred to, generically, as a filtered series; hence the command filter.

![](images/84cc66bf32f9b2eaa45e52209904e514cb179e1ecceaa000d667f6fa7b58b997.jpg)

![](images/b3340603d5242acc6e5bd207d021584a693c8855f28df408f2425b6d70c13e73.jpg)  
Fig. 1.8. Gaussian white noise series (top) and three-point moving average of the Gaussian white noise series (bottom).

1 w = rnorm(500,0,1) # 500 N(0,1) variates   
2 v = filter(w, sides=2, rep(1/3,3)) # moving average   
3 par(mfrow=c(2,1))  
4 plot.ts(w, main="white noise")   
5 plot.ts(v, main="moving average")

The speech series in Figure 1.3 and the Recruitment series in Figure 1.5, as well as some of the MRI series in Figure 1.6, differ from the moving average series because one particular kind of oscillatory behavior seems to predominate, producing a sinusoidal type of behavior. A number of methods exist for generating series with this quasi-periodic behavior; we illustrate a popular one based on the autoregressive model considered in Chapter 3.

# Example 1.10 Autoregressions

Suppose we consider the white noise series $w _ { t }$ of Example 1.8 as input and calculate the output using the second-order equation

$$
x _ {t} = x _ {t - 1} - . 9 x _ {t - 2} + w _ {t} \tag {1.2}
$$

successively for $t = 1 , 2 , \ldots , 5 0 0$ . Equation (1.2) represents a regression or prediction of the current value $x _ { t }$ of a time series as a function of the past two values of the series, and, hence, the term autoregression is suggested

![](images/e3f8055f4f3128ac3075205f06076bce3a8153ab47b3fbfa7e037eab6dc3e92f.jpg)  
Fig. 1.9. Autoregressive series generated from model (1.2).

for this model. A problem with startup values exists here because (1.2) also depends on the initial conditions $x _ { 0 }$ and $x _ { - 1 }$ , but, for now, we assume that we are given these values and generate the succeeding values by substituting into (1.2). The resulting output series is shown in Figure 1.9, and we note the periodic behavior of the series, which is similar to that displayed by the speech series in Figure 1.3. The autoregressive model above and its generalizations can be used as an underlying model for many observed series and will be studied in detail in Chapter 3.

One way to simulate and plot data from the model (1.2) in R is to use the following commands (another way is to use arima.sim).

1 w = rnorm(550,0,1) # 50 extra to avoid startup problems   
2 x = filter(w, filter=c(1,-.9), method="recursive")[-(1:50)]   
3 plot.ts(x, main="autoregression")

# Example 1.11 Random Walk with Drift

A model for analyzing trend such as seen in the global temperature data in Figure 1.2, is the random walk with drift model given by

$$
x _ {t} = \delta + x _ {t - 1} + w _ {t} \tag {1.3}
$$

for $t = 1 , 2 , \ldots$ , with initial condition $x _ { 0 } = 0$ , and where $w _ { t }$ is white noise. The constant $\delta$ is called the drift, and when $\delta = 0$ , (1.3) is called simply a random walk. The term random walk comes from the fact that, when $\delta = 0$ , the value of the time series at time $t$ is the value of the series at time $t - 1$ plus a completely random movement determined by $w _ { t }$ . Note that we may rewrite (1.3) as a cumulative sum of white noise variates. That is,

$$
x _ {t} = \delta t + \sum_ {j = 1} ^ {t} w _ {j} \tag {1.4}
$$

![](images/87c58dc52cbe7abd4cf9672efefc6e911f361d08516a52312f187e1ad3db7de7.jpg)  
Fig. 1.10. Random walk, $\sigma _ { w } = 1$ , with drift $\delta = . 2$ (upper jagged line), without drift, $\delta = 0$ (lower jagged line), and a straight line with slope .2 (dashed line).

for $t = 1 , 2 , \ldots$ ; either use induction, or plug (1.4) into (1.3) to verify this statement. Figure 1.10 shows 200 observations generated from the model with $\delta = 0$ and .2, and with $\sigma _ { w } = 1$ . For comparison, we also superimposed the straight line . $2 t$ on the graph.

To reproduce Figure 1.10 in R use the following code (notice the use of multiple commands per line using a semicolon).

1 set.seed(154) # so you can reproduce the results   
2 w = rnorm(200,0,1); x = cumsum(w) # two commands in one line   
3 $\mathtt { w d } \ = \ \mathtt { w } \ + . 2$ ; xd $=$ cumsum(wd)   
4 plot.ts(xd, ylim $\mathtt { = } \mathtt { c }$ (-5,55), main="random walk")   
5 lines(x); lines(.2*(1:200), lty="dashed")

# Example 1.12 Signal in Noise

Many realistic models for generating time series assume an underlying signal with some consistent periodic variation, contaminated by adding a random noise. For example, it is easy to detect the regular cycle fMRI series displayed on the top of Figure 1.6. Consider the model

$$
x _ {t} = 2 \cos (2 \pi t / 5 0 +. 6 \pi) + w _ {t} \tag {1.5}
$$

for $t = 1 , 2 , \ldots , 5 0 0$ , where the first term is regarded as the signal, shown in the upper panel of Figure 1.11. We note that a sinusoidal waveform can be written as

$$
A \cos (2 \pi \omega t + \phi), \tag {1.6}
$$

where $A$ is the amplitude, $\omega$ is the frequency of oscillation, and $\phi$ is a phase shift. In (1.5), $A \ = \ 2$ , $\omega = 1 / 5 0$ (one cycle every 50 time points), and $\phi = . 6 \pi$ .

![](images/4f75e5e7aece1119cc722270b242c2f2d812cded4007214bafc3c6b13d544dfe.jpg)

![](images/7cb4a800a8378fec5ff243c05ad1790ab1c521632ea891183ea97bd453e081f6.jpg)  
$2 \cos ( 2 \pi \ t / 5 0 + 0 . 6 \pi ) + \mathsf { N } ( 0 , \ 1 )$

![](images/edd962d41699c6d837b2289548764ebd3ef8e85bb3c140bf1eda559b000bfebd.jpg)  
$2 \cos ( 2 \pi \mathrm { t } / 5 0 + 0 . 6 \pi ) + \mathsf { N } ( 0 , 2 5 )$   
Fig. 1.11. Cosine wave with period 50 points (top panel) compared with the cosine wave contaminated with additive white Gaussian noise, $\sigma _ { w } = 1$ (middle panel) and $\sigma _ { w } = 5$ (bottom panel); see (1.5).

An additive noise term was taken to be white noise with $\sigma _ { w } = 1$ (middle panel) and $\sigma _ { w } = 5$ (bottom panel), drawn from a normal distribution. Adding the two together obscures the signal, as shown in the lower panels of Figure 1.11. Of course, the degree to which the signal is obscured depends on the amplitude of the signal and the size of $\sigma _ { w }$ . The ratio of the amplitude of the signal to $o _ { w }$ (or some function of the ratio) is sometimes called the signal-to-noise ratio (SNR); the larger the SNR, the easier it is to detect the signal. Note that the signal is easily discernible in the middle panel of Figure 1.11, whereas the signal is obscured in the bottom panel. Typically, we will not observe the signal but the signal obscured by noise.

To reproduce Figure 1.11 in R, use the following commands:

1 cs = 2*cos(2*pi*1:500/50 + .6*pi)   
2 w = rnorm(500,0,1)   
3 par(mfrow=c(3,1), mar=c(3,2,2,1), cex.main=1.5)   
4 plot.ts(cs, main=expression(2*cos(2*pi*t/50+.6*pi)))   
5 plot.ts(cs+w, main=expression(2*cos(2*pi*t/50+.6*pi) + N(0,1)))  
6 plot.ts(cs+5*w, main=expression(2*cos(2*pi*t/50+.6*pi) + N(0,25)))

In Chapter 4, we will study the use of spectral analysis as a possible technique for detecting regular or periodic signals, such as the one described

in Example 1.12. In general, we would emphasize the importance of simple additive models such as given above in the form

$$
x _ {t} = s _ {t} + v _ {t}, \tag {1.7}
$$

where $s _ { t }$ denotes some unknown signal and $v _ { t }$ denotes a time series that may be white or correlated over time. The problems of detecting a signal and then in estimating or extracting the waveform of $s _ { t }$ are of great interest in many areas of engineering and the physical and biological sciences. In economics, the underlying signal may be a trend or it may be a seasonal component of a series. Models such as (1.7), where the signal has an autoregressive structure, form the motivation for the state-space model of Chapter 6.

In the above examples, we have tried to motivate the use of various combinations of random variables emulating real time series data. Smoothness characteristics of observed time series were introduced by combining the random variables in various ways. Averaging independent random variables over adjacent time points, as in Example 1.9, or looking at the output of difference equations that respond to white noise inputs, as in Example 1.10, are common ways of generating correlated data. In the next section, we introduce various theoretical measures used for describing how time series behave. As is usual in statistics, the complete description involves the multivariate distribution function of the jointly sampled values $x _ { 1 } , x _ { 2 } , \ldots , x _ { n }$ , whereas more economical descriptions can be had in terms of the mean and autocorrelation functions. Because correlation is an essential feature of time series analysis, the most useful descriptive measures are those expressed in terms of covariance and correlation functions.

# 1.4 Measures of Dependence: Autocorrelation and Cross-Correlation

A complete description of a time series, observed as a collection of $n$ random variables at arbitrary integer time points $t _ { 1 } , t _ { 2 } , \ldots , t _ { n }$ , for any positive integer $n$ , is provided by the joint distribution function, evaluated as the probability that the values of the series are jointly less than the $n$ constants, $c _ { 1 } , c _ { 2 } , \ldots , c _ { n }$ ; i.e.,

$$
F \left(c _ {1}, c _ {2}, \dots , c _ {n}\right) = P \left(x _ {t _ {1}} \leq c _ {1}, x _ {t _ {2}} \leq c _ {2}, \dots , x _ {t _ {n}} \leq c _ {n}\right). \tag {1.8}
$$

Unfortunately, the multidimensional distribution function cannot usually be written easily unless the random variables are jointly normal, in which case the joint density has the well-known form displayed in (1.31).

Although the joint distribution function describes the data completely, it is an unwieldy tool for displaying and analyzing time series data. The distribution function (1.8) must be evaluated as a function of $n$ arguments, so any plotting of the corresponding multivariate density functions is virtually impossible. The marginal distribution functions

$$
F _ {t} (x) = P \{x _ {t} \leq x \}
$$

or the corresponding marginal density functions

$$
f _ {t} (x) = \frac {\partial F _ {t} (x)}{\partial x},
$$

when they exist, are often informative for examining the marginal behavior of a series.2 Another informative marginal descriptive measure is the mean function.

Definition 1.1 The mean function is defined as

$$
\mu_ {x t} = E \left(x _ {t}\right) = \int_ {- \infty} ^ {\infty} x f _ {t} (x) d x, \tag {1.9}
$$

provided it exists, where $E$ denotes the usual expected value operator. When no confusion exists about which time series we are referring to, we will drop a subscript and write $\mu _ { x t }$ as $\mu _ { t }$ .

# Example 1.13 Mean Function of a Moving Average Series

If $w _ { t }$ denotes a white noise series, then $\mu _ { w t } = E ( w _ { t } ) = 0$ for all $t$ . The top series in Figure 1.8 reflects this, as the series clearly fluctuates around a mean value of zero. Smoothing the series as in Example 1.9 does not change the mean because we can write

$$
\mu_ {v t} = E (v _ {t}) = \frac {1}{3} \left[ E \left(w _ {t - 1}\right) + E (w _ {t}) + E \left(w _ {t + 1}\right) \right] = 0.
$$

# Example 1.14 Mean Function of a Random Walk with Drift

Consider the random walk with drift model given in (1.4),

$$
x _ {t} = \delta t + \sum_ {j = 1} ^ {t} w _ {j}, \qquad t = 1, 2, \dots .
$$

Because $E ( w _ { t } ) = 0$ for all $t$ , and $\delta$ is a constant, we have

$$
\mu_ {x t} = E (x _ {t}) = \delta t + \sum_ {j = 1} ^ {t} E (w _ {j}) = \delta t
$$

which is a straight line with slope $\delta$ . A realization of a random walk with drift can be compared to its mean function in Figure 1.10.

# Example 1.15 Mean Function of Signal Plus Noise

A great many practical applications depend on assuming the observed data have been generated by a fixed signal waveform superimposed on a zeromean noise process, leading to an additive signal model of the form (1.5). It is clear, because the signal in (1.5) is a fixed function of time, we will have

$$
\begin{array}{l} \mu_ {x t} = E \left(x _ {t}\right) = E \left[ 2 \cos (2 \pi t / 5 0 +. 6 \pi) + w _ {t} \right] \\ = 2 \cos (2 \pi t / 5 0 +. 6 \pi) + E (w _ {t}) \\ = 2 \cos (2 \pi t / 5 0 +. 6 \pi), \\ \end{array}
$$

and the mean function is just the cosine wave.

The lack of independence between two adjacent values $x _ { s }$ and $x _ { t }$ can be assessed numerically, as in classical statistics, using the notions of covariance and correlation. Assuming the variance of $x _ { t }$ is finite, we have the following definition.

Definition 1.2 The autocovariance function is defined as the second moment product

$$
\gamma_ {x} (s, t) = \operatorname {c o v} \left(x _ {s}, x _ {t}\right) = E \left[ \left(x _ {s} - \mu_ {s}\right) \left(x _ {t} - \mu_ {t}\right) \right], \tag {1.10}
$$

for all s and t. When no possible confusion exists about which time series we are referring to, we will drop the subscript and write $\gamma _ { x } ( s , t )$ as $\gamma ( s , t )$ .

Note that $\gamma _ { x } ( s , t ) = \gamma _ { x } ( t , s )$ for all time points $s$ and $t$ . The autocovariance measures the linear dependence between two points on the same series observed at different times. Very smooth series exhibit autocovariance functions that stay large even when the $t$ and $s$ are far apart, whereas choppy series tend to have autocovariance functions that are nearly zero for large separations. The autocovariance (1.10) is the average cross-product relative to the joint distribution $F ( x _ { s } , x _ { t } )$ . Recall from classical statistics that if $\gamma _ { x } ( s , t ) = 0$ , $x _ { s }$ and $x _ { t }$ are not linearly related, but there still may be some dependence structure between them. If, however, $x _ { s }$ and $x _ { t }$ are bivariate normal, $\gamma _ { x } ( s , t ) = 0$ ensures their independence. It is clear that, for $s \mathit { \Theta } = \mathit { t }$ , the autocovariance reduces to the (assumed finite) variance, because

$$
\gamma_ {x} (t, t) = E \left[ \left(x _ {t} - \mu_ {t}\right) ^ {2} \right] = \operatorname {v a r} \left(x _ {t}\right). \tag {1.11}
$$

# Example 1.16 Autocovariance of White Noise

The white noise series $w _ { t }$ has $E ( w _ { t } ) = 0$ and

$$
\gamma_ {w} (s, t) = \operatorname {c o v} \left(w _ {s}, w _ {t}\right) = \left\{ \begin{array}{l l} \sigma_ {w} ^ {2} & s = t, \\ 0 & s \neq t. \end{array} \right. \tag {1.12}
$$

A realization of white noise with $\sigma _ { w } ^ { 2 } \ = \ 1$ is shown in the top panel of Figure 1.8.

# Example 1.17 Autocovariance of a Moving Average

Consider applying a three-point moving average to the white noise series $w _ { t }$ of the previous example as in Example 1.9. In this case,

$$
\gamma_ {v} (s, t) = \operatorname {c o v} (v _ {s}, v _ {t}) = \operatorname {c o v} \left\{\frac {1}{3} \left(w _ {s - 1} + w _ {s} + w _ {s + 1}\right), \frac {1}{3} \left(w _ {t - 1} + w _ {t} + w _ {t + 1}\right) \right\}.
$$

When $s = t$ we have3

$$
\begin{array}{l} \gamma_ {v} (t, t) = \frac {1}{9} \operatorname {c o v} \left\{\left(w _ {t - 1} + w _ {t} + w _ {t + 1}\right), \left(w _ {t - 1} + w _ {t} + w _ {t + 1}\right) \right\} \\ = \frac {1}{9} \left[ \operatorname {c o v} \left(w _ {t - 1}, w _ {t - 1}\right) + \operatorname {c o v} \left(w _ {t}, w _ {t}\right) + \operatorname {c o v} \left(w _ {t + 1}, w _ {t + 1}\right) \right] \\ = \frac {3}{9} \sigma_ {w} ^ {2}. \\ \end{array}
$$

When $s = t + 1$ ,

$$
\begin{array}{l} \gamma_ {v} (t + 1, t) = \frac {1}{9} \operatorname {c o v} \left\{\left(w _ {t} + w _ {t + 1} + w _ {t + 2}\right), \left(w _ {t - 1} + w _ {t} + w _ {t + 1}\right) \right\} \\ = \frac {1}{9} \left[ \operatorname {c o v} \left(w _ {t}, w _ {t}\right) + \operatorname {c o v} \left(w _ {t + 1}, w _ {t + 1}\right) \right] \\ = \frac {2}{9} \sigma_ {w} ^ {2}, \\ \end{array}
$$

using (1.12). Similar computations give $\gamma _ { v } ( t - 1 , t ) = 2 \sigma _ { w } ^ { 2 } / 9$ , $\gamma _ { v } ( t + 2 , t ) =$ $\gamma _ { v } ( t - 2 , t ) = \sigma _ { w } ^ { 2 } / 9$ , and 0 when $| t - s | > 2$ . We summarize the values for all $s$ and $t$ as

$$
\gamma_ {v} (s, t) = \left\{ \begin{array}{l l} \frac {3}{9} \sigma_ {w} ^ {2} & s = t, \\ \frac {2}{9} \sigma_ {w} ^ {2} & | s - t | = 1, \\ \frac {1}{9} \sigma_ {w} ^ {2} & | s - t | = 2, \\ 0 & | s - t | > 2. \end{array} \right. \tag {1.13}
$$

Example 1.17 shows clearly that the smoothing operation introduces a covariance function that decreases as the separation between the two time points increases and disappears completely when the time points are separated by three or more time points. This particular autocovariance is interesting because it only depends on the time separation or lag and not on the absolute location of the points along the series. We shall see later that this dependence suggests a mathematical model for the concept of weak stationarity.

# Example 1.18 Autocovariance of a Random Walk

For the random walk model, $\textstyle x _ { t } = \sum _ { j = 1 } ^ { t } w _ { j }$ , we have

$$
\gamma_ {x} (s, t) = \operatorname {c o v} \left(x _ {s}, x _ {t}\right) = \operatorname {c o v} \left(\sum_ {j = 1} ^ {s} w _ {j}, \sum_ {k = 1} ^ {t} w _ {k}\right) = \min  \{s, t \} \sigma_ {w} ^ {2},
$$

because the $w _ { t }$ are uncorrelated random variables. Note that, as opposed to the previous examples, the autocovariance function of a random walk

depends on the particular time values $s$ and $t$ , and not on the time separation or lag. Also, notice that the variance of the random walk, $\operatorname { v a r } ( x _ { t } ) = \gamma _ { x } ( t , t ) =$ $t \sigma _ { w } ^ { 2 }$ , increases without bound as time $t$ increases. The effect of this variance increase can be seen in Figure 1.10 where the processes start to move away from their mean functions $\delta t$ (note that $\delta = 0$ and .2 in that example).

As in classical statistics, it is more convenient to deal with a measure of association between $^ { - 1 }$ and 1, and this leads to the following definition.

Definition 1.3 The autocorrelation function (ACF) is defined as

$$
\rho (s, t) = \frac {\gamma (s , t)}{\sqrt {\gamma (s , s) \gamma (t , t)}}. \tag {1.14}
$$

The ACF measures the linear predictability of the series at time $t$ , say $x _ { t }$ , using only the value $x _ { s }$ . We can show easily that $- 1 \le \rho ( s , t ) \le 1$ using the Cauchy–Schwarz inequality.4 If we can predict $x _ { t }$ perfectly from $x _ { s }$ through a linear relationship, $x _ { t } = \beta _ { 0 } + \beta _ { 1 } x _ { s }$ , then the correlation will be $+ 1$ when $\beta _ { 1 } > 0$ , and $^ { - 1 }$ when $\beta _ { 1 } < 0$ . Hence, we have a rough measure of the ability to forecast the series at time $t$ from the value at time $s$ .

Often, we would like to measure the predictability of another series $y _ { t }$ from the series $x _ { s }$ . Assuming both series have finite variances, we have the following definition.

Definition 1.4 The cross-covariance function between two series, $x _ { t }$ and $y _ { t }$ , is

$$
\gamma_ {x y} (s, t) = \operatorname {c o v} \left(x _ {s}, y _ {t}\right) = E \left[ \left(x _ {s} - \mu_ {x s}\right) \left(y _ {t} - \mu_ {y t}\right) \right]. \tag {1.15}
$$

There is also a scaled version of the cross-covariance function.

Definition 1.5 The cross-correlation function (CCF) is given by

$$
\rho_ {x y} (s, t) = \frac {\gamma_ {x y} (s , t)}{\sqrt {\gamma_ {x} (s , s) \gamma_ {y} (t , t)}}. \tag {1.16}
$$

We may easily extend the above ideas to the case of more than two series, say, $x _ { t 1 } , x _ { t 2 } , \ldots , x _ { t r }$ ; that is, multivariate time series with $r$ components. For example, the extension of (1.10) in this case is

$$
\gamma_ {j k} (s, t) = E \left[ \left(x _ {s j} - \mu_ {s j}\right) \left(x _ {t k} - \mu_ {t k}\right) \right] \quad j, k = 1, 2, \dots , r. \tag {1.17}
$$

In the definitions above, the autocovariance and cross-covariance functions may change as one moves along the series because the values depend on both $s$

and $t$ , the locations of the points in time. In Example 1.17, the autocovariance function depends on the separation of $x _ { s }$ and $x _ { t }$ , say, $h = | s - t |$ , and not on where the points are located in time. As long as the points are separated by $h$ units, the location of the two points does not matter. This notion, called weak stationarity, when the mean is constant, is fundamental in allowing us to analyze sample time series data when only a single series is available.

# 1.5 Stationary Time Series

The preceding definitions of the mean and autocovariance functions are completely general. Although we have not made any special assumptions about the behavior of the time series, many of the preceding examples have hinted that a sort of regularity may exist over time in the behavior of a time series. We introduce the notion of regularity using a concept called stationarity.

Definition 1.6 A strictly stationary time series is one for which the probabilistic behavior of every collection of values

$$
\left\{x _ {t _ {1}}, x _ {t _ {2}}, \dots , x _ {t _ {k}} \right\}
$$

is identical to that of the time shifted set

$$
\left\{x _ {t _ {1} + h}, x _ {t _ {2} + h}, \dots , x _ {t _ {k} + h} \right\}.
$$

That is,

$$
P \left\{x _ {t _ {1}} \leq c _ {1}, \dots , x _ {t _ {k}} \leq c _ {k} \right\} = P \left\{x _ {t _ {1} + h} \leq c _ {1}, \dots , x _ {t _ {k} + h} \leq c _ {k} \right\} \tag {1.18}
$$

for all $k = 1 , 2 , \dots$ , all time points $t _ { 1 } , t _ { 2 } , \ldots , t _ { k }$ , all numbers $c _ { 1 } , c _ { 2 } , \ldots , c _ { k }$ , and all time shifts $h = 0 , \pm 1 , \pm 2 , \ldots$ .

If a time series is strictly stationary, then all of the multivariate distribution functions for subsets of variables must agree with their counterparts in the shifted set for all values of the shift parameter $h$ . For example, when $k = 1$ , (1.18) implies that

$$
P \left\{x _ {s} \leq c \right\} = P \left\{x _ {t} \leq c \right\} \tag {1.19}
$$

for any time points $s$ and $t$ . This statement implies, for example, that the probability that the value of a time series sampled hourly is negative at 1 am is the same as at $1 0 \mathrm { A M }$ . In addition, if the mean function, $\mu _ { t }$ , of the series $x _ { t }$ exists, (1.19) implies that $\mu _ { s } = \mu _ { t }$ for all $s$ and $t$ , and hence $\mu _ { t }$ must be constant. Note, for example, that a random walk process with drift is not strictly stationary because its mean function changes with time; see Example 1.14 on page 18.

When $k = 2$ , we can write (1.18) as

$$
P \left\{x _ {s} \leq c _ {1}, x _ {t} \leq c _ {2} \right\} = P \left\{x _ {s + h} \leq c _ {1}, x _ {t + h} \leq c _ {2} \right\} \tag {1.20}
$$

for any time points $s$ and $t$ and shift $h$ . Thus, if the variance function of the process exists, (1.20) implies that the autocovariance function of the series $x _ { t }$ satisfies

$$
\gamma (s, t) = \gamma (s + h, t + h)
$$

for all $s$ and $t$ and $h$ . We may interpret this result by saying the autocovariance function of the process depends only on the time difference between $s$ and $t$ , and not on the actual times.

The version of stationarity in Definition 1.6 is too strong for most applications. Moreover, it is difficult to assess strict stationarity from a single data set. Rather than imposing conditions on all possible distributions of a time series, we will use a milder version that imposes conditions only on the first two moments of the series. We now have the following definition.

Definition 1.7 A weakly stationary time series, $x _ { t }$ , is a finite variance process such that

(i) the mean value function, $\mu _ { t }$ , defined in (1.9) is constant and does not depend on time $t$ , and   
(ii) the autocovariance function, $\gamma ( s , t )$ , defined in (1.10) depends on s and t only through their difference $\left| s - t \right|$ .

Henceforth, we will use the term stationary to mean weakly stationary; if a process is stationary in the strict sense, we will use the term strictly stationary.

It should be clear from the discussion of strict stationarity following Definition 1.6 that a strictly stationary, finite variance, time series is also stationary. The converse is not true unless there are further conditions. One important case where stationarity implies strict stationarity is if the time series is Gaussian [meaning all finite distributions, (1.18), of the series are Gaussian]. We will make this concept more precise at the end of this section.

Because the mean function, $E ( x _ { t } ) = \mu _ { t }$ , of a stationary time series is independent of time $t$ , we will write

$$
\mu_ {t} = \mu . \tag {1.21}
$$

Also, because the autocovariance function, $\gamma ( s , t )$ , of a stationary time series, $x _ { t }$ , depends on $s$ and $t$ only through their difference $| s - t |$ , we may simplify the notation. Let $s = t + h$ , where $h$ represents the time shift or lag. Then

$$
\gamma (t + h, t) = \operatorname {c o v} \left(x _ {t + h}, x _ {t}\right) = \operatorname {c o v} \left(x _ {h}, x _ {0}\right) = \gamma (h, 0)
$$

because the time difference between times $t + h$ and $t$ is the same as the time difference between times $h$ and 0. Thus, the autocovariance function of a stationary time series does not depend on the time argument $t$ . Henceforth, for convenience, we will drop the second argument of $\gamma ( h , 0 )$ .

![](images/2dee2d5aad1ce4f89450c237ef559b0bb0836ab15c90d5caaf1f2b155db1b5b3.jpg)  
Fig. 1.12. Autocovariance function of a three-point moving average.

Definition 1.8 The autocovariance function of a stationary time series will be written as

$$
\gamma (h) = \operatorname {c o v} \left(x _ {t + h}, x _ {t}\right) = E \left[ \left(x _ {t + h} - \mu\right) \left(x _ {t} - \mu\right) \right]. \tag {1.22}
$$

Definition 1.9 The autocorrelation function (ACF) of a stationary time series will be written using (1.14) as

$$
\rho (h) = \frac {\gamma (t + h , t)}{\sqrt {\gamma (t + h , t + h) \gamma (t , t)}} = \frac {\gamma (h)}{\gamma (0)}. \tag {1.23}
$$

The Cauchy–Schwarz inequality shows again that $- 1 \leq \rho ( h ) \leq 1$ for all $h$ , enabling one to assess the relative importance of a given autocorrelation value by comparing with the extreme values $^ { - 1 }$ and 1.

# Example 1.19 Stationarity of White Noise

The mean and autocovariance functions of the white noise series discussed in Examples 1.8 and 1.16 are easily evaluated as $\mu _ { w t } = 0$ and

$$
\gamma_ {w} (h) = \operatorname {c o v} (w _ {t + h}, w _ {t}) = \left\{ \begin{array}{l l} \sigma_ {w} ^ {2} & h = 0, \\ 0 & h \neq 0. \end{array} \right.
$$

Thus, white noise satisfies the conditions of Definition 1.7 and is weakly stationary or stationary. If the white noise variates are also normally distributed or Gaussian, the series is also strictly stationary, as can be seen by evaluating (1.18) using the fact that the noise would also be iid.

# Example 1.20 Stationarity of a Moving Average

The three-point moving average process of Example 1.9 is stationary because, from Examples 1.13 and 1.17, the mean and autocovariance functions $\mu _ { v t } = 0$ , and

$$
\gamma_ {v} (h) = \left\{ \begin{array}{l l} \frac {3}{9} \sigma_ {w} ^ {2} & h = 0, \\ \frac {2}{9} \sigma_ {w} ^ {2} & h = \pm 1, \\ \frac {1}{9} \sigma_ {w} ^ {2} & h = \pm 2, \\ 0 & | h | > 2 \end{array} \right.
$$

are independent of time $t$ , satisfying the conditions of Definition 1.7. Figure 1.12 shows a plot of the autocovariance as a function of lag $h$ with $\sigma _ { w } ^ { 2 } = 1$ . Interestingly, the autocovariance function is symmetric about lag zero and decays as a function of lag.

The autocovariance function of a stationary process has several useful properties (also, see Problem 1.25). First, the value at $h = 0$ , namely

$$
\gamma (0) = E \left[ \left(x _ {t} - \mu\right) ^ {2} \right] \tag {1.24}
$$

is the variance of the time series; note that the Cauchy–Schwarz inequality implies

$$
| \gamma (h) | \leq \gamma (0).
$$

A final useful property, noted in the previous example, is that the autocovariance function of a stationary series is symmetric around the origin; that is,

$$
\gamma (h) = \gamma (- h) \tag {1.25}
$$

for all $h$ . This property follows because shifting the series by $h$ means that

$$
\begin{array}{l} \gamma (h) = \gamma (t + h - t) \\ = E \left[ \left(x _ {t + h} - \mu\right) \left(x _ {t} - \mu\right) \right] \\ = E \left[ \left(x _ {t} - \mu\right) \left(x _ {t + h} - \mu\right) \right] \\ = \gamma (t - (t + h)) \\ = \gamma (- h), \\ \end{array}
$$

which shows how to use the notation as well as proving the result.

When several series are available, a notion of stationarity still applies with additional conditions.

Definition 1.10 Two time series, say, $x _ { t }$ and $y _ { t }$ , are said to be jointly stationary if they are each stationary, and the cross-covariance function

$$
\gamma_ {x y} (h) = \operatorname {c o v} \left(x _ {t + h}, y _ {t}\right) = E \left[ \left(x _ {t + h} - \mu_ {x}\right) \left(y _ {t} - \mu_ {y}\right) \right] \tag {1.26}
$$

is a function only of lag h.

Definition 1.11 The cross-correlation function (CCF) of jointly stationary time series $x _ { t }$ and $y _ { t }$ is defined as

$$
\rho_ {x y} (h) = \frac {\gamma_ {x y} (h)}{\sqrt {\gamma_ {x} (0) \gamma_ {y} (0)}}. \tag {1.27}
$$

Again, we have the result $- 1 \leq \rho _ { x y } ( h ) \leq 1$ which enables comparison with the extreme values $^ { - 1 }$ and 1 when looking at the relation between $x _ { t + h }$ and $y _ { t }$ . The cross-correlation function is not generally symmetric about zero [i.e., typically $\rho _ { x y } ( h ) \neq \rho _ { x y } ( - h ) ]$ ; however, it is the case that

$$
\rho_ {x y} (h) = \rho_ {y x} (- h), \tag {1.28}
$$

which can be shown by manipulations similar to those used to show (1.25).

# Example 1.21 Joint Stationarity

Consider the two series, $x _ { t }$ and $y _ { t }$ , formed from the sum and difference of two successive values of a white noise process, say,

$$
x _ {t} = w _ {t} + w _ {t - 1}
$$

and

$$
y _ {t} = w _ {t} - w _ {t - 1},
$$

where $w _ { t }$ are independent random variables with zero means and variance $\sigma _ { w } ^ { 2 }$ . It is easy to show that $\gamma _ { x } ( 0 ) = \gamma _ { y } ( 0 ) = 2 \sigma _ { w } ^ { 2 }$ and $\gamma _ { x } ( 1 ) = \gamma _ { x } ( - 1 ) =$ $\sigma _ { w } ^ { 2 } , \gamma _ { y } ( 1 ) = \gamma _ { y } ( - 1 ) = - \sigma _ { w } ^ { 2 }$ . Also,

$$
\gamma_ {x y} (1) = \operatorname {c o v} \left(x _ {t + 1}, y _ {t}\right) = \operatorname {c o v} \left(w _ {t + 1} + w _ {t}, w _ {t} - w _ {t - 1}\right) = \sigma_ {w} ^ {2}
$$

because only one term is nonzero (recall footnote 3 on page 20). Similarly, $\gamma _ { x y } ( 0 ) = 0 , \gamma _ { x y } ( - 1 ) = - \sigma _ { w } ^ { 2 }$ . We obtain, using (1.27),

$$
\rho_ {x y} (h) = \left\{ \begin{array}{c l} 0 & h = 0, \\ 1 / 2 & h = 1, \\ - 1 / 2 & h = - 1, \\ 0 & | h | \geq 2. \end{array} \right.
$$

Clearly, the autocovariance and cross-covariance functions depend only on the lag separation, $h$ , so the series are jointly stationary.

# Example 1.22 Prediction Using Cross-Correlation

As a simple example of cross-correlation, consider the problem of determining possible leading or lagging relations between two series $x _ { t }$ and $y _ { t }$ . If the model

$$
y _ {t} = A x _ {t - \ell} + w _ {t}
$$

holds, the series $x _ { t }$ is said to lead $y _ { t }$ for $\ell > 0$ and is said to lag $y _ { t }$ for $\ell < 0$ . Hence, the analysis of leading and lagging relations might be important in predicting the value of $y _ { t }$ from $x _ { t }$ . Assuming, for convenience, that $x _ { t }$ and $y _ { t }$ have zero means, and the noise $w _ { t }$ is uncorrelated with the $x _ { t }$ series, the cross-covariance function can be computed as

$$
\begin{array}{l} \gamma_ {y x} (h) = \operatorname {c o v} \left(y _ {t + h}, x _ {t}\right) = \operatorname {c o v} \left(A x _ {t + h - \ell} + w _ {t + h}, x _ {t}\right) \\ = \operatorname {c o v} \left(A x _ {t + h - \ell}, x _ {t}\right) = A \gamma_ {x} (h - \ell). \\ \end{array}
$$

The cross-covariance function will look like the autocovariance of the input series $x _ { t }$ , with a peak on the positive side if $x _ { t }$ leads $y _ { t }$ and a peak on the negative side if $x _ { t }$ lags $y _ { t }$ .

The concept of weak stationarity forms the basis for much of the analysis performed with time series. The fundamental properties of the mean and autocovariance functions (1.21) and (1.22) are satisfied by many theoretical models that appear to generate plausible sample realizations. In Examples 1.9 and 1.10, two series were generated that produced stationary looking realizations, and in Example 1.20, we showed that the series in Example 1.9 was, in fact, weakly stationary. Both examples are special cases of the so-called linear process.

Definition 1.12 A linear process, $x _ { t }$ , is defined to be a linear combination of white noise variates $w _ { t }$ , and is given by

$$
x _ {t} = \mu + \sum_ {j = - \infty} ^ {\infty} \psi_ {j} w _ {t - j}, \quad \sum_ {j = - \infty} ^ {\infty} | \psi_ {j} | <   \infty . \tag {1.29}
$$

For the linear process (see Problem 1.11), we may show that the autocovariance function is given by

$$
\gamma (h) = \sigma_ {w} ^ {2} \sum_ {j = - \infty} ^ {\infty} \psi_ {j + h} \psi_ {j} \tag {1.30}
$$

for $h \geq 0$ ; recall that $\gamma ( - h ) = \gamma ( h )$ . This method exhibits the autocovariance function of the process in terms of the lagged products of the coefficients. Note that, for Example 1.9, we have $\psi _ { 0 } = \psi _ { - 1 } = \psi _ { 1 } = 1 / 3$ and the result in Example 1.20 comes out immediately. The autoregressive series in Example 1.10 can also be put in this form, as can the general autoregressive moving average processes considered in Chapter 3.

Finally, as previously mentioned, an important case in which a weakly stationary series is also strictly stationary is the normal or Gaussian series.

Definition 1.13 A process, $\{ x _ { t } \}$ , is said to be a Gaussian process if the $n$ -dimensional vectors $\pmb { x } = ( x _ { t _ { 1 } } , x _ { t _ { 2 } } , . . . , x _ { t _ { n } } ) ^ { \prime }$ , for every collection of time points $t _ { 1 } , t _ { 2 } , \ldots , t _ { n }$ , and every positive integer $n$ , have a multivariate normal distribution.

Defining the $n \times 1$ mean vector $E ( \pmb { x } ) \equiv \pmb { \mu } = ( \mu _ { t _ { 1 } } , \mu _ { t _ { 2 } } , . . . , \mu _ { t _ { n } } ) ^ { \prime }$ and the $n \times n$ covariance matrix as $\operatorname { v a r } ( { \pmb x } ) \equiv r = \{ \gamma ( t _ { i } , t _ { j } ) ; ~ i , j = 1 , \dots , n \}$ , which is

assumed to be positive definite, the multivariate normal density function can be written as

$$
f (\boldsymbol {x}) = (2 \pi) ^ {- n / 2} | \Gamma | ^ {- 1 / 2} \exp \left\{- \frac {1}{2} (\boldsymbol {x} - \boldsymbol {\mu}) ^ {\prime} \Gamma^ {- 1} (\boldsymbol {x} - \boldsymbol {\mu}) \right\}, \tag {1.31}
$$

where $\left| \cdot \right|$ denotes the determinant. This distribution forms the basis for solving problems involving statistical inference for time series. If a Gaussian time series, $\{ x _ { t } \}$ , is weakly stationary, then $\mu _ { t } ~ = ~ \mu$ and $\gamma ( t _ { i } , t _ { j } ) = \gamma ( | t _ { i } - t _ { j } | )$ , so that the vector and the matrix $\varGamma$ are independent of time. These facts $\pmb { \mu }$ imply that all the finite distributions, (1.31), of the series $\{ x _ { t } \}$ depend only on time lag and not on the actual times, and hence the series must be strictly stationary.

# 1.6 Estimation of Correlation

Although the theoretical autocorrelation and cross-correlation functions are useful for describing the properties of certain hypothesized models, most of the analyses must be performed using sampled data. This limitation means the sampled points $x _ { 1 } , x _ { 2 } , \ldots , x _ { n }$ only are available for estimating the mean, autocovariance, and autocorrelation functions. From the point of view of classical statistics, this poses a problem because we will typically not have iid copies of $x _ { t }$ that are available for estimating the covariance and correlation functions. In the usual situation with only one realization, however, the assumption of stationarity becomes critical. Somehow, we must use averages over this single realization to estimate the population means and covariance functions.

Accordingly, if a time series is stationary, the mean function (1.21) $\mu _ { t } = \mu$ is constant so that we can estimate it by the sample mean,

$$
\bar {x} = \frac {1}{n} \sum_ {t = 1} ^ {n} x _ {t}. \tag {1.32}
$$

The standard error of the estimate is the square root of $\mathrm { v a r } ( \bar { x } )$ , which can be computed using first principles (recall footnote 3 on page 20), and is given by

$$
\begin{array}{l} \operatorname {v a r} (\bar {x}) = \operatorname {v a r} \left(\frac {1}{n} \sum_ {t = 1} ^ {n} x _ {t}\right) = \frac {1}{n ^ {2}} \operatorname {c o v} \left(\sum_ {t = 1} ^ {n} x _ {t}, \sum_ {s = 1} ^ {n} x _ {s}\right) \\ = \frac {1}{n ^ {2}} \left(n \gamma_ {x} (0) + (n - 1) \gamma_ {x} (1) + (n - 2) \gamma_ {x} (2) + \dots + \gamma_ {x} (n - 1) \right. \\ \left. + (n - 1) \gamma_ {x} (- 1) + (n - 2) \gamma_ {x} (- 2) + \dots + \gamma_ {x} (1 - n)\right) \\ = \frac {1}{n} \sum_ {h = - n} ^ {n} \left(1 - \frac {| h |}{n}\right) \gamma_ {x} (h). \tag {1.33} \\ \end{array}
$$

If the process is white noise, (1.33) reduces to the familiar $\sigma _ { x } ^ { 2 } / n$ recalling that $\gamma _ { x } ( 0 ) = \sigma _ { x } ^ { 2 }$ . Note that, in the case of dependence, the standard error of $x$ may be smaller or larger than the white noise case depending on the nature of the correlation structure (see Problem 1.19)

The theoretical autocovariance function, (1.22), is estimated by the sample autocovariance function defined as follows.

Definition 1.14 The sample autocovariance function is defined as

$$
\widehat {\gamma} (h) = n ^ {- 1} \sum_ {t = 1} ^ {n - h} \left(x _ {t + h} - \bar {x}\right) \left(x _ {t} - \bar {x}\right), \tag {1.34}
$$

with ${ \widehat { \gamma } } ( - h ) = { \widehat { \gamma } } ( h )$ for $h = 0 , 1 , \ldots , n - 1$ .

The sum in (1.34) runs over a restricted range because $x _ { t + h }$ is not available for $t + h > n$ . The estimator in (1.34) is preferred to the one that would be obtained by dividing by $n { - } h$ because (1.34) is a non-negative definite function. The autocovariance function, $\gamma ( h )$ , of a stationary process is non-negative definite (see Problem 1.25) ensuring that variances of linear combinations of the variates $x _ { t }$ will never be negative. And, because $\operatorname { v a r } ( a _ { 1 } x _ { t _ { 1 } } + \cdot \cdot \cdot + a _ { n } x _ { t _ { n } } )$ is never negative, the estimate of that variance should also be non-negative. The estimator in (1.34) guarantees this result, but no such guarantee exists if we divide by $n - h$ ; this is explored further in Problem 1.25. Note that neither dividing by $n$ nor $n - h$ in (1.34) yields an unbiased estimator of $\gamma ( h )$ .

Definition 1.15 The sample autocorrelation function is defined, analogously to (1.23), as

$$
\widehat {\rho} (h) = \frac {\widehat {\gamma} (h)}{\widehat {\gamma} (0)}. \tag {1.35}
$$

The sample autocorrelation function has a sampling distribution that allows us to assess whether the data comes from a completely random or white series or whether correlations are statistically significant at some lags.

# Property 1.1 Large-Sample Distribution of the ACF

Under general conditions,5 if $x _ { t }$ is white noise, then for n large, the sample ACF, ${ \widehat { \rho } } _ { x } ( h )$ , for $h = 1 , 2 , \ldots , H$ , where $H$ is fixed but arbitrary, is approximately normally distributed with zero mean and standard deviation given by

$$
\sigma_ {\hat {\rho} _ {x} (h)} = \frac {1}{\sqrt {n}}. \tag {1.36}
$$

Based on the previous result, we obtain a rough method of assessing whether peaks in ${ \widehat { \rho } } ( h )$ are significant by determining whether the observed peak is outside the interval $\pm 2 / \sqrt { n }$ (or plus/minus two standard errors); for a white noise sequence, approximately 95% of the sample ACFs should be within these limits. The applications of this property develop because many statistical modeling procedures depend on reducing a time series to a white noise series using various kinds of transformations. After such a procedure is applied, the plotted ACFs of the residuals should then lie roughly within the limits given above.

Definition 1.16 The estimators for the cross-covariance function, $\gamma _ { x y } ( h )$ , as given in (1.26) and the cross-correlation, $\rho _ { x y } ( h )$ , in (1.27) are given, respectively, by the sample cross-covariance function

$$
\widehat {\gamma} _ {x y} (h) = n ^ {- 1} \sum_ {t = 1} ^ {n - h} \left(x _ {t + h} - \bar {x}\right) \left(y _ {t} - \bar {y}\right), \tag {1.37}
$$

where $\widehat { \gamma } _ { x y } ( - h ) = \widehat { \gamma } _ { y x } ( h )$ determines the function for negative lags, and the sample cross-correlation function

$$
\widehat {\rho} _ {x y} (h) = \frac {\widehat {\gamma} _ {x y} (h)}{\sqrt {\widehat {\gamma} _ {x} (0) \widehat {\gamma} _ {y} (0)}}. \tag {1.38}
$$

The sample cross-correlation function can be examined graphically as a function of lag $h$ to search for leading or lagging relations in the data using the property mentioned in Example 1.22 for the theoretical cross-covariance function. Because $- 1 \leq \widehat { \rho } _ { x y } ( h ) \leq 1$ , the practical importance of peaks can be assessed by comparing their magnitudes with their theoretical maximum values. Furthermore, for $x _ { t }$ and $y _ { t }$ independent linear processes of the form (1.29), we have the following property.

# Property 1.2 Large-Sample Distribution of Cross-Correlation Under Independence

The large sample distribution of ${ \widehat { \rho } } _ { x y } ( h )$ is normal with mean zero and

$$
\sigma_ {\hat {\rho} _ {x y}} = \frac {1}{\sqrt {n}} \tag {1.39}
$$

if at least one of the processes is independent white noise (see Theorem A.8 in Appendix A).

# Example 1.23 A Simulated Time Series

To give an example of the procedure for calculating numerically the autocovariance and cross-covariance functions, consider a contrived set of data

Table 1.1. Sample Realization of the Contrived Series $y _ { t }$   

<table><tr><td>t</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>Coin</td><td>H</td><td>H</td><td>T</td><td>H</td><td>T</td><td>T</td><td>T</td><td>H</td><td>T</td><td>H</td></tr><tr><td>xt</td><td>1</td><td>1</td><td>-1</td><td>1</td><td>-1</td><td>-1</td><td>-1</td><td>1</td><td>-1</td><td>1</td></tr><tr><td>yt</td><td>6.7</td><td>5.3</td><td>3.3</td><td>6.7</td><td>3.3</td><td>4.7</td><td>4.7</td><td>6.7</td><td>3.3</td><td>6.7</td></tr><tr><td>yt - y</td><td>1.56</td><td>.16</td><td>-1.84</td><td>1.56</td><td>-1.84</td><td>-.44</td><td>-.44</td><td>1.56</td><td>-1.84</td><td>1.56</td></tr></table>

generated by tossing a fair coin, letting $x _ { t } = 1$ when a head is obtained and $x _ { t } = - 1$ when a tail is obtained. Construct $y _ { t }$ as

$$
y _ {t} = 5 + x _ {t} - . 7 x _ {t - 1}. \tag {1.40}
$$

Table 1.1 shows sample realizations of the appropriate processes with $x _ { 0 } =$ $^ { - 1 }$ and $n = 1 0$ .

The sample autocorrelation for the series $y _ { t }$ can be calculated using (1.34) and (1.35) for $h = 0 , 1 , 2 , \ldots$ It is not necessary to calculate for negative values because of the symmetry. For example, for $h = 3$ , the autocorrelation becomes the ratio of

$$
\begin{array}{l} \widehat {\gamma} _ {y} (3) = \frac {1}{1 0} \sum_ {t = 1} ^ {7} \left(y _ {t + 3} - \bar {y}\right) \left(y _ {t} - \bar {y}\right) \\ = \frac {1}{1 0} \left[ (1. 5 6) (1. 5 6) + (- 1. 8 4) (. 1 6) + (-. 4 4) (- 1. 8 4) + (-. 4 4) (1. 5 6) \right. \\ + (1. 5 6) (- 1. 8 4) + (- 1. 8 4) (-. 4 4) + (1. 5 6) (-. 4 4) \bigg ] = -. 0 4 8 \\ \end{array}
$$

to

$$
\widehat {\gamma} _ {y} (0) = \frac {1}{1 0} \left[ (1. 5 6) ^ {2} + (. 1 6) ^ {2} + \dots + (1. 5 6) ^ {2} \right] = 2. 0 3 0
$$

so that

$$
\widehat {\rho} _ {y} (3) = \frac {- . 0 4 8}{2 . 0 3 0} = -. 0 2 4.
$$

The theoretical ACF can be obtained from the model (1.40) using the fact that the mean of $x _ { t }$ is zero and the variance of $x _ { t }$ is one. It can be shown that

$$
\rho_ {y} (1) = \frac {- . 7}{1 + . 7 ^ {2}} = -. 4 7
$$

and $\rho _ { y } ( h ) = 0$ for $| h | > 1$ (Problem 1.24). Table 1.2 compares the theoretical ACF with sample ACFs for a realization where $n = 1 0$ and another realization where $n = 1 0 0$ ; we note the increased variability in the smaller size sample.

Table 1.2. Theoretical and Sample ACFs for $n = 1 0$ and $n = 1 0 0$   

<table><tr><td rowspan="2">h</td><td rowspan="2">ρy(h)</td><td>n = 10</td><td>n = 100</td></tr><tr><td>ρy(h)</td><td>ρy(h)</td></tr><tr><td>0</td><td>1.00</td><td>1.00</td><td>1.00</td></tr><tr><td>±1</td><td>-.47</td><td>-.55</td><td>-.45</td></tr><tr><td>±2</td><td>.00</td><td>.17</td><td>-.12</td></tr><tr><td>±3</td><td>.00</td><td>-.02</td><td>.14</td></tr><tr><td>±4</td><td>.00</td><td>.15</td><td>.01</td></tr><tr><td>±5</td><td>.00</td><td>-.46</td><td>-.01</td></tr></table>

# Example 1.24 ACF of a Speech Signal

Computing the sample ACF as in the previous example can be thought of as matching the time series $h$ units in the future, say, $x _ { t + h }$ against itself, $x _ { t }$ . Figure 1.13 shows the ACF of the speech series of Figure 1.3. The original series appears to contain a sequence of repeating short signals. The ACF confirms this behavior, showing repeating peaks spaced at about 106-109 points. Autocorrelation functions of the short signals appear, spaced at the intervals mentioned above. The distance between the repeating signals is known as the pitch period and is a fundamental parameter of interest in systems that encode and decipher speech. Because the series is sampled at 10,000 points per second, the pitch period appears to be between .0106 and .0109 seconds.

To put the data into speech as a time series object (if it is not there already from Example 1.3) and compute the sample ACF in R, use 1 acf(speech, 250)

# Example 1.25 SOI and Recruitment Correlation Analysis

The autocorrelation and cross-correlation functions are also useful for analyzing the joint behavior of two stationary series whose behavior may be related in some unspecified way. In Example 1.5 (see Figure 1.5), we have considered simultaneous monthly readings of the SOI and the number of new fish (Recruitment) computed from a model. Figure 1.14 shows the autocorrelation and cross-correlation functions (ACFs and CCF) for these two series. Both of the ACFs exhibit periodicities corresponding to the correlation between values separated by 12 units. Observations 12 months or one year apart are strongly positively correlated, as are observations at multiples such as $2 4 , 3 6 , 4 8 , \ldots$ Observations separated by six months are negatively correlated, showing that positive excursions tend to be associated with negative excursions six months removed. This appearance is rather characteristic of the pattern that would be produced by a sinusoidal component with a period of 12 months. The cross-correlation function peaks at $h = - 6$ , showing that the SOI measured at time $t - 6$ months is associated with the Recruitment series at time $t$ . We could say the SOI leads the Recruitment series by

![](images/4bc0313ca776daafa3f1447317bfd93d1733b4f9d22535ec61fa7487f48413db.jpg)  
Fig. 1.13. ACF of the speech series.

six months. The sign of the ACF is negative, leading to the conclusion that the two series move in different directions; that is, increases in SOI lead to decreases in Recruitment and vice versa. Again, note the periodicity of 12 months in the CCF. The flat lines shown on the plots indicate $\pm 2 / \sqrt { 4 5 3 }$ , so that upper values would be exceeded about $2 . 5 \%$ of the time if the noise were white [see (1.36) and (1.39)].

To reproduce Figure 1.14 in R, use the following commands:

1 par(mfrow=c(3,1))   
2 acf(soi, 48, main="Southern Oscillation Index")   
3 acf(rec, 48, main="Recruitment")   
4 ccf(soi, rec, 48, main="SOI vs Recruitment", ylab="CCF")

# 1.7 Vector-Valued and Multidimensional Series

We frequently encounter situations in which the relationships between a number of jointly measured time series are of interest. For example, in the previous sections, we considered discovering the relationships between the SOI and Recruitment series. Hence, it will be useful to consider the notion of a vector time series $\pmb { x } _ { t } = ( x _ { t 1 } , x _ { t 2 } , . . . , x _ { t p } ) ^ { \prime }$ , which contains as its components $p$ univariate time series. We denote the $p \times 1$ column vector of the observed series as ${ \pmb x } _ { t }$ . The row vector $\pmb { x } _ { t } ^ { \prime }$ is its transpose. For the stationary case, the $p \times 1$ mean vector

$$
\boldsymbol {\mu} = E \left(\boldsymbol {x} _ {t}\right) \tag {1.41}
$$

of the form $\pmb { \mu } = ( \mu _ { t 1 } , \mu _ { t 2 } , . . . , \mu _ { t p } ) ^ { \prime }$ and the $p \times p$ autocovariance matrix

![](images/40ba33aea52456c5e964d3b2aff04d3418397556fe1b8583796b7620861fd467.jpg)

![](images/fb01e0cdd903d1bf7f51dcfd7af681eb124b99f0137f20fa3fc8f629147be25e.jpg)

![](images/af4a5a4b62999e1b78d0eb998f31e04e82b1ed31d014ef0f25f845c2712d9edc.jpg)  
Fig. 1.14. Sample ACFs of the SOI series (top) and of the Recruitment series (middle), and the sample CCF of the two series (bottom); negative lags indicate SOI leads Recruitment. The lag axes are in terms of seasons (12 months).

$$
\Gamma (h) = E \left[ \left(\boldsymbol {x} _ {t + h} - \boldsymbol {\mu}\right) \left(\boldsymbol {x} _ {t} - \boldsymbol {\mu}\right) ^ {\prime} \right] \tag {1.42}
$$

can be defined, where the elements of the matrix $T ( h )$ are the cross-covariance functions

$$
\gamma_ {i j} (h) = E \left[ \left(x _ {t + h, i} - \mu_ {i}\right) \left(x _ {t j} - \mu_ {j}\right) \right] \tag {1.43}
$$

for $i , j = 1 , \dotsc , p$ . Because $\gamma _ { i j } ( h ) = \gamma _ { j i } ( - h )$ , it follows that

$$
\Gamma (- h) = \Gamma^ {\prime} (h). \tag {1.44}
$$

Now, the sample autocovariance matrix of the vector series ${ \pmb x } _ { t }$ is the $p \times p$ matrix of sample cross-covariances, defined as

$$
\widehat {\Gamma} (h) = n ^ {- 1} \sum_ {t = 1} ^ {n - h} \left(\boldsymbol {x} _ {t + h} - \bar {\boldsymbol {x}}\right) \left(\boldsymbol {x} _ {t} - \bar {\boldsymbol {x}}\right) ^ {\prime}, \tag {1.45}
$$

![](images/ab8219657ac802f9440113079ed57a5ad7ceb96f93a9304200d416d1768021c1.jpg)  
Fig. 1.15. Two-dimensional time series of temperature measurements taken on a rectangular field ( $6 4 \times 3 6$ with 17-foot spacing). Data are from Bazza et al. (1988).

where

$$
\bar {\boldsymbol {x}} = n ^ {- 1} \sum_ {t = 1} ^ {n} \boldsymbol {x} _ {t} \tag {1.46}
$$

denotes the $p \times 1$ sample mean vector. The symmetry property of the theoretical autocovariance (1.44) extends to the sample autocovariance (1.45), which is defined for negative values by taking

$$
\widehat {\Gamma} (- h) = \widehat {\Gamma} (h) ^ {\prime}. \tag {1.47}
$$

In many applied problems, an observed series may be indexed by more than time alone. For example, the position in space of an experimental unit might be described by two coordinates, say, $s _ { 1 }$ and $s _ { 2 }$ . We may proceed in these cases by defining a multidimensional process $x _ { s }$ as a function of the $r \times 1$ vector $\pmb { \mathscr { s } } = ( \mathscr { s } _ { 1 } , \mathscr { s } _ { 2 } , \mathscr { . ~ . ~ . ~ } , \mathscr { s } _ { r } ) ^ { \prime }$ , where $s _ { i }$ denotes the coordinate of the $i$ th index.

# Example 1.26 Soil Surface Temperatures

As an example, the two-dimensional ( $r \ = \ 2$ ) temperature series $x _ { s _ { 1 } , s _ { 2 } }$ in Figure 1.15 is indexed by a row number $s _ { 1 }$ and a column number $s _ { 2 }$ that

represent positions on a $6 4 \times 3 6$ spatial grid set out on an agricultural field. The value of the temperature measured at row $s _ { 1 }$ and column $s _ { 2 }$ , is denoted by $x _ { \pmb { S } } = x _ { s 1 , s 2 }$ . We can note from the two-dimensional plot that a distinct change occurs in the character of the two-dimensional surface starting at about row 40, where the oscillations along the row axis become fairly stable and periodic. For example, averaging over the 36 columns, we may compute an average value for each $s _ { 1 }$ as in Figure 1.16. It is clear that the noise present in the first part of the two-dimensional series is nicely averaged out, and we see a clear and consistent temperature signal.

To generate Figures 1.15 and 1.16 in R, use the following commands:

1 persp(1:64, 1:36, soiltemp, phi=30, theta=30, scale=FALSE, expand=4, ticktype="detailed", xlab="rows", ylab="cols", zlab="temperature")   
2 plot.ts(rowMeans(soiltemp), xlab="row", ylab $=$ "Average Temperature")

The autocovariance function of a stationary multidimensional process, $x _ { s }$ , can be defined as a function of the multidimensional lag vector, say, $\textbf { \em h } =$ $( h _ { 1 } , h _ { 2 } , \ldots , h _ { r } ) ^ { \prime }$ , as

$$
\gamma (\boldsymbol {h}) = E \left[ \left(x _ {\boldsymbol {s} + \boldsymbol {h}} - \mu\right) \left(x _ {\boldsymbol {s}} - \mu\right) \right], \tag {1.48}
$$

where

$$
\mu = E \left(x _ {\boldsymbol {s}}\right) \tag {1.49}
$$

does not depend on the spatial coordinate $\pmb { s }$ . For the two dimensional temperature process, (1.48) becomes

$$
\gamma \left(h _ {1}, h _ {2}\right) = E \left[ \left(x _ {s _ {1} + h _ {1}, s _ {2} + h _ {2}} - \mu\right) \left(x _ {s _ {1}, s _ {2}} - \mu\right) \right], \tag {1.50}
$$

which is a function of lag, both in the row ( $h _ { 1 }$ ) and column ( $h _ { 2 }$ ) directions.

The multidimensional sample autocovariance function is defined as

$$
\widehat {\gamma} (\boldsymbol {h}) = \left(S _ {1} S _ {2} \dots S _ {r}\right) ^ {- 1} \sum_ {s _ {1}} \sum_ {s _ {2}} \dots \sum_ {s _ {r}} \left(x _ {\boldsymbol {s} + \boldsymbol {h}} - \bar {x}\right) \left(x _ {\boldsymbol {s}} - \bar {x}\right), \tag {1.51}
$$

where $\pmb { \mathscr { s } } = ( \mathscr { s } _ { 1 } , \mathscr { s } _ { 2 } , \mathscr { . . . } , \mathscr { s } _ { r } ) ^ { \prime }$ and the range of summation for each argument is $1 \leq s _ { i } \leq S _ { i } - h _ { i }$ , for $i = 1 , \ldots , r .$ The mean is computed over the $r$ -dimensional array, that is,

$$
\bar {x} = \left(S _ {1} S _ {2} \dots S _ {r}\right) ^ {- 1} \sum_ {s _ {1}} \sum_ {s _ {2}} \dots \sum_ {s _ {r}} x _ {s _ {1}, s _ {2}, \dots , s _ {r}}, \tag {1.52}
$$

where the arguments $s _ { i }$ are summed over $1 \leq s _ { i } \leq S _ { i }$ . The multidimensional sample autocorrelation function follows, as usual, by taking the scaled ratio

$$
\widehat {\rho} (\boldsymbol {h}) = \frac {\widehat {\gamma} (\boldsymbol {h})}{\widehat {\gamma} (\boldsymbol {0})}. \tag {1.53}
$$

![](images/eda406c5517a9370a6687ed4d1f833ec68827f1635f0d256a4e03fb49119c5cb.jpg)  
Fig. 1.16. Row averages of the two-dimensional soil temperature profile. $\begin{array} { r l } { \bar { x } _ { s _ { 1 } } } & { { } = } \end{array}$ $\sum _ { s _ { 2 } } x _ { s _ { 1 } , s _ { 2 } } / 3 6$ .

# Example 1.27 Sample ACF of the Soil Temperature Series

The autocorrelation function of the two-dimensional (2d) temperature process can be written in the form

$$
\widehat {\rho} (h _ {1}, h _ {2}) = \frac {\widehat {\gamma} (h _ {1} , h _ {2})}{\widehat {\gamma} (0 , 0)},
$$

where

$$
\widehat {\gamma} (h _ {1}, h _ {2}) = (S _ {1} S _ {2}) ^ {- 1} \sum_ {s _ {1}} \sum_ {s _ {2}} (x _ {s _ {1} + h _ {1}, s _ {2} + h _ {2}} - \bar {x}) (x _ {s _ {1}, s _ {2}} - \bar {x})
$$

Figure 1.17 shows the autocorrelation function for the temperature data, and we note the systematic periodic variation that appears along the rows. The autocovariance over columns seems to be strongest for $h _ { 1 } = 0$ , implying columns may form replicates of some underlying process that has a periodicity over the rows. This idea can be investigated by examining the mean series over columns as shown in Figure 1.16.

The easiest way (that we know of) to calculate a 2d ACF in R is by using the fast Fourier transform (FFT) as shown below. Unfortunately, the material needed to understand this approach is given in Chapter 4, 4.4. The 2d autocovariance function is obtained in two steps and is contained in cs below; $\widehat { \gamma } ( 0 , 0 )$ is the (1,1) element so that $\widehat { \rho } ( h _ { 1 } , h _ { 2 } )$ is obtained by dividing each element by that value. The 2d ACF is contained in $\mathbf { r s }$ below, and the rest of the code is simply to arrange the results to yield a nice display.

![](images/0ca3567ed21f989456a4b245e4e333b3b7796ab893476194d86b64192fd6bd66.jpg)  
Fig. 1.17. Two-dimensional autocorrelation function for the soil temperature data.

```txt
1 fs = abs(fft(soiltemp-mean(soiltemp))~2/(64*36)  
2 cs = Re(fft(fs, inverse=TRUE)/sqrt(64*36)) # ACoU F  
3 rs = cs/cs[1,1] # ACF  
4 rs2 = cbind(rs[1:41,21:2], rs[1:41,1:21])  
5 rs3 = rbind(rs2[41:2,], rs2)  
6 par(mar = c(1,2.5,0,0)+.1)  
7 persp(-40:40, -20:20, rs3, phi=30, theta=30, expand=30, scale="FALSE", ticktype="detailed", xlab="row lags", ylab="column lags", zlab="ACF") 
```

The sampling requirements for multidimensional processes are rather severe because values must be available over some uniform grid in order to compute the ACF. In some areas of application, such as in soil science, we may prefer to sample a limited number of rows or transects and hope these are essentially replicates of the basic underlying phenomenon of interest. Onedimensional methods can then be applied. When observations are irregular in time space, modifications to the estimators need to be made. Systematic approaches to the problems introduced by irregularly spaced observations have been developed by Journel and Huijbregts (1978) or Cressie (1993). We shall not pursue such methods in detail here, but it is worth noting that the introduction of the variogram

$$
2 V _ {x} (\boldsymbol {h}) = \operatorname {v a r} \left\{x _ {\boldsymbol {s} + \boldsymbol {h}} - x _ {\boldsymbol {s}} \right\} \tag {1.54}
$$

and its sample estimator

$$
2 \widehat {V} _ {x} (\boldsymbol {h}) = \frac {1}{N (\boldsymbol {h})} \sum_ {\boldsymbol {s}} \left(x _ {\boldsymbol {s} + \boldsymbol {h}} - x _ {\boldsymbol {s}}\right) ^ {2} \tag {1.55}
$$

play key roles, where $N ( h )$ denotes both the number of points located within $^ { h }$ , and the sum runs over the points in the neighborhood. Clearly, substantial indexing difficulties will develop from estimators of the kind, and often it will be difficult to find non-negative definite estimators for the covariance function. Problem 1.27 investigates the relation between the variogram and the autocovariance function in the stationary case.

# Problems

# Section 1.2

1.1 To compare the earthquake and explosion signals, plot the data displayed in Figure 1.7 on the same graph using different colors or different line types and comment on the results. (The R code in Example 1.11 may be of help on how to add lines to existing plots.)

1.2 Consider a signal-plus-noise model of the general form $x _ { t } ~ = ~ s _ { t } + w _ { t }$ , where $w _ { t }$ is Gaussian white noise with $\sigma _ { w } ^ { 2 } = 1$ . Simulate and plot $n = 2 0 0$ observations from each of the following two models (Save the data or your code for use in Problem 1.22 ):

(a) $x _ { t } = s _ { t } + w _ { t }$ , for $t = 1 , . . . , 2 0 0$ , where

$$
s _ {t} = \left\{ \begin{array}{l l} 0, & t = 1, \ldots , 1 0 0 \\ 1 0 \exp \{- \frac {(t - 1 0 0)}{2 0} \} \cos (2 \pi t / 4), & t = 1 0 1, \ldots , 2 0 0. \end{array} \right.
$$

Hint:

$$
\begin{array}{l} s = c (\text {r e p} (0, 1 0 0), 1 0 * \exp (- (1: 1 0 0) / 2 0) * \cos (2 * \text {p i} * 1: 1 0 0 / 4)) \\ \mathrm {x} = \operatorname {t s} (\mathrm {s} + \operatorname {r n o r m} (2 0 0, 0, 1)) \\ 3 \operatorname {p l o t} (x) \\ \end{array}
$$

$\mathrm { b } ) x _ { t } = s _ { t } + w _ { t }$ , for $t = 1 , \ldots , 2 0 0$ , where

$$
s _ {t} = \left\{ \begin{array}{l l} 0, & t = 1, \ldots , 1 0 0 \\ 1 0 \exp \{- \frac {(t - 1 0 0)}{2 0 0} \} \cos (2 \pi t / 4), & t = 1 0 1, \ldots , 2 0 0. \end{array} \right.
$$

(c) Compare the general appearance of the series (a) and (b) with the earthquake series and the explosion series shown in Figure 1.7. In addition, plot (or sketch) and compare the signal modulators (a) $\exp \{ - t / 2 0 \}$ and (b) $\exp \{ - t / 2 0 0 \}$ , for $t = 1 , 2 , \ldots , 1 0 0$ .

# Section 1.3

1.3 (a) Generate $n = 1 0 0$ observations from the autoregression

$$
x _ {t} = -. 9 x _ {t - 2} + w _ {t}
$$

with $\sigma _ { w } = 1$ , using the method described in Example 1.10, page 13. Next, apply the moving average filter

$$
v _ {t} = (x _ {t} + x _ {t - 1} + x _ {t - 2} + x _ {t - 3}) / 4
$$

to $x _ { t }$ , the data you generated. Now plot $x _ { t }$ as a line and superimpose $v _ { t }$ as a dashed line. Comment on the behavior of $x _ { t }$ and how applying the moving average filter changes that behavior. [Hints: Use $\mathtt { v } = \mathtt { f i l t e r } ( \mathtt { x } ,$ ， rep(1/4, 4), sides $\mathit { \Theta } = \mathit { \Theta } 1$ ) for the filter and note that the R code in Example 1.11 may be of help on how to add lines to existing plots.]

(b) Repeat (a) but with

$$
x _ {t} = \cos (2 \pi t / 4).
$$

(c) Repeat (b) but with added $\mathrm { { N } } ( 0 , 1 )$ noise,

$$
x _ {t} = \cos (2 \pi t / 4) + w _ {t}.
$$

(d) Compare and contrast (a)–(c).

# Section 1.4

1.4 Show that the autocovariance function can be written as

$$
\gamma (s, t) = E \left[ \left(x _ {s} - \mu_ {s}\right) \left(x _ {t} - \mu_ {t}\right) \right] = E \left(x _ {s} x _ {t}\right) - \mu_ {s} \mu_ {t},
$$

where $E [ x _ { t } ] = \mu _ { t }$

1.5 For the two series, $x _ { t }$ , in Problem 1.2 (a) and (b):

(a) Compute and plot the mean functions $\mu _ { x } ( t )$ , for $t = 1 , \ldots , 2 0 0$   
(b) Calculate the autocovariance functions, $\gamma _ { x } ( s , t )$ , for $s , t = 1 , \ldots , 2 0 0$

# Section 1.5

1.6 Consider the time series

$$
x _ {t} = \beta_ {1} + \beta_ {2} t + w _ {t},
$$

where $\beta _ { 1 }$ and $\beta _ { 2 }$ are known constants and $w _ { t }$ is a white noise process with variance $\sigma _ { w } ^ { 2 }$ .

(a) Determine whether $x _ { t }$ is stationary.   
(b) Show that the process $y _ { t } = x _ { t } - x _ { t - 1 }$ is stationary.

(c) Show that the mean of the moving average

$$
v _ {t} = \frac {1}{2 q + 1} \sum_ {j = - q} ^ {q} x _ {t - j}
$$

is $\beta _ { 1 } + \beta _ { 2 } t$ , and give a simplified expression for the autocovariance function.

1.7 For a moving average process of the form

$$
x _ {t} = w _ {t - 1} + 2 w _ {t} + w _ {t + 1},
$$

where $w _ { t }$ are independent with zero means and variance $\sigma _ { w } ^ { 2 }$ , determine the autocovariance and autocorrelation functions as a function of lag $h = s - t$ and plot the ACF as a function of $h$ .

1.8 Consider the random walk with drift model

$$
x _ {t} = \delta + x _ {t - 1} + w _ {t},
$$

for $t = 1 , 2 , \ldots$ , with $x _ { 0 } = 0$ , where $w _ { t }$ is white noise with variance $\sigma _ { w } ^ { 2 }$

$\begin{array} { r } { \boldsymbol { x } _ { t } = \boldsymbol { \delta t } + \sum _ { k = 1 } ^ { t } \boldsymbol { w } _ { k } } \end{array}$   
(b) Find the mean function and the autocovariance function of $x _ { t }$   
(c) Argue that $x _ { t }$ is not stationary.   
(d) Show $\begin{array} { r } { \rho _ { x } ( t - 1 , t ) = \sqrt { \frac { t - 1 } { t } } \to 1 } \end{array}$ as $t \to \infty$ . What is the implication of this result?   
(e) Suggest a transformation to make the series stationary, and prove that the transformed series is stationary. (Hint: See Problem 1.6b.)

1.9 A time series with a periodic component can be constructed from

$$
x _ {t} = U _ {1} \sin (2 \pi \omega_ {0} t) + U _ {2} \cos (2 \pi \omega_ {0} t),
$$

where $U _ { 1 }$ and $U _ { 2 }$ are independent random variables with zero means and $E ( U _ { 1 } ^ { 2 } ) = E ( U _ { 2 } ^ { 2 } ) = \sigma ^ { 2 }$ . The constant $\omega _ { 0 }$ determines the period or time it takes the process to make one complete cycle. Show that this series is weakly stationary with autocovariance function

$$
\gamma (h) = \sigma^ {2} \cos (2 \pi \omega_ {0} h).
$$

1.10 Suppose we would like to predict a single stationary series $x _ { t }$ with zero mean and autocorrelation function $\gamma ( h )$ at some time in the future, say, $t + \ell$ , for $\ell > 0$ .

(a) If we predict using only $x _ { t }$ and some scale multiplier $A$ , show that the mean-square prediction error

$$
M S E (A) = E \left[ \left(x _ {t + \ell} - A x _ {t}\right) ^ {2} \right]
$$

is minimized by the value

$$
A = \rho (\ell).
$$

(b) Show that the minimum mean-square prediction error is

$$
M S E (A) = \gamma (0) [ 1 - \rho^ {2} (\ell) ].
$$

(c) Show that if $x _ { t + \ell } = A x _ { t }$ , then $\rho ( \ell ) = 1$ if $A > 0$ , and $\rho ( \ell ) = - 1$ if $A < 0$

1.11 Consider the linear process defined in (1.29).

(a) Verify that the autocovariance function of the process is given by (1.30). Use the result to verify your answer to Problem 1.7.   
(b) Show that $x _ { t }$ exists as a limit in mean square (see Appendix A).

1.12 For two weakly stationary series $x _ { t }$ and $y _ { t }$ , verify (1.28).

1.13 Consider the two series

$$
x _ {t} = w _ {t}
$$

$$
y _ {t} = w _ {t} - \theta w _ {t - 1} + u _ {t},
$$

where $w _ { t }$ and $u _ { t }$ are independent white noise series with variances $\sigma _ { w } ^ { 2 }$ and $\sigma _ { u } ^ { 2 }$ respectively, and $\theta$ is an unspecified constant.

(a) Express the ACF, $\rho _ { y } ( h )$ , for $h = 0 , \pm 1 , \pm 2 , . . .$ of the series $y _ { t }$ as a function of $\sigma _ { w } ^ { 2 } , \sigma _ { u } ^ { 2 }$ , and $\theta$ .   
(b) Determine the CCF, $\rho _ { x y } ( h )$ relating $x _ { t }$ and $y _ { t }$   
(c) Show that $x _ { t }$ and $y _ { t }$ are jointly stationary.

1.14 Let $x _ { t }$ be a stationary normal process with mean $\mu _ { x }$ and autocovariance function $\gamma ( h )$ . Define the nonlinear time series

$$
y _ {t} = \exp \{x _ {t} \}.
$$

(a) Express the mean function $E ( y _ { t } )$ in terms of $\mu _ { x }$ and $\gamma ( 0 )$ . The moment generating function of a normal random variable $x$ with mean $\mu$ and variance $\sigma ^ { 2 }$ is

$$
M _ {x} (\lambda) = E [ \exp \{\lambda x \} ] = \exp \left\{\mu \lambda + \frac {1}{2} \sigma^ {2} \lambda^ {2} \right\}.
$$

(b) Determine the autocovariance function of $y _ { t }$ . The sum of the two normal random variables $x _ { t + h } + x _ { t }$ is still a normal random variable.

1.15 Let $w _ { t }$ , for $t = 0 , \pm 1 , \pm 2 , . . .$ be a normal white noise process, and consider the series

$$
x _ {t} = w _ {t} w _ {t - 1}.
$$

Determine the mean and autocovariance function of $x _ { t }$ , and state whether it is stationary.

1.16 Consider the series

$$
x _ {t} = \sin (2 \pi U t),
$$

$t = 1 , 2 , \ldots$ , where $U$ has a uniform distribution on the interval $( 0 , 1 )$ .

(a) Prove $x _ { t }$ is weakly stationary.   
(b) Prove $x _ { t }$ is not strictly stationary. [Hint: consider the joint bivariate cdf (1.18) at the points $t = 1 , s = 2$ with $h = 1$ , and find values of $c _ { t } , c _ { s }$ where strict stationarity does not hold.]

1.17 Suppose we have the linear process $x _ { t }$ generated by

$$
x _ {t} = w _ {t} - \theta w _ {t - 1},
$$

$t = 0 , 1 , 2 , \ldots$ , where $\{ w _ { t } \}$ is independent and identically distributed with characteristic function $\phi _ { w } ( \cdot )$ , and $\theta$ is a fixed constant. [Replace “characteristic function” with “moment generating function” if instructed to do so.]

(a) Express the joint characteristic function of $x _ { 1 } , x _ { 2 } , \ldots , x _ { n }$ , say,

$$
\phi_ {x _ {1}, x _ {2}, \dots , x _ {n}} (\lambda_ {1}, \lambda_ {2}, \dots , \lambda_ {n}),
$$

in terms of $\phi _ { w } ( \cdot )$ .

(b) Deduce from (a) that $x _ { t }$ is strictly stationary.

1.18 Suppose that $x _ { t }$ is a linear process of the form (1.29). Prove

$$
\sum_ {h = - \infty} ^ {\infty} | \gamma (h) | <   \infty .
$$

# Section 1.6

1.19 Suppose $x _ { 1 } , \ldots , x _ { n }$ is a sample from the process $x _ { t } = \mu + w _ { t } - . 8 w _ { t - 1 }$ where $w _ { t } \sim w n ( 0 , \sigma _ { w } ^ { 2 } )$ .

(a) Show that mean function is $E ( x _ { t } ) = \mu$   
(b) Use (1.33) to calculate the standard error of $x$ for estimating $\mu$   
(c) Compare (b) to the case where $x _ { t }$ is white noise and show that (b) is smaller. Explain the result.

1.20 (a) Simulate a series of $n = 5 0 0$ Gaussian white noise observations as in Example 1.8 and compute the sample ACF, $\widehat { \rho } ( h )$ , to lag 20. Compare the sample ACF you obtain to the actual ACF, $\rho ( h )$ . [Recall Example 1.19.]

(b) Repeat part (a) using only $n = 5 0 .$ . How does changing $n$ affect the results?

1.21 (a) Simulate a series of $n = 5 0 0$ moving average observations as in Example 1.9 and compute the sample ACF, $\widehat { \rho } ( h )$ , to lag 20. Compare the sample ACF you obtain to the actual ACF, $\rho ( h )$ . [Recall Example 1.20.]

(b) Repeat part (a) using only $n = 5 0$ . How does changing $n$ affect the results?

1.22 Although the model in Problem 1.2(a) is not stationary (Why?), the sample ACF can be informative. For the data you generated in that problem, calculate and plot the sample ACF, and then comment.   
1.23 Simulate a series of $n \ = \ 5 0 0$ observations from the signal-plus-noise model presented in Example 1.12 with $\sigma _ { w } ^ { 2 } = 1$ . Compute the sample ACF to lag 100 of the data you generated and comment.   
1.24 For the time series $y _ { t }$ described in Example 1.23, verify the stated result that $\rho _ { y } ( 1 ) = - . 4 7$ and $\rho _ { y } ( h ) = 0$ for $h > 1$ .   
1.25 A real-valued function $g ( t )$ , defined on the integers, is non-negative definite if and only if

$$
\sum_ {i = 1} ^ {n} \sum_ {j = 1} ^ {n} a _ {i} g \left(t _ {i} - t _ {j}\right) a _ {j} \geq 0
$$

for all positive integers $n$ and for all vectors $\pmb { a } = ( a _ { 1 } , a _ { 2 } , \ldots , a _ { n } ) ^ { \prime }$ and $\pmb { t } =$ $( t _ { 1 } , t _ { 2 } , \ldots , t _ { n } ) ^ { \prime }$ . For the matrix $G = \{ g ( t _ { i } - t _ { j } )$ ; $i , j = 1 , 2 , \dots , n \}$ , this implies that ${ \pmb a } ^ { \prime } G { \pmb a } \geq 0$ for all vectors $\textbf { \em a }$ . It is called positive definite if we can replace ‘ $\geq$ ’ with ‘ $>$ ’ for all $\mathbf { \delta } \mathbf { a } \neq \mathbf { 0 }$ , the zero vector.

(a) Prove that $\gamma ( h )$ , the autocovariance function of a stationary process, is a non-negative definite function.   
(b) Verify that the sample autocovariance $\widehat { \gamma } ( h )$ is a non-negative definite function.

# Section 1.7

1.26 Consider a collection of time series $x _ { 1 t } , x _ { 2 t } , \dotsc , x _ { N t }$ that are observing some common signal $\mu _ { t }$ observed in noise processes $e _ { 1 t } , e _ { 2 t } , \ldots , e _ { N t }$ , with a model for the $j$ -th observed series given by

$$
x _ {j t} = \mu_ {t} + e _ {j t}.
$$

Suppose the noise series have zero means and are uncorrelated for different $j$ . The common autocovariance functions of all series are given by $\gamma _ { e } ( s , t )$ . Define the sample mean

$$
\bar {x} _ {t} = \frac {1}{N} \sum_ {j = 1} ^ {N} x _ {j t}.
$$

(a) Show that $E [ \bar { x } _ { t } ] = \mu _ { t }$   
(b) Show that $E [ ( \bar { x } _ { t } - \mu ) ^ { 2 } ) ] = N ^ { - 1 } \gamma _ { e } ( t , t )$   
(c) How can we use the results in estimating the common signal?

1.27 A concept used in geostatistics, see Journel and Huijbregts (1978) or Cressie (1993), is that of the variogram, defined for a spatial process $x _ { s }$ , $\pmb { s } = ( s _ { 1 } , s _ { 2 } )$ , for $s _ { 1 } , s _ { 2 } = 0 , \pm 1 , \pm 2 , . . .$ , as

$$
V _ {x} (\pmb {h}) = \frac {1}{2} E [ (x _ {\pmb {s} + \pmb {h}} - x _ {\pmb {s}}) ^ {2} ],
$$

where $\pmb { h } \ = \ ( h _ { 1 } , h _ { 2 } )$ , for $h _ { 1 } , h _ { 2 } = 0 , \pm 1 , \pm 2 , . . .$ Show that, for a stationary process, the variogram and autocovariance functions can be related through

$$
V _ {x} (\boldsymbol {h}) = \gamma (\boldsymbol {0}) - \gamma (\boldsymbol {h}),
$$

where $\gamma ( h )$ is the usual $\log h$ $^ { h }$ covariance function and $\mathbf { 0 } = ( 0 , 0 )$ . Note the easy extension to any spatial dimension.

The following problems require the material given in Appendix A

1.28 Suppose $x _ { t } = \beta _ { 0 } + \beta _ { 1 } t$ , where $\beta _ { 0 }$ and $\beta _ { 1 }$ are constants. Prove as $n \to \infty$ , $\widehat { \rho } _ { x } ( h ) \to 1$ for fixed $h$ , where ${ \widehat { \rho } } _ { x } ( h )$ is the ACF (1.35).   
1.29 (a) Suppose $x _ { t }$ is a weakly stationary time series with mean zero and with absolutely summable autocovariance function, $\gamma ( h )$ , such that

$$
\sum_ {h = - \infty} ^ {\infty} \gamma (h) = 0.
$$

Prove that $\sqrt { n } \bar { x } \overset { P } {  } 0$ , where $x$ is the sample mean (1.32).

(b) Give an example of a process that satisfies the conditions of part (a). What is special about this process?

1.30 Let $x _ { t }$ be a linear process of the form (A.43)–(A.44). If we define

$$
\tilde {\gamma} (h) = n ^ {- 1} \sum_ {t = 1} ^ {n} (x _ {t + h} - \mu_ {x}) (x _ {t} - \mu_ {x}),
$$

show that

$$
n ^ {1 / 2} \big (\tilde {\gamma} (h) - \widehat {\gamma} (h) \big) = o _ {p} (1).
$$

Hint: The Markov Inequality

$$
P \{| x | \geq \epsilon \} <   \frac {E | x |}{\epsilon}
$$

can be helpful for the cross-product terms.

1.31 For a linear process of the form

$$
x _ {t} = \sum_ {j = 0} ^ {\infty} \phi^ {j} w _ {t - j},
$$

where $\{ w _ { t } \}$ satisfies the conditions of Theorem A.7 and $| \phi | < 1$ , show that

$$
\sqrt {n} \frac {\left(\widehat {\rho} _ {x} (1) - \rho_ {x} (1)\right)}{\sqrt {1 - \rho_ {x} ^ {2} (1)}} \stackrel {{d}} {{\to}} N (0, 1),
$$

and construct a $9 5 \%$ confidence interval for $\phi$ when $\widehat { \rho } _ { x } ( 1 ) = . 6 4$ and $n = 1 0 0$ .

1.32 Let $\{ x _ { t } ; ~ t = 0 , \pm 1 , \pm 2 , \ldots \}$ be iid(0, σ2).

(a) For $h \geq 1$ and $k \geq 1$ , show that $x _ { t } x _ { t + h }$ and $x _ { s } x _ { s + k }$ are uncorrelated for all $s \neq t$ .

(b) For fixed $h \geq 1$ , show that the $h \times 1$ vector

$$
\sigma^ {- 2} n ^ {- 1 / 2} \sum_ {t = 1} ^ {n} (x _ {t} x _ {t + 1}, \dots , x _ {t} x _ {t + h}) ^ {\prime} \xrightarrow {d} (z _ {1}, \dots , z _ {h}) ^ {\prime}
$$

where $z _ { 1 } , \dots , z _ { h }$ are iid $\mathrm { { N } } ( 0 , 1 )$ random variables. [Note: the sequence $\{ x _ { t } x _ { t + h } ; \ t = 1 , 2 , . . . \}$ is $h$ -dependent and white noise $( 0 , \sigma ^ { 4 } )$ . Also, recall the Cram´er-Wold device.]

(c) Show, for each $h \geq 1$ ,

$$
n ^ {- 1 / 2} \left[ \sum_ {t = 1} ^ {n} x _ {t} x _ {t + h} - \sum_ {t = 1} ^ {n - h} (x _ {t} - \bar {x}) (x _ {t + h} - \bar {x}) \right] \stackrel {{p}} {{\to}} 0 \quad \text {a s} n \to \infty
$$

where ¯x = n−1 Pn ${ \bar { x } } = n ^ { - 1 } \sum _ { t = 1 } ^ { n } x _ { t }$ t=1 xt.

(d) Noting that $\scriptstyle n ^ { - 1 } \sum _ { t = 1 } ^ { n } x _ { t } ^ { 2 } \stackrel { p } { \to } \sigma ^ { 2 }$ , conclude that

$$
n ^ {1 / 2} [ \widehat {\rho} (1), \dots , \widehat {\rho} (h) ] ^ {\prime} \xrightarrow {d} (z _ {1}, \dots , z _ {h}) ^ {\prime}
$$

where $\widehat { \rho } ( h )$ is the sample ACF of the data $x _ { 1 } , \ldots , x _ { n }$

# Time Series Regression and Exploratory Data Analysis

# 2.1 Introduction

The linear model and its applications are at least as dominant in the time series context as in classical statistics. Regression models are important for time domain models discussed in Chapters 3, 5, and 6, and in the frequency domain models considered in Chapters 4 and 7. The primary ideas depend on being able to express a response series, say $x _ { t }$ , as a linear combination of inputs, say $z _ { t 1 } , z _ { t 2 } , . . . , z _ { t q }$ . Estimating the coefficients $\beta _ { 1 } , \beta _ { 2 } , \ldots , \beta _ { q }$ in the linear combinations by least squares provides a method for modeling $x _ { t }$ in terms of the inputs.

In the time domain applications of Chapter 3, for example, we will express $x _ { t }$ as a linear combination of previous values $x _ { t - 1 } , x _ { t - 2 } , . . . , x _ { t - p }$ , of the currently observed series. The outputs $x _ { t }$ may also depend on lagged values of another series, say $y _ { t - 1 } , y _ { t - 2 } , \ldots , y _ { t - q }$ , that have influence. It is easy to see that forecasting becomes an option when prediction models can be formulated in this form. Time series smoothing and filtering can be expressed in terms of local regression models. Polynomials and regression splines also provide important techniques for smoothing.

If one admits sines and cosines as inputs, the frequency domain ideas that lead to the periodogram and spectrum of Chapter 4 follow from a regression model. Extensions to filters of infinite extent can be handled using regression in the frequency domain. In particular, many regression problems in the frequency domain can be carried out as a function of the periodic components of the input and output series, providing useful scientific intuition into fields like acoustics, oceanographics, engineering, biomedicine, and geophysics.

The above considerations motivate us to include a separate chapter on regression and some of its applications that is written on an elementary level and is formulated in terms of time series. The assumption of linearity, stationarity, and homogeneity of variances over time is critical in the regression

context, and therefore we include some material on transformations and other techniques useful in exploratory data analysis.

# 2.2 Classical Regression in the Time Series Context

We begin our discussion of linear regression in the time series context by assuming some output or dependent time series, say, $x _ { t }$ , for $t = 1 , \ldots , n$ , is being influenced by a collection of possible inputs or independent series, say, $z _ { t 1 } , z _ { t 2 } , . . . , z _ { t q }$ , where we first regard the inputs as fixed and known. This assumption, necessary for applying conventional linear regression, will be relaxed later on. We express this relation through the linear regression model

$$
x _ {t} = \beta_ {1} z _ {t 1} + \beta_ {2} z _ {t 2} + \dots + \beta_ {q} z _ {t q} + w _ {t}, \tag {2.1}
$$

where $\beta _ { 1 } , \beta _ { 2 } , \ldots , \beta _ { q }$ are unknown fixed regression coefficients, and $\{ w _ { t } \}$ is a random error or noise process consisting of independent and identically distributed (iid) normal variables with mean zero and variance $\sigma _ { w } ^ { 2 }$ ; we will relax the iid assumption later. A more general setting within which to embed mean square estimation and linear regression is given in Appendix B, where we introduce Hilbert spaces and the Projection Theorem.

# Example 2.1 Estimating a Linear Trend

Consider the global temperature data, say $x _ { t }$ , shown in Figures 1.2 and 2.1. As discussed in Example 1.2, there is an apparent upward trend in the series that has been used to argue the global warming hypothesis. We might use simple linear regression to estimate that trend by fitting the model

$$
x _ {t} = \beta_ {1} + \beta_ {2} t + w _ {t}, \quad t = 1 8 8 0, 1 8 5 7, \dots , 2 0 0 9.
$$

This is in the form of the regression model (2.1) when we make the identification $q = 2$ , $z _ { t 1 } = 1$ and $z _ { t 2 } = t$ . Note that we are making the assumption that the errors, $w _ { t }$ , are an iid normal sequence, which may not be true. We will address this problem further in 2.3; the problem of autocorrelated errors is discussed in detail in 5.5. Also note that we could have used, for example, $t = 1 , \ldots , 1 3 0$ , without affecting the interpretation of the slope coefficient, $\beta _ { 2 }$ ; only the intercept, $\beta _ { 1 }$ , would be affected.

Using simple linear regression, we obtained the estimated coefficients $\widehat { \beta } _ { 1 } =$ $- 1 1 . 2$ , and $\widehat { \beta } _ { 2 } = . 0 0 6$ (with a standard error of .0003) yielding a highly significant estimated increase of .6 degrees centigrade per 100 years. We discuss the precise way in which the solution was accomplished after the example. Finally, Figure 2.1 shows the global temperature data, say $x _ { t }$ , with the estimated trend, say $\widehat { x } _ { t } = - 1 1 . 2 + . 0 0 6 t$ , superimposed. It is apparent that the estimated trend line obtained via simple linear regression does not quite capture the trend of the data and better models will be needed.

To perform this analysis in R, use the following commands:

![](images/bce2fbb5a9ba97dc420d2ce12d066dac68367e181c70227657342f8389632329.jpg)  
Fig. 2.1. Global temperature deviations shown in Figure 1.2 with fitted linear trend line.

1 summary(fit <- lm(gtemp~time(gtemp))) # regress gtemp on time   
2 plot(gtemp, type="o", ylab="Global Temperature Deviation")   
3 abline(fit) # add regression line to the plot

The linear model described by (2.1) above can be conveniently written in a more general notation by defining the column vectors $\boldsymbol { z } _ { t } = ( z _ { t 1 } , z _ { t 2 } , \ldots , z _ { t q } ) ^ { \prime }$ and $\beta = ( \beta _ { 1 } , \beta _ { 2 } , \ldots , \beta _ { q } ) ^ { \prime }$ , where $'$ denotes transpose, so (2.1) can be written in the alternate form

$$
x _ {t} = \beta^ {\prime} z _ {t} + w _ {t}. \tag {2.2}
$$

where $w _ { t } \sim$ iid $\mathrm { N } ( 0 , \sigma _ { w } ^ { 2 } )$ . It is natural to consider estimating the unknown coefficient vector $\beta$ by minimizing the error sum of squares

$$
Q = \sum_ {t = 1} ^ {n} w _ {t} ^ {2} = \sum_ {t = 1} ^ {n} \left(x _ {t} - \beta^ {\prime} z _ {t}\right) ^ {2}, \tag {2.3}
$$

with respect to $\beta _ { 1 } , \beta _ { 2 } , \ldots , \beta _ { q }$ . Minimizing $Q$ yields the ordinary least squares estimator of $\beta$ . This minimization can be accomplished by differentiating (2.3) with respect to the vector $\beta$ or by using the properties of projections. In the notation above, this procedure gives the normal equations

$$
\left(\sum_ {t = 1} ^ {n} z _ {t} z _ {t} ^ {\prime}\right) \widehat {\beta} = \sum_ {t = 1} ^ {n} z _ {t} x _ {t}. \tag {2.4}
$$

The notation can be simplified by defining $Z ~ = ~ [ z _ { 1 } \mid z _ { 2 } \mid \cdot \cdot \cdot \mid z _ { n } ] ^ { \prime }$ as the $n \times q$ matrix composed of the $n$ samples of the input variables, the observed $n \times 1$ vector $\pmb { x } = ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } ) ^ { \prime }$ and the $n \times 1$ vector of errors

$\pmb { w } = ( w _ { 1 } , w _ { 2 } , \ldots , w _ { n } ) ^ { \prime } .$ . In this case, model (2.2) may be written as

$$
\boldsymbol {x} = Z \boldsymbol {\beta} + \boldsymbol {w}. \tag {2.5}
$$

The normal equations, (2.4), can now be written as

$$
\left(Z ^ {\prime} Z\right) \widehat {\boldsymbol {\beta}} = Z ^ {\prime} \boldsymbol {x} \tag {2.6}
$$

and the solution

$$
\widehat {\boldsymbol {\beta}} = \left(Z ^ {\prime} Z\right) ^ {- 1} Z ^ {\prime} \boldsymbol {x} \tag {2.7}
$$

when the matrix $Z ^ { \prime } Z$ is nonsingular. The minimized error sum of squares (2.3), denoted $S S E$ , can be written as

$$
\begin{array}{l} S S E = \sum_ {t = 1} ^ {n} \left(x _ {t} - \widehat {\beta} ^ {\prime} z _ {t}\right) ^ {2} \\ = \left(\boldsymbol {x} - Z \widehat {\boldsymbol {\beta}}\right) ^ {\prime} \left(\boldsymbol {x} - Z \widehat {\boldsymbol {\beta}}\right) \tag {2.8} \\ = \boldsymbol {x} ^ {\prime} \boldsymbol {x} - \hat {\beta} ^ {\prime} Z ^ {\prime} \boldsymbol {x} \\ = \boldsymbol {x} ^ {\prime} \boldsymbol {x} - \boldsymbol {x} ^ {\prime} Z (Z ^ {\prime} Z) ^ {- 1} Z ^ {\prime} \boldsymbol {x}, \\ \end{array}
$$

to give some useful versions for later reference. The ordinary least squares estimators are unbiased, i.e., $E ( { \widehat { \boldsymbol { \beta } } } ) = \beta$ , and have the smallest variance within the class of linear unbiased estimators.

If the errors $w _ { t }$ are normally distributed, $\widehat { \beta }$ is also the maximum likelihood estimator for $\beta$ and is normally distributed with

$$
\operatorname {c o v} (\widehat {\boldsymbol {\beta}}) = \sigma_ {w} ^ {2} \left(\sum_ {t = 1} ^ {n} \boldsymbol {z} _ {t} \boldsymbol {z} _ {t} ^ {\prime}\right) ^ {- 1} = \sigma_ {w} ^ {2} \left(Z ^ {\prime} Z\right) ^ {- 1} = \sigma_ {w} ^ {2} C, \tag {2.9}
$$

where

$$
C = \left(Z ^ {\prime} Z\right) ^ {- 1} \tag {2.10}
$$

is a convenient notation for later equations. An unbiased estimator for the variance $\sigma _ { w } ^ { 2 }$ is

$$
s _ {w} ^ {2} = M S E = \frac {S S E}{n - q}, \tag {2.11}
$$

where $M S E$ denotes the mean squared error, which is contrasted with the maximum likelihood estimator $\widehat { \sigma } _ { w } ^ { 2 } = S S E / n$ . Under the normal assumption, $s _ { w } ^ { 2 }$ b is distributed proportionally to a chi-squared random variable with $n - q$ degrees of freedom, denoted by $\chi _ { n - q } ^ { 2 }$ , and independently of $\widehat { \beta }$ . It follows that

$$
t _ {n - q} = \frac {\left(\widehat {\beta} _ {i} - \beta_ {i}\right)}{s _ {w} \sqrt {c _ {i i}}} \tag {2.12}
$$

has the t-distribution with $n - q$ degrees of freedom; $c _ { i i }$ denotes the $i$ -th diagonal element of $C$ , as defined in (2.10).

Table 2.1. Analysis of Variance for Regression   

<table><tr><td>Source</td><td>df</td><td>Sum of Squares</td><td>Mean Square</td></tr><tr><td>zt,r+1, ...,zt,q</td><td>q-r</td><td>SSR = SSEr - SSE</td><td>MSR = SSR/(q-r)</td></tr><tr><td>Error</td><td>n-q</td><td>SSE</td><td>MSE = SSE/(n-q)</td></tr><tr><td>Total</td><td>n-r</td><td>SSEr</td><td></td></tr></table>

Various competing models are of interest to isolate or select the best subset of independent variables. Suppose a proposed model specifies that only a subset $r < q$ independent variables, say, $\pmb { z } _ { t : r } = ( z _ { t 1 } , z _ { t 2 } , \ldots , z _ { t r } ) ^ { \prime }$ is influencing the dependent variable $x _ { t }$ . The reduced model is

$$
\boldsymbol {x} = Z _ {r} \boldsymbol {\beta} _ {r} + \boldsymbol {w} \tag {2.13}
$$

where $\beta _ { r } = ( \beta _ { 1 } , \beta _ { 2 } , \ldots , \beta _ { r } ) ^ { \prime }$ is a subset of coefficients of the original $q$ variables and $Z _ { r } = [ z _ { 1 : r } \ : | \ : \cdots \ : | \ : z _ { n : r } ] ^ { \prime }$ is the $n \times r$ matrix of inputs. The null hypothesis in this case is $\mathrm { H } _ { \mathrm { 0 } }$ : $\beta _ { r + 1 } = \cdot \cdot \cdot = \beta _ { q } = 0$ . We can test the reduced model (2.13) against the full model (2.2) by comparing the error sums of squares under the two models using the $F ^ { \dagger }$ -statistic

$$
F _ {q - r, n - q} = \frac {\left(S S E _ {r} - S S E\right) / (q - r)}{S S E / (n - q)}, \tag {2.14}
$$

which has the central $F ^ { \dagger }$ -distribution with $q - r$ and $n - q$ degrees of freedom when (2.13) is the correct model. Note that $S S E _ { r }$ is the error sum of squares under the reduced model (2.13) and it can be computed by replacing $Z$ with $Z _ { r }$ in (2.8). The statistic, which follows from applying the likelihood ratio criterion, has the improvement per number of parameters added in the numerator compared with the error sum of squares under the full model in the denominator. The information involved in the test procedure is often summarized in an Analysis of Variance (ANOVA) table as given in Table 2.1 for this particular case. The difference in the numerator is often called the regression sum of squares

In terms of Table 2.1, it is conventional to write the $F$ -statistic (2.14) as the ratio of the two mean squares, obtaining

$$
F _ {q - r, n - q} = \frac {M S R}{M S E}, \tag {2.15}
$$

where MSR, the mean squared regression, is the numerator of (2.14). A special case of interest is $r = 1$ and $z _ { t 1 } \equiv 1$ , when the model in (2.13) becomes

$$
x _ {t} = \beta_ {1} + w _ {t},
$$

and we may measure the proportion of variation accounted for by the other variables using

$$
R ^ {2} = \frac {S S E _ {1} - S S E}{S S E _ {1}}, \tag {2.16}
$$

where the residual sum of squares under the reduced model

$$
S S E _ {1} = \sum_ {t = 1} ^ {n} \left(x _ {t} - \bar {x}\right) ^ {2}, \tag {2.17}
$$

in this case is just the sum of squared deviations from the mean $x$ . The measure $R ^ { 2 }$ is also the squared multiple correlation between $x _ { t }$ and the variables $z _ { t 2 } , z _ { t 3 } , . . . , z _ { t q }$ .

The techniques discussed in the previous paragraph can be used to test various models against one another using the $F ^ { \dagger }$ test given in (2.14), (2.15), and the ANOVA table. These tests have been used in the past in a stepwise manner, where variables are added or deleted when the values from the $F$ - test either exceed or fail to exceed some predetermined levels. The procedure, called stepwise multiple regression, is useful in arriving at a set of useful variables. An alternative is to focus on a procedure for model selection that does not proceed sequentially, but simply evaluates each model on its own merits. Suppose we consider a normal regression model with $k$ coefficients and denote the maximum likelihood estimator for the variance as

$$
\widehat {\sigma} _ {k} ^ {2} = \frac {S S E _ {k}}{n}, \tag {2.18}
$$

where $S S E _ { k }$ denotes the residual sum of squares under the model with $k$ regression coefficients. Then, Akaike (1969, 1973, 1974) suggested measuring the goodness of fit for this particular model by balancing the error of the fit against the number of parameters in the model; we define the following.1

# Definition 2.1 Akaike’s Information Criterion (AIC)

$$
\mathrm {A I C} = \log \hat {\sigma} _ {k} ^ {2} + \frac {n + 2 k}{n}, \tag {2.19}
$$

where $\widehat { \sigma } _ { k } ^ { 2 }$ is given by (2.18) and $k$ is the number of parameters in the model.

The value of $k$ yielding the minimum AIC specifies the best model. The idea is roughly that minimizing $\widehat { \sigma } _ { k } ^ { 2 }$ would be a reasonable objective, except that it decreases monotonically as $k$ increases. Therefore, we ought to penalize the error variance by a term proportional to the number of parameters. The choice for the penalty term given by (2.19) is not the only one, and a considerable literature is available advocating different penalty terms. A corrected

form, suggested by Sugiura (1978), and expanded by Hurvich and Tsai (1989), can be based on small-sample distributional results for the linear regression model (details are provided in Problems 2.4 and 2.5). The corrected form is defined as follows.

Definition 2.2 AIC, Bias Corrected (AICc)

$$
\mathrm {A I C c} = \log \hat {\sigma} _ {k} ^ {2} + \frac {n + k}{n - k - 2}, \tag {2.20}
$$

where $\widehat { \sigma } _ { k } ^ { 2 }$ is given by (2.18), k is the number of parameters in the model, and $n$ is the sample size.

We may also derive a correction term based on Bayesian arguments, as in Schwarz (1978), which leads to the following.

Definition 2.3 Bayesian Information Criterion (BIC)

$$
\mathrm {B I C} = \log \hat {\sigma} _ {k} ^ {2} + \frac {k \log n}{n}, \tag {2.21}
$$

using the same notation as in Definition 2.2.

BIC is also called the Schwarz Information Criterion (SIC); see also Rissanen (1978) for an approach yielding the same statistic based on a minimum description length argument. Various simulation studies have tended to verify that BIC does well at getting the correct order in large samples, whereas AICc tends to be superior in smaller samples where the relative number of parameters is large; see McQuarrie and Tsai (1998) for detailed comparisons. In fitting regression models, two measures that have been used in the past are adjusted R-squared, which is essentially $s _ { w } ^ { 2 }$ , and Mallows $C _ { p }$ , Mallows (1973), which we do not consider in this context.

Example 2.2 Pollution, Temperature and Mortality

The data shown in Figure 2.2 are extracted series from a study by Shumway et al. (1988) of the possible effects of temperature and pollution on weekly mortality in Los Angeles County. Note the strong seasonal components in all of the series, corresponding to winter-summer variations and the downward trend in the cardiovascular mortality over the 10-year period.

A scatterplot matrix, shown in Figure 2.3, indicates a possible linear relation between mortality and the pollutant particulates and a possible relation to temperature. Note the curvilinear shape of the temperature mortality curve, indicating that higher temperatures as well as lower temperatures are associated with increases in cardiovascular mortality.

Based on the scatterplot matrix, we entertain, tentatively, four models where $M _ { t }$ denotes cardiovascular mortality, $T _ { t }$ denotes temperature and $P _ { t }$ denotes the particulate levels. They are

![](images/889b3a9c2d3c238db6427c2a47bb4dd40cd158884c2c790601c6c844decfc840.jpg)

![](images/b3ef88061d6f2f5bc51454d14b582c56fa9308ea5d05e09781c475f0a5ad2d66.jpg)

![](images/8e1dd01984f28d15b4cadb371bfb22eb17fbd675abb01973bd21d9185d32bf15.jpg)  
Fig. 2.2. Average weekly cardiovascular mortality (top), temperature (middle) and particulate pollution (bottom) in Los Angeles County. There are 508 six-day smoothed averages obtained by filtering daily values over the 10 year period 1970- 1979.

$$
M _ {t} = \beta_ {1} + \beta_ {2} t + w _ {t} \tag {2.22}
$$

$$
M _ {t} = \beta_ {1} + \beta_ {2} t + \beta_ {3} (T _ {t} - T.) + w _ {t} \tag {2.23}
$$

$$
M _ {t} = \beta_ {1} + \beta_ {2} t + \beta_ {3} (T _ {t} - T.) + \beta_ {4} (T _ {t} - T.) ^ {2} + w _ {t} \tag {2.24}
$$

$$
M _ {t} = \beta_ {1} + \beta_ {2} t + \beta_ {3} (T _ {t} - T.) + \beta_ {4} (T _ {t} - T.) ^ {2} + \beta_ {5} P _ {t} + w _ {t} \tag {2.25}
$$

where we adjust temperature for its mean, $T . = 7 4 . 6$ , to avoid scaling problems. It is clear that (2.22) is a trend only model, (2.23) is linear temperature, (2.24) is curvilinear temperature and (2.25) is curvilinear temperature and pollution. We summarize some of the statistics given for this particular case in Table 2.2. The values of $R ^ { 2 }$ were computed by noting that $S S E _ { 1 } = 5 0 , 6 8 7$ using (2.17).

We note that each model does substantially better than the one before it and that the model including temperature, temperature squared, and particulates does the best, accounting for some $6 0 \%$ of the variability and with the best value for AIC and BIC (because of the large sample size, AIC

![](images/1d4bb611d6005adbb3a01361a9bd7eb3ee144dae3e6cf91e1debdd6937b42974.jpg)  
Fig. 2.3. Scatterplot matrix showing plausible relations between mortality, temperature, and pollution.

Table 2.2. Summary Statistics for Mortality Models   

<table><tr><td>Model</td><td>k</td><td>SSE</td><td>df</td><td>MSE</td><td>R²</td><td>AIC</td><td>BIC</td></tr><tr><td>(2.22)</td><td>2</td><td>40,020</td><td>506</td><td>79.0</td><td>.21</td><td>5.38</td><td>5.40</td></tr><tr><td>(2.23)</td><td>3</td><td>31,413</td><td>505</td><td>62.2</td><td>.38</td><td>5.14</td><td>5.17</td></tr><tr><td>(2.24)</td><td>4</td><td>27,985</td><td>504</td><td>55.5</td><td>.45</td><td>5.03</td><td>5.07</td></tr><tr><td>(2.25)</td><td>5</td><td>20,508</td><td>503</td><td>40.8</td><td>.60</td><td>4.72</td><td>4.77</td></tr></table>

and AICc are nearly the same). Note that one can compare any two models using the residual sums of squares and (2.14). Hence, a model with only trend could be compared to the full model using $q = 5 , r = 2 , n = 5 0 8$ , so

$$
F _ {3, 5 0 3} = \frac {(4 0 , 0 2 0 - 2 0 , 5 0 8) / 3}{2 0 , 5 0 8 / 5 0 3} = 1 6 0,
$$

which exceeds $F _ { 3 , 5 0 3 } ( . 0 0 1 ) = 5 . 5 1$ . We obtain the best prediction model,

$$
\begin{array}{l} \widehat {M} _ {t} = 8 1. 5 9 -. 0 2 7 _ {(. 0 0 2)} t -. 4 7 3 _ {(. 0 3 2)} \left(T _ {t} - 7 4. 6\right) \\ + . 0 2 3 _ {(. 0 0 3)} \left(T _ {t} - 7 4. 6\right) ^ {2} +. 2 5 5 _ {(. 0 1 9)} P _ {t}, \\ \end{array}
$$

for mortality, where the standard errors, computed from (2.9)-(2.11), are given in parentheses. As expected, a negative trend is present in time as well as a negative coefficient for adjusted temperature. The quadratic effect of temperature can clearly be seen in the scatterplots of Figure 2.3. Pollution weights positively and can be interpreted as the incremental contribution to daily deaths per unit of particulate pollution. It would still be essential to check the residuals $\widehat { w } _ { t } = M _ { t } - \widehat { M } _ { t }$ for autocorrelation (of which there is a substantial amount), but we defer this question to to 5.6 when we discuss regression with correlated errors.

Below is the R code to plot the series, display the scatterplot matrix, fit the final regression model (2.25), and compute the corresponding values of AIC, AICc and BIC.2 Finally, the use of na.action in lm() is to retain the time series attributes for the residuals and fitted values.

```txt
1 par(mfrow=c(3,1))  
2 plot(cmort, main="Cardiovascular Mortality", xlab="", ylab="")  
3 plot(tempr, main="Temperature", xlab="", ylab="")  
4 plot(part, main="Particulates", xlab="", ylab="")  
5 dev.new() # open a new graphic device for the scatterplot matrix  
6 pairs(cbind(Mortality=cmort, Temperature=tempr, Particulates=part))  
7 temp = tempr-mean(tempr) # center temperature  
8 temp2 = temp^2  
9 trend = time(cmort) # time  
10 fit = lm(cmort~trend + temp + temp2 + part, na.action=NULL)  
11 summary(fit) # regression results  
12 summary(aov(fit)) # ANOVA table (compare to next line)  
13 summary(aov(lm(cmort~cbind(trend, temp, temp2, part)))) # Table 2.1  
14 num = length(cmort) # sample size  
15 AIC(fit)/num - log(2*pi) # AIC  
16 AIC(fit, k=log(num))/num - log(2*pi) # BIC  
17 (AICc = log(resid(fit)^2)/num) + (num+5)/(num-5-2)) # AICc 
```

As previously mentioned, it is possible to include lagged variables in time series regression models and we will continue to discuss this type of problem throughout the text. This concept is explored further in Problems 2.2 and 2.11. The following is a simple example of lagged regression.

# Example 2.3 Regression With Lagged Variables

In Example 1.25, we discovered that the Southern Oscillation Index (SOI) measured at time $t - 6$ months is associated with the Recruitment series at time $t$ , indicating that the SOI leads the Recruitment series by six months. Although there is evidence that the relationship is not linear (this is discussed further in Example 2.7), we may consider the following regression,

$$
R _ {t} = \beta_ {1} + \beta_ {2} S _ {t - 6} + w _ {t}, \tag {2.26}
$$

where $R _ { t }$ denotes Recruitment for month $t$ and $S _ { t - 6 }$ denotes SOI six months prior. Assuming the $w _ { t }$ sequence is white, the fitted model is

$$
\widehat {R} _ {t} = 6 5. 7 9 - 4 4. 2 8 _ {(2. 7 8)} S _ {t - 6} \tag {2.27}
$$

with $\widehat { \sigma } _ { w } = 2 2 . 5$ on 445 degrees of freedom. This result indicates the strong bpredictive ability of SOI for Recruitment six months in advance. Of course, it is still essential to check the the model assumptions, but again we defer this until later.

Performing lagged regression in R is a little difficult because the series must be aligned prior to running the regression. The easiest way to do this is to create a data frame that we call fish using ts.intersect, which aligns the lagged series.

1 fish $=$ ts.intersect(rec, soiL6=lag(soi,-6), dframe=TRUE)   
2 summary(lm(rec~soiL6, data=fish, na.action=NULL))

# 2.3 Exploratory Data Analysis

In general, it is necessary for time series data to be stationary, so averaging lagged products over time, as in the previous section, will be a sensible thing to do. With time series data, it is the dependence between the values of the series that is important to measure; we must, at least, be able to estimate autocorrelations with precision. It would be difficult to measure that dependence if the dependence structure is not regular or is changing at every time point. Hence, to achieve any meaningful statistical analysis of time series data, it will be crucial that, if nothing else, the mean and the autocovariance functions satisfy the conditions of stationarity (for at least some reasonable stretch of time) stated in Definition 1.7. Often, this is not the case, and we will mention some methods in this section for playing down the effects of nonstationarity so the stationary properties of the series may be studied.

A number of our examples came from clearly nonstationary series. The Johnson & Johnson series in Figure 1.1 has a mean that increases exponentially over time, and the increase in the magnitude of the fluctuations around this trend causes changes in the covariance function; the variance of the process, for example, clearly increases as one progresses over the length of the series. Also, the global temperature series shown in Figure 1.2 contains some

evidence of a trend over time; human-induced global warming advocates seize on this as empirical evidence to advance their hypothesis that temperatures are increasing.

Perhaps the easiest form of nonstationarity to work with is the trend stationary model wherein the process has stationary behavior around a trend. We may write this type of model as

$$
x _ {t} = \mu_ {t} + y _ {t} \tag {2.28}
$$

where $x _ { t }$ are the observations, $\mu _ { t }$ denotes the trend, and $y _ { t }$ is a stationary process. Quite often, strong trend, $\mu _ { t }$ , will obscure the behavior of the stationary process, $y _ { t }$ , as we shall see in numerous examples. Hence, there is some advantage to removing the trend as a first step in an exploratory analysis of such time series. The steps involved are to obtain a reasonable estimate of the trend component, say $\widehat { \mu } _ { t }$ , and then work with the residuals

$$
\widehat {y} _ {t} = x _ {t} - \widehat {\mu} _ {t}. \tag {2.29}
$$

Consider the following example.

# Example 2.4 Detrending Global Temperature

Here we suppose the model is of the form of (2.28),

$$
x _ {t} = \mu_ {t} + y _ {t},
$$

where, as we suggested in the analysis of the global temperature data presented in Example 2.1, a straight line might be a reasonable model for the trend, i.e.,

$$
\mu_ {t} = \beta_ {1} + \beta_ {2} t.
$$

In that example, we estimated the trend using ordinary least squares3 and found

$$
\widehat {\mu} _ {t} = - 1 1. 2 +. 0 0 6 t.
$$

Figure 2.1 shows the data with the estimated trend line superimposed. To obtain the detrended series we simply subtract $\widehat { \mu } _ { t }$ from the observations, $x _ { t }$ , to obtain the detrended series

$$
\widehat {y} _ {t} = x _ {t} + 1 1. 2 -. 0 0 6 t.
$$

The top graph of Figure 2.4 shows the detrended series. Figure 2.5 shows the ACF of the original data (top panel) as well as the ACF of the detrended data (middle panel).

![](images/90a3c2797bf1a8b5d9fa1dba0cada9f505a0df45fbf4011bd999865e009b2980.jpg)

![](images/06d573a80426244c8c0d3e955b0779fd1d9d8f81409070a682b5340073869478.jpg)  
Fig. 2.4. Detrended (top) and differenced (bottom) global temperature series. The original data are shown in Figures 1.2 and 2.1.

To detrend in the series in R, use the following commands. We also show how to difference and plot the differenced data; we discuss differencing after this example. In addition, we show how to generate the sample ACFs displayed in Figure 2.5.

1 fit = lm(gtemp~time(gtemp), na.action=NULL) # regress gtemp on time   
2 par(mfrow=c(2,1))  
3 plot(resid(fit), type="o", main="detrended")   
4 plot(diff(gtemp), type="o", main="first difference")   
5 par(mfrow=c(3,1)) # plot ACFs   
6 acf(gtemp, 48, main="gtemp")   
7 acf(resid(fit), 48, main="detrended")   
8 acf(diff(gtemp), 48, main $\cdot ^ { = }$ "first difference")

In Example 1.11 and the corresponding Figure 1.10 we saw that a random walk might also be a good model for trend. That is, rather than modeling trend as fixed (as in Example 2.4), we might model trend as a stochastic component using the random walk with drift model,

$$
\mu_ {t} = \delta + \mu_ {t - 1} + w _ {t}, \tag {2.30}
$$

![](images/51d5ff0fc2433e398fe0f78909e30a2c1922b7fd07e30bff84ca9d73ecc1c7c5.jpg)

![](images/41af380ea217642415d7ca14dfd18502c78db51f55fd744ba8f2a836a113d306.jpg)

![](images/050a40c1d2028cfff25041eb19a888b93eff5b180c14c67689e302002984db47.jpg)  
Fig. 2.5. Sample ACFs of the global temperature (top), and of the detrended (middle) and the differenced (bottom) series.

where $w _ { t }$ is white noise and is independent of $y _ { t }$ . If the appropriate model is (2.28), then differencing the data, $x _ { t }$ , yields a stationary process; that is,

$$
\begin{array}{l} x _ {t} - x _ {t - 1} = \left(\mu_ {t} + y _ {t}\right) - \left(\mu_ {t - 1} + y _ {t - 1}\right) \tag {2.31} \\ = \delta + w _ {t} + y _ {t} - y _ {t - 1}. \\ \end{array}
$$

It is easy to show $z _ { t } = y _ { t } - y _ { t - 1 }$ is stationary using footnote 3 of Chapter 1 on page 20. That is, because $y _ { t }$ is stationary,

$$
\begin{array}{l} \gamma_ {z} (h) = \operatorname {c o v} \left(z _ {t + h}, z _ {t}\right) = \operatorname {c o v} \left(y _ {t + h} - y _ {t + h - 1}, y _ {t} - y _ {t - 1}\right) \\ = 2 \gamma_ {y} (h) - \gamma_ {y} (h + 1) - \gamma_ {y} (h - 1) \\ \end{array}
$$

is independent of time; we leave it as an exercise (Problem 2.7) to show that $x _ { t } - x _ { t - 1 }$ in (2.31) is stationary.

One advantage of differencing over detrending to remove trend is that no parameters are estimated in the differencing operation. One disadvantage, however, is that differencing does not yield an estimate of the stationary process $y _ { t }$ as can be seen in (2.31). If an estimate of $y _ { t }$ is essential, then detrending may be more appropriate. If the goal is to coerce the data to stationarity, then differencing may be more appropriate. Differencing is also a viable tool if the trend is fixed, as in Example 2.4. That is, e.g., if $\mu _ { t } =$ $\beta _ { 1 } + \beta _ { 2 } t$ in the model (2.28), differencing the data produces stationarity (see Problem 2.6):

$$
x _ {t} - x _ {t - 1} = \left(\mu_ {t} + y _ {t}\right) - \left(\mu_ {t - 1} + y _ {t - 1}\right) = \beta_ {2} + y _ {t} - y _ {t - 1}.
$$

Because differencing plays a central role in time series analysis, it receives its own notation. The first difference is denoted as

$$
\nabla x _ {t} = x _ {t} - x _ {t - 1}. \tag {2.32}
$$

As we have seen, the first difference eliminates a linear trend. A second difference, that is, the difference of (2.32), can eliminate a quadratic trend, and so on. In order to define higher differences, we need a variation in notation that we will use often in our discussion of ARIMA models in Chapter 3.

Definition 2.4 We define the backshift operator by

$$
B x _ {t} = x _ {t - 1}
$$

and extend it to powers $B ^ { 2 } x _ { t } = B ( B x _ { t } ) = B x _ { t - 1 } = x _ { t - 2 }$ , and so on. Thus,

$$
B ^ {k} x _ {t} = x _ {t - k}. \tag {2.33}
$$

It is clear that we may then rewrite (2.32) as

$$
\nabla x _ {t} = (1 - B) x _ {t}, \tag {2.34}
$$

and we may extend the notion further. For example, the second difference becomes

$$
\begin{array}{l} \nabla^ {2} x _ {t} = (1 - B) ^ {2} x _ {t} = (1 - 2 B + B ^ {2}) x _ {t} \\ = x _ {t} - 2 x _ {t - 1} + x _ {t - 2} \\ \end{array}
$$

by the linearity of the operator. To check, just take the difference of the first difference $\nabla ( \nabla x _ { t } ) = \nabla ( x _ { t } - x _ { t - 1 } ) = ( x _ { t } - x _ { t - 1 } ) - ( x _ { t - 1 } - x _ { t - 2 } )$ .

Definition 2.5 Differences of order d are defined as

$$
\nabla^ {d} = (1 - B) ^ {d}, \tag {2.35}
$$

where we may expand the operator $( 1 - B ) ^ { d }$ algebraically to evaluate for higher integer values of $d$ . When $d = 1$ , we drop it from the notation.

The first difference (2.32) is an example of a linear filter applied to eliminate a trend. Other filters, formed by averaging values near $x _ { t }$ , can produce adjusted series that eliminate other kinds of unwanted fluctuations, as in Chapter 3. The differencing technique is an important component of the ARIMA model of Box and Jenkins (1970) (see also Box et al., 1994), to be discussed in Chapter 3.

# Example 2.5 Differencing Global Temperature

The first difference of the global temperature series, also shown in Figure 2.4, produces different results than removing trend by detrending via regression. For example, the differenced series does not contain the long middle cycle we observe in the detrended series. The ACF of this series is also shown in Figure 2.5. In this case it appears that the differenced process shows minimal autocorrelation, which may imply the global temperature series is nearly a random walk with drift. It is interesting to note that if the series is a random walk with drift, the mean of the differenced series, which is an estimate of the drift, is about .0066 (but with a large standard error):

1 mean(diff(gtemp)) # = 0.00659 (drift) 2 sd(diff(gtemp))/sqrt(length(diff(gtemp))) # = 0.00966 (SE)

An alternative to differencing is a less-severe operation that still assumes stationarity of the underlying time series. This alternative, called fractional differencing, extends the notion of the difference operator (2.35) to fractional powers $- . 5 < d < . 5$ , which still define stationary processes. Granger and Joyeux (1980) and Hosking (1981) introduced long memory time series, which corresponds to the case when $0 < d < . 5$ . This model is often used for environmental time series arising in hydrology. We will discuss long memory processes in more detail in 5.2.

Often, obvious aberrations are present that can contribute nonstationary as well as nonlinear behavior in observed time series. In such cases, transformations may be useful to equalize the variability over the length of a single series. A particularly useful transformation is

$$
y _ {t} = \log x _ {t}, \tag {2.36}
$$

which tends to suppress larger fluctuations that occur over portions of the series where the underlying values are larger. Other possibilities are power transformations in the Box–Cox family of the form

$$
y _ {t} = \left\{ \begin{array}{l l} \left(x _ {t} ^ {\lambda} - 1\right) / \lambda & \lambda \neq 0, \\ \log x _ {t} & \lambda = 0. \end{array} \right. \tag {2.37}
$$

Methods for choosing the power $\lambda$ are available (see Johnson and Wichern, 1992, 4.7) but we do not pursue them here. Often, transformations are also used to improve the approximation to normality or to improve linearity in predicting the value of one series from another.

![](images/ac0e90dce9057f25e8cca30883c511d8118e38ed4e6305b1c3499757e691aef6.jpg)

![](images/a08eeeec48fd4ef2da22c26221c81060ab48115be9d77b893b7a99638400b042.jpg)  
log(varve)   
Fig. 2.6. Glacial varve thicknesses (top) from Massachusetts for $n = 6 3 4$ years compared with log transformed thicknesses (bottom).

# Example 2.6 Paleoclimatic Glacial Varves

Melting glaciers deposit yearly layers of sand and silt during the spring melting seasons, which can be reconstructed yearly over a period ranging from the time deglaciation began in New England (about 12,600 years ago) to the time it ended (about 6,000 years ago). Such sedimentary deposits, called varves, can be used as proxies for paleoclimatic parameters, such as temperature, because, in a warm year, more sand and silt are deposited from the receding glacier. Figure 2.6 shows the thicknesses of the yearly varves collected from one location in Massachusetts for 634 years, beginning 11,834 years ago. For further information, see Shumway and Verosub (1992). Because the variation in thicknesses increases in proportion to the amount deposited, a logarithmic transformation could remove the nonstationarity observable in the variance as a function of time. Figure 2.6 shows the original and transformed varves, and it is clear that this improvement has occurred. We may also plot the histogram of the original and transformed data, as in Problem 2.8, to argue that the approximation to normality is improved. The ordinary first differences (2.34) are also computed in Problem 2.8, and we note that the first differences have a significant negative correlation at

lag $h = 1$ . Later, in Chapter 5, we will show that perhaps the varve series has long memory and will propose using fractional differencing.

Figure 2.6 was generated in R as follows:

1 par(mfrow=c(2,1))  
2 plot(varve, main="varve", ylab="")   
3 plot(log(varve), main="log(varve)", ylab="" )

Next, we consider another preliminary data processing technique that is used for the purpose of visualizing the relations between series at different lags, namely, scatterplot matrices. In the definition of the ACF, we are essentially interested in relations between $x _ { t }$ and $x _ { t - h }$ ; the autocorrelation function tells us whether a substantial linear relation exists between the series and its own lagged values. The ACF gives a profile of the linear correlation at all possible lags and shows which values of $h$ lead to the best predictability. The restriction of this idea to linear predictability, however, may mask a possible nonlinear relation between current values, $x _ { t }$ , and past values, $x _ { t - h }$ . This idea extends to two series where one may be interested in examining scatterplots of $y _ { t }$ versus $x _ { t - h }$

# Example 2.7 Scatterplot Matrices, SOI and Recruitment

To check for nonlinear relations of this form, it is convenient to display a lagged scatterplot matrix, as in Figure 2.7, that displays values of the SOI, $S _ { t }$ , on the vertical axis plotted against $S _ { t - h }$ on the horizontal axis. The sample autocorrelations are displayed in the upper right-hand corner and superimposed on the scatterplots are locally weighted scatterplot smoothing (lowess) lines that can be used to help discover any nonlinearities. We discuss smoothing in the next section, but for now, think of lowess as a robust method for fitting nonlinear regression.

In Figure 2.7, we notice that the lowess fits are approximately linear, so that the sample autocorrelations are meaningful. Also, we see strong positive linear relations at lags $h = 1 , 2 , 1 1 , 1 2$ , that is, between $S _ { t }$ and $S _ { t - 1 } , S _ { t - 2 } , S _ { t - 1 1 } , S _ { t - 1 2 }$ , and a negative linear relation at lags $h = 6 , 7 .$ These results match up well with peaks noticed in the ACF in Figure 1.14.

Similarly, we might want to look at values of one series, say Recruitment, denoted $R _ { t }$ plotted against another series at various lags, say the SOI, $S _ { t - h }$ , to look for possible nonlinear relations between the two series. Because, for example, we might wish to predict the Recruitment series, $R _ { t }$ , from current or past values of the SOI series, $S _ { t - h }$ , for $h = 0 , 1 , 2 , \ldots$ it would be worthwhile to examine the scatterplot matrix. Figure 2.8 shows the lagged scatterplot of the Recruitment series $R _ { t }$ on the vertical axis plotted against the SOI index $S _ { t - h }$ on the horizontal axis. In addition, the figure exhibits the sample cross-correlations as well as lowess fits.

Figure 2.8 shows a fairly strong nonlinear relationship between Recruitment, $R _ { t }$ , and the SOI series at $S _ { t - 5 } , S _ { t - 6 } , S _ { t - 7 } , S _ { t - 8 }$ , indicating the SOI − − − −series tends to lead the Recruitment series and the coefficients are negative, implying that increases in the SOI lead to decreases in the Recruitment. The

![](images/7c7c6b16dc343a659060a510536672bac90091fc06d51afc475efd2df2e9009c.jpg)

![](images/5fb0a128f0cfbea9f5ff31bb46121a2ba4efaff3393bb968f7f624a550fae89c.jpg)

![](images/5e28468cf54f30ad8781dcf49d998dff8cb96988e4c107d67b7569324a2ed7b3.jpg)

![](images/1db035747cca1ebca7014dfb229bdfe22308dd31ad47b2a4145cdce0e2e33b83.jpg)

![](images/b8b04229393a1a20f57be3d3157815ce7a6308e86f6e9951daf54111468c4889.jpg)

![](images/ce87b4f735ba0795e94a1d4b01b61e8f894332dbb7674628526b77b62bfc5502.jpg)

![](images/e7e57ac031b193c137ade2e32c8a08f93543be26ef419986fdda812442d4d014.jpg)

![](images/6a9ddc26e1164bbbd067810c6d517cd28da19e94f8e6ab4c59632c8cf9c7706d.jpg)

![](images/55669b933b58ccaef0dbc6800c770ccb66398e0d14bec217ed4e485503a5f24e.jpg)

![](images/e49e8db954c71d87a11605d60bf4b9d4bed35c2e82fdb4e8ad9cddb53d2f02e3.jpg)

![](images/45b8abc66d1eb00114d9984e829c8719074e72748d3a7d163171f43ed9cbeed2.jpg)

![](images/dda502b142545694802974fdda5316a623ad0b83a74cc497501eafd489205816.jpg)  
Fig. 2.7. Scatterplot matrix relating current SOI values, $S _ { t }$ , to past SOI values, $S _ { t - h }$ , at lags $h = 1 , 2 , . . . , 1 2$ . The values in the upper right corner are the sample autocorrelations and the lines are a lowess fit.

nonlinearity observed in the scatterplots (with the help of the superimposed lowess fits) indicate that the behavior between Recruitment and the SOI is different for positive values of SOI than for negative values of SOI.

Simple scatterplot matrices for one series can be obtained in R using the lag.plot command. Figures 2.7 and 2.8 may be reproduced using the following scripts provided with the text (see Appendix R for detials):

1 lag.plot1(soi, 12)   
# Fig 2.7   
2 lag.plot2(soi, rec, 8)   
# Fig 2.8

As a final exploratory tool, we discuss assessing periodic behavior in time series data using regression analysis and the periodogram; this material may be thought of as an introduction to spectral analysis, which we discuss in

![](images/5b27206591833c9c2b30c46786094edf575b93e49973572a5f0f8fa2ae2e8d44.jpg)

![](images/bf14db25ede71a380a472e0049f7f7ad4f1de7410040193c7bc752dc42c16144.jpg)

![](images/1c34a875818f52ca157290fb4164f4fbc862c903a28fd26a13bd36be887946c9.jpg)

![](images/67b1d9c48fc8a4e76e3fb52256d4bad3c0b6819d35a56570d622b3d694e7f3f4.jpg)

![](images/6790f6373e52ab099b110be7f0728666ac4f9e9061cba82c7a24d1a5df0af98e.jpg)

![](images/d92c992808739cb506ad64ae2d2e59b9f9496be80ae7a3040a024cbef3476c4e.jpg)

![](images/96e261ade89915afff12a459bd3c997a861ffc34e8a85b0cc5fc68beb8a5301b.jpg)

![](images/a12d000c895ecff54b4f19dcae1116e8b955806b1d49d2e31f399ed0100e2088.jpg)

![](images/a95f540c8d833e17dd46f0ef4b873127dbbd0da8afac1573ed7ed2acf62c196d.jpg)  
Fig. 2.8. Scatterplot matrix of the Recruitment series, $R _ { t }$ , on the vertical axis plotted against the SOI series, $S _ { t - h }$ , on the horizontal axis at lags $h = 0 , 1 , \ldots , 8$ . The values in the upper right corner are the sample cross-correlations and the lines are a lowess fit.

detail in Chapter 4. In Example 1.12, we briefly discussed the problem of identifying cyclic or periodic signals in time series. A number of the time series we have seen so far exhibit periodic behavior. For example, the data from the pollution study example shown in Figure 2.2 exhibit strong yearly cycles. Also, the Johnson & Johnson data shown in Figure 1.1 make one cycle every year (four quarters) on top of an increasing trend and the speech data in Figure 1.2 is highly repetitive. The monthly SOI and Recruitment series in Figure 1.6 show strong yearly cycles, but hidden in the series are clues to the El Ni˜no cycle.

# Example 2.8 Using Regression to Discover a Signal in Noise

In Example 1.12, we generated $n = 5 0 0$ observations from the model

$$
x _ {t} = A \cos (2 \pi \omega t + \phi) + w _ {t}, \tag {2.38}
$$

where $\omega = 1 / 5 0$ , $A = 2$ , $\phi = . 6 \pi$ , and $\sigma _ { w } \ = \ 5$ ; the data are shown on the bottom panel of Figure 1.11 on page 16. At this point we assume the frequency of oscillation $\omega ~ = ~ 1 / 5 0$ is known, but $A$ and $\phi$ are unknown parameters. In this case the parameters appear in (2.38) in a nonlinear way, so we use a trigonometric identity4 and write

$$
A \cos (2 \pi \omega t + \phi) = \beta_ {1} \cos (2 \pi \omega t) + \beta_ {2} \sin (2 \pi \omega t),
$$

where $\beta _ { 1 } = A \cos ( \phi )$ and $\beta _ { 2 } = - A \sin ( \phi )$ . Now the model (2.38) can be written in the usual linear regression form given by (no intercept term is needed here)

$$
x _ {t} = \beta_ {1} \cos (2 \pi t / 5 0) + \beta_ {2} \sin (2 \pi t / 5 0) + w _ {t}. \tag {2.39}
$$

Using linear regression on the generated data, the fitted model is

$$
\widehat {x} _ {t} = -. 7 1 _ {(. 3 0)} \cos (2 \pi t / 5 0) - 2. 5 5 _ {(. 3 0)} \sin (2 \pi t / 5 0) \tag {2.40}
$$

with $\widehat { \sigma } _ { w } ~ = ~ 4 . 6 8$ , where the values in parentheses are the standard erbrors. We note the actual values of the coefficients for this example are $\beta _ { 1 } = 2 \cos ( . 6 \pi ) = - . 6 2$ and $\beta _ { 2 } = - 2 \sin ( . 6 \pi ) = - 1 . 9 0$ . Because the parameter estimates are significant and close to the actual values, it is clear that we are able to detect the signal in the noise using regression, even though the signal appears to be obscured by the noise in the bottom panel of Figure 1.11. Figure 2.9 shows data generated by (2.38) with the fitted line, (2.40), superimposed.

To reproduce the analysis and Figure 2.9 in R, use the following commands:

1 set.seed(1000) # so you can reproduce these results   
2 x = 2*cos(2*pi*1:500/50 + .6*pi) $^ +$ rnorm(500,0,5)   
3 z1 = cos(2*pi*1:500/50); z2 = sin(2*pi*1:500/50)   
4 summary(fit <- lm(x~0+z1+z2)) # zero to exclude the intercept   
5 plot.ts(x, lty $=$ "dashed")   
6 lines(fitted(fit), lwd $^ { = 2 }$ )

# Example 2.9 Using the Periodogram to Discover a Signal in Noise

The analysis in Example 2.8 may seem like cheating because we assumed we knew the value of the frequency parameter $\omega$ . If we do not know $\omega$ , we could try to fit the model (2.38) using nonlinear regression with $\omega$ as a parameter. Another method is to try various values of $\omega$ in a systematic way. Using the

![](images/3d54e82aff081ff0a32978813cf67d15050666e3843666575eeeb2bf7d224767.jpg)  
Fig. 2.9. Data generated by (2.38) [dashed line] with the fitted [solid] line, (2.40), superimposed.

regression results of 2.2, we can show the estimated regression coefficients in Example 2.8 take on the special form given by

$$
\widehat {\beta} _ {1} = \frac {\sum_ {t = 1} ^ {n} x _ {t} \cos (2 \pi t / 5 0)}{\sum_ {t = 1} ^ {n} \cos^ {2} (2 \pi t / 5 0)} = \frac {2}{n} \sum_ {t = 1} ^ {n} x _ {t} \cos (2 \pi t / 5 0); \tag {2.41}
$$

$$
\widehat {\beta} _ {2} = \frac {\sum_ {t = 1} ^ {n} x _ {t} \sin (2 \pi t / 5 0)}{\sum_ {t = 1} ^ {n} \sin^ {2} (2 \pi t / 5 0)} = \frac {2}{n} \sum_ {t = 1} ^ {n} x _ {t} \sin (2 \pi t / 5 0). \tag {2.42}
$$

This suggests looking at all possible regression parameter estimates,5 say

$$
\widehat {\beta} _ {1} (j / n) = \frac {2}{n} \sum_ {t = 1} ^ {n} x _ {t} \cos (2 \pi t j / n); \tag {2.43}
$$

$$
\widehat {\beta} _ {2} (j / n) = \frac {2}{n} \sum_ {t = 1} ^ {n} x _ {t} \sin (2 \pi t j / n), \tag {2.44}
$$

where, $n = 5 0 0$ and $j = 1 , \ldots , \frac { \pi } { 2 } - 1$ , and inspecting the results for large values. For the endpoints, $j = 0$ 2 − and $j = n / 2$ , we have $\begin{array} { r } { \widehat { \beta } _ { 1 } ( 0 ) = n ^ { - 1 } \sum _ { t = 1 } ^ { n } x _ { t } } \end{array}$ and $\begin{array} { r } { \widehat { \beta } _ { 1 } ( \frac { 1 } { 2 } ) = n ^ { - 1 } \sum _ { t = 1 } ^ { n } ( - 1 ) ^ { t } x _ { t } } \end{array}$ , and $\widehat { \beta } _ { 2 } ( 0 ) = \widehat { \beta } _ { 2 } ( \textstyle { \frac { 1 } { 2 } } ) = 0$ .

2 2For this particular example, the values calculated in (2.41) and (2.42) are $\widehat { \beta } _ { 1 } ( 1 0 / 5 0 0 )$ and $\widehat { \beta } _ { 2 } ( 1 0 / 5 0 0 )$ . By doing this, we have regressed a series, $x _ { t }$ , of

![](images/f7c10bb5f30bd943c493a57c98640b3d01c616be9a75dd33eb55884b370dd813.jpg)  
Fig. 2.10. The scaled periodogram, (2.45), of the 500 observations generated by (2.38); the data are displayed in Figures 1.11 and 2.9.

length $n$ using $n$ regression parameters, so that we will have a perfect fit. The point, however, is that if the data contain any cyclic behavior we are likely to catch it by performing these saturated regressions.

Next, note that the regression coefficients ${ \widehat { \beta } } _ { 1 } ( j / n )$ and $\widehat { \beta } _ { 2 } ( j / n )$ , for each $j$ , are essentially measuring the correlation of the data with a sinusoid oscillating at $j$ cycles in $n$ time points.6 Hence, an appropriate measure of the presence of a frequency of oscillation of $j$ cycles in $n$ time points in the data would be

$$
P (j / n) = \widehat {\beta} _ {1} ^ {2} (j / n) + \widehat {\beta} _ {2} ^ {2} (j / n), \tag {2.45}
$$

which is basically a measure of squared correlation. The quantity (2.45) is sometimes called the periodogram, but we will call $P ( j / n )$ the scaled periodogram and we will investigate its properties in Chapter 4. Figure 2.10 shows the scaled periodogram for the data generated by (2.38), and it easily discovers the periodic component with frequency $\omega = . 0 2 = 1 0 / 5 0 0$ even though it is difficult to visually notice that component in Figure 1.11 due to the noise.

Finally, we mention that it is not necessary to run a large regression

$$
x _ {t} = \sum_ {j = 0} ^ {n / 2} \beta_ {1} (j / n) \cos (2 \pi t j / n) + \beta_ {2} (j / n) \sin (2 \pi t j / n) \tag {2.46}
$$

to obtain the values of $\beta _ { 1 } ( j / n )$ and $\beta _ { 2 } ( j / n )$ [with $\beta _ { 2 } ( 0 ) = \beta _ { 2 } ( 1 / 2 ) = 0 ]$ because they can be computed quickly if $n$ (assumed even here) is a highly

composite integer. There is no error in (2.46) because there are $_ { n }$ observations and $n$ parameters; the regression fit will be perfect. The discrete Fourier transform (DFT) is a complex-valued weighted average of the data given by

$$
\begin{array}{l} d (j / n) = n ^ {- 1 / 2} \sum_ {t = 1} ^ {n} x _ {t} \exp (- 2 \pi i t j / n) \\ = n ^ {- 1 / 2} \left(\sum_ {t = 1} ^ {n} x _ {t} \cos (2 \pi t j / n) - i \sum_ {t = 1} ^ {n} x _ {t} \sin (2 \pi t j / n)\right) \tag {2.47} \\ \end{array}
$$

where the frequencies $j / n$ are called the Fourier or fundamental frequencies. Because of a large number of redundancies in the calculation, (2.47) may be computed quickly using the fast Fourier transform (FFT)7, which is available in many computing packages such as Matlab $\textsuperscript { \textregistered }$ , S-PLUS $\textsuperscript { \textregistered }$ and R. Note that8

$$
\left| d (j / n) \right| ^ {2} = \frac {1}{n} \left(\sum_ {t = 1} ^ {n} x _ {t} \cos (2 \pi t j / n)\right) ^ {2} + \frac {1}{n} \left(\sum_ {t = 1} ^ {n} x _ {t} \sin (2 \pi t j / n)\right) ^ {2} \tag {2.48}
$$

and it is this quantity that is called the periodogram; we will write

$$
I (j / n) = | d (j / n) | ^ {2}.
$$

We may calculate the scaled periodogram, (2.45), using the periodogram as

$$
P (j / n) = \frac {4}{n} I (j / n). \tag {2.49}
$$

We will discuss this approach in more detail and provide examples with data in Chapter 4.

Figure 2.10 can be created in R using the following commands (and the data already generated in x):

1 I = abs(fft(x))^2/500 # the periodogram   
$\mathit { \Omega } _ { 2 } \texttt { P } = \texttt { ( } 4 / 5 0 0 ) * \mathtt { I } \left[ 1 : 2 5 0 \right]$ # the scaled periodogram   
3 f = 0:249/500 # frequencies   
4 plot(f, P, type="l", xlab="Frequency", ylab="Scaled Periodogram")

# 2.4 Smoothing in the Time Series Context

In 1.4, we introduced the concept of smoothing a time series, and in Example 1.9, we discussed using a moving average to smooth white noise. This method is useful in discovering certain traits in a time series, such as long-term

![](images/97a73636cf4bf0846037f9508ef95e177a2094e0325134f0303149a7b5ea0325.jpg)  
Fig. 2.11. The weekly cardiovascular mortality series discussed in Example 2.2 smoothed using a five-week moving average and a 53-week moving average.

trend and seasonal components. In particular, if $x _ { t }$ represents the observations, then

$$
m _ {t} = \sum_ {j = - k} ^ {k} a _ {j} x _ {t - j}, \tag {2.50}
$$

where $a _ { j } = a _ { - j } \geq 0$ and $\textstyle \sum _ { j = - k } ^ { k } a _ { j } = 1$ is a symmetric moving average of the

# Example 2.10 Moving Average Smoother

For example, Figure 2.11 shows the weekly mortality series discussed in Example 2.2, a five-point moving average (which is essentially a monthly average with $k = 2$ ) that helps bring out the seasonal component and a 53-point moving average (which is essentially a yearly average with $k = 2 6$ ) that helps bring out the (negative) trend in cardiovascular mortality. In both cases, the weights, $a _ { - k } , \dotsc , a _ { 0 } , \dotsc , a _ { k }$ , we used were all the same, and equal to $1 / ( 2 k + 1 )$ .9

To reproduce Figure 2.11 in R:

1 ma5 = filter(cmort, sides=2, rep(1,5)/5)   
2 ma53 = filter(cmort, sides=2, rep(1,53)/53)   
3 plot(cmort, type="p", ylab="mortality")   
4 lines(ma5); lines(ma53)

![](images/5a1d8a3b1aa804c31b5b808893bb9d7679a282e2a267594348d9138adac4f04d.jpg)  
Fig. 2.12. The weekly cardiovascular mortality series with a cubic trend and cubic trend plus periodic regression.

Many other techniques are available for smoothing time series data based on methods from scatterplot smoothers. The general setup for a time plot is

$$
x _ {t} = f _ {t} + y _ {t}, \tag {2.51}
$$

where $f _ { t }$ is some smooth function of time, and $y _ { t }$ is a stationary process. We may think of the moving average smoother $m _ { t }$ , given in (2.50), as an estimator of $f _ { t }$ . An obvious choice for $f _ { t }$ in (2.51) is polynomial regression

$$
f _ {t} = \beta_ {0} + \beta_ {1} t + \dots + \beta_ {p} t ^ {p}. \tag {2.52}
$$

We have seen the results of a linear fit on the global temperature data in Example 2.1. For periodic data, one might employ periodic regression

$$
\begin{array}{l} f _ {t} = \alpha_ {0} + \alpha_ {1} \cos (2 \pi \omega_ {1} t) + \beta_ {1} \sin (2 \pi \omega_ {1} t) \\ + \dots + \alpha_ {p} \cos (2 \pi \omega_ {p} t) + \beta_ {p} \sin (2 \pi \omega_ {p} t), \tag {2.53} \\ \end{array}
$$

where $\omega _ { 1 } , \ldots , \omega _ { p }$ are distinct, specified frequencies. In addition, one might consider combining (2.52) and (2.53). These smoothers can be applied using classical linear regression.

# Example 2.11 Polynomial and Periodic Regression Smoothers

Figure 2.12 shows the weekly mortality series with an estimated (via ordinary least squares) cubic smoother

$$
\widehat {f} _ {t} = \widehat {\beta_ {0}} + \widehat {\beta_ {1}} t + \widehat {\beta_ {2}} t ^ {2} + \widehat {\beta_ {3}} t ^ {3}
$$

superimposed to emphasize the trend, and an estimated (via ordinary least squares) cubic smoother plus a periodic regression

$$
\widehat {f _ {t}} = \widehat {\beta_ {0}} + \widehat {\beta_ {1}} t + \widehat {\beta_ {2}} t ^ {2} + \widehat {\beta_ {3}} t ^ {3} + \widehat {\alpha_ {1}} \cos (2 \pi t / 5 2) + \widehat {\alpha_ {2}} \sin (2 \pi t / 5 2)
$$

superimposed to emphasize trend and seasonality.

The R commands for this example are as follows (we note that the sampling rate is $1 / 5 2$ , so that wk below is essentially $t / 5 2$ ).

```txt
1 wk = time(cmort) - mean(time(cmort))  
2 wk2 = wk^2; wk3 = wk^3  
3 cs = cos(2*pi*wk); sn = sin(2*pi*wk)  
4 reg1 = lm(cmort^wk + wk2 + wk3, na.action=NULL)  
5 reg2 = lm(cmort^wk + wk2 + wk3 + cs + sn, na.action=NULL)  
6 plot(cmort, type="p", ylab="mortality")  
7 lines(fitted(reg1)); lines(fitted(reg2)) 
```

Modern regression techniques can be used to fit general smoothers to the pairs of points $( t , x _ { t } )$ where the estimate of $f _ { t }$ is smooth. Many of the techniques can easily be applied to time series data using the R or S-PLUS statistical packages; see Venables and Ripley (1994, Chapter 10) for details on applying these methods in S-PLUS (R is similar). A problem with the techniques used in Example 2.11 is that they assume $f _ { t }$ is the same function over the range of time, $t$ ; we might say that the technique is global. The moving average smoothers in Example 2.10 fit the data better because the technique is local; that is, moving average smoothers allow for the possibility that $f _ { t }$ is a different function over time. We describe some other local methods in the following examples.

# Example 2.12 Kernel Smoothing

Kernel smoothing is a moving average smoother that uses a weight function, or kernel, to average the observations. Figure 2.13 shows kernel smoothing of the mortality series, where $f _ { t }$ in (2.51) is estimated by

$$
\widehat {f} _ {t} = \sum_ {i = 1} ^ {n} w _ {i} (t) x _ {i}, \tag {2.54}
$$

where

$$
w _ {i} (t) = K \left(\frac {t - i}{b}\right) / \sum_ {j = 1} ^ {n} K \left(\frac {t - j}{b}\right). \tag {2.55}
$$

are the weights and $K ( \cdot )$ is a kernel function. This estimator, which was originally explored by Parzen (1962) and Rosenblatt (1956b), is often called the Nadaraya–Watson estimator (Watson, 1966); typically, the normal kernel, $K ( z ) ~ = ~ \frac { 1 } { \sqrt { 2 \pi } } \exp ( - z ^ { 2 } / 2 )$ , is used. To implement this in R, use the ksmooth function. The wider the bandwidth, $b$ , the smoother the result. In Figure 2.13, the values of $b$ for this example were $b = 5 / 5 2$ (roughly

![](images/9aa8460b8f4f7fed7046a3ea01d0d074a3f3a903059803e7fd72b1d1ac31e5e2.jpg)  
Fig. 2.13. Kernel smoothers of the mortality data.

weighted two to three week averages because $b / 2$ is the inner quartile range of the kernel) for the seasonal component, and $b = 1 0 4 / 5 2 = 2$ (roughly weighted yearly averages) for the trend component.

Figure 2.13 can be reproduced in R (or S-PLUS) as follows.

1 plot(cmort, type="p", ylab="mortality")   
2 lines(ksmooth(time(cmort), cmort, "normal", bandwidth=5/52))   
3 lines(ksmooth(time(cmort), cmort, "normal", bandwidth=2))

# Example 2.13 Lowess and Nearest Neighbor Regression

Another approach to smoothing a time plot is nearest neighbor regression. The technique is based on $k$ -nearest neighbors linear regression, wherein one uses the data $\left\{ x _ { t - k / 2 } , \ldots , x _ { t } , \ldots , x _ { t + k / 2 } \right\}$ to predict $x _ { t }$ using linear regression; the result is $\widehat { f } _ { t }$ . For example, Figure 2.14 shows cardiovascular mortality and the nearest neighbor method using the R (or S-PLUS) smoother supsmu. We used $k = n / 2$ to estimate the trend and $k = n / 1 0 0$ to estimate the seasonal component. In general, supsmu uses a variable window for smoothing (see Friedman, 1984), but it can be used for correlated data by fixing the smoothing window, as was done here.

Lowess is a method of smoothing that is rather complex, but the basic idea is close to nearest neighbor regression. Figure 2.14 shows smoothing of mortality using the R or S-PLUS function lowess (see Cleveland, 1979). First, a certain proportion of nearest neighbors to $x _ { t }$ are included in a weighting scheme; values closer to $x _ { t }$ in time get more weight. Then, a robust weighted regression is used to predict $x _ { t }$ and obtain the smoothed estimate of $f _ { t }$ . The larger the fraction of nearest neighbors included, the smoother the estimate

![](images/e88a9fb6e129ee870567b9aba3fde7dd80662ac0e43153460a372fff009017b2.jpg)

![](images/eb3ec308af8af7f94350b3f73e7dc8b0b711217d861c9aa62b525d01040bc9dd.jpg)  
Fig. 2.14. Nearest neighbor (supsmu) and locally weighted regression (lowess) smoothers of the mortality data.

$\widehat { f } _ { t }$ will be. In Figure 2.14, the smoother uses about two-thirds of the data to obtain an estimate of the trend component, and the seasonal component uses 2% of the data.

Figure 2.14 can be reproduced in R or S-PLUS as follows.

1 par(mfrow=c(2,1))  
2 plot(cmort, type="p", ylab="mortality", main="nearest neighbor")   
3 lines(supsmu(time(cmort), cmort, span=.5))   
4 lines(supsmu(time(cmort), cmort, span=.01))   
5 plot(cmort, type="p", ylab="mortality", main "lowess")   
6 lines(lowess(cmort, f=.02)); lines(lowess(cmort, f=2/3))

# Example 2.14 Smoothing Splines

An extension of polynomial regression is to first divide time $t = 1 , \ldots , n$ , into $k$ intervals, $[ t _ { 0 } = 1 , t _ { 1 } ]$ , $[ t _ { 1 } + 1 , t _ { 2 } ]$ , . . . , $\lvert t _ { k - 1 } + 1 , t _ { k } = n \rvert$ . The values $t _ { 0 } , t _ { 1 } , \ldots , t _ { k }$ are called knots. Then, in each interval, one fits a regression of the form (2.52); typically, $p = 3$ , and this is called cubic splines.

A related method is smoothing splines, which minimizes a compromise between the fit and the degree of smoothness given by

![](images/55ccf84d40109c8e060c6aa7eb0718227b98cfa081854665c94a978fb27a3af3.jpg)  
Fig. 2.15. Smoothing splines fit to the mortality data.

$$
\sum_ {t = 1} ^ {n} \left[ x _ {t} - f _ {t} \right] ^ {2} + \lambda \int \left(f _ {t} ^ {\prime \prime}\right) ^ {2} d t, \tag {2.56}
$$

where $f _ { t }$ is a cubic spline with a knot at each $t$ . The degree of smoothness is controlled by $\lambda > 0$ . There is a relationship between smoothing splines and state space models, which is investigated in Problem 6.7.

In R, the smoothing parameter is called spar and it is monotonically related to $\lambda$ ; type ?smooth.spline to view the help file for details. Figure 2.15 shows smoothing spline fits on the mortality data using generalized cross-validation, which uses the data to “optimally” assess the smoothing parameter, for the seasonal component, and spar=1 for the trend. The figure can be reproduced in R as follows.

1 plot(cmort, type="p", ylab="mortality")   
2 lines(smooth.spline(time(cmort), cmort))   
3 lines(smooth.spline(time(cmort), cmort, spar=1))

# Example 2.15 Smoothing One Series as a Function of Another

In addition to smoothing time plots, smoothing techniques can be applied to smoothing a time series as a function of another time series. In this example, we smooth the scatterplot of two contemporaneously measured time series, mortality as a function of temperature. In Example 2.2, we discovered a nonlinear relationship between mortality and temperature. Continuing along these lines, Figure 2.16 shows scatterplots of mortality, $M _ { t }$ , and temperature, $T _ { t }$ , along with $M _ { t }$ smoothed as a function of $T _ { t }$ using lowess and using smoothing splines. In both cases, mortality increases at extreme

![](images/1ac9df625fbbf35cb0ab7da779c688a9ce2207f48dab76a669419a7ea2ea522d.jpg)

![](images/8ba1da18206d93861e14f2f9b4a67e70e75a228d60fbe960ae0deff8aaf086e0.jpg)  
Fig. 2.16. Smoothers of mortality as a function of temperature using lowess and smoothing splines.

temperatures, but in an asymmetric way; mortality is higher at colder temperatures than at hotter temperatures. The minimum mortality rate seems to occur at approximately $8 0 ^ { \circ } \mathrm { F }$ .

Figure 2.16 can be reproduced in R as follows.

1 par(mfrow=c(2,1), mar=c(3,2,1,0)+.5, mgp=c(1.6,.6,0))   
2 plot(tempr, cmort, main $\cdot ^ { = }$ "lowess", xlab="Temperature", ylab="Mortality")   
3 lines(lowess(tempr,cmort))   
4 plot(tempr, cmort, main $\cdot ^ { = }$ "smoothing splines", xlab="Temperature", ylab="Mortality")   
5 lines(smooth.spline(tempr, cmort))

As a final word of caution, the methods mentioned in this section may not take into account the fact that the data are serially correlated, and most of the techniques have been designed for independent observations. That is, for example, the smoothers shown in Figure 2.16 are calculated under the false assumption that the pairs $( M _ { t } , T _ { t } )$ , are iid pairs of observations. In addition,

the degree of smoothness used in the previous examples were chosen arbitrarily to bring out what might be considered obvious features in the data set.

# Problems

# Section 2.2

2.1 For the Johnson $\&$ Johnson data, say $y _ { t }$ , shown in Figure 1.1, let $x _ { t } =$ $\log ( y _ { t } )$ .

(a) Fit the regression model

$$
x _ {t} = \beta t + \alpha_ {1} Q _ {1} (t) + \alpha_ {2} Q _ {2} (t) + \alpha_ {3} Q _ {3} (t) + \alpha_ {4} Q _ {4} (t) + w _ {t}
$$

where $Q _ { i } ( t ) = 1$ if time $t$ corresponds to quarter $i = 1 , 2 , 3 , 4$ , and zero otherwise. The $Q _ { i } ( t )$ ’s are called indicator variables. We will assume for now that $w _ { t }$ is a Gaussian white noise sequence. What is the interpretation of the parameters $\beta$ , $\alpha _ { 1 }$ , $\alpha _ { 2 }$ , $\alpha _ { 3 }$ , and $\alpha _ { 4 }$ ? (Detailed code is given in Appendix $R$ on page 574.)

(b) What happens if you include an intercept term in the model in (a)?   
(c) Graph the data, $x _ { t }$ , and superimpose the fitted values, say $\widehat { x } _ { t }$ , on the graph. Examine the residuals, $x _ { t } - \widehat { x } _ { t }$ b, and state your conclusions. Does it appear that the model fits the data well (do the residuals look white)?

2.2 For the mortality data examined in Example 2.2:

(a) Add another component to the regression in (2.25) that accounts for the particulate count four weeks prior; that is, add $P _ { t - 4 }$ to the regression in (2.25). State your conclusion.   
(b) Draw a scatterplot matrix of $M _ { t } , T _ { t } , P _ { t }$ and $P _ { t - 4 }$ and then calculate the pairwise correlations between the series. Compare the relationship between $M _ { t }$ and $P _ { t }$ versus $M _ { t }$ and $P _ { t - 4 }$ .

2.3 Repeat the following exercise six times and then discuss the results. Generate a random walk with drift, (1.4), of length $n = 1 0 0$ with $\delta = . 0 1$ and $\sigma _ { w } = 1$ . Call the data $x _ { t }$ for $t = 1 , \ldots , 1 0 0$ . Fit the regression $x _ { t } = \beta t + w _ { t }$ using least squares. Plot the data, the mean function (i.e., $\mu _ { t } = . 0 1 t$ ) and the fitted line, $\widehat { x } _ { t } = \widehat { \beta } t$ , on the same graph. Discuss your results.

The following R code may be useful:

1 par(mfcol = c(3,2)) # set up graphics  
2 for (i in 1:6)  
3 x = ts(cumsum(rnorm(100,.01,1))) # the data  
4 reg = lm(x~0+time(x), na.action=NULL) # the regression  
5 plot(x) # plot data  
6 lines(.01*time(x), col="red", lty="dashed") # plot mean  
7 abline(reg, col="blue") } # plot regression line

2.4 Kullback-Leibler Information. Given the random vector $\pmb { y }$ , we define the information for discriminating between two densities in the same family, indexed by a parameter $\pmb \theta$ , say $f ( \pmb { y } ; \pmb { \theta } _ { 1 } )$ and $f ( \pmb { y } ; \pmb { \theta } _ { 2 } )$ , as

$$
I \left(\boldsymbol {\theta} _ {1}; \boldsymbol {\theta} _ {2}\right) = \frac {1}{n} E _ {1} \log \frac {f (\boldsymbol {y} ; \boldsymbol {\theta} _ {1})}{f (\boldsymbol {y} ; \boldsymbol {\theta} _ {2})}, \tag {2.57}
$$

where $E _ { 1 }$ denotes expectation with respect to the density determined by $\pmb { \theta } _ { 1 }$ . For the Gaussian regression model, the parameters are $\pmb { \theta } = ( \beta ^ { \prime } , \sigma ^ { 2 } ) ^ { \prime }$ . Show that we obtain

$$
I \left(\boldsymbol {\theta} _ {1}; \boldsymbol {\theta} _ {2}\right) = \frac {1}{2} \left(\frac {\sigma_ {1} ^ {2}}{\sigma_ {2} ^ {2}} - \log \frac {\sigma_ {1} ^ {2}}{\sigma_ {2} ^ {2}} - 1\right) + \frac {1}{2} \frac {\left(\boldsymbol {\beta} _ {1} - \boldsymbol {\beta} _ {2}\right) ^ {\prime} Z ^ {\prime} Z \left(\boldsymbol {\beta} _ {1} - \boldsymbol {\beta} _ {2}\right)}{n \sigma_ {2} ^ {2}} \tag {2.58}
$$

in that case.

2.5 Model Selection. Both selection criteria (2.19) and (2.20) are derived from information theoretic arguments, based on the well-known Kullback-Leibler discrimination information numbers (see Kullback and Leibler, 1951, Kullback, 1958). We give an argument due to Hurvich and Tsai (1989). We think of the measure (2.58) as measuring the discrepancy between the two densities, characterized by the parameter values $\pmb { \theta } _ { 1 } ^ { \prime } = ( \beta _ { 1 } ^ { \prime } , \sigma _ { 1 } ^ { 2 } ) ^ { \prime }$ and $\pmb { \theta } _ { 2 } ^ { \prime } = ( \beta _ { 2 } ^ { \prime } , \sigma _ { 2 } ^ { 2 } ) ^ { \prime }$ . Now, if the true value of the parameter vector is $\pmb { \theta } _ { 1 }$ , we argue that the best model would be one that minimizes the discrepancy between the theoretical value and the sample, say $I ( \pmb \theta _ { 1 } ; \widehat \pmb \theta )$ . Because $\pmb { \theta } _ { 1 }$ will not be known, Hurvich and Tsai (1989) considered finding an unbiased estimator for $E _ { 1 } [ I ( \pmb { \beta } _ { 1 } , \sigma _ { 1 } ^ { 2 } ; \hat { \pmb { \beta } } , \hat { \sigma } ^ { 2 } ) ]$ , where

$$
I (\boldsymbol {\beta} _ {1}, \sigma_ {1} ^ {2}; \hat {\boldsymbol {\beta}}, \hat {\sigma} ^ {2}) = \frac {1}{2} \left(\frac {\sigma_ {1} ^ {2}}{\hat {\sigma} ^ {2}} - \log \frac {\sigma_ {1} ^ {2}}{\hat {\sigma} ^ {2}} - 1\right) + \frac {1}{2} \frac {(\boldsymbol {\beta} _ {1} - \hat {\boldsymbol {\beta}}) ^ {\prime} Z ^ {\prime} Z (\boldsymbol {\beta} _ {1} - \hat {\boldsymbol {\beta}})}{n \hat {\sigma} ^ {2}}
$$

and $\beta$ is a $k \times 1$ regression vector. Show that

$$
E _ {1} \left[ I \left(\beta_ {1}, \sigma_ {1} ^ {2}; \hat {\beta}, \hat {\sigma} ^ {2}\right) \right] = \frac {1}{2} \left(- \log \sigma_ {1} ^ {2} + E _ {1} \log \hat {\sigma} ^ {2} + \frac {n + k}{n - k - 2} - 1\right), \tag {2.59}
$$

using the distributional properties of the regression coefficients and error variance. An unbiased estimator for $E _ { 1 } \log { \widehat { \sigma } } ^ { 2 }$ is $\log { \widehat { \sigma } } ^ { 2 }$ . Hence, we have shown that the expectation of the above discrimination information is as claimed. As models with differing dimensions $k$ are considered, only the second and third terms in (2.59) will vary and we only need unbiased estimators for those two terms. This gives the form of AICc quoted in (2.20) in the chapter. You will need the two distributional results

$$
\frac {n \widehat {\sigma} ^ {2}}{\sigma_ {1} ^ {2}} \sim \chi_ {n - k} ^ {2} \quad \mathrm {a n d} \quad \frac {(\widehat {\pmb {\beta}} - \beta_ {1}) ^ {\prime} Z ^ {\prime} Z (\widehat {\pmb {\beta}} - \beta_ {1})}{\sigma_ {1} ^ {2}} \sim \chi_ {k} ^ {2}
$$

The two quantities are distributed independently as chi-squared distributions with the indicated degrees of freedom. If $x \sim \chi _ { n } ^ { 2 }$ , $E ( 1 / x ) = 1 / ( n - 2 )$ .

# Section 2.3

2.6 Consider a process consisting of a linear trend with an additive noise term consisting of independent random variables $w _ { t }$ with zero means and variances $\sigma _ { w } ^ { 2 }$ , that is,

$$
x _ {t} = \beta_ {0} + \beta_ {1} t + w _ {t},
$$

where $\beta _ { 0 } , \beta _ { 1 }$ are fixed constants.

(a) Prove $x _ { t }$ is nonstationary.   
(b) Prove that the first difference series $\nabla x _ { t } = x _ { t } - x _ { t - 1 }$ is stationary by finding its mean and autocovariance function.   
(c) Repeat part (b) if $w _ { t }$ is replaced by a general stationary process, say $y _ { t }$ with mean function $\mu _ { y }$ and autocovariance function $\gamma _ { y } ( h )$ .

2.7 Show (2.31) is stationary.

2.8 The glacial varve record plotted in Figure 2.6 exhibits some nonstationarity that can be improved by transforming to logarithms and some additional nonstationarity that can be corrected by differencing the logarithms.

(a) Argue that the glacial varves series, say $x _ { t }$ , exhibits heteroscedasticity by computing the sample variance over the first half and the second half of the data. Argue that the transformation $y _ { t } = \log x _ { t }$ stabilizes the variance over the series. Plot the histograms of $x _ { t }$ and $y _ { t }$ to see whether the approximation to normality is improved by transforming the data.   
(b) Plot the series $y _ { t }$ . Do any time intervals, of the order 100 years, exist where one can observe behavior comparable to that observed in the global temperature records in Figure 1.2?   
(c) Examine the sample ACF of $y _ { t }$ and comment.   
(d) Compute the difference $u _ { t } = y _ { t } - y _ { t - 1 }$ , examine its time plot and sample ACF, and argue that differencing the logged varve data produces a reasonably stationary series. Can you think of a practical interpretation for $u _ { t }$ ? Hint: For $| p |$ close to zero, $\log ( 1 + p ) \approx p$ ; let $p = ( y _ { t } - y _ { t - 1 } ) / y _ { t - 1 }$ .   
(e) Based on the sample ACF of the differenced transformed series computed in (c), argue that a generalization of the model given by Example 1.23 might be reasonable. Assume

$$
u _ {t} = \mu + w _ {t} - \theta w _ {t - 1}
$$

is stationary when the inputs $w _ { t }$ are assumed independent with mean 0 and variance $\sigma _ { w } ^ { 2 }$ . Show that

$$
\gamma_ {u} (h) = \left\{ \begin{array}{l l} \sigma_ {w} ^ {2} (1 + \theta^ {2}) & \text {i f} h = 0, \\ - \theta   \sigma_ {w} ^ {2} & \text {i f} h = \pm 1, \\ 0 & \text {i f} | h | > 1. \end{array} \right.
$$

(f) Based on part (e), use $\widehat { \rho } _ { u } ( 1 )$ and the estimate of the variance of $u _ { t }$ , $\widehat { \gamma } _ { u } ( 0 )$ , to derive estimates of $\theta$ and $\sigma _ { w } ^ { 2 }$ b. This is an application of the method of moments from classical statistics, where estimators of the parameters are derived by equating sample moments to theoretical moments.

2.9 In this problem, we will explore the periodic nature of $S _ { t }$ , the SOI series displayed in Figure 1.5.

(a) Detrend the series by fitting a regression of $S _ { t }$ on time $t$ . Is there a significant trend in the sea surface temperature? Comment.   
(b) Calculate the periodogram for the detrended series obtained in part (a). Identify the frequencies of the two main peaks (with an obvious one at the frequency of one cycle every 12 months). What is the probable El Ni˜no cycle indicated by the minor peak?

2.10 Consider the model (2.46) used in Example 2.9,

$$
x _ {t} = \sum_ {j = 0} ^ {n} \beta_ {1} (j / n) \cos (2 \pi t j / n) + \beta_ {2} (j / n) \sin (2 \pi t j / n).
$$

(a) Display the model design matrix $Z$ [see (2.5)] for $n = 4$   
(b) Show numerically that the columns of $Z$ in part (a) satisfy part (d) and then display $( Z ^ { \prime } Z ) ^ { - 1 }$ for this case.   
(c) If $x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 }$ are four observations, write the estimates of the four betas, $\beta _ { 1 } ( 0 ) , \beta _ { 1 } ( 1 / 4 ) , \beta _ { 2 } ( 1 / 4 ) , \beta _ { 1 } ( 1 / 2 )$ , in terms of the observations.   
(d) Verify that for any positive integer $n$ and $j , k = 0 , 1 , \ldots , \left\lfloor { n / 2 } \right\rfloor$ , where $\left[ \cdot \right]$ denotes the greatest integer function:10

(i) Except for $j = 0$ or $j = n / 2$

$$
\sum_ {t = 1} ^ {n} \cos^ {2} (2 \pi t j / n) = \sum_ {t = 1} ^ {n} \sin^ {2} (2 \pi t j / n) = n / 2
$$

(ii) When $j = 0$ or $j = n / 2$ ,

$$
\sum_ {t = 1} ^ {n} \cos^ {2} (2 \pi t j / n) = n \quad \text {b u t} \quad \sum_ {t = 1} ^ {n} \sin^ {2} (2 \pi t j / n) = 0.
$$

(iii) For $j \neq k$ ,

$$
\sum_ {t = 1} ^ {n} \cos (2 \pi t j / n) \cos (2 \pi t k / n) = \sum_ {t = 1} ^ {n} \sin (2 \pi t j / n) \sin (2 \pi t k / n) = 0.
$$

Also, for any $j$ and $k$ ,

$$
\sum_ {t = 1} ^ {n} \cos (2 \pi t j / n) \sin (2 \pi t k / n) = 0.
$$

# Section 2.4

2.11 Consider the two weekly time series oil and gas. The oil series is in dollars per barrel, while the gas series is in cents per gallon; see Appendix R for details.

(a) Plot the data on the same graph. Which of the simulated series displayed in §1.3 do these series most resemble? Do you believe the series are stationary (explain your answer)?   
(b) In economics, it is often the percentage change in price (termed growth rate or return), rather than the absolute price change, that is important. Argue that a transformation of the form $y _ { t } = \nabla \log x _ { t }$ might be applied to the data, where $x _ { t }$ is the oil or gas price series [see the hint in Problem 2.8(d)].   
(c) Transform the data as described in part (b), plot the data on the same graph, look at the sample ACFs of the transformed data, and comment. [Hint: poil $=$ diff(log(oil)) and pgas = diff(log(gas)).]   
(d) Plot the CCF of the transformed data and comment The small, but significant values when gas leads oil might be considered as feedback. [Hint: ccf(poil, pgas) will have poil leading for negative lag values.]   
(e) Exhibit scatterplots of the oil and gas growth rate series for up to three weeks of lead time of oil prices; include a nonparametric smoother in each plot and comment on the results (e.g., Are there outliers? Are the relationships linear?). [Hint: lag.plot2(poil, pgas, 3).]   
(f) There have been a number of studies questioning whether gasoline prices respond more quickly when oil prices are rising than when oil prices are falling (“asymmetry”). We will attempt to explore this question here with simple lagged regression; we will ignore some obvious problems such as outliers and autocorrelated errors, so this will not be a definitive analysis. Let $G _ { t }$ and $O _ { t }$ denote the gas and oil growth rates.

(i) Fit the regression (and comment on the results)

$$
G _ {t} = \alpha_ {1} + \alpha_ {2} I _ {t} + \beta_ {1} O _ {t} + \beta_ {2} O _ {t - 1} + w _ {t},
$$

where $I _ { t } ~ = ~ 1$ if $O _ { t } ~ \geq ~ 0$ and 0 otherwise ( $I _ { t }$ is the indicator of no growth or positive growth in oil price). Hint:

1indi $=$ ifelse(poi1 $<  0$ ,0,1)   
2mess $=$ tsintersect(pgas,poi1,poill $\mathbf{L} = \mathbf{l}$ ag(poi1,-1)，indi)   
3summary(fit<-lm(pgas\~poil $^+$ poill $^+$ indi，data=mess))

(ii) What is the fitted model when there is negative growth in oil price at time $t$ ? What is the fitted model when there is no or positive growth in oil price? Do these results support the asymmetry hypothesis?   
(iii) Analyze the residuals from the fit and comment.

2.12 Use two different smoothing techniques described in 2.4 to estimate the trend in the global temperature series displayed in Figure 1.2. Comment.

# ARIMA Models

# 3.1 Introduction

In Chapters 1 and 2, we introduced autocorrelation and cross-correlation functions (ACFs and CCFs) as tools for clarifying relations that may occur within and between time series at various lags. In addition, we explained how to build linear models based on classical regression theory for exploiting the associations indicated by large values of the ACF or CCF. The time domain, or regression, methods of this chapter are appropriate when we are dealing with possibly nonstationary, shorter time series; these series are the rule rather than the exception in many applications. In addition, if the emphasis is on forecasting future values, then the problem is easily treated as a regression problem. This chapter develops a number of regression techniques for time series that are all related to classical ordinary and weighted or correlated least squares.

Classical regression is often insufficient for explaining all of the interesting dynamics of a time series. For example, the ACF of the residuals of the simple linear regression fit to the global temperature data (see Example 2.4 of Chapter 2) reveals additional structure in the data that the regression did not capture. Instead, the introduction of correlation as a phenomenon that may be generated through lagged linear relations leads to proposing the autoregressive (AR) and autoregressive moving average (ARMA) models. Adding nonstationary models to the mix leads to the autoregressive integrated moving average (ARIMA) model popularized in the landmark work by Box and Jenkins (1970). The Box–Jenkins method for identifying a plausible ARIMA model is given in this chapter along with techniques for parameter estimation and forecasting for these models. A partial theoretical justification of the use of ARMA models is discussed in Appendix B, B.4.

# 3.2 Autoregressive Moving Average Models

The classical regression model of Chapter 2 was developed for the static case, namely, we only allow the dependent variable to be influenced by current values of the independent variables. In the time series case, it is desirable to allow the dependent variable to be influenced by the past values of the independent variables and possibly by its own past values. If the present can be plausibly modeled in terms of only the past values of the independent inputs, we have the enticing prospect that forecasting will be possible.

# Introduction to Autoregressive Models

Autoregressive models are based on the idea that the current value of the series, $x _ { t }$ , can be explained as a function of $p$ past values, $x _ { t - 1 } , x _ { t - 2 } , . . . , x _ { t - p }$ , where $p$ determines the number of steps into the past needed to forecast the current value. As a typical case, recall Example 1.10 in which data were generated using the model

$$
x _ {t} = x _ {t - 1} -. 9 0 x _ {t - 2} + w _ {t},
$$

where $w _ { t }$ is white Gaussian noise with $\sigma _ { w } ^ { 2 } = 1$ . We have now assumed the current value is a particular linear function of past values. The regularity that persists in Figure 1.9 gives an indication that forecasting for such a model might be a distinct possibility, say, through some version such as

$$
x _ {n + 1} ^ {n} = x _ {n} -. 9 0 x _ {n - 1},
$$

where the quantity on the left-hand side denotes the forecast at the next period $n + 1$ based on the observed data, $x _ { 1 } , x _ { 2 } , \ldots , x _ { n }$ . We will make this notion more precise in our discussion of forecasting ( 3.5).

The extent to which it might be possible to forecast a real data series from its own past values can be assessed by looking at the autocorrelation function and the lagged scatterplot matrices discussed in Chapter 2. For example, the lagged scatterplot matrix for the Southern Oscillation Index (SOI), shown in Figure 2.7, gives a distinct indication that lags 1 and 2, for example, are linearly associated with the current value. The ACF shown in Figure 1.14 shows relatively large positive values at lags 1, 2, 12, 24, and 36 and large negative values at 18, 30, and 42. We note also the possible relation between the SOI and Recruitment series indicated in the scatterplot matrix shown in Figure 2.8. We will indicate in later sections on transfer function and vector AR modeling how to handle the dependence on values taken by other series.

The preceding discussion motivates the following definition.

Definition 3.1 An autoregressive model of order $p$ , abbreviated AR(p), is of the form

$$
x _ {t} = \phi_ {1} x _ {t - 1} + \phi_ {2} x _ {t - 2} + \dots + \phi_ {p} x _ {t - p} + w _ {t}, \tag {3.1}
$$

where $x _ { t }$ is stationary, and $\phi _ { 1 } , \phi _ { 2 } , \ldots , \phi _ { p }$ are constants ( $\phi _ { p } \neq 0$ ). Although it is not necessary yet, we assume that $w _ { t }$ is a Gaussian white noise series with mean zero and variance $\sigma _ { w } ^ { 2 }$ , unless otherwise stated. The mean of $x _ { t }$ in (3.1) is zero. If the mean, $\mu$ , of $x _ { t }$ is not zero, replace $x _ { t }$ by $x _ { t } - \mu$ in (3.1),

$$
x _ {t} - \mu = \phi_ {1} \left(x _ {t - 1} - \mu\right) + \phi_ {2} \left(x _ {t - 2} - \mu\right) + \dots + \phi_ {p} \left(x _ {t - p} - \mu\right) + w _ {t},
$$

or write

$$
x _ {t} = \alpha + \phi_ {1} x _ {t - 1} + \phi_ {2} x _ {t - 2} + \dots + \phi_ {p} x _ {t - p} + w _ {t}, \tag {3.2}
$$

where $\alpha = \mu ( 1 - \phi _ { 1 } - \cdot \cdot \cdot - \phi _ { p } )$ .

We note that (3.2) is similar to the regression model of 2.2, and hence the term auto (or self) regression. Some technical difficulties, however, develop from applying that model because the regressors, $\boldsymbol { \mathcal { X } } _ { t - 1 } , \ldots , \boldsymbol { \mathcal { X } } _ { t - p }$ , are random components, whereas $z _ { t }$ was assumed to be fixed. A useful form follows by using the backshift operator (2.33) to write the AR(p) model, (3.1), as

$$
\left(1 - \phi_ {1} B - \phi_ {2} B ^ {2} - \dots - \phi_ {p} B ^ {p}\right) x _ {t} = w _ {t}, \tag {3.3}
$$

or even more concisely as

$$
\phi (B) x _ {t} = w _ {t}. \tag {3.4}
$$

The properties of $\phi ( B )$ are important in solving (3.4) for $x _ { t }$ . This leads to the following definition.

Definition 3.2 The autoregressive operator is defined to be

$$
\phi (B) = 1 - \phi_ {1} B - \phi_ {2} B ^ {2} - \dots - \phi_ {p} B ^ {p}. \tag {3.5}
$$

We initiate the investigation of AR models by considering the first-order model, AR(1), given by $x _ { t } = \phi x _ { t - 1 } + w _ { t }$ . Iterating backwards $k$ times, we get

$$
\begin{array}{l} x _ {t} = \phi x _ {t - 1} + w _ {t} = \phi \left(\phi x _ {t - 2} + w _ {t - 1}\right) + w _ {t} \\ = \phi^ {2} x _ {t - 2} + \phi w _ {t - 1} + w _ {t} \\ \begin{array}{c} \bullet \\ \bullet \\ \bullet \\ \bullet \end{array} \\ = \phi^ {k} x _ {t - k} + \sum_ {j = 0} ^ {k - 1} \phi^ {j} w _ {t - j}. \\ \end{array}
$$

This method suggests that, by continuing to iterate backward, and provided that $| \phi | < 1$ and $x _ { t }$ is stationary, we can represent an AR(1) model as a linear process given by1

$$
x _ {t} = \sum_ {j = 0} ^ {\infty} \phi^ {j} w _ {t - j}. \tag {3.6}
$$

The AR(1) process defined by (3.6) is stationary with mean

$$
E (x _ {t}) = \sum_ {j = 0} ^ {\infty} \phi^ {j} E (w _ {t - j}) = 0,
$$

and autocovariance function,

$$
\begin{array}{l} \gamma (h) = \operatorname {c o v} \left(x _ {t + h}, x _ {t}\right) = E \left[ \left(\sum_ {j = 0} ^ {\infty} \phi^ {j} w _ {t + h - j}\right) \left(\sum_ {k = 0} ^ {\infty} \phi^ {k} w _ {t - k}\right) \right] \\ = E \left[ \left(w _ {t + h} + \dots + \phi^ {h} w _ {t} + \phi^ {h + 1} w _ {t - 1} + \dots\right) \left(w _ {t} + \phi w _ {t - 1} + \dots\right) \right] \tag {3.7} \\ = \sigma_ {w} ^ {2} \sum_ {j = 0} ^ {\infty} \phi^ {h + j} \phi^ {j} = \sigma_ {w} ^ {2} \phi^ {h} \sum_ {j = 0} ^ {\infty} \phi^ {2 j} = \frac {\sigma_ {w} ^ {2} \phi^ {h}}{1 - \phi^ {2}}, \quad h \geq 0. \\ \end{array}
$$

Recall that $\gamma ( h ) = \gamma ( - h )$ , so we will only exhibit the autocovariance function for $h \geq 0$ . From (3.7), the ACF of an AR(1) is

$$
\rho (h) = \frac {\gamma (h)}{\gamma (0)} = \phi^ {h}, \quad h \geq 0, \tag {3.8}
$$

and $\rho ( h )$ satisfies the recursion

$$
\rho (h) = \phi \rho (h - 1), \quad h = 1, 2, \dots . \tag {3.9}
$$

We will discuss the ACF of a general AR(p) model in 3.4.

# Example 3.1 The Sample Path of an AR(1) Process

Figure 3.1 shows a time plot of two AR(1) processes, one with $\phi = . 9$ and one with $\phi = - . 9$ ; in both cases, $\sigma _ { w } ^ { 2 } = 1$ . In the first case, $\rho ( h ) = . 9 ^ { h }$ , for $h \geq 0$ , so observations close together in time are positively correlated with each other. This result means that observations at contiguous time points will tend to be close in value to each other; this fact shows up in the top of Figure 3.1 as a very smooth sample path for $x _ { t }$ . Now, contrast this with the case in which $\phi = - . 9$ , so that $\rho ( h ) = ( - . 9 ) ^ { h }$ , for $h \geq 0$ . This result means that observations at contiguous time points are negatively correlated but observations two time points apart are positively correlated. This fact shows up in the bottom of Figure 3.1, where, for example, if an observation, $x _ { t }$ , is positive, the next observation, $x _ { t + 1 }$ , is typically negative, and the next observation, $x _ { t + 2 }$ , is typically positive. Thus, in this case, the sample path is very choppy.

The following R code can be used to obtain a figure similar to Figure 3.1:

1 par(mfrow=c(2,1))  
2 plot(arima.sim(list(order=c(1,0,0), ar=.9), n=100), ylab="x", main=(expression(AR(1)~~~phi==+.9)))   
3 plot(arima.sim(list(order=c(1,0,0), ar=-.9), n=100), ylab="x", main (expression(AR(1)~~~phi==-.9)))

![](images/b93244d9912e35eb7c3371196662207c6532a124323a1be254a7f8a365a40306.jpg)

![](images/32d32f043ebcfdfdd6352e8eba3320d0835b2a8eb874084040ff7ebecc18dde5.jpg)  
Fig. 3.1. Simulated AR(1) models: $\phi = . 9$ (top); $\phi = - . 9$ (bottom).

# Example 3.2 Explosive AR Models and Causality

In Example 1.18, it was discovered that the random walk $x _ { t } = x _ { t - 1 } + w _ { t }$ is not stationary. We might wonder whether there is a stationary AR(1) process with $| \phi | > 1$ . Such processes are called explosive because the values of the time series quickly become large in magnitude. Clearly, because $| \phi | ^ { j }$ increases without bound as $j \to \infty$ , $\textstyle \sum _ { j = 0 } ^ { k - 1 } \phi ^ { j } w _ { t - j }$ will not converge (in mean square) as $k  \infty$ , so the intuition used to get (3.6) will not work directly. We can, however, modify that argument to obtain a stationary model as follows. Write $\boldsymbol { x } _ { t + 1 } = \boldsymbol { \phi } \boldsymbol { x } _ { t } + \boldsymbol { w } _ { t + 1 }$ , in which case,

$$
\begin{array}{l} x _ {t} = \phi^ {- 1} x _ {t + 1} - \phi^ {- 1} w _ {t + 1} = \phi^ {- 1} \left(\phi^ {- 1} x _ {t + 2} - \phi^ {- 1} w _ {t + 2}\right) - \phi^ {- 1} w _ {t + 1} \\ \begin{array}{c} \vdots \\ \vdots \end{array} \\ = \phi^ {- k} x _ {t + k} - \sum_ {j = 1} ^ {k - 1} \phi^ {- j} w _ {t + j}, \tag {3.10} \\ \end{array}
$$

by iterating forward $k$ steps. Because $| \phi | ^ { - 1 } < 1$ , this result suggests the stationary future dependent AR(1) model

$$
x _ {t} = - \sum_ {j = 1} ^ {\infty} \phi^ {- j} w _ {t + j}. \tag {3.11}
$$

The reader can verify that this is stationary and of the AR(1) form $x _ { t } =$ $\phi x _ { t - 1 } + w _ { t }$ . Unfortunately, this model is useless because it requires us to know the future to be able to predict the future. When a process does not depend on the future, such as the AR(1) when $| \phi | < 1$ , we will say the process is causal. In the explosive case of this example, the process is stationary, but it is also future dependent, and not causal.

# Example 3.3 Every Explosion Has a Cause

Excluding explosive models from consideration is not a problem because the models have causal counterparts. For example, if

$$
x _ {t} = \phi x _ {t - 1} + w _ {t} \quad \mathrm {w i t h} \quad | \phi | > 1
$$

and $w _ { t } \sim$ iid $\mathrm { N } ( 0 , \sigma _ { w } ^ { 2 } )$ , then using (3.11), $\{ x _ { t } \}$ is a non-causal stationary Gaussian process with $E ( x _ { t } ) = 0$ and

$$
\begin{array}{l} \gamma_ {x} (h) = \operatorname {c o v} \left(x _ {t + h}, x _ {t}\right) = \operatorname {c o v} \left(- \sum_ {j = 1} ^ {\infty} \phi^ {- j} w _ {t + h + j}, - \sum_ {k = 1} ^ {\infty} \phi^ {- k} w _ {t + k}\right) \\ = \sigma_ {w} ^ {2} \phi^ {- 2} \phi^ {- h} / (1 - \phi^ {- 2}). \\ \end{array}
$$

Thus, using (3.7), the causal process defined by

$$
y _ {t} = \phi^ {- 1} y _ {t - 1} + v _ {t}
$$

where $v _ { t } \sim$ iid $\mathbb { V } ( 0 , \sigma _ { w } ^ { 2 } \phi ^ { - 2 } )$ is stochastically equal to the $x _ { t }$ process (i.e., all finite distributions of the processes are the same). For example, if $x _ { t } =$ $2 x _ { t - 1 } + w _ { t }$ with $\sigma _ { w } ^ { 2 } = 1$ , then $y _ { t } = { \textstyle \frac { 1 } { 2 } } y _ { t - 1 } + v _ { t }$ with $\sigma _ { v } ^ { 2 } = 1 / 4$ is an equivalent causal process (see Problem 3.3). This concept generalizes to higher orders, but it is easier to show using Chapter 4 techniques; see Example 4.7.

The technique of iterating backward to get an idea of the stationary solution of AR models works well when $p = 1$ , but not for larger orders. A general technique is that of matching coefficients. Consider the AR(1) model in operator form

$$
\phi (B) x _ {t} = w _ {t}, \tag {3.12}
$$

where $\phi ( B ) = 1 - \phi B$ , and $| \phi | < 1$ . Also, write the model in equation (3.6) using operator form as

$$
x _ {t} = \sum_ {j = 0} ^ {\infty} \psi_ {j} w _ {t - j} = \psi (B) w _ {t}, \tag {3.13}
$$

where $\begin{array} { r } { \psi ( B ) = \sum _ { j = 0 } ^ { \infty } \psi _ { j } B ^ { j } } \end{array}$ and $\psi _ { j } ~ = ~ \phi ^ { \jmath }$ . Suppose we did not know that $\psi _ { j } = \phi ^ { j }$ . We could substitute $\psi ( B ) w _ { t }$ from (3.13) for $x _ { t }$ in (3.12) to obtain

$$
\phi (B) \psi (B) w _ {t} = w _ {t}. \tag {3.14}
$$

The coefficients of $B$ on the left-hand side of (3.14) must be equal to those on right-hand side of (3.14), which means

$$
(1 - \phi B) (1 + \psi_ {1} B + \psi_ {2} B ^ {2} + \dots + \psi_ {j} B ^ {j} + \dots) = 1. \tag {3.15}
$$

Reorganizing the coefficients in (3.15),

$$
1 + (\psi_ {1} - \phi) B + (\psi_ {2} - \psi_ {1} \phi) B ^ {2} + \dots + (\psi_ {j} - \psi_ {j - 1} \phi) B ^ {j} + \dots = 1,
$$

we see that for each $j = 1 , 2 , \dots$ , the coefficient of $B ^ { j }$ on the left must be zero because it is zero on the right. The coefficient of $B$ on the left is $( \psi _ { 1 } - \phi )$ , and equating this to zero, $\psi _ { 1 } - \phi = 0$ , leads to $\psi _ { 1 } = \phi$ . Continuing, the coefficient of $B ^ { 2 }$ is $( \psi _ { 2 } - \psi _ { 1 } \phi )$ , so $\psi _ { 2 } = \phi ^ { 2 }$ . In general,

$$
\psi_ {j} = \psi_ {j - 1} \phi ,
$$

with $\psi _ { 0 } = 1$ , which leads to the solution $\psi _ { j } = \phi ^ { j }$ .

Another way to think about the operations we just performed is to consider the AR(1) model in operator form, $\phi ( B ) x _ { t } = w _ { t }$ . Now multiply both sides by $\phi ^ { - 1 } ( B )$ (assuming the inverse operator exists) to get

$$
\phi^ {- 1} (B) \phi (B) x _ {t} = \phi^ {- 1} (B) w _ {t},
$$

or

$$
x _ {t} = \phi^ {- 1} (B) w _ {t}.
$$

We know already that

$$
\phi^ {- 1} (B) = 1 + \phi B + \phi^ {2} B ^ {2} + \dots + \phi^ {j} B ^ {j} + \dots ,
$$

that is, $\phi ^ { - 1 } ( B )$ is $\psi ( B )$ in (3.13). Thus, we notice that working with operators is like working with polynomials. That is, consider the polynomial $\phi ( z ) = $ $1 - \phi z$ , where $z$ is a complex number and $| \phi | < 1$ . Then,

$$
\phi^ {- 1} (z) = \frac {1}{(1 - \phi z)} = 1 + \phi z + \phi^ {2} z ^ {2} + \dots + \phi^ {j} z ^ {j} + \dots , \quad | z | \leq 1,
$$

and the coefficients of $B ^ { j }$ in $\phi ^ { - 1 } ( B )$ are the same as the coefficients of $z ^ { j }$ in $\phi ^ { - 1 } ( z )$ . In other words, we may treat the backshift operator, $B$ , as a complex number, $z$ . These results will be generalized in our discussion of ARMA models. We will find the polynomials corresponding to the operators useful in exploring the general properties of ARMA models.

# Introduction to Moving Average Models

As an alternative to the autoregressive representation in which the $x _ { t }$ on the left-hand side of the equation are assumed to be combined linearly, the moving average model of order $q$ , abbreviated as $\mathrm { M A } ( q )$ , assumes the white noise $w _ { t }$ on the right-hand side of the defining equation are combined linearly to form the observed data.

Definition 3.3 The moving average model of order $q$ , or MA(q) model, is defined to be

$$
x _ {t} = w _ {t} + \theta_ {1} w _ {t - 1} + \theta_ {2} w _ {t - 2} + \dots + \theta_ {q} w _ {t - q}, \tag {3.16}
$$

where there are $q$ lags in the moving average and $\theta _ { 1 } , \theta _ { 2 } , \ldots , \theta _ { q }$ ( ${ \theta } _ { q } \ne 0$ ) are parameters.2 Although it is not necessary yet, we assume that $w _ { t }$ is a Gaussian white noise series with mean zero and variance $\sigma _ { w } ^ { 2 }$ , unless otherwise stated.

The system is the same as the infinite moving average defined as the linear process (3.13), where $\psi _ { 0 } = 1$ , $\psi _ { j } = \theta _ { j }$ , for $j = 1 , \dotsc , q$ , and $\psi _ { j } = 0$ for other values. We may also write the $\mathrm { M A } ( q )$ process in the equivalent form

$$
x _ {t} = \theta (B) w _ {t}, \tag {3.17}
$$

using the following definition.

Definition 3.4 The moving average operator is

$$
\theta (B) = 1 + \theta_ {1} B + \theta_ {2} B ^ {2} + \dots + \theta_ {q} B ^ {q}. \tag {3.18}
$$

Unlike the autoregressive process, the moving average process is stationary for any values of the parameters $\theta _ { 1 } , \ldots , \theta _ { q }$ ; details of this result are provided in 3.4.

# Example 3.4 The MA(1) Process

Consider the MA(1) model ${ x _ { t } } = { w _ { t } } + \theta { w _ { t - 1 } }$ . Then, $E ( x _ { t } ) = 0$ ,

$$
\gamma (h) = \left\{ \begin{array}{l l} (1 + \theta^ {2}) \sigma_ {w} ^ {2} & h = 0, \\ \theta \sigma_ {w} ^ {2} & h = 1, \\ 0 & h > 1, \end{array} \right.
$$

and the ACF is

$$
\rho (h) = \left\{ \begin{array}{l l} \frac {\theta}{(1 + \theta^ {2})} & h = 1, \\ 0 & h > 1. \end{array} \right.
$$

Note $| \rho ( 1 ) | \le 1 / 2$ for all values of $\theta$ (Problem 3.1). Also, $x _ { t }$ is correlated with $x _ { t - 1 }$ , but not with $x _ { t - 2 } , x _ { t - 3 } , . . .$ . Contrast this with the case of the AR(1)

![](images/5260b1ab74126819cf12269a319f7a3190d923c965b5666032ace1a606ce6516.jpg)

![](images/4a13eeb6422eff56aed271546a1adc08c563fd207d282e005c79935f41e2eb08.jpg)  
Fig. 3.2. Simulated MA(1) models: $\theta = . 5$ (top); $\theta = - . 5$ (bottom).

model in which the correlation between $x _ { t }$ and $x _ { t - k }$ is never zero. When $\theta = . 5$ , for example, $x _ { t }$ and $x _ { t - 1 }$ are positively correlated, and $\rho ( 1 ) = . 4$ . When $\theta = - . 5$ , $x _ { t }$ and $x _ { t - 1 }$ are negatively correlated, $\rho ( 1 ) = - . 4$ . Figure 3.2 − shows a time plot of these two processes with $\sigma _ { w } ^ { 2 } = 1$ . The series in Figure 3.2 where $\theta = . 5$ is smoother than the series in Figure 3.2, where $\theta = - . 5$ .

A figure similar to Figure 3.2 can be created in R as follows:

1 par(mfrow = c(2,1))   
2 plot(arima.sim(list(order=c(0,0,1), ma=.5), n=100), ylab="x", main=(expression(MA(1)~~~theta==+.5)))   
3 plot(arima.sim(list(order=c(0,0,1), ma=-.5), n=100), ylab="x", main=(expression(MA(1)~~~theta==-.5)))

# Example 3.5 Non-uniqueness of MA Models and Invertibility

Using Example 3.4, we note that for an MA(1) model, $\rho ( h )$ is the same for $\theta$ and $\frac { 1 } { \theta }$ ; try 5 and $\frac { 1 } { 5 }$ , for example. In addition, the pair $\sigma _ { w } ^ { 2 } = 1$ and $\theta = 5$ yield the same autocovariance function as the pair $\sigma _ { w } ^ { 2 } = 2 5$ and $\theta = 1 / 5$ , namely,

$$
\gamma (h) = \left\{ \begin{array}{l l} 2 6 & h = 0, \\ 5 & h = 1, \\ 0 & h > 1. \end{array} \right.
$$

Thus, the MA(1) processes

$$
x _ {t} = w _ {t} + \frac {1}{5} w _ {t - 1}, \quad w _ {t} \sim \mathrm {i i d} \quad \mathrm {N} (0, 2 5)
$$

and

$$
y _ {t} = v _ {t} + 5 v _ {t - 1}, \quad v _ {t} \sim \mathrm {i d} \quad \mathrm {N} (0, 1)
$$

are the same because of normality (i.e., all finite distributions are the same). We can only observe the time series, $x _ { t }$ or $y _ { t }$ , and not the noise, $w _ { t }$ or $v _ { t }$ , so we cannot distinguish between the models. Hence, we will have to choose only one of them. For convenience, by mimicking the criterion of causality for AR models, we will choose the model with an infinite AR representation. Such a process is called an invertible process.

To discover which model is the invertible model, we can reverse the roles of $x _ { t }$ and $w _ { t }$ (because we are mimicking the AR case) and write the MA(1) model as $w _ { t } = - \theta w _ { t - 1 } + x _ { t }$ . Following the steps that led to (3.6), if $| \theta | < 1$ , then $\begin{array} { r } { w _ { t } = \sum _ { j = 0 } ^ { \infty } ( - \theta ) ^ { j } x _ { t - j } } \end{array}$ | |  , which is the desired infinite AR representation of the model. Hence, given a choice, we will choose the model with $\sigma _ { w } ^ { 2 } = 2 5$ and $\theta = 1 / 5$ because it is invertible.

As in the AR case, the polynomial, $\theta ( z )$ , corresponding to the moving average operators, $\theta ( B )$ , will be useful in exploring general properties of MA processes. For example, following the steps of equations (3.12)–(3.15), we can write the MA(1) model as $x _ { t } = \theta ( B ) w _ { t }$ , where $\theta ( B ) = 1 + \theta B$ . If $| \theta | < 1$ , then we can write the model as $\pi ( B ) x _ { t } = w _ { t }$ , where $\pi ( B ) = \theta ^ { - 1 } ( B )$ . Let $\theta ( z ) = 1 + \theta z$ , for $| z | \le 1$ , then $\textstyle \pi ( z ) = \theta ^ { - 1 } ( z ) = 1 / ( 1 + \theta z ) = \sum _ { j = 0 } ^ { \infty } ( - \theta ) ^ { j } z ^ { j }$ , and we determine that $\begin{array} { r } { \pi ( B ) = \sum _ { j = 0 } ^ { \infty } ( - \theta ) ^ { j } B ^ { j } } \end{array}$ .

# Autoregressive Moving Average Models

We now proceed with the general development of autoregressive, moving average, and mixed autoregressive moving average (ARMA), models for stationary time series.

Definition 3.5 A time series $\{ x _ { t } ; ~ t = 0 , \pm 1 , \pm 2 , \ldots \}$ is ARMA $( p , q )$ if it is stationary and

$$
x _ {t} = \phi_ {1} x _ {t - 1} + \dots + \phi_ {p} x _ {t - p} + w _ {t} + \theta_ {1} w _ {t - 1} + \dots + \theta_ {q} w _ {t - q}, \tag {3.19}
$$

with $\phi _ { p } \neq 0$ , ${ \theta } _ { q } \ \ne \ 0$ , and $\sigma _ { w } ^ { 2 } \ > \ 0$ . The parameters $p$ and $q$ are called the autoregressive and the moving average orders, respectively. If $x _ { t }$ has a nonzero mean $\mu$ , we set $\alpha = \mu ( 1 - \phi _ { 1 } - \cdot \cdot \cdot - \phi _ { p } )$ and write the model as

$$
x _ {t} = \alpha + \phi_ {1} x _ {t - 1} + \dots + \phi_ {p} x _ {t - p} + w _ {t} + \theta_ {1} w _ {t - 1} + \dots + \theta_ {q} w _ {t - q}. \tag {3.20}
$$

series with mean zero and variance Although it is not necessary yet, we assume that $\sigma _ { w } ^ { 2 }$ , unless otherwise stated. $w _ { t }$ is a Gaussian white noise

As previously noted, when $q = 0$ , the model is called an autoregressive model of order $p$ , $\operatorname { A R } ( p )$ , and when $p = 0$ , the model is called a moving average model of order $q$ , $\mathrm { M A } ( q )$ . To aid in the investigation of ARMA models, it will be useful to write them using the AR operator, (3.5), and the MA operator, (3.18). In particular, the ARMA $( p , q )$ model in (3.19) can then be written in concise form as

$$
\phi (B) x _ {t} = \theta (B) w _ {t}. \tag {3.21}
$$

Before we discuss the conditions under which (3.19) is causal and invertible, we point out a potential problem with the ARMA model.

# Example 3.6 Parameter Redundancy

Consider a white noise process $x _ { t } = w _ { t }$ . Equivalently, we can write this as . $5 x _ { t - 1 } = . 5 w _ { t - 1 }$ by shifting back one unit of time and multiplying by .5. Now, subtract the two representations to obtain

$$
x _ {t} -. 5 x _ {t - 1} = w _ {t} -. 5 w _ {t - 1},
$$

or

$$
x _ {t} = . 5 x _ {t - 1} - . 5 w _ {t - 1} + w _ {t}, \tag {3.22}
$$

which looks like an ARMA $( 1 , 1 )$ model. Of course, $x _ { t }$ is still white noise; nothing has changed in this regard [i.e., $x _ { t } = w _ { t }$ is the solution to (3.22)], but we have hidden the fact that $x _ { t }$ is white noise because of the parameter redundancy or over-parameterization. Write the parameter redundant model in operator form as $\phi ( B ) x _ { t } = \theta ( B ) w _ { t }$ , or

$$
(1 -. 5 B) x _ {t} = (1 -. 5 B) w _ {t}.
$$

Apply the operator $\phi ( B ) ^ { - 1 } = ( 1 - . 5 B ) ^ { - 1 }$ to both sides to obtain

$$
x _ {t} = (1 -. 5 B) ^ {- 1} (1 -. 5 B) x _ {t} = (1 -. 5 B) ^ {- 1} (1 -. 5 B) w _ {t} = w _ {t},
$$

which is the original model. We can easily detect the problem of overparameterization with the use of the operators or their associated polynomials. That is, write the AR polynomial $\phi ( z ) = ( 1 - . 5 z )$ , the MA polynomial $\theta ( z ) = ( 1 - . 5 z )$ , and note that both polynomials have a common factor, namely $( 1 - . 5 z )$ . This common factor immediately identifies the parameter redundancy. Discarding the common factor in each leaves $\phi ( z ) = 1$ and $\theta ( z ) = 1$ , from which we conclude $\phi ( B ) = 1$ and $\theta ( B ) = 1$ , and we deduce that the model is actually white noise. The consideration of parameter redundancy will be crucial when we discuss estimation for general ARMA models. As this example points out, we might fit an ARMA(1, 1) model to white noise data and find that the parameter estimates are significant. If we were unaware of parameter redundancy, we might claim the data are correlated when in fact they are not (Problem 3.20).

Examples 3.2, 3.5, and 3.6 point to a number of problems with the general definition of ARMA $( p , q )$ models, as given by (3.19), or, equivalently, by (3.21). To summarize, we have seen the following problems:

(i) parameter redundant models,   
(ii) stationary AR models that depend on the future, and   
(iii) MA models that are not unique.

To overcome these problems, we will require some additional restrictions on the model parameters. First, we make the following definitions.

Definition 3.6 The AR and MA polynomials are defined as

$$
\phi (z) = 1 - \phi_ {1} z - \dots - \phi_ {p} z ^ {p}, \quad \phi_ {p} \neq 0, \tag {3.23}
$$

and

$$
\theta (z) = 1 + \theta_ {1} z + \dots + \theta_ {q} z ^ {q}, \quad \theta_ {q} \neq 0, \tag {3.24}
$$

respectively, where $z$ is a complex number.

To address the first problem, we will henceforth refer to an $\mathrm { A R M A } ( p , q )$ $( p , q )$ model to mean that it is in its simplest form. That is, in addition to the original definition given in equation (3.19), we will also require that $\phi ( z )$ and $\theta ( z )$ have no common factors. So, the process, $x _ { t } = . 5 x _ { t - 1 } - . 5 w _ { t - 1 } + w _ { t }$ , discussed in Example 3.6 is not referred to as an ARMA(1, 1) process because, in its reduced form, $x _ { t }$ is white noise.

To address the problem of future-dependent models, we formally introduce the concept of causality.

Definition 3.7 An ARMA(p, q) model is said to be causal, if the time series $\{ x _ { t } ; ~ t = 0 , \pm 1 , \pm 2 , \ldots \}$ can be written as a one-sided linear process:

$$
x _ {t} = \sum_ {j = 0} ^ {\infty} \psi_ {j} w _ {t - j} = \psi (B) w _ {t}, \tag {3.25}
$$

where $\begin{array} { r } { \psi ( B ) = \sum _ { j = 0 } ^ { \infty } \psi _ { j } B ^ { j } } \end{array}$ , and $\textstyle \sum _ { j = 0 } ^ { \infty } | \psi _ { j } | < \infty$ ; we set $\psi _ { 0 } = 1$

In Example 3.2, the AR(1) process, $x _ { t } = \phi x _ { t - 1 } + w _ { t }$ , is causal only when $| \phi | < 1$ . Equivalently, the process is causal only when the root of $\phi ( z ) = 1 - \phi z$ is bigger than one in absolute value. That is, the root, say, $z _ { 0 }$ , of $\phi ( z )$ is $z _ { 0 } = 1 / \phi$ (because $\phi ( z _ { 0 } ) = 0$ ) and $| z _ { 0 } | > 1$ because $| \phi | < 1$ . In general, we have the following property.

# Property 3.1 Causality of an ARMA $( p , q )$ Process

An $A R M A ( p , q )$ model is causal if and only if $\phi ( z ) \neq 0$ for $| z | \le 1$ . The coefficients of the linear process given in (3.25) can be determined by solving

$$
\psi (z) = \sum_ {j = 0} ^ {\infty} \psi_ {j} z ^ {j} = \frac {\theta (z)}{\phi (z)}, \quad | z | \leq 1.
$$

Another way to phrase Property 3.1 is that an ARMA process is causal only when the roots of $\phi ( z )$ lie outside the unit circle; that is, $\phi ( z ) = 0$ only when $| z | > 1$ . Finally, to address the problem of uniqueness discussed in Example 3.5, we choose the model that allows an infinite autoregressive representation.

Definition 3.8 An $A R M A ( p , q )$ model is said to be invertible, if the time series $\{ x _ { t } ; ~ t = 0 , \pm 1 , \pm 2 , \ldots \}$ can be written as

$$
\pi (B) x _ {t} = \sum_ {j = 0} ^ {\infty} \pi_ {j} x _ {t - j} = w _ {t}, \tag {3.26}
$$

where $\begin{array} { r } { \pi ( B ) = \sum _ { j = 0 } ^ { \infty } \pi _ { j } B ^ { j } } \end{array}$ , and $\textstyle \sum _ { j = 0 } ^ { \infty } | \pi _ { j } | < \infty$ ; we set $\pi _ { 0 } = 1$

Analogous to Property 3.1, we have the following property.

# Property 3.2 Invertibility of an ARMA $( p , q )$ Process

An ARMA(p, q) model is invertible if and only if $\theta ( z ) \neq 0$ for $| z | \le 1$ . The coefficients $\boldsymbol { \mathscr { n } } _ { j }$ of $\pi ( B )$ given in (3.26) can be determined by solving

$$
\pi (z) = \sum_ {j = 0} ^ {\infty} \pi_ {j} z ^ {j} = \frac {\phi (z)}{\theta (z)}, \quad | z | \leq 1.
$$

Another way to phrase Property 3.2 is that an ARMA process is invertible only when the roots of $\theta ( z )$ lie outside the unit circle; that is, $\theta ( z ) = 0$ only when $| z | > 1$ . The proof of Property 3.1 is given in Appendix B (the proof of Property 3.2 is similar and, hence, is not provided). The following examples illustrate these concepts.

# Example 3.7 Parameter Redundancy, Causality, Invertibility

Consider the process

$$
x _ {t} = . 4 x _ {t - 1} +. 4 5 x _ {t - 2} + w _ {t} + w _ {t - 1} +. 2 5 w _ {t - 2},
$$

or, in operator form,

$$
(1 -. 4 B -. 4 5 B ^ {2}) x _ {t} = (1 + B +. 2 5 B ^ {2}) w _ {t}.
$$

At first, $x _ { t }$ appears to be an ARMA $( 2 , 2 )$ process. But, the associated polynomials

$$
\begin{array}{l} \phi (z) = 1 -. 4 z -. 4 5 z ^ {2} = (1 +. 5 z) (1 -. 9 z) \\ \theta (z) = (1 + z +. 2 5 z ^ {2}) = (1 +. 5 z) ^ {2} \\ \end{array}
$$

have a common factor that can be canceled. After cancellation, the polynomials become $\phi ( z ) = ( 1 - . 9 z ) \quad$ and $\theta ( z ) = ( 1 + . 5 z )$ , so the model is an $\mathrm { A R M A } ( 1 , 1 )$ model, $( 1 - . 9 B ) x _ { t } = ( 1 + . 5 B ) w _ { t }$ , or

$$
x _ {t} = . 9 x _ {t - 1} +. 5 w _ {t - 1} + w _ {t}. \tag {3.27}
$$

The model is causal because $\phi ( z ) = ( 1 - . 9 z ) = 0$ when $z = 1 0 / 9$ , which is outside the unit circle. The model is also invertible because the root of $\theta ( z ) = ( 1 + . 5 z )$ is $z = - 2$ , which is outside the unit circle.

To write the model as a linear process, we can obtain the $\psi$ -weights using Property 3.1, $\phi ( z ) \psi ( z ) = \theta ( z )$ , or

$$
(1 -. 9 z) \left(\psi_ {0} + \psi_ {1} z + \psi_ {2} z ^ {2} + \dots\right) = (1 +. 5 z).
$$

Matching coefficients we get $\psi _ { 0 } = 1$ , $\psi _ { 1 } = . 5 + . 9 = 1 . 4$ , and $\psi _ { j } = . 9 \psi _ { j - 1 }$ for $j > 1$ . Thus, $\psi _ { j } = 1 . 4 ( . 9 ) ^ { j - 1 }$ for $j \geq 1$ and (3.27) can be written as

$$
x _ {t} = w _ {t} + 1. 4 \sum_ {j = 1} ^ {\infty}. 9 ^ {j - 1} w _ {t - j}.
$$

Similarly, the invertible representation using Property 3.2 is

$$
x _ {t} = 1. 4 \sum_ {j = 1} ^ {\infty} (-. 5) ^ {j - 1} x _ {t - j} + w _ {t}.
$$

# Example 3.8 Causal Conditions for an AR(2) Process

For an AR(1) model, $( 1 - \phi B ) x _ { t } = w _ { t }$ , to be causal, the root of $\phi ( z ) = 1 - \phi z$ must lie outside of the unit circle. In this case, the root (or zero) occurs at $z _ { 0 } = 1 / \phi$ [i.e., $\phi ( z _ { 0 } ) = 0$ ], so it is easy to go from the causal requirement on the root, $| 1 / \phi | > 1$ , to a requirement on the parameter, $| \phi | < 1$ . It is not so easy to establish this relationship for higher order models.

For example, the AR(2) model, $( 1 - \phi _ { 1 } B - \phi _ { 2 } B ^ { 2 } ) x _ { t } = w _ { t }$ , is causal when the two roots of $\phi ( z ) = 1 - \phi _ { 1 } z - \phi _ { 2 } z ^ { 2 }$ lie outside of the unit circle. Using the quadratic formula, this requirement can be written as

$$
\left| \frac {\phi_ {1} \pm \sqrt {\phi_ {1} ^ {2} + 4 \phi_ {2}}}{- 2 \phi_ {2}} \right| > 1.
$$

The roots of $\phi ( z )$ may be real and distinct, real and equal, or a complex conjugate pair. If we denote those roots by $z _ { 1 }$ and $z _ { 2 }$ , we can write $\phi ( z ) =$ $( 1 - z _ { 1 } ^ { - 1 } z ) ( 1 - z _ { 2 } ^ { - 1 } z )$ ; note that $\phi ( z _ { 1 } ) = \phi ( z _ { 2 } ) = 0 .$ . The model can be written in operator form as $( 1 - z _ { 1 } ^ { - 1 } B ) ( 1 - z _ { 2 } ^ { - 1 } B ) x _ { t } = w _ { t } ,$ . From this representation, it follows that $\phi _ { 1 } = ( z _ { 1 } ^ { - 1 } + z _ { 2 } ^ { - 1 } )$ and $\phi _ { 2 } = - ( z _ { 1 } z _ { 2 } ) ^ { - 1 }$ . This relationship and the fact that $| z _ { 1 } | > 1$ and $| z _ { 2 } | > 1$ can be used to establish the following equivalent condition for causality:

$$
\phi_ {1} + \phi_ {2} <   1, \quad \phi_ {2} - \phi_ {1} <   1, \quad \text {a n d} \quad | \phi_ {2} | <   1. \tag {3.28}
$$

This causality condition specifies a triangular region in the parameter space. We leave the details of the equivalence to the reader (Problem 3.5).

# 3.3 Difference Equations

The study of the behavior of ARMA processes and their ACFs is greatly enhanced by a basic knowledge of difference equations, simply because they are difference equations. This topic is also useful in the study of time domain models and stochastic processes in general. We will give a brief and heuristic account of the topic along with some examples of the usefulness of the theory. For details, the reader is referred to Mickens (1990).

Suppose we have a sequence of numbers $u _ { 0 } , u _ { 1 } , u _ { 2 } , \ldots$ such that

$$
u _ {n} - \alpha u _ {n - 1} = 0, \quad \alpha \neq 0, \quad n = 1, 2, \dots . \tag {3.29}
$$

For example, recall (3.9) in which we showed that the ACF of an AR(1) process is a sequence, $\rho ( h )$ , satisfying

$$
\rho (h) - \phi \rho (h - 1) = 0, \quad h = 1, 2, \dots .
$$

Equation (3.29) represents a homogeneous difference equation of order 1. To solve the equation, we write:

$$
u _ {1} = \alpha u _ {0}
$$

$$
u _ {2} = \alpha u _ {1} = \alpha^ {2} u _ {0}
$$

$$
u _ {n} = \alpha u _ {n - 1} = \alpha^ {n} u _ {0}.
$$

Given an initial condition $u _ { 0 } = c$ , we may solve (3.29), namely, $u _ { n } = \alpha ^ { \pi } c$

In operator notation, (3.29) can be written as $( 1 - \alpha B ) u _ { n } = 0$ . The polynomial associated with (3.29) is $\alpha ( z ) = 1 - \alpha z$ , and the root, say, $z _ { 0 }$ , of this polynomial is $z _ { 0 } = 1 / \alpha$ ; that is $\alpha ( z _ { 0 } ) = 0$ . We know a solution (in fact, the solution) to (3.29), with initial condition $u _ { 0 } = c$ , is

$$
u _ {n} = \alpha^ {n} c = \left(z _ {0} ^ {- 1}\right) ^ {n} c. \tag {3.30}
$$

That is, the solution to the difference equation (3.29) depends only on the initial condition and the inverse of the root to the associated polynomial $\alpha ( z )$ .

Now suppose that the sequence satisfies

$$
u _ {n} - \alpha_ {1} u _ {n - 1} - \alpha_ {2} u _ {n - 2} = 0, \quad \alpha_ {2} \neq 0, \quad n = 2, 3, \dots \tag {3.31}
$$

This equation is a homogeneous difference equation of order 2. The corresponding polynomial is

$$
\alpha (z) = 1 - \alpha_ {1} z - \alpha_ {2} z ^ {2},
$$

which has two roots, say, $z _ { 1 }$ and $z _ { 2 }$ ; that is, $\alpha ( z _ { 1 } ) = \alpha ( z _ { 2 } ) = 0$ . We will consider two cases. First suppose $z _ { 1 } \neq z _ { 2 }$ . Then the general solution to (3.31) is

$$
u _ {n} = c _ {1} z _ {1} ^ {- n} + c _ {2} z _ {2} ^ {- n}, \tag {3.32}
$$

where $c _ { 1 }$ and $c _ { 2 }$ depend on the initial conditions. The claim that is $a$ solution can be verified by direct substitution of (3.32) into (3.31):

$$
\begin{array}{l} \left(c _ {1} z _ {1} ^ {- n} + c _ {2} z _ {2} ^ {- n}\right) - \alpha_ {1} \left(c _ {1} z _ {1} ^ {- (n - 1)} + c _ {2} z _ {2} ^ {- (n - 1)}\right) - \alpha_ {2} \left(c _ {1} z _ {1} ^ {- (n - 2)} + c _ {2} z _ {2} ^ {- (n - 2)}\right) \\ = c _ {1} z _ {1} ^ {- n} \left(1 - \alpha_ {1} z _ {1} - \alpha_ {2} z _ {1} ^ {2}\right) + c _ {2} z _ {2} ^ {- n} \left(1 - \alpha_ {1} z _ {2} - \alpha_ {2} z _ {2} ^ {2}\right) \\ = c _ {1} z _ {1} ^ {- n} \alpha (z _ {1}) + c _ {2} z _ {2} ^ {- n} \alpha (z _ {2}) = 0. \\ \end{array}
$$

Given two initial conditions $u _ { 0 }$ and $u _ { 1 }$ , we may solve for $c _ { 1 }$ and $c _ { 2 }$

$$
u _ {0} = c _ {1} + c _ {2} \quad \text {a n d} \quad u _ {1} = c _ {1} z _ {1} ^ {- 1} + c _ {2} z _ {2} ^ {- 1},
$$

where $z _ { 1 }$ and $z _ { 2 }$ can be solved for in terms of $\alpha _ { 1 }$ and $\alpha _ { 2 }$ using the quadratic formula, for example.

When the roots are equal, $z _ { 1 } = z _ { 2 }$ ( $\mathbf { \Phi } = \mathbf { \Phi } _ { Z 0 }$ ), a general solution to (3.31) is

$$
u _ {n} = z _ {0} ^ {- n} \left(c _ {1} + c _ {2} n\right). \tag {3.33}
$$

This claim can also be verified by direct substitution of (3.33) into (3.31):

$$
\begin{array}{l} z _ {0} ^ {- n} \left(c _ {1} + c _ {2} n\right) - \alpha_ {1} \left(z _ {0} ^ {- (n - 1)} [ c _ {1} + c _ {2} (n - 1) ]\right) - \alpha_ {2} \left(z _ {0} ^ {- (n - 2)} [ c _ {1} + c _ {2} (n - 2) ]\right) \\ = z _ {0} ^ {- n} \left(c _ {1} + c _ {2} n\right) \left(1 - \alpha_ {1} z _ {0} - \alpha_ {2} z _ {0} ^ {2}\right) + c _ {2} z _ {0} ^ {- n + 1} \left(\alpha_ {1} + 2 \alpha_ {2} z _ {0}\right) \\ = c _ {2} z _ {0} ^ {- n + 1} \left(\alpha_ {1} + 2 \alpha_ {2} z _ {0}\right). \\ \end{array}
$$

To show that $( \alpha _ { 1 } + 2 \alpha _ { 2 } z _ { 0 } ) = 0$ , write $1 - \alpha _ { 1 } z - \alpha _ { 2 } z ^ { 2 } = ( 1 - z _ { 0 } ^ { - 1 } z ) ^ { 2 }$ , and take derivatives with respect to $z$ on both sides of the equation to obtain $( \alpha _ { 1 } + 2 \alpha _ { 2 } z ) = 2 z _ { 0 } ^ { - 1 } ( 1 - z _ { 0 } ^ { - 1 } z )$ . Thus, $( \alpha _ { 1 } + 2 \alpha _ { 2 } z _ { 0 } ) = 2 z _ { 0 } ^ { - 1 } ( 1 - z _ { 0 } ^ { - 1 } z _ { 0 } ) = 0$ , as was to be shown. Finally, given two initial conditions, $u _ { 0 }$ and $u _ { 1 }$ , we can solve for $c _ { 1 }$ and $c _ { 2 }$ :

$$
u _ {0} = c _ {1} \quad \text {a n d} \quad u _ {1} = (c _ {1} + c _ {2}) z _ {0} ^ {- 1}.
$$

It can also be shown that these solutions are unique.

To summarize these results, in the case of distinct roots, the solution to the homogeneous difference equation of degree two was

$$
\begin{array}{l} u _ {n} = z _ {1} ^ {- n} \times (\text {a p o l y n o m i a l i n} n \text {o f d e g r e e} m _ {1} - 1) \tag {3.34} \\ + z _ {2} ^ {- n} \times (\text {a p o l y n o m i a l i n} n \text {o f d e g r e e} m _ {2} - 1), \\ \end{array}
$$

where $m _ { 1 }$ is the multiplicity of the root $z _ { 1 }$ and $m _ { 2 }$ is the multiplicity of the root ${ \mathit { a } } _ { 2 }$ . In this example, of course, $m _ { 1 } = m _ { 2 } = 1$ , and we called the polynomials of degree zero $c _ { 1 }$ and $c _ { 2 }$ , respectively. In the case of the repeated root, the solution was

$$
u _ {n} = z _ {0} ^ {- n} \times (\text {a p o l y n o m i a l i n} n \text {o f d e g r e e} m _ {0} - 1), \tag {3.35}
$$

where $m _ { 0 }$ is the multiplicity of the root $z _ { 0 }$ ; that is, $m _ { 0 } = 2$ . In this case, we wrote the polynomial of degree one as $c _ { 1 } + c _ { 2 } n$ . In both cases, we solved for $c _ { 1 }$ and $c _ { 2 }$ given two initial conditions, $u _ { 0 }$ and $u _ { 1 }$ .

# Example 3.9 The ACF of an AR(2) Process

Suppose $x _ { t } = \phi _ { 1 } x _ { t - 1 } + \phi _ { 2 } x _ { t - 2 } + w _ { t }$ is a causal AR(2) process. Multiply each side of the model by $x _ { t - h }$ for $h > 0$ , and take expectation:

$$
E \left(x _ {t} x _ {t - h}\right) = \phi_ {1} E \left(x _ {t - 1} x _ {t - h}\right) + \phi_ {2} E \left(x _ {t - 2} x _ {t - h}\right) + E \left(w _ {t} x _ {t - h}\right).
$$

The result is

$$
\gamma (h) = \phi_ {1} \gamma (h - 1) + \phi_ {2} \gamma (h - 2), \quad h = 1, 2, \dots . \tag {3.36}
$$

In (3.36), we used the fact that $E ( x _ { t } ) = 0$ and for $h > 0$ ,

$$
E \left(w _ {t} x _ {t - h}\right) = E \left(w _ {t} \sum_ {j = 0} ^ {\infty} \psi_ {j} w _ {t - h - j}\right) = 0.
$$

Divide (3.36) through by $\gamma ( 0 )$ to obtain the difference equation for the ACF of the process:

$$
\rho (h) - \phi_ {1} \rho (h - 1) - \phi_ {2} \rho (h - 2) = 0, \quad h = 1, 2, \dots . \tag {3.37}
$$

The initial conditions are $\rho ( 0 ) = 1$ and $\rho ( - 1 ) = \phi _ { 1 } / ( 1 - \phi _ { 2 } )$ , which is obtained by evaluating (3.37) for $h = 1$ and noting that $\rho ( 1 ) = \rho ( - 1 )$ .

Using the results for the homogeneous difference equation of order two, let $z _ { 1 }$ and $z _ { 2 }$ be the roots of the associated polynomial, $\phi ( z ) = 1 - \phi _ { 1 } z - \phi _ { 2 } z ^ { 2 }$ . Because the model is causal, we know the roots are outside the unit circle: $| z _ { 1 } | > 1$ and $| z _ { 2 } | > 1$ . Now, consider the solution for three cases:

(i) When $z _ { 1 }$ and $z _ { 2 }$ are real and distinct, then

$$
\rho (h) = c _ {1} z _ {1} ^ {- h} + c _ {2} z _ {2} ^ {- h},
$$

so $\rho ( h ) \to 0$ exponentially fast as $h  \infty$

(ii) When $z _ { 1 } = z _ { 2 } ( = z _ { 0 } )$ are real and equal, then

$$
\rho (h) = z _ {0} ^ {- h} \left(c _ {1} + c _ {2} h\right),
$$

so $\rho ( h ) \to 0$ exponentially fast as $h  \infty$

(iii) When $z _ { 1 } = z _ { 2 }$ are a complex conjugate pair, then $c _ { 2 } = c _ { 1 }$ (because $\rho ( h )$ is real), and

$$
\rho (h) = c _ {1} z _ {1} ^ {- h} + \bar {c} _ {1} \bar {z} _ {1} ^ {- h}.
$$

Write $c _ { 1 }$ and $z _ { 1 }$ in polar coordinates, for example, $z _ { 1 } = | z _ { 1 } | e ^ { i \theta }$ , where $\theta$ is the angle whose tangent is the ratio of the imaginary part and the real part of $z _ { 1 }$ (sometimes called $\mathrm { a r g } ( z _ { 1 } )$ ; the range of $\theta$ is $[ - \pi , \pi ] )$ . Then, using the fact that $e ^ { i \alpha } + e ^ { - i \alpha } = 2 \cos ( \alpha )$ , the solution has the form

$$
\rho (h) = a \left| z _ {1} \right| ^ {- h} \cos (h \theta + b),
$$

where $a$ and $b$ are determined by the initial conditions. Again, $\rho ( h )$ dampens to zero exponentially fast as $h  \infty$ , but it does so in a sinusoidal fashion. The implication of this result is shown in the next example.

# Example 3.10 An AR(2) with Complex Roots

Figure 3.3 shows $n = 1 4 4$ observations from the AR(2) model

$$
x _ {t} = 1. 5 x _ {t - 1} -. 7 5 x _ {t - 2} + w _ {t},
$$

with $\sigma _ { w } ^ { 2 } = 1$ , and with complex roots chosen so the process exhibits pseudocyclic behavior at the rate of one cycle every 12 time points. The autoregressive polynomial for this model is $\phi ( z ) = 1 - 1 . 5 z + . 7 5 z ^ { 2 }$ . The roots of $\phi ( z )$ are $1 \pm i / \sqrt { 3 }$ , and $\theta = \tan ^ { - 1 } ( 1 / \sqrt { 3 } ) = 2 \pi / 1 2$ radians per unit time. To convert the angle to cycles per unit time, divide by $2 \pi$ to get $1 / 1 2$ cycles per unit time. The ACF for this model is shown in §3.4, Figure 3.4.

To calculate the roots of the polynomial and solve for arg in R:

1 $\texttt { z } = \texttt { c } ( 1 , - 1 . 5 , . 7 5 )$ # coefficients of the polynomial   
2 (a = polyroot(z)[1]) # print one root: $1 + 0 . 5 7 7 3 5 i = 1 + i / s q r t ( 3 )$   
3 arg = Arg(a)/(2*pi) # arg in cycles/pt   
4 1/arg $\# \ = \ 1 2$ , the pseudo period

To reproduce Figure 3.3:

1 set.seed(90210)   
2 ar2 $=$ arima.sim(list(order $\Bumpeq { \bf c }$ (2,0,0), ar=c(1.5,-.75)), $\ l { \textsc { n } } = \ l { 1 4 4 } { \ r { , } }$   
3 plot(1:144/12, ar2, type="l", xlab "Time (one unit $=$ 12 points)")   
4 abline( $\mathtt { v } = 0 : 1 2$ , lty="dotted", lwd $^ { = 2 }$ )

To calculate and display the ACF for this model:

1 ACF $=$ ARMAacf(ar=c(1.5,-.75), ma=0, 50)   
2 plot(ACF, type="h", xlab="lag")   
3 abline( $\scriptstyle \mathtt { h } = 0$ )

We now exhibit the solution for the general homogeneous difference equation of order $p$ :

$$
u _ {n} - \alpha_ {1} u _ {n - 1} - \dots - \alpha_ {p} u _ {n - p} = 0, \quad \alpha_ {p} \neq 0, \quad n = p, p + 1, \dots . \tag {3.38}
$$

The associated polynomial is

$$
\alpha (z) = 1 - \alpha_ {1} z - \dots - \alpha_ {p} z ^ {p}.
$$

Suppose $\alpha ( z )$ has $r$ distinct roots, $z _ { 1 }$ with multiplicity $m _ { 1 }$ , $z _ { 2 }$ with multiplicity $m _ { 2 }$ , . . . , and $z _ { r }$ with multiplicity $m _ { r }$ , such that $m _ { 1 } + m _ { 2 } + \cdot \cdot \cdot + m _ { r } = p$ . The general solution to the difference equation (3.38) is

$$
u _ {n} = z _ {1} ^ {- n} P _ {1} (n) + z _ {2} ^ {- n} P _ {2} (n) + \dots + z _ {r} ^ {- n} P _ {r} (n), \tag {3.39}
$$

where $P _ { j } ( n )$ , for $j = 1 , 2 , \dots , r$ , is a polynomial in $n$ , of degree $m _ { j } - 1$ . Given $p$ initial conditions $u _ { 0 } , \ldots , u _ { p - 1 }$ , we can solve for the $P _ { j } ( n )$ explicitly.

# Example 3.11 The $\psi$ -weights for an ARMA Model

For a causal ARMA $( p , q )$ model, $\phi ( B ) x _ { t } = \theta ( B ) w _ { t }$ , where the zeros of $\phi ( z )$ are outside the unit circle, recall that we may write

![](images/d679dc3d7316c99905b061bf0ed3be1672804ed63eff4977bfe94eb1e6a6758d.jpg)  
Fig. 3.3. Simulated AR(2) model, $n = 1 4 4$ with $\phi _ { 1 } = 1 . 5$ and $\phi _ { 2 } = - . 7 5$ .

$$
x _ {t} = \sum_ {j = 0} ^ {\infty} \psi_ {j} w _ {t - j},
$$

where the $\psi$ -weights are determined using Property 3.1.

For the pure $\mathrm { M A } ( q )$ model, $\psi _ { 0 } = 1$ , $\psi _ { j } = \theta _ { j }$ , for $j = 1 , \dots , q$ , and $\psi _ { j } = 0$ , otherwise. For the general case of ARMA $( p , q )$ models, the task of solving for the $\psi$ -weights is much more complicated, as was demonstrated in Example 3.7. The use of the theory of homogeneous difference equations can help here. To solve for the $\psi$ -weights in general, we must match the coefficients in $\phi ( z ) \psi ( z ) = \theta ( z )$ :

$$
(1 - \phi_ {1} z - \phi_ {2} z ^ {2} - \dots) (\psi_ {0} + \psi_ {1} z + \psi_ {2} z ^ {2} + \dots) = (1 + \theta_ {1} z + \theta_ {2} z ^ {2} + \dots).
$$

The first few values are

$$
\psi_ {0} = 1
$$

$$
\psi_ {1} - \phi_ {1} \psi_ {0} = \theta_ {1}
$$

$$
\psi_ {2} - \phi_ {1} \psi_ {1} - \phi_ {2} \psi_ {0} = \theta_ {2}
$$

$$
\psi_ {3} - \phi_ {1} \psi_ {2} - \phi_ {2} \psi_ {1} - \phi_ {3} \psi_ {0} = \theta_ {3}
$$

where we would take $\phi _ { j } = 0$ for $j > p$ , and $\theta _ { j } = 0$ for $j > q$ . The $\psi$ -weights satisfy the homogeneous difference equation given by

$$
\psi_ {j} - \sum_ {k = 1} ^ {p} \phi_ {k} \psi_ {j - k} = 0, \quad j \geq \max  (p, q + 1), \tag {3.40}
$$

with initial conditions

$$
\psi_ {j} - \sum_ {k = 1} ^ {j} \phi_ {k} \psi_ {j - k} = \theta_ {j}, \quad 0 \leq j <   \max  (p, q + 1). \tag {3.41}
$$

The general solution depends on the roots of the AR polynomial $\phi ( z ) = $ $1 - \phi _ { 1 } z - \cdot \cdot \cdot - \phi _ { p } z ^ { p }$ , as seen from (3.40). The specific solution will, of course, depend on the initial conditions.

Consider the ARMA process given in (3.27), $x _ { t } = . 9 x _ { t - 1 } + . 5 w _ { t - 1 } + w _ { t }$ . Because $\operatorname* { m a x } ( p , q + 1 ) = 2$ , using (3.41), we have $\psi _ { 0 } = 1$ and $\psi _ { 1 } = . 9 + . 5 =$ 1.4. By (3.40), for $j = 2 , 3 , \dots$ , the $\psi$ -weights satisfy $\psi _ { j } - . 9 \psi _ { j - 1 } = 0$ . The general solution is $\psi _ { j } = c . 9 ^ { j }$ . To find the specific solution, use the initial condition $\psi _ { 1 } = 1 . 4$ , so $1 . 4 = . 9 c$ or $c = 1 . 4 / . 9$ . Finally, $\psi _ { j } = 1 . 4 ( . 9 ) ^ { \ j - 1 }$ , for $j \geq 1$ , as we saw in Example 3.7.

To view, for example, the first 50 $\psi$ -weights in R, use:

1 ARMAtoMA(ar=.9, ma=.5, 50) # for a list   
2 plot(ARMAtoMA(ar=.9, ma=.5, 50)) # for a graph

# 3.4 Autocorrelation and Partial Autocorrelation

We begin by exhibiting the ACF of an MA(q) process, $x _ { t } = \theta ( B ) w _ { t }$ , where $\theta ( B ) = 1 + \theta _ { 1 } B + \cdot \cdot \cdot + \theta _ { q } B ^ { q } .$ . Because $x _ { t }$ is a finite linear combination of white noise terms, the process is stationary with mean

$$
E (x _ {t}) = \sum_ {j = 0} ^ {q} \theta_ {j} E (w _ {t - j}) = 0,
$$

where we have written $\theta _ { 0 } = 1$ , and with autocovariance function

$$
\begin{array}{l} \gamma (h) = \operatorname {c o v} \left(x _ {t + h}, x _ {t}\right) = \operatorname {c o v} \left(\sum_ {j = 0} ^ {q} \theta_ {j} w _ {t + h - j}, \sum_ {k = 0} ^ {q} \theta_ {k} w _ {t - k}\right) \\ = \left\{ \begin{array}{l l} \sigma_ {w} ^ {2} \sum_ {j = 0} ^ {q - h} \theta_ {j} \theta_ {j + h}, & 0 \leq h \leq q \\ 0 & h > q. \end{array} \right. \tag {3.42} \\ \end{array}
$$

Recall that $\gamma ( h ) = \gamma ( - h )$ , so we will only display the values for $h \geq 0$ . The cutting off of $\gamma ( h )$ after $q$ lags is the signature of the $\mathrm { M A } ( q )$ model. Dividing (3.42) by $\gamma ( 0 )$ yields the ACF of an $\mathrm { M A } ( q )$ :

$$
\rho (h) = \left\{ \begin{array}{l l} \frac {\sum_ {j = 0} ^ {q - h} \theta_ {j} \theta_ {j + h}}{1 + \theta_ {1} ^ {2} + \cdots + \theta_ {q} ^ {2}} & 1 \leq h \leq q \\ 0 & h > q. \end{array} \right. \tag {3.43}
$$

For a causal ARMA $( p , q )$ model, $\phi ( B ) x _ { t } \ : = \ : \theta ( B ) w _ { t }$ , where the zeros of $\phi ( z )$ are outside the unit circle, write

$$
x _ {t} = \sum_ {j = 0} ^ {\infty} \psi_ {j} w _ {t - j}. \tag {3.44}
$$

It follows immediately that $E ( x _ { t } ) = 0$ . Also, the autocovariance function of $x _ { t }$ can be written as

$$
\gamma (h) = \operatorname {c o v} \left(x _ {t + h}, x _ {t}\right) = \sigma_ {w} ^ {2} \sum_ {j = 0} ^ {\infty} \psi_ {j} \psi_ {j + h}, \quad h \geq 0. \tag {3.45}
$$

We could then use (3.40) and (3.41) to solve for the $\psi$ -weights. In turn, we could solve for $\gamma ( h )$ , and the ACF $\rho ( h ) = \gamma ( h ) / \gamma ( 0 )$ . As in Example 3.9, it is also possible to obtain a homogeneous difference equation directly in terms of $\gamma ( h )$ . First, we write

$$
\begin{array}{l} \gamma (h) = \operatorname {c o v} _ {p} \left(x _ {t + h}, x _ {t}\right) = \operatorname {c o v} \left(\sum_ {j = 1} ^ {p} \phi_ {j} x _ {t + h - j} + \sum_ {j = 0} ^ {q} \theta_ {j} w _ {t + h - j}, x _ {t}\right) \tag {3.46} \\ = \sum_ {j = 1} ^ {p} \phi_ {j} \gamma (h - j) + \sigma_ {w} ^ {2} \sum_ {j = h} ^ {q} \theta_ {j} \psi_ {j - h}, \quad h \geq 0, \\ \end{array}
$$

where we have used the fact that, for $h \geq 0$ ,

$$
\operatorname {c o v} (w _ {t + h - j}, x _ {t}) = \operatorname {c o v} \Bigl (w _ {t + h - j}, \sum_ {k = 0} ^ {\infty} \psi_ {k} w _ {t - k} \Bigr) = \psi_ {j - h} \sigma_ {w} ^ {2}.
$$

From (3.46), we can write a general homogeneous equation for the ACF of a causal ARMA process:

$$
\gamma (h) - \phi_ {1} \gamma (h - 1) - \dots - \phi_ {p} \gamma (h - p) = 0, \quad h \geq \max  (p, q + 1), \tag {3.47}
$$

with initial conditions

$$
\gamma (h) - \sum_ {j = 1} ^ {p} \phi_ {j} \gamma (h - j) = \sigma_ {w} ^ {2} \sum_ {j = h} ^ {q} \theta_ {j} \psi_ {j - h}, \quad 0 \leq h <   \max  (p, q + 1). \tag {3.48}
$$

Dividing (3.47) and (3.48) through by $\gamma ( 0 )$ will allow us to solve for the ACF, $\rho ( h ) = \gamma ( h ) / \gamma ( 0 )$ .

# Example 3.12 The ACF of an $\mathbf { A R } ( p )$

In Example 3.9 we considered the case where $p = 2$ . For the general case, it follows immediately from (3.47) that

$$
\rho (h) - \phi_ {1} \rho (h - 1) - \dots - \phi_ {p} \rho (h - p) = 0, \quad h \geq p. \tag {3.49}
$$

Let $z _ { 1 } , \ldots , z _ { r }$ denote the roots of $\phi ( z )$ , each with multiplicity $m _ { 1 } , \ldots , m _ { r }$ , respectively, where $m _ { 1 } + \cdot \cdot \cdot + m _ { r } = p _ { \cdot }$ . Then, from (3.39), the general solution is

$$
\rho (h) = z _ {1} ^ {- h} P _ {1} (h) + z _ {2} ^ {- h} P _ {2} (h) + \dots + z _ {r} ^ {- h} P _ {r} (h), \quad h \geq p, \tag {3.50}
$$

where $P _ { j } ( h )$ is a polynomial in $h$ of degree $m _ { j } - 1$ .

Recall that for a causal model, all of the roots are outside the unit circle, $| z _ { i } | > 1$ , for $i = 1 , \ldots , r$ . If all the roots are real, then $\rho ( h )$ dampens exponentially fast to zero as $h  \infty$ . If some of the roots are complex, then they will be in conjugate pairs and $\rho ( h )$ will dampen, in a sinusoidal fashion, exponentially fast to zero as $h  \infty$ . In the case of complex roots, the time series will appear to be cyclic in nature. This, of course, is also true for ARMA models in which the AR part has complex roots.

# Example 3.13 The ACF of an $\mathbf { A R M A } ( 1 , 1 )$ $( 1 , 1 )$

Consider the ARMA $( 1 , 1 )$ process $x _ { t } = \phi x _ { t - 1 } + \theta w _ { t - 1 } + w _ { t }$ , where $| \phi | < 1$ . Based on (3.47), the autocovariance function satisfies

$$
\gamma (h) - \phi \gamma (h - 1) = 0, \quad h = 2, 3, \dots ,
$$

and it follows from (3.29)–(3.30) that the general solution is

$$
\gamma (h) = c \phi^ {h}, \quad h = 1, 2, \dots . \tag {3.51}
$$

To obtain the initial conditions, we use (3.48):

$$
\gamma (0) = \phi \gamma (1) + \sigma_ {w} ^ {2} [ 1 + \theta \phi + \theta^ {2} ] \quad \text {a n d} \quad \gamma (1) = \phi \gamma (0) + \sigma_ {w} ^ {2} \theta .
$$

Solving for $\gamma ( 0 )$ and $\gamma ( 1 )$ , we obtain:

$$
\gamma (0) = \sigma_ {w} ^ {2} \frac {1 + 2 \theta \phi + \theta^ {2}}{1 - \phi^ {2}} \quad \mathrm {a n d} \quad \gamma (1) = \sigma_ {w} ^ {2} \frac {(1 + \theta \phi) (\phi + \theta)}{1 - \phi^ {2}}.
$$

To solve for $c$ , note that from (3.51), $\gamma ( 1 ) = c \phi$ or $c = \gamma ( 1 ) / \phi$ . Hence, the specific solution for $h \geq 1$ is

$$
\gamma (h) = \frac {\gamma (1)}{\phi} \phi^ {h} = \sigma_ {w} ^ {2} \frac {(1 + \theta \phi) (\phi + \theta)}{1 - \phi^ {2}} \phi^ {h - 1}.
$$

Finally, dividing through by $\gamma ( 0 )$ yields the ACF

$$
\rho (h) = \frac {(1 + \theta \phi) (\phi + \theta)}{1 + 2 \theta \phi + \theta^ {2}} \phi^ {h - 1}, \quad h \geq 1. \tag {3.52}
$$

Notice that the general pattern of $\rho ( h )$ in (3.52) is not different from that of an AR(1) given in (3.8). Hence, it is unlikely that we will be able to tell the difference between an ARMA(1,1) and an AR(1) based solely on an ACF estimated from a sample. This consideration will lead us to the partial autocorrelation function.

# The Partial Autocorrelation Function (PACF)

We have seen in (3.43), for $\mathrm { M A } ( q )$ models, the ACF will be zero for lags greater than $q$ . Moreover, because ${ \theta } _ { q } \ne 0$ , the ACF will not be zero at lag $q$ . Thus, the ACF provides a considerable amount of information about the order of the dependence when the process is a moving average process. If the process, however, is ARMA or AR, the ACF alone tells us little about the orders of dependence. Hence, it is worthwhile pursuing a function that will behave like the ACF of MA models, but for AR models, namely, the partial autocorrelation function (PACF).

To motivate the idea, consider a causal AR(1) model, $x _ { t } = \phi x _ { t - 1 } + w _ { t }$ Then,

$$
\begin{array}{l} \gamma_ {x} (2) = \operatorname {c o v} \left(x _ {t}, x _ {t - 2}\right) = \operatorname {c o v} \left(\phi x _ {t - 1} + w _ {t}, x _ {t - 2}\right) \\ = \operatorname {c o v} \left(\phi^ {2} x _ {t - 2} + \phi w _ {t - 1} + w _ {t}, x _ {t - 2}\right) = \phi^ {2} \gamma_ {x} (0). \\ \end{array}
$$

This result follows from causality because $x _ { t - 2 }$ involves $\{ w _ { t - 2 } , w _ { t - 3 } , . . . \}$ , which are all uncorrelated with $w _ { t }$ and $w _ { t - 1 }$ − − −. The correlation between $x _ { t }$ and $x _ { t - 2 }$ is not zero, as it would be for an MA(1), because $x _ { t }$ is dependent on $x _ { t - 2 }$ through $x _ { t - 1 }$ . Suppose we break this chain of dependence by removing (or partial out) the effect $x _ { t - 1 }$ . That is, we consider the correlation between $x _ { t } - \phi x _ { t - 1 }$ and $x _ { t - 2 } - \phi x _ { t - 1 }$ , because it is the correlation between $x _ { t }$ and $x _ { t - 2 }$ with the linear dependence of each on $x _ { t - 1 }$ removed. In this way, we have broken the dependence chain between $x _ { t }$ and $x _ { t - 2 }$ . In fact,

$$
\operatorname {c o v} \left(x _ {t} - \phi x _ {t - 1}, x _ {t - 2} - \phi x _ {t - 1}\right) = \operatorname {c o v} \left(w _ {t}, x _ {t - 2} - \phi x _ {t - 1}\right) = 0.
$$

Hence, the tool we need is partial autocorrelation, which is the correlation between $x _ { s }$ and $x _ { t }$ with the linear effect of everything “in the middle” removed.

To formally define the PACF for mean-zero stationary time series, let $\widehat { x } _ { t + h }$ , for $h \geq 2$ , denote the regression3 of $x _ { t + h }$ on $\{ x _ { t + h - 1 } , x _ { t + h - 2 } , \ldots , x _ { t + 1 } \}$ b, which we write as

$$
\widehat {x} _ {t + h} = \beta_ {1} x _ {t + h - 1} + \beta_ {2} x _ {t + h - 2} + \dots + \beta_ {h - 1} x _ {t + 1}. \tag {3.53}
$$

No intercept term is needed in (3.53) because the mean of $x _ { t }$ is zero (otherwise, replace $x _ { t }$ by $x _ { t } - \mu _ { x }$ in this discussion). In addition, let $\widehat { x } _ { t }$ denote the regression of $x _ { t }$ on $\{ x _ { t + 1 } , x _ { t + 2 } , \ldots , x _ { t + h - 1 } \}$ , then

$$
\widehat {x} _ {t} = \beta_ {1} x _ {t + 1} + \beta_ {2} x _ {t + 2} + \dots + \beta_ {h - 1} x _ {t + h - 1}. \tag {3.54}
$$

Because of stationarity, the coefficients, $\beta _ { 1 } , \ldots , \beta _ { h - 1 }$ are the same in (3.53) and (3.54); we will explain this result in the next section.

Definition 3.9 The partial autocorrelation function (PACF) of a stationary process, $x _ { t }$ , denoted $\phi _ { h h }$ , for $h = 1 , 2 , \ldots$ , is

$$
\phi_ {1 1} = \operatorname {c o r r} \left(x _ {t + 1}, x _ {t}\right) = \rho (1) \tag {3.55}
$$

and

$$
\phi_ {h h} = \operatorname {c o r r} \left(x _ {t + h} - \widehat {x} _ {t + h}, x _ {t} - \widehat {x} _ {t}\right), \quad h \geq 2. \tag {3.56}
$$

Both $\left( x _ { t + h } - \widehat { x } _ { t + h } \right)$ and $\left( x _ { t } - { \widehat { x } } _ { t } \right)$ are uncorrelated with $\{ x _ { t + 1 } , \ldots , x _ { t + h - 1 } \}$ . The PACF, $\phi _ { h h }$ b b, is the correlation between $x _ { t + h }$ and $x _ { t }$ with the linear dependence of $\{ x _ { t + 1 } , \ldots , x _ { t + h - 1 } \}$ on each, removed. If the process $x _ { t }$ is Gaussian, then $\phi _ { h h } = \operatorname { c o r r } ( x _ { t + h } , x _ { t } \mid x _ { t + 1 } , \ldots , x _ { t + h - 1 } )$ ; that is, $\phi _ { h h }$ is the correlation coefficient between $x _ { t + h }$ and $x _ { t }$ in the bivariate distribution of $\displaystyle ( x _ { t + h } , x _ { t } )$ conditional on $\{ x _ { t + 1 } , \ldots , x _ { t + h - 1 } \}$ .

# Example 3.14 The PACF of an AR(1)

Consider the PACF of the AR(1) process given by $x _ { t } = \phi x _ { t - 1 } + w _ { t }$ , with $| \phi | < 1$ . By definition, $\phi _ { 1 1 } = \rho ( 1 ) = \phi$ . To calculate $\phi _ { 2 2 }$ , consider the regression of $x _ { t + 2 }$ on $x _ { t + 1 }$ , say, $\hat { x } _ { t + 2 } = \beta x _ { t + 1 }$ . We choose $\beta$ to minimize

$$
E (x _ {t + 2} - \widehat {x} _ {t + 2}) ^ {2} = E (x _ {t + 2} - \beta x _ {t + 1}) ^ {2} = \gamma (0) - 2 \beta \gamma (1) + \beta^ {2} \gamma (0).
$$

Taking derivatives with respect to $\beta$ and setting the result equal to zero, we have $\beta = \gamma ( 1 ) / \gamma ( 0 ) = \rho ( 1 ) = \phi$ . Next, consider the regression of $x _ { t }$ on $x _ { t + 1 }$ , say $\hat { x } _ { t } = \beta x _ { t + 1 }$ . We choose $\beta$ to minimize

$$
E \left(x _ {t} - \widehat {x} _ {t}\right) ^ {2} = E \left(x _ {t} - \beta x _ {t + 1}\right) ^ {2} = \gamma (0) - 2 \beta \gamma (1) + \beta^ {2} \gamma (0).
$$

This is the same equation as before, so $\beta = \phi$ . Hence,

$$
\begin{array}{l} \phi_ {2 2} = \operatorname {c o r r} \left(x _ {t + 2} - \widehat {x} _ {t + 2}, x _ {t} - \widehat {x} _ {t}\right) = \operatorname {c o r r} \left(x _ {t + 2} - \phi x _ {t + 1}, x _ {t} - \phi x _ {t + 1}\right) \\ = \operatorname {c o r r} \left(w _ {t + 2}, x _ {t} - \phi x _ {t + 1}\right) = 0 \\ \end{array}
$$

by causality. Thus, $\phi _ { 2 2 } = 0$ . In the next example, we will see that in this case, $\phi _ { h h } = 0$ for all $h > 1$ .

# Example 3.15 The PACF of an $\mathbf { A R } ( p )$

The model implies $\begin{array} { r } { x _ { t + h } \ = \ \sum _ { j = 1 } ^ { p } \phi _ { j } x _ { t + h - j } \ + \ w _ { t + h } } \end{array}$ , where the roots of $\phi ( z )$ are outside the unit circle. When $h > p$ , the regression of $x _ { t + h }$ on $\{ x _ { t + 1 } , \ldots , x _ { t + h - 1 } \}$ , is

$$
\widehat {x} _ {t + h} = \sum_ {j = 1} ^ {p} \phi_ {j} x _ {t + h - j}.
$$

We have not proved this obvious result yet, but we will prove it in the next section. Thus, when $h > p$ ,

$$
\phi_ {h h} = \operatorname {c o r r} \left(x _ {t + h} - \widehat {x} _ {t + h}, x _ {t} - \widehat {x} _ {t}\right) = \operatorname {c o r r} \left(w _ {t + h}, x _ {t} - \widehat {x} _ {t}\right) = 0,
$$

![](images/7a4b3409140730194050637a42d161654a6c5d7f2863ae391697b3fdf7472f4b.jpg)

![](images/fb4dee1295a4bcd4b56eacd912afe4c4cc0bcb3e1ac34ec463cee7257476bc7d.jpg)  
Fig. 3.4. The ACF and PACF of an AR(2) model with $\phi _ { 1 } = 1 . 5$ and $\phi _ { 2 } = - . 7 5$ .

because, by causality, $x _ { t } - \widehat { x } _ { t }$ depends only on $\{ w _ { t + h - 1 } , w _ { t + h - 2 } , . . . \}$ ; recall equation (3.54). When $h \leq p$ , $\phi _ { p p }$ is not zero, and $\phi _ { 1 1 } , \ldots , \phi _ { p - 1 , p - 1 }$ are not necessarily zero. We will see later that, in fact, $\phi _ { p p } = \phi _ { p }$ . Figure 3.4 shows the ACF and the PACF of the AR(2) model presented in Example 3.10.

To reproduce Figure 3.4 in R, use the following commands:

1 ACF $=$ ARMAacf(ar=c(1.5,-.75), ma=0, 24)[-1]   
2 PACF $=$ ARMAacf(ar=c(1.5,-.75), ma=0, 24, pacf=TRUE)   
3 par(mfrow=c(1,2))  
4 plot(ACF, type="h", xlab="lag", ylim=c(-.8,1)); abline(h=0)   
5 plot(PACF, type="h", xlab="lag", ylim=c(-.8,1)); abline(h=0)

# Example 3.16 The PACF of an Invertible MA(q)

For an invertible $\operatorname { M A } ( q )$ , we can write $\begin{array} { r } { x _ { t } = - \sum _ { j = 1 } ^ { \infty } \pi { _ j } x _ { t - j } + w _ { t } , } \end{array}$ . Moreover, no finite representation exists. From this result, it should be apparent that the PACF will never cut off, as in the case of an $\operatorname { A R } ( p )$ .

For an MA(1), $x _ { t } = w _ { t } + \theta w _ { t - 1 }$ , with $| \theta | < 1$ , calculations similar to Example 3.14 will yield $\phi _ { 2 2 } = - \theta ^ { 2 } / ( 1 + \theta ^ { 2 } + \theta ^ { 4 } )$ . For the MA(1) in general, we can show that

$$
\phi_ {h h} = - \frac {(- \theta) ^ {h} (1 - \theta^ {2})}{1 - \theta^ {2 (h + 1)}}, \quad h \geq 1.
$$

In the next section, we will discuss methods of calculating the PACF. The PACF for MA models behaves much like the ACF for AR models. Also, the PACF for AR models behaves much like the ACF for MA models. Because an invertible ARMA model has an infinite AR representation, the PACF will not cut off. We may summarize these results in Table 3.1.

Table 3.1. Behavior of the ACF and PACF for ARMA Models   

<table><tr><td></td><td>AR(p)</td><td>MA(q)</td><td>ARMA(p,q)</td></tr><tr><td>ACF</td><td>Tails off</td><td>Cuts off after lag q</td><td>Tails off</td></tr><tr><td>PACF</td><td>Cuts off after lag p</td><td>Tails off</td><td>Tails off</td></tr></table>

# Example 3.17 Preliminary Analysis of the Recruitment Series

We consider the problem of modeling the Recruitment series shown in Figure 1.5. There are 453 months of observed recruitment ranging over the years 1950-1987. The ACF and the PACF given in Figure 3.5 are consistent with the behavior of an AR(2). The ACF has cycles corresponding roughly to a 12-month period, and the PACF has large values for $h = 1 , 2$ and then is essentially zero for higher order lags. Based on Table 3.1, these results suggest that a second-order ( $p \ = \ 2$ ) autoregressive model might provide a good fit. Although we will discuss estimation in detail in 3.6, we ran a regression (see 2.2) using the data triplets $\left\{ { \left( x ; z _ { 1 } , z _ { 2 } \right) : \left( x _ { 3 } ; x _ { 2 } , x _ { 1 } \right) , \left( x _ { 4 } ; x _ { 3 } , x _ { 2 } \right) , . . . , \left( x _ { 4 5 3 } ; x _ { 4 5 2 } , x _ { 4 5 1 } \right) } \right\}$ to fit a model of the form

$$
x _ {t} = \phi_ {0} + \phi_ {1} x _ {t - 1} + \phi_ {2} x _ {t - 2} + w _ {t}
$$

for $t = 3 , 4 , \dots , 4 5 3$ . The values of the estimates were $\widehat { \phi } _ { 0 } ~ = ~ 6 . 7 4 _ { ( 1 . 1 1 ) }$ $\widehat { \phi } _ { 1 } = 1 . 3 5 _ { ( . 0 4 ) } , \widehat { \phi } _ { 2 } = - . 4 6 _ { ( . 0 4 ) }$ , and $\widehat { \sigma } _ { w } ^ { 2 } = 8 9 . 7 2$ , where the estimated standard errors are in parentheses.

The following R code can be used for this analysis. We use the script acf2 to print and plot the ACF and PACF; see Appendix R for details.

1 acf2(rec, 48) # will produce values and a graphic   
2 (regr = ar.ols(rec, order=2, demean=FALSE, intercept=TRUE))   
3 regr$asy.se.coef # standard errors of the estimates

# 3.5 Forecasting

In forecasting, the goal is to predict future values of a time series, $x _ { n + m }$ , $m =$ $1 , 2 , \ldots$ , based on the data collected to the present, $\pmb { x } = \{ x _ { n } , x _ { n - 1 } , . ~ . ~ . ~ , x _ { 1 } \}$ . Throughout this section, we will assume $x _ { t }$ is stationary and the model parameters are known. The problem of forecasting when the model parameters are unknown will be discussed in the next section; also, see Problem 3.26. The minimum mean square error predictor of $x _ { n + m }$ is

$$
x _ {n + m} ^ {n} = E \left(x _ {n + m} \mid \boldsymbol {x}\right) \tag {3.57}
$$

because the conditional expectation minimizes the mean square error

![](images/038cb64a976cc68b02b2fb737015f60b7af60b8324de4b19036d728a490bd2b6.jpg)

![](images/772bbd72bc6ebb5ac175a37142e0fc1fcf37c60f90634cc06b4d878fd9b4dac7.jpg)  
Fig. 3.5. ACF and PACF of the Recruitment series. Note that the lag axes are in terms of season (12 months in this case).

$$
E \left[ x _ {n + m} - g (\boldsymbol {x}) \right] ^ {2}, \tag {3.58}
$$

where $g ( { \pmb x } )$ is a function of the observations $_ { x }$ ; see Problem 3.14.

First, we will restrict attention to predictors that are linear functions of the data, that is, predictors of the form

$$
x _ {n + m} ^ {n} = \alpha_ {0} + \sum_ {k = 1} ^ {n} \alpha_ {k} x _ {k}, \tag {3.59}
$$

where $\alpha _ { 0 } , \alpha _ { 1 } , \ldots , \alpha _ { n }$ are real numbers. Linear predictors of the form (3.59) that minimize the mean square prediction error (3.58) are called best linear predictors (BLPs). As we shall see, linear prediction depends only on the second-order moments of the process, which are easy to estimate from the data. Much of the material in this section is enhanced by the theoretical material presented in Appendix B. For example, Theorem B.3 states that if the process is Gaussian, minimum mean square error predictors and best linear predictors are the same. The following property, which is based on the Projection Theorem, Theorem B.1 of Appendix B, is a key result.

# Property 3.3 Best Linear Prediction for Stationary Processes

Given data $x _ { 1 } , \ldots , x _ { n }$ , the best linear predictor, $\begin{array} { r } { x _ { n + m } ^ { n } = \alpha _ { 0 } + \sum _ { k = 1 } ^ { n } \alpha _ { k } x _ { k } } \end{array}$ of $x _ { n + m }$ , for $m \geq 1$ , is found by solving

$$
E \left[ \left(x _ {n + m} - x _ {n + m} ^ {n}\right) x _ {k} \right] = 0, \quad k = 0, 1, \dots , n, \tag {3.60}
$$

where $x _ { 0 } = 1$ , for $\alpha _ { 0 } , \alpha _ { 1 } , \ldots \alpha _ { n }$

The equations specified in (3.60) are called the prediction equations, and they are used to solve for the coefficients $\{ \alpha _ { 0 } , \alpha _ { 1 } , \ldots , \alpha _ { n } \}$ . If $E ( x _ { t } ) = \mu$ , the first equation ( $k = 0$ ) of (3.60) implies

$$
E (x _ {n + m} ^ {n}) = E (x _ {n + m}) = \mu .
$$

Thus, taking expectation in (3.59), we have

$$
\mu = \alpha_ {0} + \sum_ {k = 1} ^ {n} \alpha_ {k} \mu \qquad \text {o r} \qquad \alpha_ {0} = \mu \Big (1 - \sum_ {k = 1} ^ {n} \alpha_ {k} \Big).
$$

Hence, the form of the BLP is

$$
x _ {n + m} ^ {n} = \mu + \sum_ {k = 1} ^ {n} \alpha_ {k} (x _ {k} - \mu).
$$

Thus, until we discuss estimation, there is no loss of generality in considering the case that $\mu = 0$ , in which case, $\alpha _ { 0 } = 0$ .

First, consider one-step-ahead prediction. That is, given $\{ x _ { 1 } , \ldots , x _ { n } \}$ , we wish to forecast the value of the time series at the next time point, $x _ { n + 1 }$ . The BLP of $x _ { n + 1 }$ is of the form

$$
x _ {n + 1} ^ {n} = \phi_ {n 1} x _ {n} + \phi_ {n 2} x _ {n - 1} + \dots + \phi_ {n n} x _ {1}, \tag {3.61}
$$

where, for purposes that will become clear shortly, we have written $\alpha _ { k }$ in (3.59), as $\phi _ { n , n + 1 - k }$ in (3.61), for $k = 1 , \ldots , n$ . Using Property 3.3, the coefficients $\{ \phi _ { n 1 } , \phi _ { n 2 } , . . . , \phi _ { n n } \}$ satisfy

$$
E \left[ \left(x _ {n + 1} - \sum_ {j = 1} ^ {n} \phi_ {n j} x _ {n + 1 - j}\right) x _ {n + 1 - k} \right] = 0, \quad k = 1, \dots , n,
$$

or

$$
\sum_ {j = 1} ^ {n} \phi_ {n j} \gamma (k - j) = \gamma (k), \quad k = 1, \dots , n. \tag {3.62}
$$

The prediction equations (3.62) can be written in matrix notation as

$$
\Gamma_ {n} \boldsymbol {\phi} _ {n} = \boldsymbol {\gamma} _ {n}, \tag {3.63}
$$

where ${ \varGamma _ { n } } = \{ \gamma ( k - j ) \} _ { j , k = 1 } ^ { n }$ is an $n \times n$ matrix, $\phi _ { n } = ( \phi _ { n 1 } , \ldots , \phi _ { n n } ) ^ { \prime }$ is an $n \times 1$ vector, and $\gamma _ { n } = ( \gamma ( 1 ) , \dots , \gamma ( n ) ) ^ { \prime }$ is an $n \times 1$ vector.

The matrix $\varGamma _ { n }$ is nonnegative definite. If $\varGamma _ { n }$ is singular, there are many solutions to (3.63), but, by the Projection Theorem (Theorem B.1), $x _ { n + 1 } ^ { n }$ i s unique. If $\varGamma _ { n }$ is nonsingular, the elements of $\phi _ { n }$ are unique, and are given by

$$
\boldsymbol {\phi} _ {n} = \Gamma_ {n} ^ {- 1} \boldsymbol {\gamma} _ {n}. \tag {3.64}
$$

For ARMA models, the fact that $\sigma _ { w } ^ { 2 } > 0$ and $\gamma ( h ) \to 0$ as $h  \infty$ is enough to ensure that $\varGamma _ { n }$ is positive definite (Problem 3.12). It is sometimes convenient to write the one-step-ahead forecast in vector notation

$$
x _ {n + 1} ^ {n} = \phi_ {n} ^ {\prime} \boldsymbol {x}, \tag {3.65}
$$

where $\pmb { x } = ( x _ { n } , x _ { n - 1 } , \ldots , x _ { 1 } ) ^ { \prime }$ .

The mean square one-step-ahead prediction error is

$$
P _ {n + 1} ^ {n} = E \left(x _ {n + 1} - x _ {n + 1} ^ {n}\right) ^ {2} = \gamma (0) - \boldsymbol {\gamma} _ {n} ^ {\prime} \Gamma_ {n} ^ {- 1} \boldsymbol {\gamma} _ {n}. \tag {3.66}
$$

To verify (3.66) using (3.64) and (3.65),

$$
\begin{array}{l} E \left(x _ {n + 1} - x _ {n + 1} ^ {n}\right) ^ {2} = E \left(x _ {n + 1} - \boldsymbol {\phi} _ {n} ^ {\prime} \boldsymbol {x}\right) ^ {2} = E \left(x _ {n + 1} - \boldsymbol {\gamma} _ {n} ^ {\prime} \Gamma_ {n} ^ {- 1} \boldsymbol {x}\right) ^ {2} \\ = E \left(x _ {n + 1} ^ {2} - 2 \gamma_ {n} ^ {\prime} \Gamma_ {n} ^ {- 1} \boldsymbol {x} x _ {n + 1} + \gamma_ {n} ^ {\prime} \Gamma_ {n} ^ {- 1} \boldsymbol {x} \boldsymbol {x} ^ {\prime} \Gamma_ {n} ^ {- 1} \gamma_ {n}\right) \\ = \gamma (0) - 2 \gamma_ {n} ^ {\prime} \Gamma_ {n} ^ {- 1} \gamma_ {n} + \gamma_ {n} ^ {\prime} \Gamma_ {n} ^ {- 1} \Gamma_ {n} \Gamma_ {n} ^ {- 1} \gamma_ {n} \\ = \gamma (0) - \boldsymbol {\gamma} _ {n} ^ {\prime} \Gamma_ {n} ^ {- 1} \boldsymbol {\gamma} _ {n}. \\ \end{array}
$$

# Example 3.18 Prediction for an AR(2)

Suppose we have a causal AR(2) process $x _ { t } = \phi _ { 1 } x _ { t - 1 } + \phi _ { 2 } x _ { t - 2 } + w _ { t }$ , and one observation $x _ { 1 }$ . Then, using equation (3.64), the one-step-ahead prediction of $x _ { 2 }$ based on $x _ { 1 }$ is

$$
x _ {2} ^ {1} = \phi_ {1 1} x _ {1} = \frac {\gamma (1)}{\gamma (0)} x _ {1} = \rho (1) x _ {1}.
$$

Now, suppose we want the one-step-ahead prediction of $x _ { 3 }$ based on two observations $x _ { 1 }$ and $x _ { 2 }$ ; i.e., $x _ { 3 } ^ { 2 } = \phi _ { 2 1 } x _ { 2 } + \phi _ { 2 2 } x _ { 1 }$ . We could use (3.62)

$$
\phi_ {2 1} \gamma (0) + \phi_ {2 2} \gamma (1) = \gamma (1)
$$

$$
\phi_ {2 1} \gamma (1) + \phi_ {2 2} \gamma (0) = \gamma (2)
$$

to solve for $\phi _ { 2 1 }$ and $\phi _ { 2 2 }$ , or use the matrix form in (3.64) and solve

$$
\left( \begin{array}{c} \phi_ {2 1} \\ \phi_ {2 2} \end{array} \right) = \left( \begin{array}{c c} \gamma (0) & \gamma (1) \\ \gamma (1) & \gamma (0) \end{array} \right) ^ {- 1} \left( \begin{array}{c} \gamma (1) \\ \gamma (2) \end{array} \right),
$$

but, it should be apparent from the model that $x _ { 3 } ^ { 2 } = \phi _ { 1 } x _ { 2 } + \phi _ { 2 } x _ { 1 }$ . Because $\phi _ { 1 } x _ { 2 } + \phi _ { 2 } x _ { 1 }$ satisfies the prediction equations (3.60),

$$
E \left\{\left[ x _ {3} - \left(\phi_ {1} x _ {2} + \phi_ {2} x _ {1}\right) \right] x _ {1} \right\} = E \left(w _ {3} x _ {1}\right) = 0,
$$

$$
E \left\{\left[ x _ {3} - \left(\phi_ {1} x _ {2} + \phi_ {2} x _ {1}\right) \right] x _ {2} \right\} = E \left(w _ {3} x _ {2}\right) = 0,
$$

it follows that, indeed, $x _ { 3 } ^ { 2 } = \phi _ { 1 } x _ { 2 } + \phi _ { 2 } x _ { 1 }$ , and by the uniqueness of the coefficients in this case, that $\phi _ { 2 1 } = \phi _ { 1 }$ and $\phi _ { 2 2 } = \phi _ { 2 }$ . Continuing in this way, it is easy to verify that, for $n \geq 2$ ,

$$
x _ {n + 1} ^ {n} = \phi_ {1} x _ {n} + \phi_ {2} x _ {n - 1}.
$$

That is, $\phi _ { n 1 } = \phi _ { 1 } , \phi _ { n 2 } = \phi _ { 2 }$ , and $\phi _ { n j } = 0$ , for $j = 3 , 4 , \dotsc , n$

From Example 3.18, it should be clear (Problem 3.40) that, if the time series is a causal AR(p) process, then, for $n \geq p$ ,

$$
x _ {n + 1} ^ {n} = \phi_ {1} x _ {n} + \phi_ {2} x _ {n - 1} + \dots + \phi_ {p} x _ {n - p + 1}. \tag {3.67}
$$

For ARMA models in general, the prediction equations will not be as simple as the pure AR case. In addition, for $n$ large, the use of (3.64) is prohibitive because it requires the inversion of a large matrix. There are, however, iterative solutions that do not require any matrix inversion. In particular, we mention the recursive solution due to Levinson (1947) and Durbin (1960).

# Property 3.4 The Durbin–Levinson Algorithm

Equations (3.64) and (3.66) can be solved iteratively as follows:

$$
\phi_ {0 0} = 0, \quad P _ {1} ^ {0} = \gamma (0). \tag {3.68}
$$

For $n \geq 1$ ,

$$
\phi_ {n n} = \frac {\rho (n) - \sum_ {k = 1} ^ {n - 1} \phi_ {n - 1 , k} \rho (n - k)}{1 - \sum_ {k = 1} ^ {n - 1} \phi_ {n - 1 , k} \rho (k)}, \quad P _ {n + 1} ^ {n} = P _ {n} ^ {n - 1} \left(1 - \phi_ {n n} ^ {2}\right), \tag {3.69}
$$

where, for $n \geq 2$ ,

$$
\phi_ {n k} = \phi_ {n - 1, k} - \phi_ {n n} \phi_ {n - 1, n - k}, \quad k = 1, 2, \dots , n - 1. \tag {3.70}
$$

The proof of Property 3.4 is left as an exercise; see Problem 3.13.

# Example 3.19 Using the Durbin–Levinson Algorithm

To use the algorithm, start with $\phi _ { 0 0 } = 0$ , $P _ { 1 } ^ { 0 } = \gamma ( 0 )$ . Then, for $n = 1$

$$
\phi_ {1 1} = \rho (1), \quad P _ {2} ^ {1} = \gamma (0) [ 1 - \phi_ {1 1} ^ {2} ].
$$

For $n = 2$

$$
\phi_ {2 2} = \frac {\rho (2) - \phi_ {1 1} \rho (1)}{1 - \phi_ {1 1} \rho (1)}, \phi_ {2 1} = \phi_ {1 1} - \phi_ {2 2} \phi_ {1 1},
$$

$$
P _ {3} ^ {2} = P _ {2} ^ {1} [ 1 - \phi_ {2 2} ^ {2} ] = \gamma (0) [ 1 - \phi_ {1 1} ^ {2} ] [ 1 - \phi_ {2 2} ^ {2} ].
$$

For $n = 3$

$$
\phi_ {3 3} = \frac {\rho (3) - \phi_ {2 1} \rho (2) - \phi_ {2 2} \rho (1)}{1 - \phi_ {2 1} \rho (1) - \phi_ {2 2} \rho (2)},
$$

$$
\phi_ {3 2} = \phi_ {2 2} - \phi_ {3 3} \phi_ {2 1}, \phi_ {3 1} = \phi_ {2 1} - \phi_ {3 3} \phi_ {2 2},
$$

$$
P _ {4} ^ {3} = P _ {3} ^ {2} [ 1 - \phi_ {3 3} ^ {2} ] = \gamma (0) [ 1 - \phi_ {1 1} ^ {2} ] [ 1 - \phi_ {2 2} ^ {2} ] [ 1 - \phi_ {3 3} ^ {2} ],
$$

and so on. Note that, in general, the standard error of the one-step-ahead forecast is the square root of

$$
P _ {n + 1} ^ {n} = \gamma (0) \prod_ {j = 1} ^ {n} [ 1 - \phi_ {j j} ^ {2} ]. \tag {3.71}
$$

An important consequence of the Durbin–Levinson algorithm is (see Problem 3.13) as follows.

# Property 3.5 Iterative Solution for the PACF

The PACF of a stationary process $x _ { t }$ , can be obtained iteratively via (3.69) as $\phi _ { n n }$ , for $n = 1 , 2 , \ldots$ .

Using Property 3.5 and putting $n = p$ in (3.61) and (3.67), it follows that for an AR(p) model,

$$
\begin{array}{l} x _ {p + 1} ^ {p} = \phi_ {p 1} x _ {p} + \phi_ {p 2} x _ {p - 1} + \dots + \phi_ {p p} x _ {1} \tag {3.72} \\ = \phi_ {1} x _ {p} + \phi_ {2} x _ {p - 1} + \dots + \phi_ {p} x _ {1}. \\ \end{array}
$$

Result (3.72) shows that for an AR(p) model, the partial autocorrelation coefficient at lag $p$ , $\phi _ { p p }$ , is also the last coefficient in the model, $\phi _ { p }$ , as was claimed in Example 3.15.

# Example 3.20 The PACF of an AR(2)

We will use the results of Example 3.19 and Property 3.5 to calculate the first three values, $\phi _ { 1 1 }$ , $\phi _ { 2 2 }$ , $\phi _ { 3 3 }$ , of the PACF. Recall from Example 3.9 that $\rho ( h ) - \phi _ { 1 } \rho ( h - 1 ) - \phi _ { 2 } \rho ( h - 2 ) = 0$ for $h \geq 1$ . When $h = 1 , 2 , 3$ , we have $\rho ( 1 ) = \phi _ { 1 } / ( 1 - \phi _ { 2 } ) , \ \rho ( 2 ) = \phi _ { 1 } \rho ( 1 ) + \phi _ { 2 }$ 2, $\rho ( 3 ) - \phi _ { 1 } \rho ( 2 ) - \phi _ { 2 } \rho ( 1 ) = 0$ . Thus,

$$
\begin{array}{l} \phi_ {1 1} = \rho (1) = \frac {\phi_ {1}}{1 - \phi_ {2}} \\ \phi_ {2 2} = \frac {\rho (2) - \rho (1) ^ {2}}{1 - \rho (1) ^ {2}} = \frac {\left[ \phi_ {1} \left(\frac {\phi_ {1}}{1 - \phi_ {2}}\right) + \phi_ {2} \right] - \left(\frac {\phi_ {1}}{1 - \phi_ {2}}\right) ^ {2}}{1 - \left(\frac {\phi_ {1}}{1 - \phi_ {2}}\right) ^ {2}} = \phi_ {2} \\ \phi_ {2 1} = \rho (1) [ 1 - \phi_ {2} ] = \phi_ {1} \\ \phi_ {3 3} = \frac {\rho (3) - \phi_ {1} \rho (2) - \phi_ {2} \rho (1)}{1 - \phi_ {1} \rho (1) - \phi_ {2} \rho (2)} = 0. \\ \end{array}
$$

Notice that, as shown in (3.72), $\phi _ { 2 2 } = \phi _ { 2 }$ for an AR(2) model.

So far, we have concentrated on one-step-ahead prediction, but Property 3.3 allows us to calculate the BLP of $x _ { n + m }$ for any $m \geq 1$ . Given data, $\{ x _ { 1 } , \ldots , x _ { n } \}$ , the $m$ -step-ahead predictor is

$$
x _ {n + m} ^ {n} = \phi_ {n 1} ^ {(m)} x _ {n} + \phi_ {n 2} ^ {(m)} x _ {n - 1} + \dots + \phi_ {n n} ^ {(m)} x _ {1}, \tag {3.73}
$$

where $\{ \phi _ { n 1 } ^ { ( m ) } , \phi _ { n 2 } ^ { ( m ) } , . . . , \phi _ { n n } ^ { ( m ) } \}$ φnn satisfy the prediction equations,

$$
\sum_ {j = 1} ^ {n} \phi_ {n j} ^ {(m)} E (x _ {n + 1 - j} x _ {n + 1 - k}) = E (x _ {n + m} x _ {n + 1 - k}), \quad k = 1, \dots , n,
$$

or

$$
\sum_ {j = 1} ^ {n} \phi_ {n j} ^ {(m)} \gamma (k - j) = \gamma (m + k - 1), \quad k = 1, \dots , n. \tag {3.74}
$$

The prediction equations can again be written in matrix notation as

$$
\Gamma_ {n} \phi_ {n} ^ {(m)} = \gamma_ {n} ^ {(m)}, \tag {3.75}
$$

where $\gamma _ { n } ^ { ( m ) } = ( \gamma ( m ) , \ldots , \gamma ( m + n - 1 ) ) ^ { \prime } , \mathrm { a n d } \phi _ { n } ^ { ( m ) } = ( \phi _ { n 1 } ^ { ( m ) } , \ldots , \phi _ { n n } ^ { ( m ) } ) ^ { \prime }$ $\gamma _ { n } ^ { ( m ) } = ( \gamma ( m ) , \ldots , \gamma ( m + n - 1 ) ) ^ { \prime }$ $\phi _ { n } ^ { ( m ) } = ( \phi _ { n 1 } ^ { ( m ) } , \dots , \phi _ { n n } ^ { ( m ) } ) ^ { \prime }$ are $n \times 1$ vectors.

The mean square m-step-ahead prediction error is

$$
P _ {n + m} ^ {n} = E \left(x _ {n + m} - x _ {n + m} ^ {n}\right) ^ {2} = \gamma (0) - \boldsymbol {\gamma} _ {n} ^ {(m) ^ {\prime}} \Gamma_ {n} ^ {- 1} \boldsymbol {\gamma} _ {n} ^ {(m)}. \tag {3.76}
$$

Another useful algorithm for calculating forecasts was given by Brockwell and Davis (1991, Chapter 5). This algorithm follows directly from applying the projection theorem (Theorem B.1) to the innovations, $x _ { t } - x _ { t } ^ { t - 1 }$ , for $t =$ $1 , \ldots , n$ , using the fact that the innovations $x _ { t } \ - \ x _ { t } ^ { t - 1 }$ and $x _ { s } \mathrm { ~ - ~ } x _ { s } ^ { s - 1 }$ ar e uncorrelated for $s \neq t$ (see Problem 3.41). We present the case in which $x _ { t }$ is a mean-zero stationary time series.

# Property 3.6 The Innovations Algorithm

The one-step-ahead predictors, $\boldsymbol { x } _ { t + 1 } ^ { t }$ , and their mean-squared errors, $P _ { t + 1 } ^ { t }$ can be calculated iteratively as

$$
x _ {1} ^ {0} = 0, \quad P _ {1} ^ {0} = \gamma (0)
$$

$$
x _ {t + 1} ^ {t} = \sum_ {j = 1} ^ {t} \theta_ {t j} \left(x _ {t + 1 - j} - x _ {t + 1 - j} ^ {t - j}\right), \quad t = 1, 2, \dots \tag {3.77}
$$

$$
P _ {t + 1} ^ {t} = \gamma (0) - \sum_ {j = 0} ^ {t - 1} \theta_ {t, t - j} ^ {2} P _ {j + 1} ^ {j} \quad t = 1, 2, \dots , \tag {3.78}
$$

where, for $j = 0 , 1 , \ldots , t - 1$

$$
\theta_ {t, t - j} = \left(\gamma (t - j) - \sum_ {k = 0} ^ {j - 1} \theta_ {j, j - k} \theta_ {t, t - k} P _ {k + 1} ^ {k}\right) / P _ {j + 1} ^ {j}. \tag {3.79}
$$

cessively for Given data $t = 1$ $x _ { 1 } , \ldots , x _ { n }$ $t = 2$ , the innovations algorithm can be calculated suc- and so on, in which case the calculation of $x _ { n + 1 } ^ { n }$ and $P _ { n + 1 } ^ { n }$ is made at the final step $t = n$ . The $m$ -step-ahead predictor and its mean-square error based on the innovations algorithm (Problem 3.41) are given by

$$
x _ {n + m} ^ {n} = \sum_ {j = m} ^ {n + m - 1} \theta_ {n + m - 1, j} \left(x _ {n + m - j} - x _ {n + m - j} ^ {n + m - j - 1}\right), \tag {3.80}
$$

$$
P _ {n + m} ^ {n} = \gamma (0) - \sum_ {j = m} ^ {n + m - 1} \theta_ {n + m - 1, j} ^ {2} P _ {n + m - j} ^ {n + m - j - 1}, \tag {3.81}
$$

where the $\theta _ { n + m - 1 , j }$ are obtained by continued iteration of (3.79).

# Example 3.21 Prediction for an MA(1)

The innovations algorithm lends itself well to prediction for moving average processes. Consider an MA(1) model, $x _ { t } = w _ { t } + \theta w _ { t - 1 }$ . Recall that $\gamma ( 0 ) =$ $( 1 + \theta ^ { 2 } ) \sigma _ { w } ^ { 2 }$ , $\gamma ( 1 ) = \theta \sigma _ { w } ^ { 2 }$ , and $\gamma ( h ) = 0$ for $h > 1$ . Then, using Property 3.6, we have

$$
\begin{array}{l} \theta_ {n 1} = \theta \sigma_ {w} ^ {2} / P _ {n} ^ {n - 1} \\ \theta_ {n j} = 0, \quad j = 2, \ldots , n \\ P _ {1} ^ {0} = \left(1 + \theta^ {2}\right) \sigma_ {w} ^ {2} \\ P _ {n + 1} ^ {n} = \left(1 + \theta^ {2} - \theta \theta_ {n 1}\right) \sigma_ {w} ^ {2}. \\ \end{array}
$$

Finally, from (3.77), the one-step-ahead predictor is

$$
x _ {n + 1} ^ {n} = \theta \left(x _ {n} - x _ {n} ^ {n - 1}\right) \sigma_ {w} ^ {2} / P _ {n} ^ {n - 1}.
$$

# Forecasting ARMA Processes

The general prediction equations (3.60) provide little insight into forecasting for ARMA models in general. There are a number of different ways to express these forecasts, and each aids in understanding the special structure of ARMA prediction. Throughout, we assume $x _ { t }$ is a causal and invertible $\mathrm { A R M A } ( p , q )$ $( p , q )$ process, $\phi ( B ) x _ { t } = \theta ( B ) w _ { t }$ , where $w _ { t } \sim$ iid $\mathrm { N } ( 0 , \sigma _ { w } ^ { 2 } )$ . In the non-zero mean case, $E ( x _ { t } ) = \mu _ { x }$ , simply replace $x _ { t }$ with ${ \boldsymbol { x } } _ { t } ~ - ~ { \boldsymbol { \mu } } _ { \boldsymbol { x } }$ in the model. First, we consider two types of forecasts. We write $x _ { n + m } ^ { \pi }$ to mean the minimum mean square error predictor of $x _ { n + m }$ based on the data $\{ x _ { n } , \ldots , x _ { 1 } \}$ , that is,

$$
x _ {n + m} ^ {n} = E (x _ {n + m} \mid x _ {n}, \dots , x _ {1}).
$$

For ARMA models, it is easier to calculate the predictor of $x _ { n + m }$ , assuming we have the complete history of the process $\{ x _ { n } , x _ { n - 1 } , \ldots , x _ { 1 } , x _ { 0 } , x _ { - 1 } , \ldots \}$ . We will denote the predictor of $x _ { n + m }$ based on the infinite past as

$$
\widetilde {x} _ {n + m} = E \left(x _ {n + m} \mid x _ {n}, x _ {n - 1}, \dots , x _ {1}, x _ {0}, x _ {- 1}, \dots\right).
$$

nlarge samples, In general, $x _ { n + m } ^ { n }$ $\widetilde { x } _ { n + m }$ and e will provide a good approximation to $\widetilde { x } _ { n + m }$ are not the same, but the idea here is that, for $x _ { n + m } ^ { n }$ .

Now, write $x _ { n + m }$ in its causal and invertible forms:

$$
x _ {n + m} = \sum_ {j = 0} ^ {\infty} \psi_ {j} w _ {n + m - j}, \quad \psi_ {0} = 1 \tag {3.82}
$$

$$
w _ {n + m} = \sum_ {j = 0} ^ {\infty} \pi_ {j} x _ {n + m - j}, \quad \pi_ {0} = 1. \tag {3.83}
$$

Then, taking conditional expectations in (3.82), we have

$$
\widetilde {x} _ {n + m} = \sum_ {j = 0} ^ {\infty} \psi_ {j} \widetilde {w} _ {n + m - j} = \sum_ {j = m} ^ {\infty} \psi_ {j} w _ {n + m - j}, \tag {3.84}
$$

because, by causality and invertibility,

$$
\widetilde {w} _ {t} = E (w _ {t} \mid x _ {n}, x _ {n - 1}, \ldots , x _ {0}, x _ {- 1}, \ldots) = \left\{ \begin{array}{l l} 0 & t > n \\ w _ {t} & t \leq n. \end{array} \right.
$$

Similarly, taking conditional expectations in (3.83), we have

$$
0 = \widetilde {x} _ {n + m} + \sum_ {j = 1} ^ {\infty} \pi_ {j} \widetilde {x} _ {n + m - j},
$$

or

$$
\widetilde {x} _ {n + m} = - \sum_ {j = 1} ^ {m - 1} \pi_ {j} \widetilde {x} _ {n + m - j} - \sum_ {j = m} ^ {\infty} \pi_ {j} x _ {n + m - j}, \tag {3.85}
$$

using the fact $E ( x _ { t } \mid x _ { n } , x _ { n - 1 } , \ldots , x _ { 0 } , x _ { - 1 } , \ldots ) = x _ { t }$ , for $t \leq n$ . Prediction is accomplished recursively using (3.85), starting with the one-step-ahead predictor, $m = 1$ , and then continuing for $m = 2 , 3 , \ldots$ . Using (3.84), we can write

$$
x _ {n + m} - \widetilde {x} _ {n + m} = \sum_ {j = 0} ^ {m - 1} \psi_ {j} w _ {n + m - j},
$$

so the mean-square prediction error can be written as

$$
P _ {n + m} ^ {n} = E \left(x _ {n + m} - \widetilde {x} _ {n + m}\right) ^ {2} = \sigma_ {w} ^ {2} \sum_ {j = 0} ^ {m - 1} \psi_ {j} ^ {2}. \tag {3.86}
$$

Also, we note, for a fixed sample size, $n$ , the prediction errors are correlated. That is, for $k \geq 1$ ,

$$
E \left\{\left(x _ {n + m} - \widetilde {x} _ {n + m}\right) \left(x _ {n + m + k} - \widetilde {x} _ {n + m + k}\right) \right\} = \sigma_ {w} ^ {2} \sum_ {j = 0} ^ {m - 1} \psi_ {j} \psi_ {j + k}. \tag {3.87}
$$

# Example 3.22 Long-Range Forecasts

Consider forecasting an ARMA process with mean $\mu _ { x }$ . Replacing $x _ { n + m }$ with $x _ { n + m } - \mu _ { x }$ in (3.82), and taking conditional expectation as is in (3.84), we deduce that the $m$ -step-ahead forecast can be written as

$$
\widetilde {x} _ {n + m} = \mu_ {x} + \sum_ {j = m} ^ {\infty} \psi_ {j} w _ {n + m - j}. \tag {3.88}
$$

Noting that the $\psi$ -weights dampen to zero exponentially fast, it is clear that

$$
\widetilde {x} _ {n + m} \rightarrow \mu_ {x} \tag {3.89}
$$

exponentially fast (in the mean square sense) as $m  \infty$ . Moreover, by (3.86), the mean square prediction error

$$
P _ {n + m} ^ {n} \rightarrow \sigma_ {w} ^ {2} \sum_ {j = 0} ^ {\infty} \psi_ {j} ^ {2} = \gamma_ {x} (0) = \sigma_ {x} ^ {2}, \tag {3.90}
$$

exponentially fast as $m \to \infty$ ; recall (3.45).

It should be clear from (3.89) and (3.90) that ARMA forecasts quickly settle to the mean with a constant prediction error as the forecast horizon, $m$ , grows. This effect can be seen in Figure 3.6 on page 119 where the Recruitment series is forecast for 24 months; see Example 3.24.

When $n$ is small, the general prediction equations (3.60) can be used easily. When $n$ is large, we would use (3.85) by truncating, because we do not observe $x _ { 0 } , x _ { - 1 } , x _ { - 2 } , . . .$ , and only the data $x _ { 1 } , x _ { 2 } , \ldots , x _ { n }$ are available. In this case, we can truncate (3.85) by setting $\sum _ { j = n + m } ^ { \infty } \pi _ { j } x _ { n + m - j } \ = \ 0$ . The truncated predictor is then written as

$$
\widetilde {x} _ {n + m} ^ {n} = - \sum_ {j = 1} ^ {m - 1} \pi_ {j} \widetilde {x} _ {n + m - j} ^ {n} - \sum_ {j = m} ^ {n + m - 1} \pi_ {j} x _ {n + m - j}, \tag {3.91}
$$

which is also calculated recursively, $m = 1 , 2 , \ldots$ The mean square prediction error, in this case, is approximated using (3.86).

For $\operatorname { A R } ( p )$ models, and when $n \ > \ p$ , equation (3.67) yields the exact for predictor, $x _ { n + m } ^ { \pi }$ , of $x _ { n + m }$ , and there is no need for approximations. That is, . Also, in this case, the one-step-ahead en+m prediction error is $n \ > \ p$ $\tilde { x } _ { n + m } ^ { n } = \tilde { x } _ { n + m } = x _ { n + m } ^ { n }$ $E ( x _ { n + 1 } - x _ { n + 1 } ^ { n } ) ^ { 2 } = \sigma _ { w } ^ { 2 }$ . For pure $\operatorname { M A } ( q )$ or $\mathrm { A R M A } ( p , q )$ models, truncated prediction has a fairly nice form.

# Property 3.7 Truncated Prediction for ARMA

For $A R M A ( p , q )$ models, the truncated predictors for $m = 1 , 2 , \ldots$ , are

$$
\widetilde {x} _ {n + m} ^ {n} = \phi_ {1} \widetilde {x} _ {n + m - 1} ^ {n} + \dots + \phi_ {p} \widetilde {x} _ {n + m - p} ^ {n} + \theta_ {1} \widetilde {w} _ {n + m - 1} ^ {n} + \dots + \theta_ {q} \widetilde {w} _ {n + m - q} ^ {n}, \tag {3.92}
$$

where $\widetilde { x } _ { t } ^ { n } = x _ { t }$ for $1 \leq t \leq n$ and $\partial x _ { t } ^ { n } = 0$ for $t \leq 0$ . The truncated prediction errors are given by: $w _ { t } ^ { n } = 0$ for $t \leq 0$ or $t > n$ , and

$$
\widetilde {w} _ {t} ^ {n} = \phi (B) \widetilde {x} _ {t} ^ {n} - \theta_ {1} \widetilde {w} _ {t - 1} ^ {n} - \dots - \theta_ {q} \widetilde {w} _ {t - q} ^ {n}
$$

for $1 \leq t \leq n$

# Example 3.23 Forecasting an $\mathbf { A R M A } ( 1 , 1 )$ $( 1 , 1 )$ Series

Given data $x _ { 1 } , \ldots , x _ { n }$ , for forecasting purposes, write the model as

$$
x _ {n + 1} = \phi x _ {n} + w _ {n + 1} + \theta w _ {n}.
$$

Then, based on (3.92), the one-step-ahead truncated forecast is

$$
\widetilde {x} _ {n + 1} ^ {n} = \phi x _ {n} + 0 + \theta \widetilde {w} _ {n} ^ {n}.
$$

For $m \geq 2$ , we have

$$
\widetilde {x} _ {n + m} ^ {n} = \phi \widetilde {x} _ {n + m - 1} ^ {n},
$$

which can be calculated recursively, $m = 2 , 3 , \ldots$

To calculate $\widetilde { w } _ { n } ^ { n }$ , which is needed to initialize the successive forecasts, the model can be written as $w _ { t } = x _ { t } - \phi x _ { t - 1 } - \theta w _ { t - 1 }$ for $t = 1 , \ldots , n$ . For truncated forecasting using (3.92), put $\widetilde { w } _ { 0 } ^ { n } = 0$ , $x _ { 0 } = 0$ , and then iterate the errors forward in time

$$
\widetilde {w} _ {t} ^ {n} = x _ {t} - \phi x _ {t - 1} - \theta \widetilde {w} _ {t - 1} ^ {n}, \quad t = 1, \dots , n.
$$

The approximate forecast variance is computed from (3.86) using the $\psi$ - weights determined as in Example 3.11. In particular, the $\psi$ -weights satisfy $\psi _ { j } = ( \phi + \theta ) \phi ^ { j - 1 }$ , for $j \geq 1$ . This result gives

$$
P _ {n + m} ^ {n} = \sigma_ {w} ^ {2} \bigg [ 1 + (\phi + \theta) ^ {2} \sum_ {j = 1} ^ {m - 1} \phi^ {2 (j - 1)} \bigg ] = \sigma_ {w} ^ {2} \bigg [ 1 + \frac {(\phi + \theta) ^ {2} (1 - \phi^ {2 (m - 1)})}{(1 - \phi^ {2})} \bigg ].
$$

To assess the precision of the forecasts, prediction intervals are typically calculated along with the forecasts. In general, $( 1 - \alpha )$ prediction intervals are of the form

$$
x _ {n + m} ^ {n} \pm c _ {\frac {\alpha}{2}} \sqrt {P _ {n + m} ^ {n}}, \tag {3.93}
$$

where $c _ { \alpha / 2 }$ is chosen to get the desired degree of confidence. For example, if the process is Gaussian, then choosing $c _ { \alpha / 2 } = 2$ will yield an approximate 95% prediction interval for $x _ { n + m }$ . If we are interested in establishing prediction intervals over more than one time period, then $c _ { \alpha / 2 }$ should be adjusted appropriately, for example, by using Bonferroni’s inequality [see (4.55) in Chapter 4 or Johnson and Wichern, 1992, Chapter 5].

# Example 3.24 Forecasting the Recruitment Series

Using the parameter estimates as the actual parameter values, Figure 3.6 shows the result of forecasting the Recruitment series given in Example 3.17 over a 24-month horizon, $m = 1 , 2 , \ldots , 2 4$ . The actual forecasts are calculated as

$$
x _ {n + m} ^ {n} = 6. 7 4 + 1. 3 5 x _ {n + m - 1} ^ {n} -. 4 6 x _ {n + m - 2} ^ {n}
$$

for $n = 4 5 3$ and $m = 1 , 2 , \ldots , 1 2$ . Recall that $x _ { t } ^ { s } = x _ { t }$ when $t \le s$ . The forecasts errors $P _ { n + m } ^ { n }$ t   are calculated using (3.86). Recall that $\widehat { \sigma } _ { w } ^ { 2 } = 8 9 . 7 2$

![](images/d4209c0f7913a90ca56c31a1550e92d3b0fd547befc7638b1cd5d53df7eaf499.jpg)  
Fig. 3.6. Twenty-four month forecasts for the Recruitment series. The actual data shown are from about January 1980 to September 1987, and then the forecasts plus and minus one standard error are displayed.

and using (3.40) from Example 3.11, we have $\psi _ { j } = 1 . 3 5 \psi _ { j - 1 } - . 4 6 \psi _ { j - 2 }$ for $j \geq 2$ , where $\psi _ { 0 } = 1$ and $\psi _ { 1 } = 1 . 3 5$ . Thus, for $n = 4 5 3$ ,

$$
\begin{array}{l} P _ {n + 1} ^ {n} = 8 9. 7 2, \\ P _ {n + 2} ^ {n} = 8 9. 7 2 \left(1 + 1. 3 5 ^ {2}\right), \\ P _ {n + 3} ^ {n} = 8 9. 7 2 \left(1 + 1. 3 5 ^ {2} + \left[ 1. 3 5 ^ {2} - . 4 6 \right] ^ {2}\right), \\ \end{array}
$$

and so on.

Note how the forecast levels off quickly and the prediction intervals are wide, even though in tstandard error; that is, $x _ { n + m } ^ { n } \pm \sqrt { P _ { n + m } ^ { n } }$ ecast limits are only based on one.

To reproduce the analysis and Figure 3.6, use the following commands:

1 regr $=$ ar.ols(rec, order=2, demean=FALSE, intercept=TRUE)   
2 fore $=$ predict(regr, n.ahead=24)   
3 ts.plot(rec, fore$pred, col=1:2, xlim=c(1980,1990), ylab="Recruitment")   
4 lines(fore$pred, type="p", col=2)   
5 lines(fore$pred+fore$se, lty="dashed", col=4)   
6 lines(fore$pred-fore$se, lty="dashed", col=4)

We complete this section with a brief discussion of backcasting. In backcasting, we want to predict $x _ { 1 - m }$ , for $m \ = \ 1 , 2 , . . .$ , based on the data $\{ x _ { 1 } , \ldots , x _ { n } \}$ . Write the backcast as

$$
x _ {1 - m} ^ {n} = \sum_ {j = 1} ^ {n} \alpha_ {j} x _ {j}. \tag {3.94}
$$

Analogous to (3.74), the prediction equations (assuming $\mu _ { x } = 0$ ) are

$$
\sum_ {j = 1} ^ {n} \alpha_ {j} E \left(x _ {j} x _ {k}\right) = E \left(x _ {1 - m} x _ {k}\right), \quad k = 1, \dots , n, \tag {3.95}
$$

or

$$
\sum_ {j = 1} ^ {n} \alpha_ {j} \gamma (k - j) = \gamma (m + k - 1), \quad k = 1, \dots , n. \tag {3.96}
$$

These equations are precisely the prediction equations for forward prediction. That is, $\alpha _ { j } \equiv \phi _ { n j } ^ { ( m ) }$ for $j = 1 , \dotsc , n$ , where the $\phi _ { n j } ^ { ( m ) }$ φnj are given by (3.75). Finally, the backcasts are given by

$$
x _ {1 - m} ^ {n} = \phi_ {n 1} ^ {(m)} x _ {1} + \dots + \phi_ {n n} ^ {(m)} x _ {n}, \quad m = 1, 2, \dots . \tag {3.97}
$$

# Example 3.25 Backcasting an $\mathbf { A R M A } ( 1 , 1 )$ $( 1 , 1 )$

Consider an $\mathrm { A R M A } ( 1 , 1 )$ process, $x _ { t } = \phi x _ { t - 1 } + \theta w _ { t - 1 } + w _ { t }$ ; we will call this the forward model. We have just seen that best linear prediction backward in time is the same as best linear prediction forward in time for stationary models. Because we are assuming ARMA models are Gaussian, we also have that minimum mean square error prediction backward in time is the same as forward in time for ARMA models.4 Thus, the process can equivalently be generated by the backward model,

$$
x _ {t} = \phi x _ {t + 1} + \theta v _ {t + 1} + v _ {t},
$$

where $\{ v _ { t } \}$ is a Gaussian white noise process with variance $\sigma _ { w } ^ { 2 }$ . We may write $\begin{array} { r } { x _ { t } = \sum _ { j = 0 } ^ { \infty } \psi _ { j } v _ { t + j } } \end{array}$ , where $\psi _ { 0 } = 1$ ; this means that $x _ { t }$ is uncorrelated with $\{ v _ { t - 1 } , v _ { t - 2 } , . . . \}$ , in analogy to the forward model.

Given data $\{ x _ { 1 } , . . . . , x _ { n } \}$ , truncate $v _ { n } ^ { n } = E ( v _ { n } | x _ { 1 } , . . . . . , x _ { n } )$ to zero and then iterate backward. That is, put $\widetilde { v } _ { n } ^ { n } = 0$ , as an initial approximation, and then generate the errors backward

$$
\widetilde {v} _ {t} ^ {n} = x _ {t} - \phi x _ {t + 1} - \theta \widetilde {v} _ {t + 1} ^ {n}, \quad t = (n - 1), (n - 2), \dots , 1.
$$

Then,

$$
\widetilde {x} _ {0} ^ {n} = \phi x _ {1} + \theta \widetilde {v} _ {1} ^ {n} + \widetilde {v} _ {0} ^ {n} = \phi x _ {1} + \theta \widetilde {v} _ {1} ^ {n},
$$

because $\tilde { v } _ { t } ^ { n } = 0$ for $t \leq 0$ . Continuing, the general truncated backcasts are given by

$$
\widetilde {x} _ {1 - m} ^ {n} = \phi \widetilde {x} _ {2 - m} ^ {n}, \quad m = 2, 3, \dots .
$$

# 3.6 Estimation

Throughout this section, we assume we have $n$ observations, $x _ { 1 } , \ldots , x _ { n }$ , from a causal and invertible Gaussian $\mathrm { A R M A } ( p , q )$ $( p , q )$ process in which, initially, the order parameters, $p$ and $q$ , are known. Our goal is to estimate the parameters, $\phi _ { 1 } , . . . , \phi _ { p }$ , $\theta _ { 1 } , \ldots , \theta _ { q }$ , and $\sigma _ { w } ^ { 2 }$ . We will discuss the problem of determining $p$ and $q$ later in this section.

We begin with method of moments estimators. The idea behind these estimators is that of equating population moments to sample moments and then solving for the parameters in terms of the sample moments. We immediately see that, if $E ( x _ { t } ) = \mu$ , then the method of moments estimator of $\mu$ is the sample average, $x$ . Thus, while discussing method of moments, we will assume $\mu = 0$ . Although the method of moments can produce good estimators, they can sometimes lead to suboptimal estimators. We first consider the case in which the method leads to optimal (efficient) estimators, that is, $\operatorname { A R } ( p )$ models.

When the process is AR(p),

$$
x _ {t} = \phi_ {1} x _ {t - 1} + \dots + \phi_ {p} x _ {t - p} + w _ {t},
$$

the first $p + 1$ equations of (3.47) and (3.48) lead to the following:

Definition 3.10 The Yule–Walker equations are given by

$$
\begin{array}{l} \gamma (h) = \phi_ {1} \gamma (h - 1) + \dots + \phi_ {p} \gamma (h - p), \quad h = 1, 2, \dots , p, (3.98) \\ \sigma_ {w} ^ {2} = \gamma (0) - \phi_ {1} \gamma (1) - \dots - \phi_ {p} \gamma (p). (3.99) \\ \end{array}
$$

In matrix notation, the Yule–Walker equations are

$$
\Gamma_ {p} \boldsymbol {\phi} = \boldsymbol {\gamma} _ {p}, \quad \sigma_ {w} ^ {2} = \gamma (0) - \boldsymbol {\phi} ^ {\prime} \boldsymbol {\gamma} _ {p}, \tag {3.100}
$$

where ${ \varGamma _ { p } } = \{ \gamma ( { k - j } ) \} _ { j , k = 1 } ^ { p }$ is a $p \times p$ matrix, $\pmb { \phi } = ( \phi _ { 1 } , \ldots , \phi _ { p } ) ^ { \prime }$ is a $p \times 1$ vector, and $\gamma _ { p } = ( \gamma ( 1 ) , \ldots , \gamma ( p ) ) ^ { \prime }$ is a $p \times 1$ vector. Using the method of moments, we replace $\gamma ( h )$ in (3.100) by $\widehat { \gamma } ( h )$ [see equation (1.34)] and solve

$$
\widehat {\boldsymbol {\phi}} = \widehat {\Gamma} _ {p} ^ {- 1} \widehat {\gamma} _ {p}, \quad \widehat {\sigma} _ {w} ^ {2} = \widehat {\gamma} (0) - \widehat {\gamma} _ {p} ^ {\prime} \widehat {\Gamma} _ {p} ^ {- 1} \widehat {\gamma} _ {p}. \tag {3.101}
$$

These estimators are typically called the Yule–Walker estimators. For calculation purposes, it is sometimes more convenient to work with the sample ACF. By factoring $\widehat { \gamma } ( 0 )$ in (3.101), we can write the Yule–Walker estimates as

$$
\widehat {\boldsymbol {\phi}} = \widehat {\boldsymbol {R}} _ {p} ^ {- 1} \widehat {\boldsymbol {\rho}} _ {p}, \quad \widehat {\sigma} _ {w} ^ {2} = \widehat {\gamma} (0) \left[ 1 - \widehat {\boldsymbol {\rho}} _ {p} ^ {\prime} \widehat {\boldsymbol {R}} _ {p} ^ {- 1} \widehat {\boldsymbol {\rho}} _ {p} \right], \tag {3.102}
$$

where $\widehat { R } _ { p } = \{ \widehat { \rho } ( k - j ) \} _ { j , k = 1 } ^ { p }$ is a $p \times p$ matrix and $\widehat { \pmb { \rho } } _ { p } = ( \widehat { \rho } ( 1 ) , \dots , \widehat { \rho } ( p ) ) ^ { \prime }$ is a $p \times 1$ vector.

For $\operatorname { A R } ( p )$ models, if the sample size is large, the Yule–Walker estimators are approximately normally distributed, and $\widehat { \sigma } _ { w } ^ { 2 }$ is close to the true value of $\sigma _ { w } ^ { 2 }$ bw . We state these results in Property 3.8; for details, see Appendix B, §B.3.

# Property 3.8 Large Sample Results for Yule–Walker Estimators

The asymptotic ( $n  \infty$ ) behavior of the Yule–Walker estimators in the case of causal $A R ( p )$ processes is as follows:

$$
\sqrt {n} (\widehat {\boldsymbol {\phi}} - \boldsymbol {\phi}) \stackrel {{d}} {{\rightarrow}} N \left(\mathbf {0}, \sigma_ {w} ^ {2} \Gamma_ {p} ^ {- 1}\right), \quad \widehat {\sigma} _ {w} ^ {2} \stackrel {{p}} {{\rightarrow}} \sigma_ {w} ^ {2}. \tag {3.103}
$$

The Durbin–Levinson algorithm, (3.68)-(3.70), can be used to calculate $\hat { \phi }$ without inverting $\widehat { \cal T } _ { p }$ or $\widehat { R } _ { p }$ , by replacing $\gamma ( h )$ by $\widehat { \gamma } ( h )$ in the algorithm. In running the algorithm, we will iteratively calculate the $h \times 1$ vector, $\widehat { \phi } _ { h } =$ $( \widehat { \phi } _ { h 1 } , \ldots , \widehat { \phi } _ { h h } ) ^ { \prime }$ , for $h = 1 , 2 , \ldots$ . Thus, in addition to obtaining the desired forecasts, the Durbin–Levinson algorithm yields $\widehat { \phi } _ { h h }$ , the sample PACF. Using (3.103), we can show the following property.

# Property 3.9 Large Sample Distribution of the PACF

For a causal AR(p) process, asymptotically ( $n \to \infty$ ),

$$
\sqrt {n} \widehat {\phi} _ {h h} \stackrel {{d}} {{\to}} N (0, 1), \quad \text {f o r} \quad h > p. \tag {3.104}
$$

# Example 3.26 Yule–Walker Estimation for an AR(2) Process

The data shown in Figure 3.3 were $n = 1 4 4$ simulated observations from the AR(2) model

$$
x _ {t} = 1. 5 x _ {t - 1} - . 7 5 x _ {t - 2} + w _ {t},
$$

where $w _ { t } \sim$ iid $\mathrm { { N } } ( 0 , 1 )$ . For these data, ${ \widehat \gamma } ( 0 ) ~ = ~ 8 . 9 0 3$ , $\widehat { \rho } ( 1 ) \ : = \ : . 8 4 9$ , and $\widehat { \rho } ( 2 ) = . 5 1 9$ . Thus,

$$
\widehat {\boldsymbol {\phi}} = \left( \begin{array}{c} \widehat {\phi} _ {1} \\ \widehat {\phi} _ {2} \end{array} \right) = \left[ \begin{array}{c c} 1 & . 8 4 9 \\ . 8 4 9 & 1 \end{array} \right] ^ {- 1} \left( \begin{array}{c} . 8 4 9 \\ . 5 1 9 \end{array} \right) = \left( \begin{array}{c} 1. 4 6 3 \\ -. 7 2 3 \end{array} \right)
$$

and

$$
\widehat {\sigma} _ {w} ^ {2} = 8. 9 0 3 \left[ 1 - (. 8 4 9, . 5 1 9) \left( \begin{array}{c} 1. 4 6 3 \\ -. 7 2 3 \end{array} \right) \right] = 1. 1 8 7.
$$

By Property 3.8, the asymptotic variance–covariance matrix of $\widehat { \phi }$

$$
\frac {1}{1 4 4} \frac {1 . 1 8 7}{8 . 9 0 3} \left[ \begin{array}{c c} 1 & . 8 4 9 \\ . 8 4 9 & 1 \end{array} \right] ^ {- 1} = \left[ \begin{array}{c c} . 0 5 8 ^ {2} & -. 0 0 3 \\ -. 0 0 3 & . 0 5 8 ^ {2} \end{array} \right],
$$

can be used to get confidence regions for, or make inferences about $\widehat { \phi }$ and its components. For example, an approximate 95% confidence interval for $\phi _ { 2 }$ is $- . 7 2 3 \pm 2 ( . 0 5 8 )$ , or $( - . 8 3 8 , - . 6 0 8 )$ , which contains the true value of $\phi _ { 2 } = - . 7 5$ .

For these data, the first three sample partial autocorrelations are $\hat { \phi } _ { 1 1 } =$ $\widehat { \rho } ( 1 ) = . 8 4 9$ , $\widehat { \phi } _ { 2 2 } = \widehat { \phi } _ { 2 } = - . 7 2 1$ , and $\widehat { \phi } _ { 3 3 } = - . 0 8 5$ . According to Property 3.9, the asymptotic standard error of $\widehat { \phi } _ { 3 3 }$ is $1 / \sqrt { 1 4 4 } = . 0 8 3$ , and the observed value, $- . 0 8 5$ , is about only one standard deviation from $\phi _ { 3 3 } = 0$ .

# Example 3.27 Yule–Walker Estimation of the Recruitment Series

In Example 3.17 we fit an AR(2) model to the recruitment series using regression. Below are the results of fitting the same model using Yule-Walker estimation in R, which are nearly identical to the values in Example 3.17.

1 rec.yw = ar.yw(rec, order=2)
2 rec.yw$x.mean # = 62.26 (mean estimate)
3 rec.yw$ar # = 1.33, -.44 (parameter estimates)
4 sqrt(diag(rec.yw$asy.var.coef)) # = .04, .04 (standard errors)
5 rec.yw$var_pred # = 94.80 (error variance estimate)

To obtain the 24 month ahead predictions and their standard errors, and then plot the results as in Example 3.24, use the R commands:

1 rec.pr = predict(rec.yw, n.ahead=24)
2 U = rec.pr$pred + rec.pr$se
3 L = rec.pr$pred - rec.pr$se
4 minx = min(rec,L); maxx = max(rec,U)
5 ts.plot(rec, rec.pr$kPred, xlim=c(1980,1990), ylim=c(minx,maxx))
6 lines(rec.pr$kPred, col="red", type="o")
7 lines(U, col="blue", lty="dashed")
8 lines(L, col="blue", lty="dashed")

In the case of AR(p) models, the Yule–Walker estimators given in (3.102) are optimal in the sense that the asymptotic distribution, (3.103), is the best asymptotic normal distribution. This is because, given initial conditions, AR(p) models are linear models, and the Yule–Walker estimators are essentially least squares estimators. If we use method of moments for MA or ARMA models, we will not get optimal estimators because such processes are nonlinear in the parameters.

# Example 3.28 Method of Moments Estimation for an MA(1)

Consider the time series

$$
x _ {t} = w _ {t} + \theta w _ {t - 1},
$$

where $| \theta | < 1$ . The model can then be written as

$$
x _ {t} = \sum_ {j = 1} ^ {\infty} (- \theta) ^ {j} x _ {t - j} + w _ {t},
$$

which is nonlinear in $\theta$ . The first two population autocovariances are $\gamma ( 0 ) =$ $\sigma _ { w } ^ { 2 } \big ( 1 + \theta ^ { 2 } \big )$ and $\gamma ( 1 ) = \sigma _ { w } ^ { 2 } \theta$ , so the estimate of $\theta$ is found by solving:

$$
\widehat {\rho} (1) = \frac {\widehat {\gamma} (1)}{\widehat {\gamma} (0)} = \frac {\widehat {\theta}}{1 + \widehat {\theta} ^ {2}}.
$$

Two solutions exist, so we would pick the invertible one. If $| \widehat { \rho } ( 1 ) | \le \frac { 1 } { 2 }$ , the solutions are real, otherwise, a real solution does not exist. Even though $| \rho ( 1 ) | < \frac { 1 } { 2 }$ for an invertible MA(1), it may happen that $| \widehat { \rho } ( 1 ) | \geq \frac { 1 } { 2 }$ because b it is an estimator. For example, the following simulation in R produces a value of $\widehat { \rho } ( 1 ) = . 5 0 7$ when the true value is $\rho ( 1 ) = . 9 / ( 1 + . 9 ^ { 2 } ) = . 4 9 7$ .

1 set.seed(2)   
2 ma1 $=$ arima.sim(list(order = c(0,0,1), $\mathtt { m a } \ = \ 0 . 9 ,$ ), $\mathrm { ~ \tt ~ n ~ } = \mathrm { ~ 5 0 ~ } \cdot$ )   
3 acf(ma1, plot=FALSE)[1] # = .507 (lag 1 sample ACF)

When $\begin{array} { r } { | \widehat { \rho } ( 1 ) | < \frac { 1 } { 2 } } \end{array}$ , the invertible estimate is

$$
\widehat {\theta} = \frac {1 - \sqrt {1 - 4 \widehat {\rho} (1) ^ {2}}}{2 \widehat {\rho} (1)}.
$$

It can be shown that5

$$
\widehat {\theta} \sim \mathrm {A N} \left(\theta , \frac {1 + \theta^ {2} + 4 \theta^ {4} + \theta^ {6} + \theta^ {8}}{n (1 - \theta^ {2}) ^ {2}}\right);
$$

AN is read asymptotically normal and is defined in Definition A.5, page 515, of Appendix A. The maximum likelihood estimator (which we discuss next) of $\theta$ , in this case, has an asymptotic variance of $( 1 - \theta ^ { 2 } ) / n$ . When $\theta = . 5$ , for example, the ratio of the asymptotic variance of the method of moments estimator to the maximum likelihood estimator of $\theta$ is about 3.5. That is, for large samples, the variance of the method of moments estimator is about 3.5 times larger than the variance of the MLE of $\theta$ when $\theta = . 5$ .

# Maximum Likelihood and Least Squares Estimation

To fix ideas, we first focus on the causal AR(1) case. Let

$$
x _ {t} = \mu + \phi \left(x _ {t - 1} - \mu\right) + w _ {t} \tag {3.105}
$$

where $| \phi | < 1$ and $w _ { t } \sim$ iid N $( 0 , \sigma _ { w } ^ { 2 } )$ . Given data $x _ { 1 } , x _ { 2 } , \ldots , x _ { n }$ , we seek the likelihood

$$
L (\mu , \phi , \sigma_ {w} ^ {2}) = f (x _ {1}, x _ {2}, \dots , x _ {n} | \mu , \phi , \sigma_ {w} ^ {2}).
$$

In the case of an AR(1), we may write the likelihood as

$$
L (\mu , \phi , \sigma_ {w} ^ {2}) = f (x _ {1}) f (x _ {2} \mid x _ {1}) \dots f (x _ {n} \mid x _ {n - 1}),
$$

where we have dropped the parameters in the densities, $f ( \cdot )$ , to ease the notation. Because $x _ { t } \mid x _ { t - 1 } \sim \mathrm { N } \left( \mu + \phi ( x _ { t - 1 } - \mu ) , \sigma _ { w } ^ { 2 } \right)$ , we have

$$
f (x _ {t} \mid x _ {t - 1}) = f _ {w} [ (x _ {t} - \mu) - \phi (x _ {t - 1} - \mu) ],
$$

where $f _ { w } ( \cdot )$ is the density of $w _ { t }$ , that is, the normal density with mean zero and variance $\sigma _ { w } ^ { 2 }$ . We may then write the likelihood as

$$
L (\mu , \phi , \sigma_ {w}) = f (x _ {1}) \prod_ {t = 2} ^ {n} f _ {w} \left[ \left(x _ {t} - \mu\right) - \phi \left(x _ {t - 1} - \mu\right) \right].
$$

To find $f ( x _ { 1 } )$ , we can use the causal representation

$$
x _ {1} = \mu + \sum_ {j = 0} ^ {\infty} \phi^ {j} w _ {1 - j}
$$

to see that $x _ { 1 }$ is normal, with mean $\mu$ and variance $\sigma _ { w } ^ { 2 } / ( 1 - \phi ^ { 2 } )$ . Finally, for an AR(1), the likelihood is

$$
L (\mu , \phi , \sigma_ {w} ^ {2}) = (2 \pi \sigma_ {w} ^ {2}) ^ {- n / 2} (1 - \phi^ {2}) ^ {1 / 2} \exp \left[ - \frac {S (\mu , \phi)}{2 \sigma_ {w} ^ {2}} \right], \tag {3.106}
$$

where

$$
S (\mu , \phi) = (1 - \phi^ {2}) (x _ {1} - \mu) ^ {2} + \sum_ {t = 2} ^ {n} \left[ \left(x _ {t} - \mu\right) - \phi \left(x _ {t - 1} - \mu\right) \right] ^ {2}. \tag {3.107}
$$

Typically, $S ( \mu , \phi )$ is called the unconditional sum of squares. We could have also considered the estimation of $\mu$ and $\phi$ using unconditional least squares, that is, estimation by minimizing $S ( \mu , \phi )$ .

Taking the partial derivative of the log of (3.106) with respect to $\sigma _ { w } ^ { 2 }$ and setting the result equal to zero, we see that for any given values of $\mu$ and $\phi$ in the parameter space, $\sigma _ { w } ^ { 2 } = n ^ { - 1 } S ( \mu , \phi )$ maximizes the likelihood. Thus, the maximum likelihood estimate of $\sigma _ { w } ^ { 2 }$ is

$$
\hat {\sigma} _ {w} ^ {2} = n ^ {- 1} S (\widehat {\mu}, \widehat {\phi}), \tag {3.108}
$$

where $\widehat { \mu }$ and $\widehat { \phi }$ are the MLEs of $\mu$ and $\phi$ , respectively. If we replace $n$ in (3.108) by $n - 2$ , we would obtain the unconditional least squares estimate of $\sigma _ { w } ^ { 2 }$ .

If, in (3.106), we take logs, replace $\sigma _ { w } ^ { 2 }$ by $\widehat { \sigma } _ { w } ^ { 2 }$ , and ignore constants, $\widehat { \mu }$ and $\widehat { \phi }$ are the values that minimize the criterion function

$$
l (\mu , \phi) = \log [ n ^ {- 1} S (\mu , \phi) ] - n ^ {- 1} \log (1 - \phi^ {2}); \tag {3.109}
$$

that is, $l ( \mu , \phi ) \propto - 2 \log L ( \mu , \phi , \widehat { \sigma } _ { w } ^ { 2 } )$ .6 Because (3.107) and (3.109) are complicated functions of the parameters, the minimization of $l ( \mu , \phi )$ or $S ( \mu , \phi )$ is accomplished numerically. In the case of AR models, we have the advantage that, conditional on initial values, they are linear models. That is, we can drop the term in the likelihood that causes the nonlinearity. Conditioning on $x _ { 1 }$ , the conditional likelihood becomes

$$
\begin{array}{l} L (\mu , \phi , \sigma_ {w} ^ {2} \mid x _ {1}) = \prod_ {t = 2} ^ {n} f _ {w} [ (x _ {t} - \mu) - \phi (x _ {t - 1} - \mu) ] \\ = \left(2 \pi \sigma_ {w} ^ {2}\right) ^ {- (n - 1) / 2} \exp \left[ - \frac {S _ {c} (\mu , \phi)}{2 \sigma_ {w} ^ {2}} \right], \tag {3.110} \\ \end{array}
$$

where the conditional sum of squares is

$$
S _ {c} (\mu , \phi) = \sum_ {t = 2} ^ {n} \left[ \left(x _ {t} - \mu\right) - \phi \left(x _ {t - 1} - \mu\right) \right] ^ {2}. \tag {3.111}
$$

The conditional MLE of $\sigma _ { w } ^ { 2 }$ is

$$
\hat {\sigma} _ {w} ^ {2} = S _ {c} (\hat {\mu}, \hat {\phi}) / (n - 1), \tag {3.112}
$$

and $\widehat { \mu }$ and $\widehat { \phi }$ are the values that minimize the conditional sum of squares, $S _ { c } ( \mu , \phi )$ . Letting $\alpha = \mu ( 1 - \phi )$ , the conditional sum of squares can be written as

$$
S _ {c} (\mu , \phi) = \sum_ {t = 2} ^ {n} \left[ x _ {t} - \left(\alpha + \phi x _ {t - 1}\right) \right] ^ {2}. \tag {3.113}
$$

The problem is now the linear regression problem stated in §2.2. Following the results from least squares estimation, we have $\widehat { \alpha } = \bar { x } _ { ( 2 ) } - \widehat { \phi } \bar { x } _ { ( 1 ) }$ , where $\begin{array} { r } { \bar { x } _ { ( 1 ) } = ( n - 1 ) ^ { - 1 } \sum _ { t = 1 } ^ { n - 1 } x _ { t } } \end{array}$ , and $\begin{array} { r } { \bar { x } _ { ( 2 ) } = ( n - 1 ) ^ { - 1 } \sum _ { t = 2 } ^ { n } x _ { t } } \end{array}$ (2) − b (1), and the conditional estimates are then

$$
\widehat {\mu} = \frac {\bar {x} _ {(2)} - \widehat {\phi} \bar {x} _ {(1)}}{1 - \widehat {\phi}} \tag {3.114}
$$

$$
\widehat {\phi} = \frac {\sum_ {t = 2} ^ {n} \left(x _ {t} - \bar {x} _ {(2)}\right) \left(x _ {t - 1} - \bar {x} _ {(1)}\right)}{\sum_ {t = 2} ^ {n} \left(x _ {t - 1} - \bar {x} _ {(1)}\right) ^ {2}}. \tag {3.115}
$$

From (3.114) and (3.115), we see that $\widehat { \mu } \approx \bar { x }$ and $\widehat { \phi } \approx \widehat { \rho } ( 1 )$ . That is, the b bYule–Walker estimators and the conditional least squares estimators are approximately the same. The only difference is the inclusion or exclusion of terms involving the endpoints, $x _ { 1 }$ and $x _ { n }$ . We can also adjust the estimate of $\sigma _ { w } ^ { 2 }$ in (3.112) to be equivalent to the least squares estimator, that is, divide $S _ { c } ( \widehat { \mu } , \widehat { \phi } )$ by $( n - 3 )$ instead of $( n - 1 )$ in (3.112).

bFor general $\operatorname { A R } ( p )$ models, maximum likelihood estimation, unconditional least squares, and conditional least squares follow analogously to the AR(1) example. For general ARMA models, it is difficult to write the likelihood as an explicit function of the parameters. Instead, it is advantageous to write the likelihood in terms of the innovations, or one-step-ahead prediction errors, $x _ { t } - x _ { t } ^ { t - 1 }$ . This will also be useful in Chapter 6 when we study state-space models.

For a normal $\mathrm { A R M A } ( p , q )$ $( p , q )$ model, $\operatorname { l e t } \beta = ( \mu , \phi _ { 1 } , \dots , \phi _ { p } , \theta _ { 1 } , \dots , \theta _ { q } ) ^ { \prime }$ be the $( p + q + 1 )$ -dimensional vector of the model parameters. The likelihood can be written as

$$
L (\boldsymbol {\beta}, \sigma_ {w} ^ {2}) = \prod_ {t = 1} ^ {n} f (x _ {t} \mid x _ {t - 1}, \dots , x _ {1}).
$$

conditional di and variance ution of . Recall $x _ { t }$ given om (3.7 $x _ { t - 1 } , \ldots , x _ { 1 }$ $x _ { t } ^ { t - 1 }$ $P _ { t } ^ { t - 1 }$ $\begin{array} { r } { P _ { t } ^ { t - 1 } = \gamma ( 0 ) \prod _ { j = 1 } ^ { t - 1 } ( 1 - \phi _ { j j } ^ { 2 } ) } \end{array}$ t For ARMA models, $\begin{array} { r } { \gamma ( 0 ) = \sigma _ { w } ^ { 2 } \sum _ { j = 0 } ^ { \infty } \psi _ { j } ^ { 2 } } \end{array}$ t j=1, in which case we may write

$$
P _ {t} ^ {t - 1} = \sigma_ {w} ^ {2} \left\{\left[ \sum_ {j = 0} ^ {\infty} \psi_ {j} ^ {2} \right] \left[ \prod_ {j = 1} ^ {t - 1} \left(1 - \phi_ {j j} ^ {2}\right) \right] \right\} \stackrel {\text {d e f}} {=} \sigma_ {w} ^ {2} r _ {t},
$$

where $r _ { t }$ is the term in the braces. Note that the $r _ { t }$ terms are functions only of the regression parameters and that they may be computed recursively as $r _ { t + 1 } = ( 1 - \phi _ { t t } ^ { 2 } ) r _ { t }$ with initial condition $\begin{array} { r } { r _ { 1 } = \sum _ { j = 0 } ^ { \infty } \psi _ { j } ^ { 2 } } \end{array}$ . The likelihood of the data can now be written as

$$
L (\boldsymbol {\beta}, \sigma_ {w} ^ {2}) = (2 \pi \sigma_ {w} ^ {2}) ^ {- n / 2} \left[ r _ {1} (\boldsymbol {\beta}) r _ {2} (\boldsymbol {\beta}) \dots r _ {n} (\boldsymbol {\beta}) \right] ^ {- 1 / 2} \exp \left[ - \frac {S (\boldsymbol {\beta})}{2 \sigma_ {w} ^ {2}} \right], \tag {3.116}
$$

where

$$
S (\boldsymbol {\beta}) = \sum_ {t = 1} ^ {n} \left[ \frac {\left(x _ {t} - x _ {t} ^ {t - 1} (\boldsymbol {\beta})\right) ^ {2}}{r _ {t} (\boldsymbol {\beta})} \right]. \tag {3.117}
$$

Both $x _ { t } ^ { t - 1 }$ and $r _ { t }$ are functions of $\beta$ alone, and we make that fact explicit in (3.116)-(3.117). Given values for $\beta$ and $\sigma _ { w } ^ { 2 }$ , the likelihood may be evaluated using the techniques of 3.5. Maximum likelihood estimation would now proceed by maximizing (3.116) with respect to $\beta$ and $\sigma _ { w } ^ { 2 }$ . As in the AR(1) example, we have

$$
\hat {\sigma} _ {w} ^ {2} = n ^ {- 1} S (\hat {\beta}), \tag {3.118}
$$

where $\widehat { \beta }$ is the value of $\beta$ that minimizes the concentrated likelihood

$$
l (\boldsymbol {\beta}) = \log \left[ n ^ {- 1} S (\boldsymbol {\beta}) \right] + n ^ {- 1} \sum_ {t = 1} ^ {n} \log r _ {t} (\boldsymbol {\beta}). \tag {3.119}
$$

For the $\operatorname { A R } ( 1 )$ model (3.105) discussed previously, recall that $x _ { 1 } ^ { 0 } = \mu$ and t and $x _ { t } ^ { t - 1 } = \mu + \phi ( x _ { t - 1 } - \mu )$ x $\phi _ { h h } ~ = ~ 0$ t− for $h > 1$ , for , we have $t = 2 , \ldots , n$ $\begin{array} { r } { r _ { 1 } = \sum _ { j = 0 } ^ { \infty } \phi ^ { 2 j } = ( 1 - \phi ^ { 2 } ) ^ { - 1 } } \end{array}$ 1 . Also, using the fact that , $r _ { 2 } = ( 1 -$ $\phi _ { 1 1 } = \phi$ $\phi ^ { 2 } ) ^ { - 1 } ( 1 - \phi ^ { 2 } ) = 1$ , and in general, $r _ { t } = 1$ for $t = 2 , \ldots , n .$ . Hence, the likelihood presented in (3.106) is identical to the innovations form of the likelihood given by (3.116). Moreover, the generic $S ( \beta )$ in (3.117) is $S ( \mu , \phi )$ given in (3.107) and the generic $l ( \beta )$ in (3.119) is $l ( \mu , \phi )$ in (3.109).

Unconditional least squares would be performed by minimizing (3.117) with respect to $\beta$ . Conditional least squares estimation would involve minimizing (3.117) with respect to $\beta$ but where, to ease the computational burden, the predictions and their errors are obtained by conditioning on initial values of the data. In general, numerical optimization routines are used to obtain the actual estimates and their standard errors.

# Example 3.29 The Newton–Raphson and Scoring Algorithms

Two common numerical optimization routines for accomplishing maximum likelihood estimation are Newton–Raphson and scoring. We will give a brief account of the mathematical ideas here. The actual implementation of these algorithms is much more complicated than our discussion might imply. For

details, the reader is referred to any of the Numerical Recipes books, for example, Press et al. (1993).

Let $l ( \beta )$ be a criterion function of $k$ parameters $\beta = ( \beta _ { 1 } , \ldots , \beta _ { k } )$ that we wish to minimize with respect to $\beta$ . For example, consider the likelihood function given by (3.109) or by (3.119). Suppose $l ( { \widehat { \beta } } )$ is the extremum that we are interested in finding, and $\widehat { \beta }$ is found by solving $\partial l ( \beta ) / \partial \beta _ { j } = 0$ , for $j = 1 , \dots , k$ . Let $l ^ { ( 1 ) } ( \beta )$ denote the $k \times 1$ vector of partials

$$
l ^ {(1)} (\boldsymbol {\beta}) = \left(\frac {\partial l (\boldsymbol {\beta})}{\partial \beta_ {1}}, \dots , \frac {\partial l (\boldsymbol {\beta})}{\partial \beta_ {k}}\right) ^ {\prime}.
$$

Note, $l ^ { ( 1 ) } ( { \widehat { \beta } } ) = \mathbf { 0 }$ , the $k \times 1$ zero vector. Let $l ^ { ( 2 ) } ( \beta )$ denote the $k \times k$ matrix of second-order partials

$$
l ^ {(2)} (\boldsymbol {\beta}) = \left\{- \frac {\partial l ^ {2} (\boldsymbol {\beta})}{\partial \beta_ {i} \partial \beta_ {j}} \right\} _ {i, j = 1} ^ {k},
$$

and assume $l ^ { ( 2 ) } ( \beta )$ is nonsingular. Let $\beta _ { ( 0 ) }$ be an initial estimator of $\beta$ . Then, using a Taylor expansion, we have the following approximation:

$$
\mathbf {0} = l ^ {(1)} (\widehat {\boldsymbol {\beta}}) \approx l ^ {(1)} (\boldsymbol {\beta} _ {(0)}) - l ^ {(2)} (\boldsymbol {\beta} _ {(0)}) \left[ \widehat {\boldsymbol {\beta}} - \boldsymbol {\beta} _ {(0)} \right].
$$

Setting the right-hand side equal to zero and solving for $\widehat { \beta }$ [call the solution $\beta _ { ( 1 ) } ]$ , we get

$$
\boldsymbol {\beta} _ {(1)} = \boldsymbol {\beta} _ {(0)} + \left[ l ^ {(2)} (\boldsymbol {\beta} _ {(0)}) \right] ^ {- 1} l ^ {(1)} (\boldsymbol {\beta} _ {(0)}).
$$

The Newton–Raphson algorithm proceeds by iterating this result, replacing $\beta _ { ( 0 ) }$ by $\beta _ { ( 1 ) }$ to get $\beta _ { ( 2 ) }$ , and so on, until convergence. Under a set of appropriate conditions, the sequence of estimators, $\beta _ { ( 1 ) } , \beta _ { ( 2 ) } , \ldots$ , will converge to $\widehat { \beta }$ , the MLE of $\beta$ .

For maximum likelihood estimation, the criterion function used is $l ( \beta )$ given by (3.119); $l ^ { ( 1 ) } ( \beta )$ is called the score vector, and $l ^ { ( 2 ) } ( \beta )$ is called the Hessian. In the method of scoring, we replace $l ^ { ( 2 ) } ( \beta )$ by $E [ l ^ { ( 2 ) } ( \beta ) ]$ , the information matrix. Under appropriate conditions, the inverse of the information matrix is the asymptotic variance–covariance matrix of the estimator $\widehat { \beta }$ . This is sometimes approximated by the inverse of the Hessian at $\widehat { \beta }$ . If the derivatives are difficult to obtain, it is possible to use quasi-maximum likelihood estimation where numerical techniques are used to approximate the derivatives.

# Example 3.30 MLE for the Recruitment Series

So far, we have fit an AR(2) model to the Recruitment series using ordinary least squares (Example 3.17) and using Yule–Walker (Example 3.27). The following is an R session used to fit an AR(2) model via maximum likelihood estimation to the Recruitment series; these results can be compared to the results in Examples 3.17 and 3.27.

1 rec.mle = ar.mle(rec, order=2)
2 rec.mle\(x.mean # 62.26
3 rec.mle\)ar # 1.35, -.46
4 sqrt(diag(rec.mle\)asy.var.coef)) # .04, .04
5 rec.mle\)var_pred # 89.34

We now discuss least squares for ARMA $( p , q )$ models via Gauss–Newton. For general and complete details of the Gauss–Newton procedure, the reader is referred to Fuller (1996). As before, write $\pmb { \beta } = ( \phi _ { 1 } , \ldots , \phi _ { p } , \theta _ { 1 } , \ldots , \theta _ { q } ) ^ { \prime }$ , and for the ease of discussion, we will put $\mu = 0$ . We write the model in terms of the errors

$$
w _ {t} (\boldsymbol {\beta}) = x _ {t} - \sum_ {j = 1} ^ {p} \phi_ {j} x _ {t - j} - \sum_ {k = 1} ^ {q} \theta_ {k} w _ {t - k} (\boldsymbol {\beta}), \tag {3.120}
$$

emphasizing the dependence of the errors on the parameters.

For conditional least squares, we approximate the residual sum of squares by conditioning on $x _ { 1 } , \ldots , x _ { p }$ (if $p > 0$ ) and $w _ { p } = w _ { p - 1 } = w _ { p - 2 } = \cdot \cdot \cdot =$ $w _ { 1 - q } = 0$ (if $q > 0$ ), in which case, given $\beta$ , we may evaluate (3.120) for $t = p + 1 , p + 2 , \ldots , n$ . Using this conditioning argument, the conditional error sum of squares is

$$
S _ {c} (\beta) = \sum_ {t = p + 1} ^ {n} w _ {t} ^ {2} (\beta). \tag {3.121}
$$

Minimizing $S _ { c } ( \beta )$ with respect to $\beta$ yields the conditional least squares estimates. If $q = 0$ , the problem is linear regression and no iterative technique is needed to minimize $S _ { c } ( \phi _ { 1 } , \ldots , \phi _ { p } )$ . If $q > 0$ , the problem becomes nonlinear regression and we will have to rely on numerical optimization.

When $n$ is large, conditioning on a few initial values will have little influence on the final parameter estimates. In the case of small to moderate sample sizes, one may wish to rely on unconditional least squares. The unconditional least squares problem is to choose $\beta$ to minimize the unconditional sum of squares, which we have generically denoted by $S ( \beta )$ in this section. The unconditional sum of squares can be written in various ways, and one useful form in the case of ARMA $( p , q )$ models is derived in Box et al. (1994, Appendix A7.3). They showed (see Problem 3.19) the unconditional sum of squares can be written as

$$
S (\boldsymbol {\beta}) = \sum_ {t = - \infty} ^ {n} \hat {w} _ {t} ^ {2} (\boldsymbol {\beta}), \tag {3.122}
$$

where $\widehat { w } _ { t } ( \beta ) \ = \ E ( w _ { t } \vert x _ { 1 } , \ldots , x _ { n } )$ . When $t ~ \leq ~ 0$ , the $\widehat { w } _ { t } ( \beta )$ are obtained b bby backcasting. As a practical matter, we approximate $S ( \beta )$ by starting $t = - M + 1$ , where e case o $M$ is chosen large enough to guaranteenconditional least squares estimation, $\begin{array} { r } { \sum _ { t = - \infty } ^ { - M } \widehat { w } _ { t } ^ { 2 } ( \beta ) \approx 0 } \end{array}$ a numerical optimization technique is needed even when $q = 0$ .

To employ Gauss–Newton, let $\beta _ { ( 0 ) } = ( \phi _ { 1 } ^ { ( 0 ) } , \ldots , \phi _ { p } ^ { ( 0 ) } , \theta _ { 1 } ^ { ( 0 ) } , \ldots , \theta _ { q } ^ { ( 0 ) } ) ^ { \prime }$ . , φ(0)p , be an initial estimate of $\beta$ . For example, we could obtain $\beta _ { ( 0 ) }$ by method of moments. The first-order Taylor expansion of $w _ { t } ( \beta )$ is

$$
w _ {t} (\boldsymbol {\beta}) \approx w _ {t} \left(\boldsymbol {\beta} _ {(0)}\right) - \left(\boldsymbol {\beta} - \boldsymbol {\beta} _ {(0)}\right) ^ {\prime} \boldsymbol {z} _ {t} \left(\boldsymbol {\beta} _ {(0)}\right), \tag {3.123}
$$

where

$$
\boldsymbol {z} _ {t} (\boldsymbol {\beta} _ {(0)}) = \left(- \frac {\partial w _ {t} (\boldsymbol {\beta} _ {(0)})}{\partial \beta_ {1}}, \dots , - \frac {\partial w _ {t} (\boldsymbol {\beta} _ {(0)})}{\partial \beta_ {p + q}}\right) ^ {\prime}, \quad t = 1, \dots , n.
$$

The linear approximation of $S _ { c } ( \beta )$ is

$$
Q (\boldsymbol {\beta}) = \sum_ {t = p + 1} ^ {n} \left[ w _ {t} \left(\boldsymbol {\beta} _ {(0)}\right) - \left(\boldsymbol {\beta} - \boldsymbol {\beta} _ {(0)}\right) ^ {\prime} z _ {t} \left(\boldsymbol {\beta} _ {(0)}\right) \right] ^ {2} \tag {3.124}
$$

and this is the quantity that we will minimize. For approximate unconditional least squares, we would start the sum in (3.124) at $t = - M + 1$ , for a large value of $M$ , and work with the backcasted values.

Using the results of ordinary least squares ( 2.2), we know

$$
\widehat {(\boldsymbol {\beta} - \boldsymbol {\beta} _ {(0)})} = \left(n ^ {- 1} \sum_ {t = p + 1} ^ {n} z _ {t} \left(\boldsymbol {\beta} _ {(0)}\right) z _ {t} ^ {\prime} \left(\boldsymbol {\beta} _ {(0)}\right)\right) ^ {- 1} \left(n ^ {- 1} \sum_ {t = p + 1} ^ {n} z _ {t} \left(\boldsymbol {\beta} _ {(0)}\right) w _ {t} \left(\boldsymbol {\beta} _ {(0)}\right)\right) \tag {3.125}
$$

minimizes $Q ( \beta )$ . From (3.125), we write the one-step Gauss–Newton estimate as

$$
\boldsymbol {\beta} _ {(1)} = \boldsymbol {\beta} _ {(0)} + \Delta (\boldsymbol {\beta} _ {(0)}), \tag {3.126}
$$

where $\varDelta ( \beta _ { ( 0 ) } )$ denotes the right-hand side of (3.125). Gauss–Newton estimation is accomplished by replacing $\beta _ { ( 0 ) }$ by $\beta _ { ( 1 ) }$ in (3.126). This process is repeated by calculating, at iteration $j = 2 , 3 , \dots$ ,

$$
\boldsymbol {\beta} _ {(j)} = \boldsymbol {\beta} _ {(j - 1)} + \Delta (\boldsymbol {\beta} _ {(j - 1)})
$$

until convergence.

# Example 3.31 Gauss–Newton for an MA(1)

Consider an invertible MA(1) process, $x _ { t } = w _ { t } + \theta w _ { t - 1 }$ . Write the truncated errors as

$$
w _ {t} (\theta) = x _ {t} - \theta w _ {t - 1} (\theta), \quad t = 1, \dots , n, \tag {3.127}
$$

where we condition on $w _ { 0 } ( \theta ) = 0$ . Taking derivatives,

$$
- \frac {\partial w _ {t} (\theta)}{\partial \theta} = w _ {t - 1} (\theta) + \theta \frac {\partial w _ {t - 1} (\theta)}{\partial \theta}, \quad t = 1, \dots , n, \tag {3.128}
$$

where $\partial w _ { 0 } ( \theta ) / \partial \theta = 0$ . Using the notation of (3.123), we can also write (3.128) as

![](images/874b557fda4d95375524903cdf100e18feec194286423d988ceea276adc7a7b8.jpg)

![](images/e30954a5bea4a2d10d38a013870a084b8bac42b88329557df9430a99acfffbc0.jpg)  
Fig. 3.7. ACF and PACF of transformed glacial varves.

$$
z _ {t} (\theta) = w _ {t - 1} (\theta) - \theta z _ {t - 1} (\theta), \quad t = 1, \ldots , n, \qquad (3. 1 2 9)
$$

where $z _ { 0 } ( \theta ) = 0$ .

Let $\theta _ { ( 0 ) }$ be an initial estimate of $\theta$ , for example, the estimate given in Example 3.28. Then, the Gauss–Newton procedure for conditional least squares is given by

$$
\theta_ {(j + 1)} = \theta_ {(j)} + \frac {\sum_ {t = 1} ^ {n} z _ {t} \left(\theta_ {(j)}\right) w _ {t} \left(\theta_ {(j)}\right)}{\sum_ {t = 1} ^ {n} z _ {t} ^ {2} \left(\theta_ {(j)}\right)}, \quad j = 0, 1, 2, \dots , \tag {3.130}
$$

where the values in (3.130) are calculated recursively using (3.127) and (3.129). The calculations are stopped when $| \theta _ { ( j + 1 ) } - \theta _ { ( j ) } |$ , or $| Q ( \theta _ { ( j + 1 ) } ) -$ $Q ( \theta _ { ( j ) } ) |$ , are smaller than some preset amount.

# Example 3.32 Fitting the Glacial Varve Series

Consider the series of glacial varve thicknesses from Massachusetts for $n =$ 634 years, as analyzed in Example 2.6 and in Problem 2.8, where it was argued that a first-order moving average model might fit the logarithmically transformed and differenced varve series, say,

$$
\nabla \log (x _ {t}) = \log (x _ {t}) - \log (x _ {t - 1}) = \log \left(\frac {x _ {t}}{x _ {t - 1}}\right),
$$

which can be interpreted as being approximately the percentage change in the thickness.

![](images/829842486d592d7462e7541c445a75474507c580c172ed36ce0bb0f7f8b73207.jpg)  
Fig. 3.8. Conditional sum of squares versus values of the moving average parameter for the glacial varve example, Example 3.32. Vertical lines indicate the values of the parameter obtained via Gauss–Newton; see Table 3.2 for the actual values.

The sample ACF and PACF, shown in Figure 3.7, confirm the tendency of $\nabla \log ( { \boldsymbol { x } } _ { t } )$ to behave as a first-order moving average process as the ACF has only a significant peak at lag one and the PACF decreases exponentially. Using Table 3.1, this sample behavior fits that of the MA(1) very well.

The results of eleven iterations of the Gauss–Newton procedure, (3.130), starting with $\theta _ { ( 0 ) } ~ = ~ - . 1 0$ are given in Table 3.2. The final estimate is $\widehat \theta = \theta _ { ( 1 1 ) } = - . 7 7 3$ ; interim values and the corresponding value of the conditional sum of squares, $S _ { c } ( \theta )$ given in (3.121), are also displayed in the table. The final estimate of the error variance is $\widehat { \sigma } _ { w } ^ { 2 } = 1 4 8 . 9 8 / 6 3 2 = . 2 3 6$ with b 632 degrees of freedom (one is lost in differencing). The value of the sum of the squared derivatives at convergence is $\textstyle \sum _ { t = 1 } ^ { n } z _ { t } ^ { 2 } ( \theta _ { ( 1 1 ) } ) = 3 6 9 . 7 3 \quad$ , and consequently, the estimated standard error of $\widehat { \theta }$ is $\sqrt { . 2 3 6 / 3 6 9 . 7 3 } = . 0 2 5$ ;7 this leads to a $t$ -value of $- . 7 7 3 / . 0 2 5 = - 3 0 . 9 2$ with 632 degrees of freedom.

Figure 3.8 displays the conditional sum of squares, $S _ { c } ( \theta )$ as a function of $\theta$ , as well as indicating the values of each step of the Gauss–Newton algorithm. Note that the Gauss–Newton procedure takes large steps toward the minimum initially, and then takes very small steps as it gets close to the minimizing value. When there is only one parameter, as in this case, it would be easy to evaluate $S _ { c } ( \theta )$ on a grid of points, and then choose the appropriate value of $\theta$ from the grid search. It would be difficult, however, to perform grid searches when there are many parameters.

Table 3.2. Gauss–Newton Results for Example 3.32   

<table><tr><td>j</td><td>θ(j)</td><td>Sc(θ(j))</td><td>∑t=1nzt2(θ(j))</td></tr><tr><td>0</td><td>-0.100</td><td>195.0010</td><td>183.3464</td></tr><tr><td>1</td><td>-0.250</td><td>177.7614</td><td>163.3038</td></tr><tr><td>2</td><td>-0.400</td><td>165.0027</td><td>161.6279</td></tr><tr><td>3</td><td>-0.550</td><td>155.6723</td><td>182.6432</td></tr><tr><td>4</td><td>-0.684</td><td>150.2896</td><td>247.4942</td></tr><tr><td>5</td><td>-0.736</td><td>149.2283</td><td>304.3125</td></tr><tr><td>6</td><td>-0.757</td><td>149.0272</td><td>337.9200</td></tr><tr><td>7</td><td>-0.766</td><td>148.9885</td><td>355.0465</td></tr><tr><td>8</td><td>-0.770</td><td>148.9812</td><td>363.2813</td></tr><tr><td>9</td><td>-0.771</td><td>148.9804</td><td>365.4045</td></tr><tr><td>10</td><td>-0.772</td><td>148.9799</td><td>367.5544</td></tr><tr><td>11</td><td>-0.773</td><td>148.9799</td><td>369.7314</td></tr></table>

In the general case of causal and invertible $\mathrm { A R M A } ( p , q )$ $( p , q )$ models, maximum likelihood estimation and conditional and unconditional least squares estimation (and Yule–Walker estimation in the case of AR models) all lead to optimal estimators. The proof of this general result can be found in a number of texts on theoretical time series analysis (for example, Brockwell and Davis, 1991, or Hannan, 1970, to mention a few). We will denote the ARMA coefficient parameters by $\beta = ( \phi _ { 1 } , \ldots , \phi _ { p } , \theta _ { 1 } , \ldots , \theta _ { q } ) ^ { \prime }$ .

# Property 3.10 Large Sample Distribution of the Estimators

Under appropriate conditions, for causal and invertible ARMA processes, the maximum likelihood, the unconditional least squares, and the conditional least squares estimators, each initialized by the method of moments estimator, all provide optimal estimators of $\sigma _ { w } ^ { 2 }$ and $\beta$ , in the sense that $\widehat { \sigma } _ { w } ^ { 2 }$ is consistent, and the asymptotic distribution of $\widehat { \beta }$ is the best asymptotic normal distribution. In particular, as $n \to \infty$ ,

$$
\sqrt {n} (\widehat {\boldsymbol {\beta}} - \boldsymbol {\beta}) \xrightarrow {d} N \left(\mathbf {0}, \sigma_ {w} ^ {2} \boldsymbol {\Gamma} _ {p, q} ^ {- 1}\right). \tag {3.131}
$$

The asymptotic variance–covariance matrix of the estimator $\widehat { \beta }$ is the inverse of the information matrix. In particular, the $( p + q ) \times ( p + q )$ matrix $\varGamma _ { p , q }$ , has the form

$$
\Gamma_ {p, q} = \left( \begin{array}{c c} \Gamma_ {\phi \phi} & \Gamma_ {\phi \theta} \\ \Gamma_ {\theta \phi} & \Gamma_ {\theta \theta} \end{array} \right). \tag {3.132}
$$

The $p \times p$ matrix $\displaystyle { \int _ { \phi \phi } }$ is given by (3.100), that is, the $_ { i j }$ -th element of $\displaystyle { I _ { \phi \phi } }$ , for $i , j = 1 , \dotsc , p$ , is $\gamma _ { x } ( i - j )$ from an $A R ( p )$ process, $\phi ( B ) x _ { t } = w _ { t }$ . Similarly, $\varGamma _ { \theta \theta }$ is a $q \times q$ matrix with the $_ { i j }$ -th element, for $i , j = 1 , \ldots , q$ , equal to $\gamma _ { y } ( i - j )$ from an $A R ( q )$ process, $\theta ( B ) y _ { t } = w _ { t }$ . The $p \times q$ matrix $T _ { \phi \theta } = \{ \gamma _ { x y } ( i - j ) \}$ , for $i = 1 , \ldots , p$ ; $j = 1 , \dots , q$ ; that is, the ij-th element is the cross-covariance

between the two AR processes given by $\phi ( B ) x _ { t } = w _ { t }$ and $\theta ( B ) y _ { t } = w _ { t }$ . Finally, $T _ { \theta \phi } = T _ { \phi \theta } ^ { \prime }$ is $q \times p$ .

Further discussion of Property 3.10, including a proof for the case of least squares estimators for $\operatorname { A R } ( p )$ processes, can be found in Appendix B, §B.3.

# Example 3.33 Some Specific Asymptotic Distributions

The following are some specific cases of Property 3.10.

$$
\begin{array}{l} \mathbf {A R} (1): \gamma_ {x} (0) = \sigma_ {w} ^ {2} / (1 - \phi^ {2}), \text {s o} \sigma_ {w} ^ {2} \Gamma_ {1, 0} ^ {- 1} = (1 - \phi^ {2}). \text {T h u s}, \\ \widehat {\phi} \sim \mathrm {A N} [ \phi , n ^ {- 1} (1 - \phi^ {2}) ]. \tag {3.133} \\ \end{array}
$$

AR(2): The reader can verify that

$$
\gamma_ {x} (0) = \left(\frac {1 - \phi_ {2}}{1 + \phi_ {2}}\right) \frac {\sigma_ {w} ^ {2}}{(1 - \phi_ {2}) ^ {2} - \phi_ {1} ^ {2}}
$$

and $\gamma _ { x } ( 1 ) = \phi _ { 1 } \gamma _ { x } ( 0 ) + \phi _ { 2 } \gamma _ { x } ( 1 )$ . From these facts, we can compute $T _ { 2 , 0 } ^ { - 1 }$ . In particular, we have

$$
\binom {\widehat {\phi} _ {1}} {\widehat {\phi} _ {2}} \sim \mathrm {A N} \left[ \binom {\phi_ {1}} {\phi_ {2}}, n ^ {- 1} \binom {1 - \phi_ {2} ^ {2}} {\text {s y m}} \begin{array}{c} - \phi_ {1} (1 + \phi_ {2}) \\ 1 - \phi_ {2} ^ {2} \end{array} \right]. \tag {3.134}
$$

MA(1): In this case, write $\theta ( B ) y _ { t } = w _ { t }$ , or $y _ { t } + \theta y _ { t - 1 } = w _ { t } .$ . Then, analogous to the AR(1) case, $\gamma _ { y } ( 0 ) = \sigma _ { w } ^ { 2 } / ( 1 - \theta ^ { 2 } )$ , so $\sigma _ { w } ^ { 2 } { \cal T } _ { 0 , 1 } ^ { - 1 } = ( 1 - \theta ^ { 2 } )$ . Thus,

$$
\widehat {\theta} \sim \mathrm {A N} [ \theta , n ^ {- 1} (1 - \theta^ {2}) ]. \tag {3.135}
$$

MA(2): Write $y _ { t } + \theta _ { 1 } y _ { t - 1 } + \theta _ { 2 } y _ { t - 2 } = w _ { t }$ , so , analogous to the AR(2) case, we have

$$
\binom {\widehat {\theta} _ {1}} {\widehat {\theta} _ {2}} \sim \mathrm {A N} \left[ \binom {\theta_ {1}} {\theta_ {2}}, n ^ {- 1} \binom {1 - \theta_ {2} ^ {2}} {\text {s y m}} \binom {\theta_ {1} (1 + \theta_ {2})} {1 - \theta_ {2} ^ {2}} \right]. \tag {3.136}
$$

ARMA(1,1): To calculate $\Gamma _ { \phi \theta }$ , we must find $\gamma _ { x y } ( 0 )$ , where $x _ { t } - \phi x _ { t - 1 } = w _ { t }$ and $y _ { t } + \theta y _ { t - 1 } = w _ { t }$ . We have

$$
\begin{array}{l} \gamma_ {x y} (0) = \operatorname {c o v} \left(x _ {t}, y _ {t}\right) = \operatorname {c o v} \left(\phi x _ {t - 1} + w _ {t}, - \theta y _ {t - 1} + w _ {t}\right) \\ = - \phi \theta \gamma_ {x y} (0) + \sigma_ {w} ^ {2}. \\ \end{array}
$$

Solving, we find, $\gamma _ { x y } ( 0 ) = \sigma _ { w } ^ { 2 } / ( 1 + \phi \theta )$ . Thus,

$$
\binom {\widehat {\phi}} {\widehat {\theta}} \sim \mathrm {A N} \left[ \binom {\phi} {\theta}, n ^ {- 1} \left[ \begin{array}{c c} (1 - \phi^ {2}) ^ {- 1} & (1 + \phi \theta) ^ {- 1} \\ \text {s y m} & (1 - \theta^ {2}) ^ {- 1} \end{array} \right] ^ {- 1} \right]. \tag {3.137}
$$

# Example 3.34 Overfitting Caveat

The asymptotic behavior of the parameter estimators gives us an additional insight into the problem of fitting ARMA models to data. For example, suppose a time series follows an AR(1) process and we decide to fit an AR(2) to the data. Do any problems occur in doing this? More generally, why not simply fit large-order AR models to make sure that we capture the dynamics of the process? After all, if the process is truly an AR(1), the other autoregressive parameters will not be significant. The answer is that if we overfit, we obtain less efficient, or less precise parameter estimates. For example, if we fit an AR(1) to an AR(1) process, for large $n$ , $\mathrm { v a r } ( \hat { \phi } _ { 1 } ) \approx$ $n ^ { - 1 } ( 1 - \phi _ { 1 } ^ { 2 } )$ . But, if we fit an AR(2) to the AR(1) process, for large $n$ , $\mathrm { v a r } ( \hat { \phi _ { 1 } } ) \approx n ^ { - 1 } ( 1 - \phi _ { 2 } ^ { 2 } ) = n ^ { - 1 }$ because $\phi _ { 2 } = 0$ . Thus, the variance of $\phi _ { 1 }$ has been inflated, making the estimator less precise.

We do want to mention, however, that overfitting can be used as a diagnostic tool. For example, if we fit an AR(2) model to the data and are satisfied with that model, then adding one more parameter and fitting an AR(3) should lead to approximately the same model as in the AR(2) fit. We will discuss model diagnostics in more detail in 3.8.

The reader might wonder, for example, why the asymptotic distributions of $\widehat { \phi }$ from an AR(1) and $\widehat { \theta }$ from an MA(1) are of the same form; compare (3.133) to (3.135). It is possible to explain this unexpected result heuristically using the intuition of linear regression. That is, for the normal regression model presented in 2.2 with no intercept term, $x _ { t } = \beta z _ { t } + w _ { t }$ , we know $\widehat { \beta }$ i s normally distributed with mean $\beta$ , and from (2.9),

$$
\operatorname {v a r} \left\{\sqrt {n} \left(\widehat {\beta} - \beta\right) \right\} = n \sigma_ {w} ^ {2} \left(\sum_ {t = 1} ^ {n} z _ {t} ^ {2}\right) ^ {- 1} = \sigma_ {w} ^ {2} \left(n ^ {- 1} \sum_ {t = 1} ^ {n} z _ {t} ^ {2}\right) ^ {- 1}.
$$

For the causal AR(1) model given by $x _ { t } = \phi x _ { t - 1 } + w _ { t }$ , the intuition of regression tells us to expect that, for $n$ large,

$$
\sqrt {n} \left(\widehat {\phi} - \phi\right)
$$

is approximately normal with mean zero and with variance given by

$$
\sigma_ {w} ^ {2} \left(n ^ {- 1} \sum_ {t = 2} ^ {n} x _ {t - 1} ^ {2}\right) ^ {- 1}.
$$

Now, $n ^ { - 1 } \textstyle \sum _ { t = 2 } ^ { n } x _ { t - 1 } ^ { 2 }$ is the sample variance (recall that the mean of $x _ { t }$ is zero) of the $x _ { t }$ , so as $n$ becomes large we would expect it to approach $\mathrm { v a r } ( x _ { t } ) =$ $\gamma ( 0 ) = \sigma _ { w } ^ { 2 } / ( 1 - \phi ^ { 2 } )$ . Thus, the large sample variance of $\sqrt { n } \left( { \widehat { \phi } } - \phi \right)$ is

$$
\sigma_ {w} ^ {2} \gamma_ {x} (0) ^ {- 1} = \sigma_ {w} ^ {2} \left(\frac {\sigma_ {w} ^ {2}}{1 - \phi^ {2}}\right) ^ {- 1} = (1 - \phi^ {2});
$$

that is, (3.133) holds.

In the case of an MA(1), we may use the discussion of Example 3.31 to write an approximate regression model for the MA(1). That is, consider the approximation (3.129) as the regression model

$$
z _ {t} (\widehat {\theta}) = - \theta z _ {t - 1} (\widehat {\theta}) + w _ {t - 1},
$$

where now, $z _ { t - 1 } ( \widehat { \theta } )$ as defined in Example 3.31, plays the role of the regressor. Continuing with the analogy, we would expect the asymptotic distribution of ${ \sqrt { n } } \left( { \widehat { \theta } } - \theta \right)$ to be normal, with mean zero, and approximate variance

$$
\sigma_ {w} ^ {2} \left(n ^ {- 1} \sum_ {t = 2} ^ {n} z _ {t - 1} ^ {2} (\widehat {\theta})\right) ^ {- 1}.
$$

As in the A (1) case, $\scriptstyle n ^ { - 1 } \sum _ { t = 2 } ^ { n } z _ { t - 1 } ^ { 2 } ( { \widehat { \theta } } )$ sample variance of the $z _ { t } ( \widehat { \theta } )$ $n$ $\operatorname { v a r } \{ z _ { t } ( \theta ) \} = \gamma _ { z } ( 0 )$ (3.129), $z _ { t } ( \theta )$ is approximately an AR(1) process with parameter $- \theta$ . Thus,

$$
\sigma_ {w} ^ {2} \gamma_ {z} (0) ^ {- 1} = \sigma_ {w} ^ {2} \left(\frac {\sigma_ {w} ^ {2}}{1 - (- \theta) ^ {2}}\right) ^ {- 1} = (1 - \theta^ {2}),
$$

which agrees with (3.135). Finally, the asymptotic distributions of the AR parameter estimates and the MA parameter estimates are of the same form because in the MA case, the “regressors” are the differential processes $z _ { t } ( \theta )$ that have AR structure, and it is this structure that determines the asymptotic variance of the estimators. For a rigorous account of this approach for the general case, see Fuller (1996, Theorem 5.5.4).

In Example 3.32, the estimated standard error of $\widehat { \theta }$ was .025. In that example, we used regression results to estimate the standard error as the square root of

$$
n ^ {- 1} \widehat {\sigma} _ {w} ^ {2} \left(n ^ {- 1} \sum_ {t = 1} ^ {n} z _ {t} ^ {2} (\widehat {\theta})\right) ^ {- 1} = \frac {\widehat {\sigma} _ {w} ^ {2}}{\sum_ {t = 1} ^ {n} z _ {t} ^ {2} (\widehat {\theta})},
$$

where $n = 6 3 2$ , $\widehat { \sigma } _ { w } ^ { 2 } = . 2 3 6$ , $\textstyle \sum _ { t = 1 } ^ { n } z _ { t } ^ { 2 } ( { \widehat { \theta } } ) = 3 6 9 . 7 3$ and ${ \widehat { \theta } } = - . 7 7 3 .$ . Using (3.135), b  we could have also calculated this value using the asymptotic approximation, the square root of $( 1 - ( - . 7 7 3 ) ^ { 2 } ) / 6 3 2$ , which is also .025.

If $n$ is small, or if the parameters are close to the boundaries, the asymptotic approximations can be quite poor. The bootstrap can be helpful in this case; for a broad treatment of the bootstrap, see Efron and Tibshirani (1994). We discuss the case of an AR(1) here and leave the general discussion for Chapter 6. For now, we give a simple example of the bootstrap for an AR(1) process.

![](images/b2c59ac8805a0ec9144f944beb9ab9e7a9748eab10fee6460418d9a50b3f33b1.jpg)  
Fig. 3.9. One hundred observations generated from the model in Example 3.35.

# Example 3.35 Bootstrapping an AR(1)

We consider an AR(1) model with a regression coefficient near the boundary of causality and an error process that is symmetric but not normal. Specifically, consider the causal model

$$
x _ {t} = \mu + \phi \left(x _ {t - 1} - \mu\right) + w _ {t}, \tag {3.138}
$$

where $\mu = 5 0$ , $\phi = . 9 5$ , and $w _ { t }$ are iid double exponential with location zero, and scale parameter $\beta = 2$ . The density of $w _ { t }$ is given by

$$
f (w) = \frac {1}{2 \beta} \exp \left\{- | w | / \beta \right\} - \infty <   w <   \infty .
$$

In this example, $E ( w _ { t } ) ~ = ~ 0$ and $\operatorname { v a r } ( w _ { t } ) = 2 \beta ^ { 2 } = 8$ . Figure 3.9 shows $n = 1 0 0$ simulated observations from this process. This particular realization is interesting; the data look like they were generated from a nonstationary process with three different mean levels. In fact, the data were generated from a well-behaved, albeit non-normal, stationary and causal model. To show the advantages of the bootstrap, we will act as if we do not know the actual error distribution and we will proceed as if it were normal; of course, this means, for example, that the normal based MLE of $\phi$ will not be the actual MLE because the data are not normal.

Using the data shown in Figure 3.9, we obtained the Yule–Walker estimates $\widehat { \mu } = 4 0 . 0 5$ , $\hat { \phi } = . 9 6$ , and $s _ { w } ^ { 2 } = 1 5 . 3 0$ , where $s _ { w } ^ { 2 }$ is the estimate of $\mathrm { v a r } ( w _ { t } )$ . Based on Property 3.10, we would say that $\widehat { \phi }$ is approximately normal with mean $\phi$ (which we supposedly do not know) and variance $( 1 - \phi ^ { 2 } ) / 1 0 0$ , which we would approximate by $( 1 - . 9 6 ^ { 2 } ) / 1 0 0 = . 0 3 ^ { 2 }$ .

![](images/095745032359ffae3d20f0b1c9a13debb839c4e588ccb2e095a22f881a0ff9c5.jpg)  
Fig. 3.10. Finite sample density of the Yule–Walker estimate of $\phi$ in Example 3.35.

To assess the finite sample distribution of $\widehat { \phi }$ when $n = 1 0 0$ , we simulated 1000 realizations of this AR(1) process and estimated the parameters via Yule–Walker. The finite sampling density of the Yule–Walker estimate of $\phi$ , based on the 1000 repeated simulations, is shown in Figure 3.10. Clearly the sampling distribution is not close to normality for this sample size. The mean of the distribution shown in Figure 3.10 is .89, and the variance of the distribution is . $0 5 ^ { 2 }$ ; these values are considerably different than the asymptotic values. Some of the quantiles of the finite sample distribution are .79 $( 5 \%$ ), .86 $( 2 5 \% )$ , .90 (50%), .93 (75%), and .95 (95%). The R code to perform the simulation and plot the histogram is as follows:

```txt
1 set.seed(111)  
2 phi.yw = rep(NA, 1000)  
3 for (i in 1:1000)  
4 e = rexp(150, rate=.5); u = runif(150,-1,1); de = e*sign(u)  
5 x = 50 + arima.sim(n=100, list(ar=.95), innov=de, n.start=50)  
6 phi.yw[i] = ar.yw(x, order=1)$ar}  
7 hist(phi.yw, prob=TRUE, main="")  
8 lines密度 phi.yw, bw=.015)) 
```

Before discussing the bootstrap, we first investigate the sample innovation process, $x _ { t } - x _ { t } ^ { t - 1 }$ , with corresponding variances $P _ { t } ^ { t - 1 }$ . For the AR(1) model in this example,

$$
x _ {t} ^ {t - 1} = \mu + \phi (x _ {t - 1} - \mu), \qquad t = 2, \dots , 1 0 0.
$$

From this, it follows that

$$
P _ {t} ^ {t - 1} = E \left(x _ {t} - x _ {t} ^ {t - 1}\right) ^ {2} = \sigma_ {w} ^ {2}, \quad t = 2, \dots , 1 0 0.
$$

When $t = 1$ , we have

$$
x _ {1} ^ {0} = \mu \quad \text {a n d} \quad P _ {1} ^ {0} = \sigma_ {w} ^ {2} / (1 - \phi^ {2}).
$$

Thus, the innovations have zero mean but different variances; in order that all of the innovations have the same variance, $\sigma _ { w } ^ { 2 }$ , we will write them as

$$
\begin{array}{l} \epsilon_ {1} = (x _ {1} - \mu) \sqrt {(1 - \phi^ {2})} \\ \epsilon_ {t} = \left(x _ {t} - \mu\right) - \phi \left(x _ {t - 1} - \mu\right), \quad \text {f o r} \quad t = 2, \dots , 1 0 0. \tag {3.139} \\ \end{array}
$$

From these equations, we can write the model in terms of the $\epsilon _ { t }$ as

$$
\begin{array}{l} x _ {1} = \mu + \epsilon_ {1} / \sqrt {(1 - \phi^ {2})} \\ x _ {t} = \mu + \phi \left(x _ {t - 1} - \mu\right) + \epsilon_ {t} \quad \text {f o r} \quad t = 2, \dots , 1 0 0. \tag {3.140} \\ \end{array}
$$

Next, replace the parameters with their estimates in (3.139), that is, $\widehat { \mu } = 4 0 . 0 4 8$ and $\widehat { \phi } \ = \ . 9 5 7$ , and denote the resulting sample innovations as $\{ \widehat { \epsilon } _ { 1 } , \ldots , \widehat { \epsilon } _ { 1 0 0 } \}$ . To obtain one bootstrap sample, first randomly sample, with replacement, $n = 1 0 0$ values from the set of sample innovations; call the sampled values $\{ \epsilon _ { 1 } ^ { * } , \hdots , \epsilon _ { 1 0 0 } ^ { * } \}$ . Now, generate a bootstrapped data set sequentially by setting

$$
\begin{array}{l} x _ {1} ^ {*} = 4 0. 0 4 8 + \epsilon_ {1} ^ {*} / \sqrt {\left(1 -. 9 5 7 ^ {2}\right)} \\ x _ {t} ^ {*} = 4 0. 0 4 8 +. 9 5 7 \left(x _ {t - 1} ^ {*} - 4 0. 0 4 8\right) + \epsilon_ {t} ^ {*}, \quad t = 2, \dots , n. \tag {3.141} \\ \end{array}
$$

Next, estimate the parameters as if the data were $\boldsymbol { x } _ { t } ^ { * }$ . Call these estimates $\widehat { \mu } ( 1 )$ , $\widehat { \phi } ( 1 )$ , and $s _ { w } ^ { 2 } ( 1 )$ . Repeat this process a large number, $B$ , bof times, generating a collection of bootstrapped parameter estimates, $\{ \widehat { \mu } ( b ) , \widehat { \phi } ( b ) , s _ { w } ^ { 2 } ( b ) , b = 1 , \ldots , B \}$ . We can then approximate the finite sample distribution of an estimator from the bootstrapped parameter values. For example, we can approximate the distribution of ${ \widehat { \phi } } - \phi$ by the empirical distribution of ${ \widehat { \phi } } ( b ) - { \widehat { \phi } }$ , for $b = 1 , \ldots , B$ .

Figure 3.11 shows the bootstrap histogram of 200 bootstrapped estimates of $\phi$ using the data shown in Figure 3.9. In addition, Figure 3.11 shows a density estimate based on the bootstrap histogram, as well as the asymptotic normal density that would have been used based on Proposition 3.10. Clearly, the bootstrap distribution of $\widehat { \phi }$ is closer to the distribution of $\widehat { \phi }$ shown in Figure 3.10 than to the asymptotic normal approximation. In particular, the mean of the distribution of $\widehat { \phi } ( b )$ is .92 with a variance of . $0 5 ^ { 2 }$ . Some quantiles of this distribution are .83 (5%), .90 (25%), .93 (50%), .95 (75%), and .98 (95%).

To perform a similar bootstrap exercise in R, use the following commands. We note that the R estimation procedure is conditional on the first observation, so the first residual is not returned. To get around this problem,

![](images/4680cbb306187f4dacd5faaccab0964425bbffc3ce4d56cffb9d2b948b0eb644.jpg)  
Fig. 3.11. Bootstrap histogram of $\widehat { \phi }$ based on 200 bootstraps; a density estimate based on the histogram (solid line) and the corresponding asymptotic normal density (dashed line).

we simply fix the first observation and bootstrap the remaining data. The simulated data are available in the file ar1boot, but you can simulate your own data as was done in the code that produced Figure 3.10.

```r
1 x = ar1boot
2 m = mean(x) # estimate of mu
3 fit = ar.yw(x, order=1)
4 phi = fit$ar # estimate of phi
5 nboot = 200 # number of bootstrap replicates
6 resids = fit$resid[-1] # the first resid is NA
7 x_star = x # initialize x*
8 phi/star.yw = rep(NA, nboot)
9 for (i in 1:nboot) {
10 resid_star = sample(resids, replace=True)
11 for (t in 1:99) { x_star[t+1] = m + phi*(x_star[t]-m) + resid_star[t]} 
12 phi/star.yw[i] = ar.yw(x_star, order=1)$ar }
13 hist(phi/star.yw, 10, main="", prob=TRUE, ylim=c(0,14), xlim=c(.75,1.05)) 
14 lines(density(phi/star.yw, bw=.02))
15 u = seq(.75, 1.05, by=.001)
16 lines(u, dnorm(u, mean=.96, sd=.03), lty="dashed", lwd=2) 
```

# 3.7 Integrated Models for Nonstationary Data

In Chapters 1 and 2, we saw that if $x _ { t }$ is a random walk, $x _ { t } = x _ { t - 1 } + w _ { t }$ , then by differencing $x _ { t }$ , we find that $\nabla x _ { t } = w _ { t }$ is stationary. In many situations, time series can be thought of as being composed of two components, a nonstationary trend component and a zero-mean stationary component. For example, in 2.2 we considered the model

$$
x _ {t} = \mu_ {t} + y _ {t}, \tag {3.142}
$$

where $\mu _ { t } = \beta _ { 0 } + \beta _ { 1 } t$ and $y _ { t }$ is stationary. Differencing such a process will lead to a stationary process:

$$
\nabla x _ {t} = x _ {t} - x _ {t - 1} = \beta_ {1} + y _ {t} - y _ {t - 1} = \beta_ {1} + \nabla y _ {t}.
$$

Another model that leads to first differencing is the case in which $\mu _ { t }$ in (3.142) is stochastic and slowly varying according to a random walk. That is,

$$
\mu_ {t} = \mu_ {t - 1} + v _ {t}
$$

where $v _ { t }$ is stationary. In this case,

$$
\nabla x _ {t} = v _ {t} + \nabla y _ {t},
$$

is stationary. If $\mu _ { t }$ in (3.142) is a $k$ -th order polynomial, $\begin{array} { r } { \mu _ { t } = \sum _ { j = 0 } ^ { k } \beta _ { j } t ^ { j } } \end{array}$ then (Problem 3.27) the differenced series $\nabla ^ { k } y _ { t }$ is stationary. Stochastic trend models can also lead to higher order differencing. For example, suppose

$$
\mu_ {t} = \mu_ {t - 1} + v _ {t} \quad \text {a n d} \quad v _ {t} = v _ {t - 1} + e _ {t},
$$

where $e _ { t }$ is stationary. Then, $\nabla x _ { t } = v _ { t } + \nabla y _ { t }$ is not stationary, but

$$
\nabla^ {2} x _ {t} = e _ {t} + \nabla^ {2} y _ {t}
$$

is stationary.

The integrated ARMA, or ARIMA, model is a broadening of the class of ARMA models to include differencing.

Definition 3.11 A process $x _ { t }$ is said to be ARIMA $( p , d , q )$ i f

$$
\nabla^ {d} x _ {t} = (1 - B) ^ {d} x _ {t}
$$

is $A R M A ( p , q )$ . In general, we will write the model as

$$
\phi (B) (1 - B) ^ {d} x _ {t} = \theta (B) w _ {t}. \tag {3.143}
$$

If $E ( \nabla ^ { d } x _ { t } ) = \mu$ , we write the model as

$$
\phi (B) (1 - B) ^ {d} x _ {t} = \delta + \theta (B) w _ {t},
$$

where $\delta = \mu ( 1 - \phi _ { 1 } - \cdot \cdot \cdot - \phi _ { p } )$ .

Because of the nonstationarity, care must be taken when deriving forecasts. For the sake of completeness, we discuss this issue briefly here, but we stress the fact that both the theoretical and computational aspects of the problem are best handled via state-space models. We discuss the theoretical details in Chapter 6. For information on the state-space based computational aspects in R, see the ARIMA help files (?arima and ?predict.Arima); our scripts sarima and sarima.for are basically front ends for these R scripts.

It should be clear that, since $y _ { t } = \nabla ^ { d } x _ { t }$ is ARMA, we can use 3.5 methods to obtain forecasts of $y _ { t }$ , which in turn lead to forecasts for $x _ { t }$ . For example, if $d = 1$ , given forecasts $y _ { n + m } ^ { \pi }$ for $m = 1 , 2 , \ldots$ , we have $y _ { n + m } ^ { n } = x _ { n + m } ^ { n } - x _ { n + m - 1 } ^ { n }$ , so that

$$
x _ {n + m} ^ {n} = y _ {n + m} ^ {n} + x _ {n + m - 1} ^ {n}
$$

with initial condition $x _ { n + 1 } ^ { n } = y _ { n + 1 } ^ { n } + x _ { n }$ (noting $x _ { n } ^ { n } = x _ { n }$

n+1  n+1  n n  nIt is a little more difficult to obtain the prediction errors $P _ { n + m } ^ { n }$ , but for large $n$ , the approximation used in 3.5, equation (3.86), works well. That is, the mean-squared prediction error can be approximated by

$$
P _ {n + m} ^ {n} = \sigma_ {w} ^ {2} \sum_ {j = 0} ^ {m - 1} \psi_ {j} ^ {* 2}, \tag {3.144}
$$

where $\psi _ { j } ^ { * }$ is the coefficient of $z ^ { j }$ in $\psi ^ { * } ( z ) = \theta ( z ) / \phi ( z ) ( 1 - z ) ^ { d }$

To better understand integrated models, we examine the properties of some simple cases; Problem 3.29 covers the ARIMA $( 1 , 1 , 0 )$ case.

# Example 3.36 Random Walk with Drift

To fix ideas, we begin by considering the random walk with drift model first presented in Example 1.11, that is,

$$
x _ {t} = \delta + x _ {t - 1} + w _ {t},
$$

for $t = 1 , 2 , \ldots$ , and $x _ { 0 } = 0$ . Technically, the model is not ARIMA, but we could include it trivially as an ARIMA $( 0 , 1 , 0 )$ model. Given data $x _ { 1 } , \ldots , x _ { n }$ , the one-step-ahead forecast is given by

$$
x _ {n + 1} ^ {n} = E \left(x _ {n + 1} \mid x _ {n}, \dots , x _ {1}\right) = E \left(\delta + x _ {n} + w _ {n + 1} \mid x _ {n}, \dots , x _ {1}\right) = \delta + x _ {n}.
$$

The two-step-ahead forecast is given by $x _ { n + 2 } ^ { n } = \delta + x _ { n + 1 } ^ { n } = 2 \delta + x _ { n }$ , and consequently, the $m$ -step-ahead forecast, for $m = 1 , 2 , \ldots$ , is

$$
x _ {n + m} ^ {n} = m \delta + x _ {n}, \tag {3.145}
$$

To obtain the forecast errors, it is convenient to recall equation (1.4), i.e., $\begin{array} { r } { x _ { n } = n \delta + \sum _ { j = 1 } ^ { n } w _ { j } } \end{array}$ , in which case we may write

$$
x _ {n + m} = (n + m) \delta + \sum_ {j = 1} ^ {n + m} w _ {j} = m \delta + x _ {n} + \sum_ {j = n + 1} ^ {n + m} w _ {j}.
$$

From this it follows that the $m$ -step-ahead prediction error is given by

$$
P _ {n + m} ^ {n} = E \left(x _ {n + m} - x _ {n + m} ^ {n}\right) ^ {2} = E \left(\sum_ {j = n + 1} ^ {n + m} w _ {j}\right) ^ {2} = m \sigma_ {w} ^ {2}. \tag {3.146}
$$

Hence, unlike the stationary case (see Example 3.22), as the forecast horizon grows, the prediction errors, (3.146), increase without bound and the that (3.144) is exact in this case because forecasts follow a straight line with slope $\textstyle \psi ^ { * } ( z ) = 1 / ( 1 - z ) = \sum _ { j = 0 } ^ { \infty } z ^ { j }$ $\delta$ emanating from $x _ { n }$ . We note f or $| z | < 1$ , so that $\psi _ { j } ^ { * } = 1$ for all $j$ .

The $w _ { t }$ are Gaussian, so estimation is straightforward because the differenced data, say $y _ { t } = \nabla x _ { t }$ , are independent and identically distributed normal variates with mean $\delta$ and variance $\sigma _ { w } ^ { 2 }$ . Consequently, optimal estimates of $\delta$ and $\sigma _ { w } ^ { 2 }$ are the sample mean and variance of the $y _ { t }$ , respectively.

# Example 3.37 $\mathbf { I M A } ( 1 , 1 )$ and EWMA

The ARIMA(0,1,1), or IMA(1,1) model is of interest because many economic time series can be successfully modeled this way. In addition, the model leads to a frequently used, and abused, forecasting method called exponentially weighted moving averages (EWMA). We will write the model as

$$
x _ {t} = x _ {t - 1} + w _ {t} - \lambda w _ {t - 1}, \tag {3.147}
$$

with $| \lambda | < 1$ , for $t = 1 , 2 , \ldots$ , and $x _ { 0 } = 0$ , because this model formulation is easier to work with here, and it leads to the standard representation for EWMA. We could have included a drift term in (3.147), as was done in the previous example, but for the sake of simplicity, we leave it out of the discussion. If we write

$$
y _ {t} = w _ {t} - \lambda w _ {t - 1},
$$

representation, we may write (3.147) as $\begin{array} { r } { y _ { t } = \sum _ { j = 1 } ^ { \infty } \lambda ^ { j } y _ { t - j } + w _ { t } } \end{array}$ $x _ { t } = x _ { t - 1 } + y _ { t }$ . Because | |   , and substituting $| \lambda | < 1$ , $y _ { t }$ $y _ { t } = x _ { t } - x _ { t - 1 }$ has an invertible , we may write

$$
x _ {t} = \sum_ {j = 1} ^ {\infty} (1 - \lambda) \lambda^ {j - 1} x _ {t - j} + w _ {t}. \tag {3.148}
$$

as an approximation for large $t$ (put $x _ { t } = 0$ for $t \leq 0$ ). Verification of (3.148) is left to the reader (Problem 3.28). Using the approximation (3.148), we have that the approximate one-step-ahead predictor, using the notation of §3.5, is

$$
\begin{array}{l} \tilde {x} _ {n + 1} = \sum_ {j = 1} ^ {\infty} (1 - \lambda) \lambda^ {j - 1} x _ {n + 1 - j} \\ = (1 - \lambda) x _ {n} + \lambda \sum_ {j = 1} ^ {\infty} (1 - \lambda) \lambda^ {j - 1} x _ {n - j} \\ = (1 - \lambda) x _ {n} + \lambda \tilde {x} _ {n}. \tag {3.149} \\ \end{array}
$$

From (3.149), we see that the new forecast is a linear combination of the old forecast and the new observation. Based on (3.149) and the fact that we only observe $x _ { 1 } , \ldots , x _ { n }$ , and consequently $y _ { 1 } , \ldots , y _ { n }$ (because $y _ { t } = x _ { t } - x _ { t - 1 }$ ; $x _ { 0 } = 0$ ), the truncated forecasts are

$$
\tilde {x} _ {n + 1} ^ {n} = (1 - \lambda) x _ {n} + \lambda \tilde {x} _ {n} ^ {n - 1}, \quad n \geq 1, \tag {3.150}
$$

with $\tilde { x } _ { 1 } ^ { 0 } = x _ { 1 }$ as an initial value. The mean-square prediction error can be approximated using (3.144) by noting that $\psi ^ { * } ( z ) = ( 1 - \lambda z ) / ( 1 - z ) =$ $\begin{array} { r } { 1 + ( 1 - \lambda ) \sum _ { j = 1 } ^ { \infty } z ^ { j } } \end{array}$ for $| z | < 1$ ; consequently, for large $n$ , (3.144) leads to

$$
P _ {n + m} ^ {n} \approx \sigma_ {w} ^ {2} [ 1 + (m - 1) (1 - \lambda) ^ {2} ].
$$

In EWMA, the parameter $1 - \lambda$ is often called the smoothing parameter and is restricted to be between zero and one. Larger values of $\lambda$ lead to smoother forecasts. This method of forecasting is popular because it is easy to use; we need only retain the previous forecast value and the current observation to forecast the next time period. Unfortunately, as previously suggested, the method is often abused because some forecasters do not verify that the observations follow an $\mathrm { I M A } ( 1 , 1 )$ process, and often arbitrarily pick values of $\lambda$ . In the following, we show how to generate 100 observations from an IMA(1,1) model with $\lambda = - \theta = . 8$ and then calculate and display the fitted EWMA superimposed on the data. This is accomplished using the Holt-Winters command in R (see the help file ?HoltWinters for details; no output is shown):

1 set.seed(666)   
2 $\mathrm { ~ \tt ~ { ~ x ~ } ~ } =$ arima.sim(list(order = c(0,1,1), $\mathtt { m a } \ = \ - 0 . 8 )$ , $\mathrm { ~ \tt ~ n ~ } = \mathrm { ~ \tt ~ 1 0 0 ~ } \cdot$ )   
3 (x.ima $=$ HoltWinters(x, beta=FALSE, gamma=FALSE)) # $\alpha$ below is $1 - \lambda$ Smoothing parameter: alpha: 0.1663072   
4 plot(x.ima)

# 3.8 Building ARIMA Models

There are a few basic steps to fitting ARIMA models to time series data. These steps involve plotting the data, possibly transforming the data, identifying the dependence orders of the model, parameter estimation, diagnostics, and model choice. First, as with any data analysis, we should construct a time plot of the data, and inspect the graph for any anomalies. If, for example, the variability in the data grows with time, it will be necessary to transform the data to stabilize the variance. In such cases, the Box–Cox class of power transformations, equation (2.37), could be employed. Also, the particular application might suggest an appropriate transformation. For example, suppose a process evolves as a fairly small and stable percent-change, such as an investment. For example, we might have

$$
x _ {t} = (1 + p _ {t}) x _ {t - 1},
$$

where $x _ { t }$ is the value of the investment at time $t$ and $p _ { t }$ is the percentagechange from period $t - 1$ to $t$ , which may be negative. Taking logs we have

$$
\log (x _ {t}) = \log (1 + p _ {t}) + \log (x _ {t - 1}),
$$

or

$$
\nabla \log (x _ {t}) = \log (1 + p _ {t}).
$$

If the percent change $p _ { t }$ stays relatively small in magnitude, then $\log ( 1 + p _ { t } ) \approx$ ${ p _ { t } } ^ { \mathrm { s } }$ and, thus,

$$
\nabla \log (x _ {t}) \approx p _ {t},
$$

will be a relatively stable process. Frequently, $\nabla \log ( { \boldsymbol { x } } _ { t } )$ is called the return or growth rate. This general idea was used in Example 3.32, and we will use it again in Example 3.38.

After suitably transforming the data, the next step is to identify preliminary values of the autoregressive order, $p$ , the order of differencing, $d$ , and the moving average order, $q$ . We have already addressed, in part, the problem of selecting $d$ . A time plot of the data will typically suggest whether any differencing is needed. If differencing is called for, then difference the data once, $d = 1$ , and inspect the time plot of $\nabla x _ { t }$ . If additional differencing is necessary, then try differencing again and inspect a time plot of $\nabla ^ { 2 } \boldsymbol { x } _ { t }$ . Be careful not to overdifference because this may introduce dependence where none exists. For example, $x _ { t } = w _ { t }$ is serially uncorrelated, but $\nabla x _ { t } = w _ { t } - w _ { t - 1 }$ is MA(1). In addition to time plots, the sample ACF can help in indicating whether differencing is needed. Because the polynomial $\phi ( z ) ( 1 - z ) ^ { d }$ has a unit root, the sample ACF, $\widehat { \rho } ( h )$ , will not decay to zero fast as $h$ increases. Thus, a slow decay in $\widehat { \rho } ( h )$ b is an indication that differencing may be needed.

bWhen preliminary values of $d$ have been settled, the next step is to look at the sample ACF and PACF of $\nabla ^ { d } x _ { t }$ for whatever values of $d$ have been chosen. Using Table 3.1 as a guide, preliminary values of $p$ and $q$ are chosen. Recall that, if $p = 0$ and $q > 0$ , the ACF cuts off after lag $q$ , and the PACF tails off. If $q = 0$ and $p > 0$ , the PACF cuts off after lag $p$ , and the ACF tails off. If $p > 0$ and $q > 0$ , both the ACF and PACF will tail off. Because we are dealing with estimates, it will not always be clear whether the sample ACF or PACF is tailing off or cutting off. Also, two models that are seemingly different can actually be very similar. With this in mind, we should not worry about being so precise at this stage of the model fitting. At this stage, a few preliminary values of $p$ , $d$ , and $q$ should be at hand, and we can start estimating the parameters.

# Example 3.38 Analysis of GNP Data

In this example, we consider the analysis of quarterly U.S. GNP from 1947(1) to 2002(3), $n \ = \ 2 2 3$ observations. The data are real U.S. gross

![](images/b1e149103be33f17b0ccf58d2aa91bb9886f7fdd46dee7c8a66d52fb27fcf29d.jpg)  
Fig. 3.12. Quarterly U.S. GNP from 1947(1) to 2002(3).

![](images/2aa87d8d972f7a6c53b30a8b9c436a77ac75eda6001593961edcb6e0da6a418e.jpg)  
Fig. 3.13. Sample ACF of the GNP data. Lag is in terms of years.

national product in billions of chained 1996 dollars and have been seasonally adjusted. The data were obtained from the Federal Reserve Bank of St. Louis (http://research.stlouisfed.org/). Figure 3.12 shows a plot of the data, say, $y _ { t }$ . Because strong trend hides any other effect, it is not clear from Figure 3.12 that the variance is increasing with time. For the purpose of demonstration, the sample ACF of the data is displayed in Figure 3.13. Figure 3.14 shows the first difference of the data, $\nabla y _ { t }$ , and now that the trend has been removed we are able to notice that the variability in the second half of the data is larger than in the first half of the data. Also, it appears as though a trend is still present after differencing. The growth

![](images/9b0e1d6fe69f5af7051227a4d138cc12d6c43ade07baf8c297eb40f7833c6fda.jpg)  
Fig. 3.14. First difference of the U.S. GNP data.

![](images/7269d7fb86f3dd00d46ff3f77a5e926f6af373e57e434d7d43c18776239506c1.jpg)  
Fig. 3.15. U.S. GNP quarterly growth rate.

rate, say, $x _ { t } = \nabla \log ( y _ { t } )$ , is plotted in Figure 3.15, and, appears to be a stable process. Moreover, we may interpret the values of $x _ { t }$ as the percentage quarterly growth of U.S. GNP.

The sample ACF and PACF of the quarterly growth rate are plotted in Figure 3.16. Inspecting the sample ACF and PACF, we might feel that the ACF is cutting off at lag 2 and the PACF is tailing off. This would suggest the GNP growth rate follows an MA(2) process, or log GNP follows an ARIMA $( 0 , 1 , 2 )$ model. Rather than focus on one model, we will also suggest that it appears that the ACF is tailing off and the PACF is cutting off at

![](images/6745502e972ad6eaf91e763c1e5de06770f5aec9ba2c52e96586622b7da81294.jpg)

![](images/ce4881aae1635681d3e906bf94f3bd9d37ab29a772048812d10fcbd0b50d205f.jpg)  
Fig. 3.16. Sample ACF and PACF of the GNP quarterly growth rate. Lag is in terms of years.

lag 1. This suggests an AR(1) model for the growth rate, or ARIMA $( 1 , 1 , 0 )$ for log GNP. As a preliminary analysis, we will fit both models.

Using MLE to fit the MA(2) model for the growth rate, $x _ { t }$ , the estimated model is

$$
x _ {t} = . 0 0 8 _ {(. 0 0 1)} +. 3 0 3 _ {(. 0 6 5)} \widehat {w} _ {t - 1} +. 2 0 4 _ {(. 0 6 4)} \widehat {w} _ {t - 2} + \widehat {w} _ {t}, \tag {3.151}
$$

where $\widehat { \sigma } _ { w } = . 0 0 9 4$ is based on 219 degrees of freedom. The values in parentheses are the corresponding estimated standard errors. All of the regression coefficients are significant, including the constant. We make a special note of this because, as a default, some computer packages do not fit a constant in a differenced model. That is, these packages assume, by default, that there is no drift. In this example, not including a constant leads to the wrong conclusions about the nature of the U.S. economy. Not including a constant assumes the average quarterly growth rate is zero, whereas the U.S. GNP average quarterly growth rate is about 1% (which can be seen easily in Figure 3.15). We leave it to the reader to investigate what happens when the constant is not included.

The estimated AR(1) model is

$$
x _ {t} = . 0 0 8 _ {(. 0 0 1)} (1 - . 3 4 7) +. 3 4 7 _ {(. 0 6 3)} x _ {t - 1} + \widehat {w} _ {t}, \tag {3.152}
$$

where $\widehat { \sigma } _ { w } ~ = ~ . 0 0 9 5$ on 220 degrees of freedom; note that the constant in (3.152) is . $. 0 0 8 \left( 1 - . 3 4 7 \right) = . 0 0 5$ .

We will discuss diagnostics next, but assuming both of these models fit well, how are we to reconcile the apparent differences of the estimated models

(3.151) and (3.152)? In fact, the fitted models are nearly the same. To show this, consider an AR(1) model of the form in (3.152) without a constant term; that is,

$$
x _ {t} = . 3 5 x _ {t - 1} + w _ {t},
$$

and write it in its causal form, $\begin{array} { r } { x _ { t } = \sum _ { j = 0 } ^ { \infty } \psi _ { j } w _ { t - j } } \end{array}$ , where we recall $\psi _ { j } = . 3 5 ^ { j }$ Thus, $\psi _ { 0 } = 1 , \psi _ { 1 } = . 3 5 0 , \psi _ { 2 } = . 1 2 3 , \psi _ { 3 } = . 0 4 3 , \psi _ { 4 } = . 0 1 5 , \psi _ { 5 } = . 0 0 5 , \psi _ { 6 } =$ . $0 0 2 , \psi _ { 7 } = . 0 0 1 , \psi _ { 8 } = 0 , \psi _ { 9 } = 0 , \psi _ { 1 0 } = 0$ , and so forth. Thus,

$$
x _ {t} \approx . 3 5 w _ {t - 1} +. 1 2 w _ {t - 2} + w _ {t},
$$

which is similar to the fitted MA(2) model in (3.152).

The analysis can be performed in R as follows.

```txt
1 plot(gnp)  
2 acf2(gnp, 50)  
3 gnpgr = diff(log(gnp)) # growth rate  
4 plot(gnpgr)  
5 acf2(gnpgr, 24)  
6 sarima(gnpgr, 1, 0, 0) # AR(1)  
7 sarima(gnpgr, 0, 0, 2) # MA(2)  
8 ARMAtoMA(ar=.35, ma=0, 10) # prints psi-weights 
```

The next step in model fitting is diagnostics. This investigation includes the analysis of the residuals as well as model comparisons. Again, the first step involves a time plot of the innovations (or residuals), $x _ { t } - \widehat { x } _ { t } ^ { t - 1 }$ , or of the standardized innovations

$$
e _ {t} = \left(x _ {t} - \widehat {x} _ {t} ^ {t - 1}\right) / \sqrt {\widehat {P}} _ {t} ^ {t - 1}, \tag {3.153}
$$

where $\widehat { x } _ { t } ^ { t - 1 }$ is the one-step-ahead prediction of $x _ { t }$ based on the fitted model and $\widehat { P } _ { t } ^ { t - 1 }$ b  is the estimated one-step-ahead error variance. If the model fits well, the standardized residuals should behave as an iid sequence with mean zero and variance one. The time plot should be inspected for any obvious departures from this assumption. Unless the time series is Gaussian, it is not enough that the residuals are uncorrelated. For example, it is possible in the non-Gaussian case to have an uncorrelated process for which values contiguous in time are highly dependent. As an example, we mention the family of GARCH models that are discussed in Chapter 5.

Investigation of marginal normality can be accomplished visually by looking at a histogram of the residuals. In addition to this, a normal probability plot or a Q-Q plot can help in identifying departures from normality. See Johnson and Wichern (1992, Chapter 4) for details of this test as well as additional tests for multivariate normality.

There are several tests of randomness, for example the runs test, that could be applied to the residuals. We could also inspect the sample autocorrelations of the residuals, say, $\widehat { \rho } _ { e } ( h )$ , for any patterns or large values. Recall that, for a white noise sequence, the sample autocorrelations are approximately independently and normally distributed with zero means and variances $1 / n$ . Hence, a

good check on the correlation structure of the residuals is to plot $\widehat { \rho } _ { e } ( h )$ versus $h$ along with the error bounds of $\pm 2 / \sqrt { n }$ . The residuals from a model fit, however, will not quite have the properties of a white noise sequence and the variance of $\widehat { \rho } _ { e } ( h )$ can be much less than $1 / n$ . Details can be found in Box and Pierce (1970) and McLeod (1978). This part of the diagnostics can be viewed as a visual inspection of $\widehat { \rho } _ { e } ( h )$ with the main concern being the detection of obvious departures from the independence assumption.

In addition to plotting $\widehat { \rho } _ { e } ( h )$ , we can perform a general test that takes into consideration the magnitudes of $\widehat { \rho } _ { e } ( h )$ as a group. For example, it may be the case that, individually, each $\widehat { \rho } _ { e } ( h )$ is small in magnitude, say, each one is just slightly less that $2 / { \sqrt { n } }$ in magnitude, but, collectively, the values are large. The Ljung–Box–Pierce Q-statistic given by

$$
Q = n (n + 2) \sum_ {h = 1} ^ {H} \frac {\widehat {\rho} _ {e} ^ {2} (h)}{n - h} \tag {3.154}
$$

can be used to perform such a test. The value $H$ in (3.154) is chosen somewhat arbitrarily, typically, $H = 2 0$ . Under the null hypothesis of model adequacy, asymptotically ( $n  \infty$ ), $Q \sim \chi _ { H - p - q } ^ { 2 }$ . Thus, we would reject the null hypothesis at level $\alpha$ if the value of $Q$ −p−qexceeds the $( 1 - \alpha )$ -quantile of the $\chi _ { H - p - q } ^ { 2 }$ − −distribution. Details can be found in Box and Pierce (1970), Ljung and Box (1978), and Davies et al. (1977). The basic idea is that if $w _ { t }$ is white noise, dent then by Property 1.1, $\chi _ { 1 } ^ { 2 }$ bw   random variables. This means that $n \widehat { \rho } _ { w } ^ { 2 } ( h )$ , for $h = 1 , \ldots , H$ $n \textstyle \sum _ { h = 1 } ^ { H } \widehat { \rho } _ { w } ^ { 2 } ( h )$ , are asymptotically indepen- is approximately a $\chi _ { H } ^ { 2 }$ random variable. Because the test involves the ACF of residuals from a model fit, there is a loss of $p { + } q$ degrees of freedom; the other values in (3.154) are used to adjust the statistic to better match the asymptotic chi-squared distribution.

# Example 3.39 Diagnostics for GNP Growth Rate Example

We will focus on the MA(2) fit from Example 3.38; the analysis of the AR(1) residuals is similar. Figure 3.17 displays a plot of the standardized residuals, the ACF of the residuals, a boxplot of the standardized residuals, and the p-values associated with the Q-statistic, (3.154), at lags $H \ = \ 3$ through $H = 2 0$ (with corresponding degrees of freedom $H - 2$ ).

Inspection of the time plot of the standardized residuals in Figure 3.17 shows no obvious patterns. Notice that there are outliers, however, with a few values exceeding 3 standard deviations in magnitude. The ACF of the standardized residuals shows no apparent departure from the model assumptions, and the Q-statistic is never significant at the lags shown. The normal Q-Q plot of the residuals shows departure from normality at the tails due to the outliers that occurred primarily in the 1950s and the early 1980s.

The model appears to fit well except for the fact that a distribution with heavier tails than the normal distribution should be employed. We discuss

![](images/f3a8414eed11417f6c0c5af441fcc596bd4db7d627612271bdd6bb6ecfb25aba.jpg)  
Standardized Residuals

![](images/b160809f3c9374c13aa4b1730c237b7eaba7adef38b4a3c35e0b2461e0ee6ef4.jpg)  
ACF of Residuals

![](images/980c89f266ccfd0bab064d893a649be4c206fd23a27b8abf823e6ca26031a005.jpg)  
Normal Q−Q Plot of Std Residuals

![](images/8ba9eb7b913f296ef30947bb4a0e4845d801f8a606ba9728537d2ad013544fb8.jpg)  
p values for Ljung−Box statistic   
Fig. 3.17. Diagnostics of the residuals from MA(2) fit on GNP growth rate.

some possibilities in Chapters 5 and 6. The diagnostics shown in Figure 3.17 are a by-product of the sarima command from the previous example.9

# Example 3.40 Diagnostics for the Glacial Varve Series

In Example 3.32, we fit an ARIMA $( 0 , 1 , 1 )$ model to the logarithms of the glacial varve data and there appears to be a small amount of autocorrelation left in the residuals and the Q-tests are all significant; see Figure 3.18.

To adjust for this problem, we fit an ARIMA $( 1 , 1 , 1 )$ to the logged varve data and obtained the estimates

$$
\widehat {\phi} = . 2 3 _ {(. 0 5)}, \widehat {\theta} = -. 8 9 _ {(. 0 3)}, \widehat {\sigma} _ {w} ^ {2} = . 2 3.
$$

Hence the AR term is significant. The Q-statistic p-values for this model are also displayed in Figure 3.18, and it appears this model fits the data well.

As previously stated, the diagnostics are byproducts of the individual sarima runs. We note that we did not fit a constant in either model because

![](images/63ae60db7f0b08879b571e713edfb47f22bc325056aaa176a5dda9e07ea1d800.jpg)

![](images/46b0d9019ed0f5bd12807c2c8322bbc6988011828bdf74044ba5291262f114f4.jpg)  
Fig. 3.18. Q-statistic $p$ -values for the ARIMA $( 0 , 1 , 1 )$ fit [top] and the ARIMA $( 1 , 1 , 1 )$ fit [bottom] to the logged varve data.

there is no apparent drift in the differenced, logged varve series. This fact can be verified by noting the constant is not significant when the command no.constant=TRUE is removed in the code:

1 sarima(log(varve), 0, 1, 1, no.constant=TRUE) # ARIMA(0,1,1)   
2 sarima(log(varve), 1, 1, 1, no.constant=TRUE) # ARIMA(1,1,1)

In Example 3.38, we have two competing models, an AR(1) and an MA(2) on the GNP growth rate, that each appear to fit the data well. In addition, we might also consider that an AR(2) or an MA(3) might do better for forecasting. Perhaps combining both models, that is, fitting an ARMA(1, 2) to the GNP growth rate, would be the best. As previously mentioned, we have to be concerned with overfitting the model; it is not always the case that more is better. Overfitting leads to less-precise estimators, and adding more parameters may fit the data better but may also lead to bad forecasts. This result is illustrated in the following example.

# Example 3.41 A Problem with Overfitting

Figure 3.19 shows the U.S. population by official census, every ten years from 1910 to 1990, as points. If we use these nine observations to predict the future population, we can use an eight-degree polynomial so the fit to the nine observations is perfect. The model in this case is

$$
x _ {t} = \beta_ {0} + \beta_ {1} t + \beta_ {2} t ^ {2} + \dots + \beta_ {8} t ^ {8} + w _ {t}.
$$

The fitted line, which is plotted in the figure, passes through the nine observations. The model predicts that the population of the United States will be close to zero in the year 2000, and will cross zero sometime in the year 2002!

![](images/577c7b509a4a81cac646ebfe2a65262e2852d6eab6ff2474a99bf98cc35a2ba6.jpg)  
U.S. Population by Official Census   
Fig. 3.19. A perfect fit and a terrible forecast.

The final step of model fitting is model choice or model selection. That is, we must decide which model we will retain for forecasting. The most popular techniques, AIC, AICc, and BIC, were described in 2.2 in the context of regression models.

# Example 3.42 Model Choice for the U.S. GNP Series

Returning to the analysis of the U.S. GNP data presented in Examples 3.38 and 3.39, recall that two models, an AR(1) and an MA(2), fit the GNP growth rate well. To choose the final model, we compare the AIC, the AICc, and the BIC for both models. These values are a byproduct of the sarima runs displayed at the end of Example 3.38, but for convenience, we display them again here (recall the growth rate data are in gnpgr):

1 sarima(gnpgr, 1, 0, 0) # AR(1)

$AIC: -8.294403 $AICc: -8.284898 $BIC: -9.263748

2 sarima(gnpgr, 0, 0, 2) # MA(2)

$AIC: -8.297693 $AICc: -8.287854 $BIC: -9.251711

The AIC and AICc both prefer the MA(2) fit, whereas the BIC prefers the simpler AR(1) model. It is often the case that the BIC will select a model of smaller order than the AIC or AICc. It would not be unreasonable in this case to retain the AR(1) because pure autoregressive models are easier to work with.

# 3.9 Multiplicative Seasonal ARIMA Models

In this section, we introduce several modifications made to the ARIMA model to account for seasonal and nonstationary behavior. Often, the dependence on the past tends to occur most strongly at multiples of some underlying seasonal lag $s$ . For example, with monthly economic data, there is a strong yearly component occurring at lags that are multiples of $s ~ = ~ 1 2$ , because of the strong connections of all activity to the calendar year. Data taken quarterly will exhibit the yearly repetitive period at $s = 4$ quarters. Natural phenomena such as temperature also have strong components corresponding to seasons. Hence, the natural variability of many physical, biological, and economic processes tends to match with seasonal fluctuations. Because of this, it is appropriate to introduce autoregressive and moving average polynomials that identify with the seasonal lags. The resulting pure seasonal autoregressive moving average model, say, ARMA $( P , Q ) _ { s }$ , then takes the form

$$
\Phi_ {P} \left(B ^ {s}\right) x _ {t} = \Theta_ {Q} \left(B ^ {s}\right) w _ {t}, \tag {3.155}
$$

with the following definition.

Definition 3.12 The operators

$$
\Phi_ {P} \left(B ^ {s}\right) = 1 - \Phi_ {1} B ^ {s} - \Phi_ {2} B ^ {2 s} - \dots - \Phi_ {P} B ^ {P s} \tag {3.156}
$$

and

$$
\Theta_ {Q} \left(B ^ {s}\right) = 1 + \Theta_ {1} B ^ {s} + \Theta_ {2} B ^ {2 s} + \dots + \Theta_ {Q} B ^ {Q s} \tag {3.157}
$$

are the seasonal autoregressive operator and the seasonal moving average operator of orders $P$ and $Q$ , respectively, with seasonal period $s$ .

Analogous to the properties of nonseasonal ARMA models, the pure seasonal $\mathrm { A R M A } ( P , Q ) _ { s }$ is causal only when the roots of $\varPhi _ { P } ( z ^ { s } )$ lie outside the unit circle, and it is invertible only when the roots of $\Theta _ { Q } ( z ^ { s } )$ lie outside the unit circle.

# Example 3.43 A Seasonal ARMA Series

A first-order seasonal autoregressive moving average series that might run over months could be written as

$$
(1 - \varPhi B ^ {1 2}) x _ {t} = (1 + \Theta B ^ {1 2}) w _ {t}
$$

or

$$
x _ {t} = \varPhi x _ {t - 1 2} + w _ {t} + \Theta w _ {t - 1 2}.
$$

This model exhibits the series $x _ { t }$ in terms of past lags at the multiple of the yearly seasonal period $s = 1 2$ months. It is clear from the above form that estimation and forecasting for such a process involves only straightforward modifications of the unit lag case already treated. In particular, the causal condition requires $| \varPhi | < 1$ , and the invertible condition requires $| \Theta | < 1$ .

Table 3.3. Behavior of the ACF and PACF for Pure SARMA Models   

<table><tr><td></td><td>AR(P)s</td><td>MA(Q)s</td><td>ARMA(P,Q)s</td></tr><tr><td>ACF*</td><td>Tails off at lags ks, k = 1,2,...,</td><td>Cuts off after lag Qs</td><td>Tails off at lags ks</td></tr><tr><td>PACF*</td><td>Cuts off after lag Ps</td><td>Tails off at lags ks k = 1,2,...,</td><td>Tails off at lags ks</td></tr></table>

*The values at nonseasonal lags $h \neq k s$ , for $k = 1 , 2 , \ldots$ , are zero.

For the first-order seasonal ( $s = 1 2$ ) MA model, $x _ { t } = w _ { t } + \Theta w _ { t - 1 2 }$ , it is easy to verify that

$$
\begin{array}{l} \gamma (0) = (1 + \Theta^ {2}) \sigma^ {2} \\ \gamma (\pm 1 2) = \Theta \sigma^ {2} \\ \gamma (h) = 0, \quad \text {o t h e r w i s e}. \\ \end{array}
$$

Thus, the only nonzero correlation, aside from lag zero, is

$$
\rho (\pm 1 2) = \Theta / (1 + \Theta^ {2}).
$$

For the first-order seasonal ( $s = 1 2$ ) AR model, using the techniques of the nonseasonal AR(1), we have

$$
\begin{array}{l} \gamma (0) = \sigma^ {2} / (1 - \Phi^ {2}) \\ \gamma (\pm 1 2 k) = \sigma^ {2} \Phi^ {k} / (1 - \Phi^ {2}) \quad k = 1, 2, \dots \\ \gamma (h) = 0, \quad \text {o t h e r w i s e}. \\ \end{array}
$$

In this case, the only non-zero correlations are

$$
\rho (\pm 1 2 k) = \Phi^ {k}, \quad k = 0, 1, 2, \dots .
$$

These results can be verified using the general result that $\gamma ( h ) = \varPhi \gamma ( h - 1 2 )$ , for $h \geq 1$ . For example, when $h = 1$ , $\gamma ( 1 ) = \varPhi \gamma ( 1 1 )$ , but when $h = 1 1$ , we have $\gamma ( 1 1 ) = \varPhi \gamma ( 1 )$ , which implies that $\gamma ( 1 ) = \gamma ( 1 1 ) = 0$ . In addition to these results, the PACF have the analogous extensions from nonseasonal to seasonal models.

As an initial diagnostic criterion, we can use the properties for the pure seasonal autoregressive and moving average series listed in Table 3.3. These properties may be considered as generalizations of the properties for nonseasonal models that were presented in Table 3.1.

In general, we can combine the seasonal and nonseasonal operators into a multiplicative seasonal autoregressive moving average model, denoted by ARMA $( p , q ) \times ( P , Q ) _ { s }$ , and write

$$
\Phi_ {P} \left(B ^ {s}\right) \phi (B) x _ {t} = \Theta_ {Q} \left(B ^ {s}\right) \theta (B) w _ {t} \tag {3.158}
$$

as the overall model. Although the diagnostic properties in Table 3.3 are not strictly true for the overall mixed model, the behavior of the ACF and PACF tends to show rough patterns of the indicated form. In fact, for mixed models, we tend to see a mixture of the facts listed in Tables 3.1 and 3.3. In fitting such models, focusing on the seasonal autoregressive and moving average components first generally leads to more satisfactory results.

# Example 3.44 A Mixed Seasonal Model

Consider an ARMA $( 0 , 1 ) \times ( 1 , 0 ) _ { 1 2 }$ model

$$
x _ {t} = \varPhi x _ {t - 1 2} + w _ {t} + \theta w _ {t - 1},
$$

| | lated, and where $| \varPhi | < 1$ $x _ { t }$ | |   is stationary, and $| \theta | < 1$ . Then, because $\gamma ( 0 ) = \varPhi ^ { 2 } \gamma ( 0 ) + \sigma _ { w } ^ { 2 } + \theta ^ { 2 } \sigma _ { w } ^ { 2 }$ $x _ { t - 1 2 }$ , $w _ { t }$ , and , o $w _ { t - 1 }$ are uncorre-

$$
\gamma (0) = \frac {1 + \theta^ {2}}{1 - \varPhi^ {2}} \sigma_ {w} ^ {2}.
$$

In addition, multiplying the model by $x _ { t - h }$ , $h > 0$ , and taking expectations, we have $\gamma ( 1 ) = \varPhi \gamma ( 1 1 ) + \theta \sigma _ { w } ^ { 2 }$ , and $\gamma ( h ) = \varPhi \gamma ( h - 1 2 )$ , for $h \geq 2$ . Thus, the ACF for this model is

$$
\begin{array}{l} \rho (1 2 h) = \varPhi^ {h} \quad h = 1, 2, \dots \\ \rho (1 2 h - 1) = \rho (1 2 h + 1) = \frac {\theta}{1 + \theta^ {2}} \Phi^ {h} \quad h = 0, 1, 2, \dots , \\ \rho (h) = 0, \quad \text {o t h e r w i s e}. \\ \end{array}
$$

The ACF and PACF for this model, with $\phi = . 8$ and $\theta = - . 5$ , are shown in Figure 3.20. These type of correlation relationships, although idealized here, are typically seen with seasonal data.

To reproduce Figure 3.20 in R, use the following commands:

1 phi = c(rep(0,11),.8)   
2 ACF $=$ ARMAacf(ar=phi, ma=-.5, 50)[-1] # $\boldsymbol { L }$ -1] removes 0 lag   
3 PACF $=$ ARMAacf(ar=phi, ma=-.5, 50, pacf=TRUE)  
4 par(mfrow=c(1,2))  
5 plot(ACF, type="h", xlab="lag", ylim=c(-.4,.8)); abline(h=0)   
6 plot(PACF, type="h", xlab="lag", ylim=c(-.4,.8)); abline(h=0)

Seasonal nonstationarity can occur, for example, when the process is nearly periodic in the season. For example, with average monthly temperatures over the years, each January would be approximately the same, each February would be approximately the same, and so on. In this case, we might think of average monthly temperature $x _ { t }$ as being modeled as

$$
x _ {t} = S _ {t} + w _ {t},
$$

where $S _ { t }$ is a seasonal component that varies slowly from one year to the next, according to a random walk,

![](images/57e8b8497d1110b671334930b81a4c6dc3b175aeb32d380bfa5b24a54f983729.jpg)

![](images/00e121f1ba89f42203ed89743f731f8b7a7734488bbf6768ec12ef0e7cdf06ce.jpg)  
Fig. 3.20. ACF and PACF of the mixed seasonal ARMA model $x _ { t } = . 8 x _ { t - 1 2 } +$ $w _ { t } - . 5 w _ { t - 1 }$ .

$$
S _ {t} = S _ {t - 1 2} + v _ {t}.
$$

In this model, $w _ { t }$ and $v _ { t }$ are uncorrelated white noise processes. The tendency of data to follow this type of model will be exhibited in a sample ACF that is large and decays very slowly at lags $h = 1 2 k$ , for $k = 1 , 2 , \ldots$ . If we subtract the effect of successive years from each other, we find that

$$
(1 - B ^ {1 2}) x _ {t} = x _ {t} - x _ {t - 1 2} = v _ {t} + w _ {t} - w _ {t - 1 2}.
$$

This model is a stationary $\mathrm { M A } ( 1 ) _ { 1 2 }$ , and its ACF will have a peak only at lag 12. In general, seasonal differencing can be indicated when the ACF decays slowly at multiples of some season $s$ , but is negligible between the periods. Then, a seasonal difference of order D is defined as

$$
\nabla_ {s} ^ {D} x _ {t} = \left(1 - B ^ {s}\right) ^ {D} x _ {t}, \tag {3.159}
$$

where $D = 1 , 2 , \ldots$ , takes positive integer values. Typically, $D = 1$ is sufficient to obtain seasonal stationarity. Incorporating these ideas into a general model leads to the following definition.

Definition 3.13 The multiplicative seasonal autoregressive integrated moving average model, or SARIMA model is given by

$$
\Phi_ {P} \left(B ^ {s}\right) \phi (B) \nabla_ {s} ^ {D} \nabla^ {d} x _ {t} = \delta + \Theta_ {Q} \left(B ^ {s}\right) \theta (B) w _ {t}, \tag {3.160}
$$

where $w _ { t }$ is the usual Gaussian white noise process. The general model is denoted as ARIMA $( p , d , q ) \times ( P , D , Q ) _ { s }$ . The ordinary autoregressive and moving average components are represented by polynomials $\phi ( B )$ and $\theta ( B )$ of orders $p$ and $q$ , respectively [see (3.5) and (3.18)], and the seasonal autoregressive and moving average components by $\varPhi _ { P } ( B ^ { s } )$ and $\Theta _ { Q } ( B ^ { s } )$ [see (3.156) and (3.157)] of orders $P$ and $Q$ and ordinary and seasonal difference components by $\nabla ^ { d } = ( 1 - B ) ^ { d }$ and $\nabla _ { s } ^ { D } = ( 1 - B ^ { s } ) ^ { D }$ .

![](images/e4df0a2444f012d2cd6e7e491f60a2889dde250a8b92b38dd1d9fe66100efbde.jpg)

![](images/f85e7c70c731859039fe33d77f8d3d0146db1af6acd0fa52f8d61af929521bfe.jpg)  
Fig. 3.21. Values of the Monthly Federal Reserve Board Production Index and Unemployment (1948-1978, $n = 3 7 2$ months).

# Example 3.45 An SARIMA Model

Consider the following model, which often provides a reasonable representation for seasonal, nonstationary, economic time series. We exhibit the equations for the model, denoted by ARIM $\mathbf { \boldsymbol { \mathrm { \Lambda } } } ( 0 , 1 , 1 ) \times ( 0 , 1 , 1 ) _ { 1 2 }$ in the notation given above, where the seasonal fluctuations occur every 12 months. Then, the model (3.160) becomes

$$
(1 - B ^ {1 2}) (1 - B) x _ {t} = (1 + \Theta B ^ {1 2}) (1 + \theta B) w _ {t}. \tag {3.161}
$$

Expanding both sides of (3.161) leads to the representation

$$
(1 - B - B ^ {1 2} + B ^ {1 3}) x _ {t} = (1 + \theta B + \Theta B ^ {1 2} + \Theta \theta B ^ {1 3}) w _ {t},
$$

or in difference equation form

$$
x _ {t} = x _ {t - 1} + x _ {t - 1 2} - x _ {t - 1 3} + w _ {t} + \theta w _ {t - 1} + \Theta w _ {t - 1 2} + \Theta \theta w _ {t - 1 3}.
$$

Note that the multiplicative nature of the model implies that the coefficient of $w _ { t - 1 3 }$ is the product of the coefficients of $w _ { t - 1 }$ and $w _ { t - 1 2 }$ rather than a free parameter. The multiplicative model assumption seems to work well with many seasonal time series data sets while reducing the number of parameters that must be estimated.

Selecting the appropriate model for a given set of data from all of those represented by the general form (3.160) is a daunting task, and we usually

![](images/2f8efe0555852a555c0621210a2d37e34dec62e94259bf8b85d999aeb6486454.jpg)

![](images/e1509e24c969904060478fe73c1fdfae5747e1d0e68e815c94c39de56900099a.jpg)  
Fig. 3.22. ACF and PACF of the production series.

think first in terms of finding difference operators that produce a roughly stationary series and then in terms of finding a set of simple autoregressive moving average or multiplicative seasonal ARMA to fit the resulting residual series. Differencing operations are applied first, and then the residuals are constructed from a series of reduced length. Next, the ACF and the PACF of these residuals are evaluated. Peaks that appear in these functions can often be eliminated by fitting an autoregressive or moving average component in accordance with the general properties of Tables 3.1 and 3.2. In considering whether the model is satisfactory, the diagnostic techniques discussed in 3.8 still apply.

# Example 3.46 The Federal Reserve Board Production Index

A problem of great interest in economics involves first identifying a model within the Box–Jenkins class for a given time series and then producing forecasts based on the model. For example, we might consider applying this methodology to the Federal Reserve Board Production Index shown in Figure 3.21. For demonstration purposes only, the ACF and PACF for this series are shown in Figure 3.22. We note that the trend in the data, the slow decay in the ACF, and the fact that the PACF at the first lag is nearly 1, all indicate nonstationary behavior.

Following the recommended procedure, a first difference was taken, and the ACF and PACF of the first difference

$$
\nabla x _ {t} = x _ {t} - x _ {t - 1}
$$

![](images/5fdf5ccdcebb93e16d6a5e78159aae89582603bb410bf8c0adf8cde6b59d8045.jpg)

![](images/6ab82d04355dc2c69a6a424a5bc353a3c1bb75b0ed62a92b35c1e4833c6ded47.jpg)  
Fig. 3.23. ACF and PACF of differenced production, $( 1 - B ) x _ { t }$ .

are shown in Figure 3.23. Noting the peaks at seasonal lags, $h = 1 s , 2 s , 3 s , 4 s$ where $s = 1 2$ (i.e., $h = 1 2 , 2 4 , 3 6 , 4 8$ ) with relatively slow decay suggests a seasonal difference. Figure 3.24 shows the ACF and PACF of the seasonal difference of the differenced production, say,

$$
\nabla_ {1 2} \nabla x _ {t} = (1 - B ^ {1 2}) (1 - B) x _ {t}.
$$

First, concentrating on the seasonal ( $s = 1 2$ ) lags, the characteristics of the ACF and PACF of this series tend to show a strong peak at $h = 1 s$ in the autocorrelation function, with smaller peaks appearing at $h = 2 s , 3 s$ , combined with peaks at $h \ = \ 1 s , 2 s , 3 s , 4 s$ in the partial autocorrelation function. It appears that either

(i) the ACF is cutting off after lag $_ { 1 s }$ and the PACF is tailing off in the seasonal lags,   
(ii) the ACF is cutting off after lag 3s and the PACF is tailing off in the seasonal lags, or   
(iii) the ACF and PACF are both tailing off in the seasonal lags.

Using Table 3.3, this suggests either (i) an SMA of order $Q = 1$ , (ii) an SMA of order $Q = 3$ , or (iii) an SARMA of orders $P = 2$ (because of the two spikes in the PACF) and $Q = 1$ .

Next, inspecting the ACF and the PACF at the within season lags, $h =$ $1 , \ldots , 1 1$ , it appears that either (a) both the ACF and PACF are tailing off, or (b) that the PACF cuts off at lag 2. Based on Table 3.1, this result indicates that we should either consider fitting a model (a) with both $p > 0$ and $q > 0$ for the nonseasonal components, say $p = 1 , q = 1$ , or (b) $p =$

![](images/420f724480c05aec78294dcc593a0ca66becd9f59be4f49441c387fe4ea5593e.jpg)

![](images/0f372e17811c9f91a025b7a7e01f4c7c701a37d8b2d17d29dbce07e338d8fe77.jpg)  
Fig. 3.24. ACF and PACF of first differenced and then seasonally differenced production, $( 1 - B ) ( 1 - B ^ { 1 2 } ) x _ { t }$ .

$2 , q = 0$ . It turns out that there is little difference in the results for case (a) and (b), but that (b) is slightly better, so we will concentrate on case (b).

Fitting the three models suggested by these observations we obtain:

(i) $\mathrm { A R I M A } ( 2 , 1 , 0 ) \times ( 0 , 1 , 1 ) _ { 1 2 }$ :

$$
\mathrm {A I C} = 1. 3 7 2, \mathrm {A I C c} = 1. 3 7 8, \mathrm {B I C} = . 4 0 4
$$

(ii) $\mathrm { A R I M A } ( 2 , 1 , 0 ) \times ( 0 , 1 , 3 ) _ { 1 2 }$

$$
\mathrm {A I C} = 1. 2 9 9, \mathrm {A I C c} = 1. 3 0 5, \mathrm {B I C} = . 3 5 1
$$

(iii) ARIMA(2, 1, 0) × (2, 1, 1)12:

$$
\mathrm {A I C} = 1. 3 2 6, \mathrm {A I C c} = 1. 3 3 2, \mathrm {B I C} = . 3 7 9
$$

The $\mathrm { A R I M A ( 2 , 1 , 0 ) \times ( 0 , 1 , 3 ) _ { 1 2 } }$ is the preferred model, and the fitted model in this case is

$$
\begin{array}{l} (1 -. 3 0 _ {(. 0 5)} B -. 1 1 _ {(. 0 5)} B ^ {2}) \nabla_ {1 2} \nabla \widehat {x} _ {t} \\ = (1 -. 7 4 _ {(. 0 5)} B ^ {1 2} -. 1 4 _ {(. 0 6)} B ^ {2 4} +. 2 8 _ {(. 0 5)} B ^ {3 6}) \widehat {w} _ {t} \\ \end{array}
$$

with $\widehat { \sigma } _ { w } ^ { 2 } = 1 . 3 1 2$

b The diagnostics for the fit are displayed in Figure 3.25. We note the few outliers in the series as exhibited in the plot of the standardized residuals and their normal Q-Q plot, and a small amount of autocorrelation that still remains (although not at the seasonal lags) but otherwise, the model fits well. Finally, forecasts based on the fitted model for the next 12 months are shown in Figure 3.26.

![](images/c0c50740347d56ca49cccba9a41c56b6e4b6cbcaa061b62fcc21f5b4623469cb.jpg)  
Standardized Residuals

![](images/05987d8485b95085a5a0761023a8534a3ef843960fde576e3979531d03d4e3f1.jpg)

![](images/d2a6b2a7b0c8adc0354fc94ed391bb11bb3818fa9257691a58832e207f9980f6.jpg)

![](images/b714cda48273592c6332d9f2bbf729d3eb5cdbddad6aea5d7d0f7f8dabf0b965.jpg)  
Fig. 3.25. Diagnostics for the AR $\mathrm { I M A ( 2 , 1 , 0 ) \times ( 0 , 1 , 3 ) _ { 1 2 } }$ fit on the Production Index.

The following R code can be used to perform the analysis.

1 acf2(prodn, 48)   
2 acf2(diff(prodn), 48)   
3 acf2(diff(diff(prodn), 12), 48)   
4 sarima(prodn, 2, 1, 1, 0, 1, 3, 12) # fit model (ii)   
5 sarima.for(prodn, 12, 2, 1, 1, 0, 1, 3, 12) # forecast

# Problems

# Section 3.2

3.1 For an MA(1), ${ x _ { t } } = { w _ { t } } + \theta { w _ { t - 1 } }$ , show that $| \rho _ { x } ( 1 ) | \leq 1 / 2$ for any number $\theta$ . For which values of $\theta$ does $\rho _ { x } ( 1 )$ attain its maximum and minimum?   
3.2 Let $w _ { t }$ be white noise with variance $\sigma _ { w } ^ { 2 }$ and let $| \phi | < 1$ be a constant. Consider the process $x _ { 1 } = w _ { 1 }$ , and

$$
x _ {t} = \phi x _ {t - 1} + w _ {t}, \quad t = 2, 3, \dots .
$$

![](images/21512f74b761931678604ac84501567a76c6333535053538a74d689007cc376e.jpg)  
Fig. 3.26. Forecasts and limits for production index. The vertical dotted line separates the data from the predictions.

(a) Find the mean and the variance of $\{ x _ { t } , \ t = 1 , 2 , . . . \}$ . Is $x _ { t }$ stationary?   
(b) Show

$$
\mathrm {c o r r} (x _ {t}, x _ {t - h}) = \phi^ {h} \left[ \frac {\mathrm {v a r} (x _ {t - h})}{\mathrm {v a r} (x _ {t})} \right] ^ {1 / 2}
$$

for $h \geq 0$ .

(c) Argue that for large $t$ ,

$$
\operatorname {v a r} (x _ {t}) \approx \frac {\sigma_ {w} ^ {2}}{1 - \phi^ {2}}
$$

and

$$
\operatorname {c o r r} \left(x _ {t}, x _ {t - h}\right) \approx \phi^ {h}, \quad h \geq 0,
$$

so in a sense, $x _ { t }$ is “asymptotically stationary.”

(d) Comment on how you could use these results to simulate $n$ observations of a stationary Gaussian AR(1) model from simulated iid N(0,1) values.   
(e) Now suppose $x _ { 1 } = w _ { 1 } / \sqrt { 1 - \phi ^ { 2 } }$ . Is this process stationary?

3.3 Verify the calculations made in Example 3.3:

(a) Let $x _ { t } = \phi x _ { t - 1 } + w _ { t }$ where $| \phi | > 1$ and $w _ { t } \sim$ iid N $\textstyle \int ( 0 , \sigma _ { w } ^ { 2 } )$ . Show $E ( x _ { t } ) = 0$ and $\gamma _ { x } ( h ) = \sigma _ { w } ^ { 2 } \phi ^ { - 2 } \phi ^ { - h } / ( 1 - \phi ^ { - 2 } )$ .   
(b) Let $y _ { t } = \phi ^ { - 1 } y _ { t - 1 } + v _ { t }$ where $v _ { t } \sim$ iid $\mathrm { N } ( 0 , \sigma _ { w } ^ { 2 } \phi ^ { - 2 } )$ and $\phi$ and $\sigma _ { w }$ are as in part (a). Argue that $y _ { t }$ is causal with the same mean function and autocovariance function as $x _ { t }$ .

3.4 Identify the following models as ARMA $( p , q )$ models (watch out for parameter redundancy), and determine whether they are causal and/or invertible:

(a) $x _ { t } = . 8 0 x _ { t - 1 } - . 1 5 x _ { t - 2 } + w _ { t } - . 3 0 w _ { t - 1 } .$   
(b) xt = xt 1 − .50xt 2 + wt − wt 1.

3.5 Verify the causal conditions for an AR(2) model given in (3.28). That is, show that an AR(2) is causal if and only if (3.28) holds.

# Section 3.3

3.6 For the AR(2) model given by $x _ { t } = - . 9 x _ { t - 2 } + w _ { t }$ , find the roots of the autoregressive polynomial, and then sketch the ACF, $\rho ( h )$ .

3.7 For the AR(2) series shown below, use the results of Example 3.9 to determine a set of difference equations that can be used to find the ACF $\rho ( h )$ , $h = 0 , 1 , \ldots$ ; solve for the constants in the ACF using the initial conditions. Then plot the ACF values to lag 10 (use ARMAacf as a check on your answers).

(a) $x _ { t } + 1 . 6 x _ { t - 1 } + . 6 4 x _ { t - 2 } = w _ { t } .$   
( $) ) x _ { t } - . 4 0 x _ { t - 1 } - . 4 5 x _ { t - 2 } = w _ { t } .$   
(c) $x _ { t } - 1 . 2 x _ { t - 1 } + . 8 5 x _ { t - 2 } = w _ { t }$

# Section 3.4

3.8 Verify the calculations for the autocorrelation function of an $\mathrm { A R M A } ( 1 , 1 )$ process given in Example 3.13. Compare the form with that of the ACF for the $\mathrm { A R M A } ( 1 , 0 )$ and the $\mathrm { A R M A } ( 0 , 1 )$ series. Plot (or sketch) the ACFs of the three series on the same graph for $\phi = . 6$ , $\theta = . 9$ , and comment on the diagnostic capabilities of the ACF in this case.   
3.9 Generate $n = 1 0 0$ observations from each of the three models discussed in Problem 3.8. Compute the sample ACF for each model and compare it to the theoretical values. Compute the sample PACF for each of the generated series and compare the sample ACFs and PACFs with the general results given in Table 3.1.

# Section 3.5

3.10 Let $x _ { t }$ represent the cardiovascular mortality series (cmort) discussed in Chapter 2, Example 2.2.

(a) Fit an AR(2) to $x _ { t }$ using linear regression as in Example 3.17.   
(b) Assuming the fitted model in (a) is the true model, find the forecasts over a four-week horizon, $x _ { n + m } ^ { \pi }$ , for $m = 1 , 2 , 3 , 4$ , and the corresponding 95% prediction intervals.

3.11 Consider the MA(1) series

$$
x _ {t} = w _ {t} + \theta w _ {t - 1},
$$

where $w _ { t }$ is white noise with variance $\sigma _ { w } ^ { 2 }$

(a) Derive the minimum mean-square error one-step forecast based on the infinite past, and determine the mean-square error of this forecast.   
(b) Let $\widetilde { x } _ { n + 1 } ^ { n }$ be the truncated one-step-ahead forecast as given in (3.92). Show ethat

$$
E \left[ \left(x _ {n + 1} - \widetilde {x} _ {n + 1} ^ {n}\right) ^ {2} \right] = \sigma^ {2} \left(1 + \theta^ {2 + 2 n}\right).
$$

Compare the result with (a), and indicate how well the finite approximation works in this case.

3.12 In the context of equation (3.63), show that, if $\gamma ( 0 ) > 0$ and $\gamma ( h ) \to 0$ as $h  \infty$ , then $\varGamma _ { n }$ is positive definite.   
3.13 Suppose $x _ { t }$ is stationary with zero mean and recall the definition of the PACF given by (3.55) and (3.56). That is, let

$$
\epsilon_ {t} = x _ {t} - \sum_ {i = 1} ^ {h - 1} a _ {i} x _ {t - i}
$$

and

$$
\delta_ {t - h} = x _ {t - h} - \sum_ {j = 1} ^ {h - 1} b _ {j} x _ {t - j}
$$

be the two residuals where $\{ a _ { 1 } , \dotsc , a _ { h - 1 } \}$ and $\big \{ b _ { 1 } , \dotsc , b _ { h - 1 } \big \}$ are chosen so that they minimize the mean-squared errors

$$
E \left[ \epsilon_ {t} ^ {2} \right] \quad \text {a n d} \quad E \left[ \delta_ {t - h} ^ {2} \right].
$$

The PACF at lag $h$ was defined as the cross-correlation between $\epsilon _ { t }$ and $\delta _ { t - h }$ that is,

$$
\phi_ {h h} = \frac {E \left(\epsilon_ {t} \delta_ {t - h}\right)}{\sqrt {E \left(\epsilon_ {t} ^ {2}\right) E \left(\delta_ {t - h} ^ {2}\right)}}.
$$

Let $R _ { h }$ be the $h \times h$ matrix with elements $\rho ( i - j ) , i , j = 1 , . . . , h$ , and let $\pmb { \rho } _ { h } = ( \rho ( 1 ) , \rho ( 2 ) , \dots , \rho ( h ) ) ^ { \prime }$ be the vector of lagged autocorrelations, $\rho ( h ) =$ $\mathrm { c o r r } ( x _ { t + h } , x _ { t } )$ . Let $\widetilde { \pmb { \rho } } _ { h } = ( \rho ( h ) , \rho ( h - 1 ) , \dots , \rho ( 1 ) ) ^ { \prime }$ be the reversed vector. In addition, let $\boldsymbol { x } _ { t } ^ { h }$ edenote the BLP of $x _ { t }$ given $\{ x _ { t - 1 } , \ldots , x _ { t - h } \}$ :

$$
x _ {t} ^ {h} = \alpha_ {h 1} x _ {t - 1} + \dots + \alpha_ {h h} x _ {t - h},
$$

as described in Property 3.3. Prove

$$
\phi_ {h h} = \frac {\rho (h) - \widetilde {\boldsymbol {\rho}} _ {h - 1} ^ {\prime} R _ {h - 1} ^ {- 1} \boldsymbol {\rho} _ {h}}{1 - \widetilde {\boldsymbol {\rho}} _ {h - 1} ^ {\prime} R _ {h - 1} ^ {- 1} \widetilde {\boldsymbol {\rho}} _ {h - 1}} = \alpha_ {h h}.
$$

In particular, this result proves Property 3.4.

Hint: Divide the prediction equations [see (3.63)] by $\gamma ( 0 )$ and write the matrix equation in the partitioned form as

$$
\left( \begin{array}{c c} R _ {h - 1} & \widetilde {\boldsymbol {\rho}} _ {h - 1} \\ \widetilde {\boldsymbol {\rho}} _ {h - 1} ^ {\prime} & \rho (0) \end{array} \right) \left( \begin{array}{c} \boldsymbol {\alpha} _ {1} \\ \alpha_ {h h} \end{array} \right) = \left( \begin{array}{c} \boldsymbol {\rho} _ {h - 1} \\ \rho (h) \end{array} \right),
$$

where the $h \times 1$ vector of coefficients ${ \pmb { \alpha } } = ( \alpha _ { h 1 } , . . . , \alpha _ { h h } ) ^ { \prime }$ is partitioned as ${ \pmb { \alpha } } = ( { \pmb { \alpha } } _ { 1 } ^ { \prime } , \alpha _ { h h } ) ^ { \prime }$ .

3.14 Suppose we wish to find a prediction function $g ( x )$ that minimizes

$$
M S E = E \left[ (y - g (x)) ^ {2} \right],
$$

where $x$ and $y$ are jointly distributed random variables with density function $f ( x , y )$ .

(a) Show that MSE is minimized by the choice

$$
g (x) = E (y \mid x).
$$

Hint:

$$
M S E = \int \left[ \int (y - g (x)) ^ {2} f (y | x) d y \right] f (x) d x.
$$

(b) Apply the above result to the model

$$
y = x ^ {2} + z,
$$

where $x$ and $z$ are independent zero-mean normal variables with variance one. Show that $M S E = 1$ .

(c) Suppose we restrict our choices for the function $g ( x )$ to linear functions of the form

$$
g (x) = a + b x
$$

and determine $a$ and $b$ to minimize $M S E$ . Show that $a = 1$ and

$$
b = \frac {E (x y)}{E (x ^ {2})} = 0
$$

and $M S E = 3$ . What do you interpret this to mean?

3.15 For an AR(1) model, determine the general form of the $m$ -step-ahead forecast $\boldsymbol x _ { t + m } ^ { t }$ and show

$$
E [ (x _ {t + m} - x _ {t + m} ^ {t}) ^ {2} ] = \sigma_ {w} ^ {2} \frac {1 - \phi^ {2 m}}{1 - \phi^ {2}}.
$$

3.16 Consider the ARMA(1,1) model discussed in Example 3.7, equation (3.27); that is, $x _ { t } = . 9 x _ { t - 1 } + . 5 w _ { t - 1 } + w _ { t }$ . Show that truncated prediction as defined in (3.91) is equivalent to truncated prediction using the recursive formula (3.92).

3.17 Verify statement (3.87), that for a fixed sample size, the ARMA prediction errors are correlated.

# Section 3.6

3.18 Fit an AR(2) model to the cardiovascular mortality series (cmort) discussed in Chapter 2, Example 2.2. using linear regression and using Yule– Walker.

(a) Compare the parameter estimates obtained by the two methods.   
(b) Compare the estimated standard errors of the coefficients obtained by linear regression with their corresponding asymptotic approximations, as given in Property 3.10.

3.19 Suppose $x _ { 1 } , \ldots , x _ { n }$ are observations from an AR(1) process with $\mu = 0$

(a) Show the backcasts can be written as $x _ { t } ^ { n } = \phi ^ { 1 - t } x _ { 1 }$ , for $t \leq 1$   
(b) In turn, show, for $t \leq 1$ , the backcasted errors are

$$
\widehat {w} _ {t} (\phi) = x _ {t} ^ {n} - \phi x _ {t - 1} ^ {n} = \phi^ {1 - t} (1 - \phi^ {2}) x _ {1}.
$$

(c) Use the result of (b) to show $\begin{array} { r } { \sum _ { t = - \infty } ^ { 1 } \widehat { w } _ { t } ^ { 2 } ( \phi ) = ( 1 - \phi ^ { 2 } ) x _ { 1 } ^ { 2 } } \end{array}$   
−∞ b(d) Use the result of (c) to verify the unconditional sum of squares, be written as $\scriptstyle \sum _ { t = - \infty } ^ { n } { \widehat { w } } _ { t } ^ { 2 } ( \phi )$ . $S ( \phi )$ , can   
(e) Find $x _ { t } ^ { t - 1 }$ and $r _ { t }$ −for $1 \leq t \leq n$ , and show that

$$
S (\phi) = \sum_ {t = 1} ^ {n} \left(x _ {t} - x _ {t} ^ {t - 1}\right) ^ {2} / r _ {t}.
$$

3.20 Repeat the following numerical exercise three times. Generate $n = 5 0 0$ observations from the ARMA model given by

$$
x _ {t} = . 9 x _ {t - 1} + w _ {t} - . 9 w _ {t - 1},
$$

with $w _ { t } \sim$ iid $\mathrm { { N } } ( 0 , 1 )$ . Plot the simulated data, compute the sample ACF and PACF of the simulated data, and fit an $\mathrm { A R M A } ( 1 , 1 )$ model to the data. What happened and how do you explain the results?

3.21 Generate 10 realizations of length $n = 2 0 0$ each of an ARMA(1,1) process with $\phi = . 9 , \theta = . 5$ and $\sigma ^ { 2 } = 1$ . Find the MLEs of the three parameters in each case and compare the estimators to the true values.

3.22 Generate $n = 5 0$ observations from a Gaussian AR(1) model with $\phi =$ .99 and $\sigma _ { w } = 1$ . Using an estimation technique of your choice, compare the approximate asymptotic distribution of your estimate (the one you would use for inference) with the results of a bootstrap experiment (use $B = 2 0 0$ ).

3.23 Using Example 3.31 as your guide, find the Gauss–Newton procedure for estimating the autoregressive parameter, $\phi$ , from the AR(1) model, $x _ { t } = \phi x _ { t - 1 } + w _ { t }$ , given data $x _ { 1 } , \ldots , x _ { n }$ . Does this procedure produce the unconditional or the conditional estimator? Hint: Write the model as $w _ { t } ( \phi ) =$ ${ x } _ { t } - \phi { x } _ { t - 1 }$ ; your solution should work out to be a non-recursive procedure.

3.24 Consider the stationary series generated by

$$
x _ {t} = \alpha + \phi x _ {t - 1} + w _ {t} + \theta w _ {t - 1},
$$

t  | |  zero mean and variance where $E ( x _ { t } ) = \mu$ , $| \theta | < 1 , | \phi | < 1$ $\sigma _ { w } ^ { 2 }$ |. and the $w _ { t }$ are iid random variables with

(a) Determine the mean as a function of $\alpha$ for the above model. Find the autocovariance and ACF of the process $x _ { t }$ , and show that the process is weakly stationary. Is the process strictly stationary?   
(b) Prove the limiting distribution as $n \to \infty$ of the sample mean,

$$
\bar {x} = n ^ {- 1} \sum_ {t = 1} ^ {n} x _ {t},
$$

is normal, and find its limiting mean and variance in terms of $\alpha$ , $\phi$ , $\theta$ , and $\sigma _ { w } ^ { 2 }$ . (Note: This part uses results from Appendix A.)

3.25 A problem of interest in the analysis of geophysical time series involves a simple model for observed data containing a signal and a reflected version of the signal with unknown amplification factor $a$ and unknown time delay $\delta$ . For example, the depth of an earthquake is proportional to the time delay $\delta$ for the P wave and its reflected form pP on a seismic record. Assume the signal, say $s _ { t }$ , is white and Gaussian with variance $\sigma _ { s } ^ { 2 }$ , and consider the generating model

$$
x _ {t} = s _ {t} + a s _ {t - \delta}.
$$

(a) Prove the process $x _ { t }$ is stationary. If $| a | < 1$ , show that

$$
s _ {t} = \sum_ {j = 0} ^ {\infty} (- a) ^ {j} x _ {t - \delta j}
$$

is a mean square convergent representation for the signal $s _ { t }$ , for $t \ =$ $1 , \pm 1 , \pm 2 , . . .$ .

(b) If the time delay $\delta$ is assumed to be known, suggest an approximate computational method for estimating the parameters $a$ and $\sigma _ { s } ^ { 2 }$ using maximum likelihood and the Gauss–Newton method.

(c) If the time delay $\delta$ is an unknown integer, specify how we could estimate the parameters including $\sigma _ { w } ^ { 2 } = 1$ $\delta = 5$ . Estimate the integer time delay $\delta$ . Generate a $n = 5 0 0$ point series with $\delta$ by searching over $a = . 9$ , $\delta = 3 , 4 , \dots , 7$

3.26 Forecasting with estimated parameters: Let $x _ { 1 } , x _ { 2 } , \dotsc , x _ { n }$ be a sample of size $n$ from a causal AR(1) process, $x _ { t } = \phi x _ { t - 1 } + w _ { t }$ . Let $\hat { \phi }$ be the Yule–Walker estimator of $\phi$ .

(a) Show $\widehat { \phi } - \phi = O _ { p } ( n ^ { - 1 / 2 } )$ . See Appendix A for the definition of $O _ { p } ( \cdot )$   
(b) Let $x _ { n + 1 } ^ { \pi }$ be the one-step-ahead forecast of $x _ { n + 1 }$ given the data $x _ { 1 } , \ldots , x _ { n }$ based on the known parameter, $\phi$ , and let $\widehat { x } _ { n + 1 } ^ { n }$ be the one-step-ahead forecast when the parameter is replaced by $\hat { \phi }$ b. Show $x _ { n + 1 } ^ { n } - \widehat { x } _ { n + 1 } ^ { n } = O _ { p } ( n ^ { - 1 / 2 } )$

Section 3.7

3.27 Suppose

$$
y _ {t} = \beta_ {0} + \beta_ {1} t + \dots + \beta_ {q} t ^ {q} + x _ {t}, \quad \beta_ {q} \neq 0,
$$

where $x _ { t }$ is stationary. First, show that $\nabla ^ { k } x _ { t }$ is stationary for any $k = 1 , 2 , \ldots { }$ , and then show that $\nabla ^ { k } y _ { t }$ is not stationary for $k < q$ , but is stationary for $k \geq q$ .

3.28 Verify that the IMA(1,1) model given in (3.147) can be inverted and written as (3.148).

3.29 For the ARIMA $( 1 , 1 , 0 )$ model with drift, $( 1 - \phi B ) ( 1 - B ) x _ { t } = \delta + w _ { t }$ , let $y _ { t } = ( 1 - B ) x _ { t } = \nabla x _ { t }$ .

(a) Noting that $y _ { t }$ is AR(1), show that, for $j \geq 1$

$$
y _ {n + j} ^ {n} = \delta \left[ 1 + \phi + \dots + \phi^ {j - 1} \right] + \phi^ {j} y _ {n}.
$$

(b) Use part (a) to show that, for $m = 1 , 2 , \ldots$

$$
x _ {n + m} ^ {n} = x _ {n} + \frac {\delta}{1 - \phi} \Big [ m - \frac {\phi (1 - \phi^ {m})}{(1 - \phi)} \Big ] + (x _ {n} - x _ {n - 1}) \frac {\phi (1 - \phi^ {m})}{(1 - \phi)}.
$$

Hint: From (a), xnn+j $\begin{array} { r } { x _ { n + j } ^ { n } - x _ { n + j - 1 } ^ { n } = \delta \frac { 1 - \phi ^ { j } } { 1 - \phi } + \phi ^ { j } ( x _ { n } - x _ { n - 1 } ) } \end{array}$ . Now sum both sides over $j$ from 1 to $_ { I I }$ .

(c) Use (3.144) to find $P _ { n + m } ^ { n }$ by first showing that $\psi _ { 0 } ^ { * } = 1$ , $\psi _ { 1 } ^ { * } = ( 1 + \phi )$ , and $\psi _ { j } ^ { * } - ( 1 + \phi ) \psi _ { j - 1 } ^ { * } + \phi \psi _ { j - 2 } ^ { * } = 0$ for $j \geq 2$ , in which case $\begin{array} { r } { \psi _ { j } ^ { * } = \frac { 1 - \phi ^ { j + 1 } } { 1 - \phi } } \end{array}$ 1 φj+1 , for $j \geq 1$ . Note that, as in Example 3.36, equation (3.144) is exact here.

3.32, use the first 100 observations and calculate the EWMA, 3.30 For the logarithm of the glacial varve data, say, $x _ { t }$ , presented in Example $\widetilde { \boldsymbol { x } } _ { t + 1 } ^ { t }$ , given in (3.150) for $t = 1 , \ldots , 1 0 0$ , using $\lambda = . 2 5 , . 5 0$ , and .75, and plot the EWMAs and the data superimposed on each other. Comment on the results.

# Section 3.8

3.31 In Example 3.39, we presented the diagnostics for the MA(2) fit to the GNP growth rate series. Using that example as a guide, complete the diagnostics for the AR(1) fit.   
3.32 Crude oil prices in dollars per barrel are in oil; see Appendix R for more details. Fit an ARIMA $( p , d , q )$ model to the growth rate performing all necessary diagnostics. Comment.   
3.33 Fit an ARIMA $( p , d , q )$ model to the global temperature data gtemp performing all of the necessary diagnostics. After deciding on an appropriate model, forecast (with limits) the next 10 years. Comment.   
3.34 One of the series collected along with particulates, temperature, and mortality described in Example 2.2 is the sulfur dioxide series, so2. Fit an ARIMA $( p , d , q )$ model to the data, performing all of the necessary diagnostics. After deciding on an appropriate model, forecast the data into the future four time periods ahead (about one month) and calculate 95% prediction intervals for each of the four forecasts. Comment.

# Section 3.9

3.35 Consider the ARIMA model

$$
x _ {t} = w _ {t} + \Theta w _ {t - 2}.
$$

(a) Identify the model using the notation ARIMA $( p , d , q ) \times ( P , D , Q ) _ { s }$   
(b) Show that the series is invertible for $| \Theta | < 1$ , and find the coefficients in the representation

$$
w _ {t} = \sum_ {k = 0} ^ {\infty} \pi_ {k} x _ {t - k}.
$$

(c) Develop equations for the $m$ -step ahead forecast, $\widetilde { x } _ { n + m }$ , and its variance based on the infinite past, $x _ { n } , x _ { n - 1 } , \ldots .$ .

3.36 Plot (or sketch) the ACF of the seasonal ARIMA $( 0 , 1 ) \times ( 1 , 0 ) _ { 1 2 }$ model with $\phi = . 8$ and $\theta = . 5$ .   
3.37 Fit a seasonal ARIMA model of your choice to the unemployment data (unemp) displayed in Figure 3.21. Use the estimated model to forecast the next 12 months.   
3.38 Fit a seasonal ARIMA model of your choice to the U.S. Live Birth Series (birth). Use the estimated model to forecast the next 12 months.   
3.39 Fit an appropriate seasonal ARIMA model to the log-transformed Johnson and Johnson earnings series (jj) of Example 1.1. Use the estimated model to forecast the next 4 quarters.

The following problems require supplemental material given in Appendix B.

3.40 Suppose $\begin{array} { r } { x _ { t } = \sum _ { j = 1 } ^ { p } \phi _ { j } x _ { t - j } + w _ { t } } \end{array}$ , where $\phi _ { p } \neq 0$ and $w _ { t }$ is white noise such that $w _ { t }$ is uncorrelated with $\{ x _ { k } ; k < t \}$ . Use the Projection Theorem to show that, for $n > p$ , the BLP of $x _ { n + 1 }$ on s $\bar { \beta } \{ x _ { k } , k \leq n \}$ is

$$
\widehat {x} _ {n + 1} = \sum_ {j = 1} ^ {p} \phi_ {j} x _ {n + 1 - j}.
$$

3.41 Use the Projection Theorem to derive the Innovations Algorithm, Property 3.6, equations (3.77)-(3.79). Then, use Theorem B.2 to derive the $m$ -stepahead forecast results given in (3.80) and (3.81).

mean zero and variance 3.42 Consider the series $x _ { t } = w _ { t } - w _ { t - 1 }$ $\sigma _ { w } ^ { 2 }$ t− t−1 t . Suppose we consider the problem of predicting , where $w _ { t }$ is a white noise process with $x _ { n + 1 }$ , based on only $x _ { 1 } , \ldots , x _ { n }$ . Use the Projection Theorem to answer the questions below.

(a) Show the best linear predictor is

$$
x _ {n + 1} ^ {n} = - \frac {1}{n + 1} \sum_ {k = 1} ^ {n} k x _ {k}.
$$

(b) Prove the mean square error is

$$
E \left(x _ {n + 1} - x _ {n + 1} ^ {n}\right) ^ {2} = \frac {n + 2}{n + 1} \sigma_ {w} ^ {2}.
$$

3.43 Use Theorem B.2 and B.3 to verify (3.116).   
3.44 Prove Theorem B.2.   
3.45 Prove Property 3.2.

# Appendix R R Supplement

# R.1 First Things First

If you do not already have R, point your browser to the Comprehensive R Archive Network (CRAN), http://cran.r-project.org/ and download and install it. The installation includes help files and some user manuals. You can find helpful tutorials by following CRAN’s link to Contributed Documentation. If you are new to R/S-PLUS, then $R$ for Beginners by Emmanuel Paradis is a great introduction. There is also a lot of advice out there in cyberspace, but some of it will be outdated because R goes through many revisions.

Next, point your browser to http://www.stat.pitt.edu/stoffer/tsa3/, the website for the text, or one of its mirrors, download tsa3.rda and put it in a convenient place (e.g., the working directory of R).1 This file contains the data sets and scripts that are used in the text. Then, start R and issue the command

1 load("tsa3.rda")

Once you have loaded tsa3.rda, all the files will stay in R as long as you save the workspace when you close R (details in §R.2). If you don’t save the workspace, you will have to reload it. To see what is included in tsa3.rda type

2 ls() # to get a listing of your objects, and

3 tsa3.version # to check the version

Periodically check that your version matches the latest version number (yearmonth-day) on the website. Please note that tsa3.rda is subject to change.

You are free to use the data or to alter the scripts in any way you see fit. We only have two requests: reference the text if you use something from it, and contact us if you find any errors or have suggestions for improvement of the code.

# R.1.1 Included Data Sets

The data sets included in tsa3.rda, listed by the chapter in which they are first presented, are as follows.

# Chapter 1

jj - Johnson & Johnson quarterly earnings per share, 84 quarters (21 years) measured from the first quarter of 1960 to the last quarter of 1980.

EQ5 - Seismic trace of an earthquake [two phases or arrivals along the surface, the primary wave ( $t = 1 , \dots , 1 0 2 4 ,$ ) and the shear wave ( $t = 1 0 2 5 , \dots , 2 0 4 8 )$ ] recorded at a seismic station.

EXP6 - Seismic trace of an explosion (similar details as EQ5).

gtemp - Global mean land-ocean temperature deviations (from 1951-1980 average), measured in degrees centigrade, for the years 1880-2009; data taken from http://data.giss.nasa.gov/gistemp/graphs/

fmri1 - A data frame that consists of fmri bold signals at eight locations (in columns 2-9, column 1 is time period), when a stimulus was applied for 32 seconds and then stopped for 32 seconds. The signal period is 64 seconds and the sampling rate was one observation every 2 seconds for 256 seconds ( $n = 1 2 8$ ).

soi - Southern Oscillation Index (SOI) for a period of 453 months ranging over the years 1950-1987.

rec - Recruitment (number of new fish) associated with SOI.

speech - A small .1 second (1000 points) sample of recorded speech for the phrase $a a a \cdots h h $ .

nyse - Returns of the New York Stock Exchange (NYSE) from February 2, 1984 to December 31, 1991.

soiltemp - A $6 4 \times 3 6$ matrix of surface soil temperatures.

# Chapter 2

oil - Crude oil, WTI spot price FOB (in dollars per barrel), weekly data from 2000 to mid-2010. For definitions and more details, see http://tonto.eia.doe.gov/dnav/pet/pet_pri_spt_s1_w.htm.

gas - New York Harbor conventional regular gasoline weekly spot price FOB (in cents per gallon) over the same time period as oil.

varve - Sedimentary deposits from one location in Massachusetts for 634 years, beginning nearly 12,000 years ago.

cmort - Average weekly cardiovascular mortality in Los Angeles County; 508 six-day smoothed averages obtained by filtering daily values over the 10 year period 1970-1979.

tempr - Temperature series corresponding to cmort.

part - Particulate series corresponding to cmort.

so2 - Sulfur dioxide series corresponding to cmort.

# Chapter 3

prodn - Monthly Federal Reserve Board Production Index (1948-1978, $n =$ 372 months).

unemp - Unemployment series corresponding to prodn.

ar1boot - Data used in Example 3.35 on page 137.

gnp - Quarterly U.S. GNP from 1947(1) to 2002(3), $n = 2 2 3$ observations.

birth - Monthly live births (adjusted) in thousands for the United States, 1948-1979.

# Chapter 4

sunspotz - Biannual smoothed (12-month moving average) number of sunspots from June 1749 to December 1978; $n = 4 5 9$ . The “z” on the end is to distinguish this series from the one included with R (called sunspots).

salt - Salt profiles taken over a spatial grid set out on an agricultural field, 64 rows at 17-ft spacing.

saltemp - Temperature profiles corresponding to salt.

# Chapter 5

arf - 1000 simulated observations from an ARFIMA(1, 1, 0) model with $\phi = . 7 5$ and $d = . 4$ .

flu - Monthly pneumonia and influenza deaths per 10,000 people in the United States for 11 years, 1968 to 1978.

sales - Sales (with lead, a leading indicator), 150 months; taken from Box & Jenkins (1970).

lead - See sales.

econ5 - Data set containing quarterly U.S. unemployment, GNP, consumption, and government and private investment, from 1948-III to 1988- II.

# Chapter 6

ar1miss - Data for Problem 6.14 on page 403.

gtemp2 - Similar to gtemp but the data are based only on surface air temperature data obtained from meteorological stations.

qinfl - Quarterly inflation rate in the Consumer Price Index from 1953-I to 1980-II, $n = 1 1 0$ observations; from Newbold and Bos (1985).

qintr - Quarterly interest rate recorded for Treasury bills over the same period as qinfl.

WBC - Measurements made for 91 days on the three variables, log(white blood count) [WBC], log(platelet) [PLT] and hematocrit [HCT]; taken from Jones (1984).

PLT - See WBC.

HCT - See WBC.

# Chapter 7

beamd - Infrasonic signals from a nuclear explosion. This is a data frame consisting of three columns (which are not time series objects) that are data from different channels. The series names are sensor1, sensor2, sensor3. See Example 7.2 on page 421 for more information.

bnrf1ebv - Nucleotide sequence of the BNRF1 gene of the Epstein-Barr virus (EBV): 1=A, 2=C, 3=G, 4=T. The data are used in 7.9.

bnrf1hvs - Nucleotide sequence of the BNRF1 gene of the herpes virus saimiri (HVS); same codes as for EBV.

fmri - Data (as a vector list) from an fMRI experiment in pain, listed by location and stimulus. The specfic locations of the brain where the signal was measured were [1] Cortex 1: Primary Somatosensory, Contralateral, [2] Cortex 2: Primary Somatosensory, Ipsilateral, [3] Cortex 3: Secondary Somatosensory, Contralateral, [4] Cortex 4: Secondary Somatosensory, Ipsilateral, [5] Caudate, [6] Thalamus 1: Contralateral, [7] Thalamus 2: Ipsilateral, [8] Cerebellum 1: Contralateral and [9] Cerebellum 2: Ipsilateral. The stimuli (and number of subjects in each condition) are [1] Awake-Brush (5 subjects), [2] Awake-Heat (4 subjects), [3] Awake-Shock (5 subjects), [4] Low-Brush (3 subjects), [5] Low-Heat (5 subjects), and [6] Low-Shock (4 subjects). Issue the command summary(fmri) for further details. As an example, fmri$L1T6 (location 1, treatment 6) will show the data for the four subjects receiving the Low-Shock treatment at the Cortex 1 location; note that fmri[[6]] will display the same data. See Examples 7.7–7.9 for examples.

climhyd - Lake Shasta inflow data; see Example 7.1. This is a data frame with column names: Temp, DewPt, CldCvr, WndSpd, Precip, Inflow.

eqexp - This is a data frame of the earthquake and explosion seismic series used throughout the text. The matrix has 17 columns, the first eight are earthquakes, the second eight are explosions, and the last column is the Novaya Zemlya series. The column names are: EQ1, EQ2,...,EQ8; EX1, EX2,...,EX8; NZ.

# R.1.2 Included Scripts

The following scripts are included in tsa3.rda. At the end of the description of each script, a text example that demonstrates the use of the script is given.

lag.plot2(series1, series2, max.lag=0, corr=TRUE, smooth=TRUE)

Produces a grid of scatterplots of one series versus another. If $( x _ { t } , y _ { t } )$ is a vector time series, then lag.plot2(x,y,m) will generate a grid of scatterplots of $x _ { t - h }$ versus $y _ { t }$ for $h = 0 , 1 , . . . , m$ , along with the cross-correlation values (corr=TRUE) and a lowess fit (smooth=TRUE) assuming $x _ { t }$ is in $\mathbf { x }$ and $y _ { t }$ is in y. Note that the first series, $x _ { t }$ , is the one that gets lagged. If you just want the scatterplots and nothing else, then use lag.plot2(x,y,m,corr=FALSE,smooth=FALSE). See Example 2.7 on page 64 for a demonstration.

lag.plot1(series, max.lag=1, corr=TRUE, smooth=TRUE)

Produces a grid of scatterplots of a series versus lagged values of the series. Similar to lag.plot2, the call lag.plot1(x,m) will generate a grid of scatterplots of $x _ { t - h }$ versus $x _ { t }$ for $h = 1 , . . . , m$ , along with the autocorrelation values (corr=TRUE) and a lowess fit (smooth=TRUE). The defaults are the same as lag.plot2; if you don’t want either the correlation values or the lowess fit, you can either use lag.plot1(x,m,corr=FALSE,smooth=FALSE) or R’s lag.plot. See Example 2.7 on page 64 for a demonstration.

acf2(series, max.lag=NULL)

Produces a simultaneous plot (and a printout) of the sample ACF and PACF on the same scale. If x contains $n$ observations, acf2(x) will print and plot the ACF and PACF of $\mathbf { x }$ to the default lag of $\sqrt { n } + 1 0$ (unless $n$ is smaller than 50). The number of lags may be specified, e.g., acf2(x, 33). See Example 3.17 on page 108.

sarima(series, p, d, q, P=0, D=0, $\scriptstyle { \mathsf { Q } } = 0$ , S=-1, details=TRUE,

tol=sqrt(.Machine$double.eps), no.constant=FALSE)

Fits ARIMA models including diagnostics in a short command. If your time series is in x and you want to fit an ARIMA $( p , d , q )$ model to the data, the basic call is sarima(x,p,d,q). The results are the parameter estimates, standard errors, AIC, AICc, BIC (as defined in Chapter 2) and diagnostics. To fit a seasonal ARIMA model, the basic call is sarima(x,p,d,q,P,D,Q,S). So, for example, sarima(x,2,1,0) will fit an ARIMA(2, 1, 0) model to the series in $\mathbf { x }$ , and sarim $\mathbf { a } ( \mathbf { x } , 2 , 1 , 0 , 0 , 1 , 1 , 1 2 )$ will fit a seasonal $\mathrm { A R I M A } ( 2 , 1 , 0 ) \times ( 0 , 1 , 1 ) _ { 1 2 }$ model to the series in x. If you want to look at the innovations (i.e., the residuals) from the fit, they’re stored in innov.

There are three additional options that can be included in the call.

details turns on/off the output from the nonlinear optimization routine, which is optim. The default is TRUE, use details=FALSE to turn off the output; e.g., sarima(x,2,1,0,details=FALSE).   
tol controls the relative tolerance (reltol) used to assess convergence in sarima and sarima.for. The default is tol=sqrt(.Machine$double.eps), the R default. For details, see the help file for optim under the control arguments. For example, sarima(rec,2,0,0,tol=.0001) will speed up the convergence. If there are many parameters to estimate (e.g., seasonal models), the analysis may take a long time using the default.   
no.constant can control whether or not sarima includes a constant in the model. In particular, with sarima, if there is no differencing ( $d = 0$ and $D = 0$ ) you get the mean estimate. If there’s differencing of order one (either $d = 1$ or $D = 1$ , but not both), a constant term is included in the model; this may be overridden by setting this to TRUE; e.g., sarima(x,1,1,0,no.constant=TRUE). In any other situation, no constant or mean term is included in the model. The idea is that if you difference more than once ( $d + D > 1$ ), any drift is likely to be removed.

See Examples 3.38, 3.39, 3.40, 3.42, and 3.46 on pages 145–159 for demonstrations.

sarima.for(series, n.ahead, p, d, q, P=0, D=0, $\scriptstyle { \mathsf { Q } } = 0$ , S=-1,

tol=sqrt(.Machine$double.eps), no.constant=FALSE)

Gives ARIMA forecasts. Similar to sarima, to forecast n.ahead time points from an ARIMA fit to the data in x, the form is sarima.for(x, n.ahead, p, d, q) or sarima.for(x, n.ahead, p, d, q, P, D, Q, S) for a seasonal model. For example, sarima.for(x,5,1,0,1) will forecast five time points ahead for an ARMA(1,1) fit to x. The output prints the forecasts and the standard errors of the forecasts, and supplies a graphic of the forecast with $\pm 2$ prediction error

bounds. The options tol and no.constant are also available. See Example 3.46 on page 159.

spec.arma(ar=0, $\mathtt { m a } = 0$ , var.noise=1, n.freq=500, ...)

Gives the ARMA spectrum (on a log scale), tests for causality, invertibility, and common zeros. The basic call is spec.arma(ar, ma) where ar and ma are vectors containing the model parameters. Use log="no" if you do not want the plot on a log scale. If the model is not causal or invertible an error message is given. If there are common zeros, a spectrum will be displayed and a warning will be given; e.g., spec.arma(ar= .9, $\mathtt { m a } = \ - . 9 .$ ) will yield a warning and the plot will be the spectrum of white noise. The variance of the noise can be changed with var.noise. Finally, the frequencies and the spectral density ordinates are returned invisibly, e.g., spec.arma(ar=.9)$freq and spec.arma(ar=.9)$spec, if you’re interested in the actual values. See Example 4.6 on page 184.

LagReg(input, output, ${ \tt L } = { \tt C }$ (3,3), $\mathtt { M } = 2 0$ , threshold=0, inverse=FALSE)

Performs lagged regression as discussed in Chapter 4, 4.10. For a bivariate series, input is the input series and output is the output series. The degree of smoothing for the spectral estimate is given by L; see spans in the help file for spec.pgram. The number of terms used in the lagged regression approximation is given by M, which must be even. The threshold value is the cut-off used to set small (in absolute value) regression coefficients equal to zero (it is easiest to run LagReg twice, once with the default threshold of zero, and then again after inspecting the resulting coefficients and the corresponding values of the CCF). Setting inverse=TRUE will fit a forward-lagged regression; the default is to run a backward-lagged regression. The script is based on code that was contributed by Professor Doug Wiens, Department of Mathematical and Statistical Sciences, University of Alberta. See Example 4.24 on page 244 for a demonstration.

SigExtract(series, L=c(3,3), M=50, max.freq=.05)

Performs signal extraction and optimal filtering as discussed in Chapter 4, 4.11. The basic function of the script, and the default setting, is to remove frequencies above $1 / 2 0$ (and, in particular, the seasonal frequency of 1 cycle every 12 time points). The time series to be filtered is series, and its sampling frequency is set to unity ( $\varDelta = 1$ ). The values of L and M are the same as in LagReg and max.freq denotes the truncation frequency, which must be larger than 1/M. The filtered series is returned silently; e.g., f.x = SigExtract(x) will store the extracted signal in f.x. The script is based on code that was contributed by Professor Doug Wiens, Department of Mathematical and Statistical Sciences, University of Alberta. See Example 4.25 on page 249 for a demonstration.

Kfilter0(n, y, A, mu0, Sigma0, Phi, cQ, cR)

Returns the filtered values in Property 6.1 on page 326 for the state-space model, (6.1)–(6.2). In addition, the script returns the evaluation of the likelihood at the given parameter values and the innovation sequence. The inputs are n: number of

observations; y: data matrix; A: observation matrix (assumed constant); mu0: initial state mean; Sigma0: initial state variance-covariance matrix; Phi: state transition matrix; cQ: Cholesky decomposition of $Q$ [cQ=chol(Q)]; cR: Cholesky decomposition of $R$ [cR=chol(R)]. Note: The script requires only that $Q$ or $R$ may be reconstructed as t(cQ)%*%cQ or $\mathtt { t } \left( \mathtt { c R } \right) \% * \% \mathtt { c R }$ , which offers a little more flexibility than requiring $Q$ or $R$ to be positive definite. For demonstrations, see Example 6.6 on page 336, Example 6.8 on page 342, and Example 6.10 on page 350.

Ksmooth0(n, y, A, mu0, Sigma0, Phi, cQ, cR)

Returns both the filtered values in Property 6.1 on page 326 and the smoothed values in Property 6.2 on page 330 for the state-space model, (6.1)–(6.2). The inputs are the same as Kfilter0. For demonstrations, see Example 6.5 on page 331, and Example 6.10 on page 350.

EM0(n, y, A, mu0, Sigma0, Phi, cQ, cR, max.iter=50, tol=.01)

Estimation of the parameters in the model (6.1)–(6.2) via the EM algorithm. Most of the inputs are the same as for Ksmooth0 and the script uses Ksmooth0. To control the number of iterations, use max.iter (set to 50 by default) and to control the relative tolerance for determining convergence, use tol (set to .01 by default). For a demonstration, see Example 6.8 on page 342.

Kfilter1(n, y, A, mu0, Sigma0, Phi, Ups, Gam, cQ, cR, input)

Returns the filtered values in Property 6.1 on page 326 for the state-space model, (6.3)–(6.4). In addition, the script returns the evaluation of the likelihood at the given parameter values and the innovation sequence. The inputs are n: number of observations; y: data matrix; A: observation matrix, an array with dim=c(q,p,n); mu0: initial state mean; Sigma0: initial state variance-covariance matrix; Phi: state transition matrix; Ups: state input matrix; Gam: observation input matrix; cQ: Cholesky decomposition of Q; cR: Cholesky decomposition of R [the note in Kfilter0 applies here]; input: matrix of inputs having the same row dimension as y. Set Ups or Gam or input to 0 (zero) if they are not used. For demonstrations, see Example 6.7 on page 338 and Example 6.9 on page 348.

Ksmooth1(n, y, A, mu0, Sigma0, Phi, Ups, Gam, cQ, cR, input)

Returns both the filtered values in Property 6.1 on page 326 and the smoothed values in Property 6.2 on page 330 for the state-space model, (6.3)–(6.4). The inputs are the same as Kfilter1. See Example 6.7 on page 338 and Example 6.9 on page 348.

EM1(n, y, A, mu0, Sigma0, Phi, Ups, Gam, cQ, cR, input, max.iter=50, tol=.01)

Estimation of the parameters in the model (6.3)–(6.4) via the EM algorithm. Most of the inputs are the same as for Ksmooth1 and the script uses Ksmooth1. To control the number of iterations, use max.iter (set to 50 by default) and to control the relative tolerance for determining convergence, use tol (set to .01 by default). For a demonstration, see Example 6.12 on page 357.

Kfilter2(n, y, A, mu0, Sigma0, Phi, Ups, Gam, Theta, cQ, cR, S, input) Returns the filtered values in Property 6.5 on page 354 for the state-space model, (6.97)–(6.99). In addition, the script returns the evaluation of the likelihood at the given parameter values and the innovation sequence. The inputs are similar to Kfilter1, except that the noise covariance matrix, S must be included. For demonstrations, see Example 6.11 on page 356 and Example 6.13 on page 361.

Ksmooth2(n, y, A, mu0, Sigma0, Phi, Ups, Gam, Theta, cQ, cR, S, input) This is the smoother companion to Kfilter2.

SVfilter(n, y, phi0, phi1, sQ, alpha, sR0, mu1, sR1)

Performs the special case switching filter for the stochastic volatility model, (6.173), (6.175)–(6.176). The state parameters are phi0, phi1, sQ $[ \phi _ { 0 } , \phi _ { 1 } , \sigma _ { w } ]$ , and alpha, sR0, mu1, sR1 $[ \alpha , \sigma _ { 0 } , \mu _ { 1 } , \sigma _ { 1 } ]$ are observation equation parameters as presented in Section 6.9. See Example 6.18 page 380 and Example 6.19 page 383.

mvspec(x, spans $=$ NULL, kernel = NULL, taper $\qquad = \ 0$ , pad = 0, fast $=$ TRUE, demean $=$ TRUE, detrend $=$ FALSE, plot $=$ FALSE, na.action $=$ na.fail, ...)

This is spec.pgram with a few changes in the defaults and written so you can extract the estimate of the multivariate spectral matrix as fxx. For example, if $\mathbf { x }$ contains a $p$ -variate time series (i.e., the $p$ columns of x are time series), and you issue the command spec $=$ mvspec(x, spans=3) say, then spec$fxx is an array with dimensions dim=c(p,p,nfreq), where nfreq is the number of frequencies used. If you print spec$fxx, you will see nfreq $p \times p$ spectral matrix estimates. See Example 7.12 on page 461 for a demonstration.

FDR(pvals, qlevel=0.001)

Computes the basic false discovery rate given a vector of p-values; see Example 7.4 on page 427 for a demonstration.

stoch.reg(data, cols.full, cols.red, alpha, L, M, plot.which)

Performs frequency domain stochastic regression discussed in 7.3. Enter the entire data matrix (data), and then the corresponding columns of input series in the full model (cols.full) and in the reduced model (cols.red; use NULL if there are no inputs under the reduced model). The response variable should be the last column of the data matrix, and this need not be specified among the inputs. Other arguments are alpha (test size), L (smoothing), M (number of points in the discretization of the integral) and plot.which $=$ coh or F.stat, to plot either the squared-coherencies or the $F ^ { \prime }$ -statistics. The coefficients of the impulse response function are returned and plotted. The script is based on code that was contributed by Professor Doug Wiens, Department of Mathematical and Statistical Sciences, University of Alberta. See Example 7.1 on page 417 for a demonstration.

# R.2 Getting Started

If you are experienced with R/S-PLUS you can skip this section, and perhaps the rest of this appendix. Otherwise, it is essential to have R up and running before you start this tutorial. The best way to use the rest of this appendix is to start up R and enter the example code as it is presented. Also, you can use the results and help files to get a better understanding of how R works (or doesn’t work). The character $\#$ is used for comments.

The convention throughout the text is that R code is in typewriter font with a small line number in the left margin. Get comfortable, then start her up and try some simple tasks.

1 2+2 #addition [1]5   
2 $5*5 + 2$ #multiplication and addition [1]27   
3 5/5-3 #division and subtraction [1]-2   
4 log(exp(pi)) #log,exponential,pi [1]3.141593   
5 sin(pi/2)#sinusoids [1]1   
6 exp(1)\~(-2) #power [1]0.1353353   
7 sqrt(8) #square root [1]2.828427   
8 1:5 #sequences [1]12345   
9 seq(1，10，by=2） #sequences [1]13579   
10 rep(2,3) #repeat2three times [1]222

Next, we’ll use assignment to make some objects:

```txt
1 x <- 1 + 2 # put 1 + 2 in object x  
2 x = 1 + 2 # same as above with fewer keystrokes  
3 1 + 2 -> x # same  
4 x # view object x  
[1] 3  
5 (y = 9*3) # put 9 times 3 in y and view the result  
[1] 27  
6 (z = rnorm(5,0,1)) # put 5 standard normals into z and print z  
[1] 0.96607946 1.98135811 -0.06064527 0.31028473 0.02046853 
```

To list your objects, remove objects, get help, find out which directory is current (or to change it) or to quit, use the following commands:

1 ls() # list all objects [1] "dummy" "mydata" "x" "y" "z"   
2 ls(pattern $=$ "my") # list every object that contains "my" [1] "dummy" "mydata"   
3 rm(dummy) # remove object "dummy"   
4 help.start() # html help and documentation (use it)   
5 help(exp) # specific help (?exp is the same)   
6 getwd() # get working directory   
7 setwd("/TimeSeries/" # change working directory to TimeSeries   
8 q() # end the session (keep reading)

When you quit, R will prompt you to save an image of your current workspace. Answering “yes” will save all the work you have done so far, and load it up when you next start R. Our suggestion is to answer “yes” even though you will also be loading irrelevant past analyses every time you start R. Keep in mind that you can remove items via rm(). If you do not save the workspace, you will have to reload tsa3.rda as described in §R.1.

To create your own data set, you can make a data vector as follows:

mydata $=$ c(1,2,3,2,1)

Now you have an object called mydata that contains five elements. R calls these objects vectors even though they have no dimensions (no rows, no columns); they do have order and length:

```txt
2 mydata # display the data [1] 1 2 3 2 1  
3 mydata[3] # the third element [1] 3  
4 mydata[3:5] # elements three through five [1] 3 2 1  
5 mydata[-(1:2)] # everything except the first two elements [1] 3 2 1  
6 length(mydata) # number of elements [1] 5  
7 dim(mydata) # no dimensions NULL  
8 mydata = as.matrix(mydata) # make it a matrix  
9 dim(mydata) # now it has dimensions [1] 5 1 
```

It is worth pointing out R’s recycling rule for doing arithmetic. The rule is extremely helpful for shortening code, but it can also lead to mistakes if you are not careful. Here are some examples.

$\mathrm{1x} = \mathrm{c}(1,2,3,4);\quad \mathrm{y} = \mathrm{c}(2,4,6,8);\quad \mathrm{z} = \mathrm{c}(10,20)$ $\begin{array}{rl}\mathbf{x*y}&\#i t's1*2,2*4,3*6,4*8\\ [1]&281832\\ \mathbf{x}/\mathbf{z}&\#i t's1/10,2/20,3/10,4/20\\ [1]&0.10.10.30.2\end{array}$

4 x+z # guess

[1] 11 22 13 24

If you have an external data set, you can use scan or read.table to input the data. For example, suppose you have an ascii (text) data file called dummy.dat in a directory called TimeSeries in your root directory, and the file looks like this:

```txt
12321 90210 
```

1 dummy $=$ scan("dummy.dat") # if TimeSeries is the working directory   
2 (dummy $=$ scan("/TimeSeries/dummy.dat")) # if not, do this

Read 10 items

[1] 1 2 3 2 1 9 0 2 1 0

3 (dummy $=$ read.table("/TimeSeries/dummy.dat"))

```txt
V1 V2 V3 V4 V5 1 2 3 2 1 9 0 2 1 0 
```

There is a difference between scan and read.table. The former produced a data vector of 10 items while the latter produced a data frame with names V1 to V5 and two observations per variate. In this case, if you want to list (or use) the second variate, V2, you would use

4 dummy$V2

[1] 2 0

and so on. You might want to look at the help files ?scan and ?read.table now. Data frames (?data.frame) are “used as the fundamental data structure by most of R’s modeling software.” Notice that R gave the columns of dummy generic names, V1, ..., V5. You can provide your own names and then use the names to access the data without the use of $\$ 1$ as in line 4 above.

5 colnames(dummy) $=$ c("Dog", "Cat", "Rat", "Pig", "Man")   
6 attach(dummy)   
7 Cat

[1] 2 0

R is case sensitive, thus cat and Cat are different. Also, cat is a reserved name (?cat) in R, so using "cat" instead of "Cat" may cause problems later. You may also include a header in the data file to avoid using line 5 above; type ?read.table for further information.

It can’t hurt to learn a little about programming in R because you will see some of it along the way. Consider a simple program that we will call crazy to produce a graph of a sequence of sample means of increasing sample sizes from a Cauchy distribution with location parameter zero. The code is:

1 crazy <- function(num) {   
2 x <- rep(NA, num)  
3 for (n in 1:num) x[n] <- mean(rcauchy(n))   
4 plot(x, type="l", xlab "sample size", ylab="sample mean")   
5 }

![](images/ba8bb461ea2763899a559d4ace2c3f4be42b166c3bbeb90fdd214a3675dcdeea.jpg)  
Fig. R.1. Crazy example.

The first line creates the function crazy and gives it one argument, num, that is the sample size that will end the sequence. Line 2 makes a vector, x, of num missing values NA, that will be used to store the sample means. Line 3 generates n random Cauchy variates [rcauchy(n)], finds the mean of those values, and puts the result into $\mathbf { x } \left[ \mathbf { \bar { n } } \right]$ , the $n$ -th value of x. The process is repeated in a “do loop” num times so that $\mathbf { x } \left[ 1 \right]$ is the sample mean from a sample of size one, x[2] is the sample mean from a sample of size two, and so on, until finally, x[num] is the sample mean from a sample of size num. After the do loop is complete, the fourth line generates a graphic (see Figure R.1). The fifth line closes the function. To use crazy with a limit sample size of 100, for example, type

6 crazy(100)

and you will get a graphic that looks like Figure R.1

You may want to use one of the R packages. In this case you have to first download the package and then install it. For example,

1 install.packages(c("wavethresh", "tseries"))

will download and install the packages wavethresh that we use in Chapter 4 and tseries that we use in Chapter 5; you will be asked to choose the closest mirror to you. To use a package, you have to load it at each start up of R, for example:

2 library(wavethresh) # load the wavethresh package

A good way to get help for a package is to use html help

3 help.start()

and follow the Packages link.

Finally, a word of caution: TRUE and FALSE are reserved words, whereas T and F are initially set to these. Get in the habit of using the words rather than the letters T or F because you may get into trouble if you do something like F = qf(p=.01, df1=3, df2=9), so that F is no longer FALSE, but a quantile of the specified $F ^ { \dagger }$ -distribution.

# R.3 Time Series Primer

In this section, we give a brief introduction on using R for time series. We assume that tsa3.rda has been loaded. To create a time series object, use the command ts. Related commands are as.ts to coerce an object to a time series and is.ts to test whether an object is a time series.

First, make a small data set:

1 (mydata = c(1,2,3,2,1)) # make it and view it [1] 1 2 3 2 1

Now make it a time series:

2 (mydata $=$ as.ts(mydata)) Time Series: Start $\ l = \ 1$ End = 5 Frequency = 1 [1] 1 2 3 2 1

Make it an annual time series that starts in 1950:

3 (mydata $=$ ts(mydata, start=1950)) Time Series: Start $=$ 1950 End $=$ 1954 Frequency = 1 [1] 1 2 3 2 1

Now make it a quarterly time series that starts in 1950-III:

4 (mydata $=$ ts(mydata, start $= _ { \mathtt { C } }$ (1950,3), frequency=4)) Qtr1 Qtr2 Qtr3 Qtr4 1950 1 2 1951 3 2 1

5 time(mydata) # view the sampled times Qtr1 Qtr2 Qtr3 Qtr4 1950 1950.50 1950.75 1951 1951.00 1951.25 1951.50

To use part of a time series object, use window():

6 ( $\mathbf { \nabla } _ { \mathbf { X } } \mathbf { \Psi } =$ window(mydata, start $= _ { \mathtt { C } }$ (1951,1), end=c(1951,3))) Qtr1 Qtr2 Qtr3 1951 3 2 1

Next, we’ll look at lagging and differencing. First make a simple series, $x _ { t }$ 1 $\textbf { x } = \mathtt { t s } ( 1 : 5 )$

Now, column bind (cbind) lagged values of $x _ { t }$ and you will notice that $\mathtt { l a g } ( \mathtt { x } )$ is forward lag, whereas $\boldsymbol { \mathrm { 1 a g } } ( \mathbf { x } , \mathbf { \theta } - \mathbf { 1 } )$ is backward lag (we display the time series attributes in a single row of the output to save space).

2 cbind(x, lag(x), lag(x,-1))

```txt
Time Series: Start = 0 End = 6 Frequency = 1  
x lag(x) lag(x, -1)  
0 NA 1 NA  
1 1 2 NA  
2 2 3 1  
3 3 4 2 <- in this row, for example, x is 3,  
4 4 5 3 lag(x) is ahead at 4, and  
5 5 NA 4 lag(x, -1) is behind at 2  
6 NA NA 5 
```

Compare cbind and ts.intersect:

3 ts.intersect(x, lag(x,1), lag(x,-1))

```txt
Time Series: Start = 2 End = 4 Frequency = 1  
x lag(x, 1) lag(x, -1)  
2 2 3 1  
3 3 4 2  
4 4 5 3 
```

To difference a series, $\nabla x _ { t } = x _ { t } - x _ { t - 1 }$ , use

1 diff(x)

but note that

2 diff(x, 2)

is not second order differencing, it is $x _ { t } - x _ { t - 2 }$ . For second order differencing, that is, $\nabla ^ { 2 } \boldsymbol { x } _ { t }$ , do this:

3 diff(diff(x))

and so on for higher order differencing.

For graphing time series, there a few standard plotting mechanisms that we use repeatedly. If x is a time series, then plot(x) will produce a time plot. If $_ \texttt { x }$ is not a time series object, then plot.ts(x) will coerce it into a time plot as will ts.plot(x). There are differences, which we explore in the following. It would be a good idea to skim the graphical parameters help file (?par) while you are here.2 See Figure R.2 for the resulting graphic.

1 $x = -5:5$ # $x$ is NOT a time series object   
2 $y = 5*\cos (x)$ # neither is y   
3 op $\equiv$ par(mfrow=c(3,2)) # multifigure setup: 3 rows, 2 cols   
4 plot(x, main="plot(x)")   
5 plot(x, y, main="plot(x,y)")   
6 plot.ts(x, main="plot.ts(x)")   
7 plot.ts(x, y, main="plot.ts(x,y)")   
8 ts.plot(x, main="ts.plot(x)")   
9 ts.plot(ts(x), ts(y), col=1:2, main="ts.plot(x,y)")   
10 par(op) # reset the graphics parameters [see footnote]

![](images/5e68c2779f1c8c2778a0e050089f01ae48c0d842059e7f8db2dc53f4ad25d0eb.jpg)

![](images/2c6af2e57bd0726d231045bc8eb6e1ac186c1df63fb9f35d78bdd5354c7a1e4c.jpg)

![](images/b162d91bc71911de82b631694871d9070d42f6adaf4835bbeaf1e6a7a1f2f294.jpg)

![](images/ea68c5b8c100dcfe5205c90052b3bc01f07fe866bd7fc7948d544c68c9a04d44.jpg)

![](images/0813a243cf0698e75c2a0c767be893613c354f40824b6a7acc74243f5d8d0c2b.jpg)

![](images/bc5e8c1958110bee38ff3311bb840100c23f7d334b69991de39fcc15395e7085.jpg)  
Fig. R.2. Demonstration of different R graphic tools for plotting time series.

We will also make use of regression via lm(). First, suppose we want to fit a simple linear regression, $y = \alpha + \beta x + \epsilon$ . In R, the formula is written as $\mathbb { y } ^ { \sim } \mathbb { x }$ :

1 set.seed(1999) # so you can reproduce the result   
2 $\mathrm { ~ \tt ~ { ~ x ~ } ~ } =$ rnorm(10,0,1)   
3 ${ \textbf { y } = \textbf { x } + }$ rnorm(10,0,1)   
4 summary(fit <- lm(y~x))

Residuals:

<table><tr><td>Min</td><td>1Q</td><td>Median</td><td>3Q</td><td>Max</td></tr><tr><td>-0.8851</td><td>-0.3867</td><td>0.1325</td><td>0.3896</td><td>0.6561</td></tr></table>

Coefficients:

<table><tr><td></td><td>Estimate</td><td>Std. Error</td><td>t value</td><td>Pr(&gt;|t|)</td></tr><tr><td>(Intercept)</td><td>0.2576</td><td>0.1892</td><td>1.362</td><td>0.2104</td></tr><tr><td>x</td><td>0.4577</td><td>0.2016</td><td>2.270</td><td>0.0529</td></tr></table>

Residual standard error: 0.58 on 8 degrees of freedom

Multiple R-squared: 0.3918, Adjusted R-squared: 0.3157

F-statistic: 5.153 on 1 and 8 DF, p-value: 0.05289

5 plot(x, y) # draw a scatterplot of the data (not shown)   
6 abline(fit) # add the fitted line to the plot (not shown)

All sorts of information can be extracted from the lm object, which we called fit. For example,

7 resid(fit) # will display the residuals (not shown)   
8 fitted(fit) # will display the fitted values (not shown)   
9 $\ln ( \mathbf { y } ^ { \mathrm { ~ \tiny ~ \sim ~ } } \boldsymbol { 0 } + \mathbf { x } )$ # will exclude the intercept (not shown)

You have to be careful if you use lm() for lagged values of a time series. If you use $\mathtt { l m } ( )$ , then what you have to do is “tie” the series together using ts.intersect. If you do not tie the series together, they will not be aligned properly. Please read the warning Using time series in the lm() help file [help(lm)]. Here is an example regressing Chapter 2 data, weekly cardiovascular mortality (cmort) on particulate pollution (part) at the present value and lagged four weeks (part4). First, we create a data frame called ded that consists of the three series:

1 ded $=$ ts.intersect(cmort, part, part4=lag(part,-4), dframe=TRUE)   
Now the series are all aligned and the regression will work.   
2 fit $=$ lm(mort~part+part4, data=ded, na.action=NULL)   
3 summary(fit)

Call: lm(formula=mort~part+part4,data=ded,na.action=NULL)

Residuals:

<table><tr><td>Min</td><td>1Q</td><td>Median</td><td>3Q</td><td>Max</td></tr><tr><td>-22.7429</td><td>-5.3677</td><td>-0.4136</td><td>5.2694</td><td>37.8539</td></tr></table>

Coefficients:

<table><tr><td></td><td>Estimate</td><td>Std. Error</td><td>t value</td><td>Pr(&gt;|t|)</td></tr><tr><td>(Intercept)</td><td>69.01020</td><td>1.37498</td><td>50.190</td><td>&lt; 2e-16</td></tr><tr><td>part</td><td>0.15140</td><td>0.02898</td><td>5.225</td><td>2.56e-07</td></tr><tr><td>part4</td><td>0.26297</td><td>0.02899</td><td>9.071</td><td>&lt; 2e-16</td></tr></table>

Residual standard error: 8.323 on 501 degrees of freedom

Multiple R-Squared: 0.3091, Adjusted R-squared: 0.3063

F-statistic: 112.1 on 2 and 501 DF, p-value: < 2.2e-16

There was no need to rename lag(part,-4) to part4, it’s just an example of what you can do. There is a package called dynlm that makes it easy to fit lagged regressions. The basic advantage of dynlm is that it avoids having to make a data frame; that is, line 1 would be avoided.

In Problem 2.1, you are asked to fit a regression model

$$
x _ {t} = \beta t + \alpha_ {1} Q _ {1} (t) + \alpha_ {2} Q _ {2} (t) + \alpha_ {3} Q _ {3} (t) + \alpha_ {4} Q _ {4} (t) + w _ {t}
$$

where $x _ { t }$ is logged Johnson & Johnson quarterly earnings $n = 8 4$ ), and $Q _ { i } ( t )$ is the indicator of quarter $i = 1 , 2 , 3 , 4$ . The indicators can be made using factor.

1 trend $=$ time(jj) - 1970 # helps to ‘center’ time   
2 ${ \sf Q } =$ factor(rep(1:4, 21)) # make (Q)uarter factors   
3 $\mathrm { r e g ~ = ~ 1 m ( 1 o g ( j j ) ^ { \sim } 0 ~ + ~ t r e n d ~ + ~ 0 ~ }$ , na.action=NULL) # no intercept   
4 model.matrix(reg) # view the model matrix

```txt
trend Q1 Q2 Q3 Q4  
1 -10.00 1 0 0 0  
2 -9.75 0 1 0 0  
3 -9.50 0 0 1 0  
4 -9.25 0 0 0 1  
. . . . . . . .  
. . . . . . . .  
83 10.50 0 0 1 0  
84 10.75 0 0 0 1 
```

```txt
5 summary(reg) # view the results (not shown) 
```

The workhorse for ARIMA simulations is arima.sim. Here are some examples; no output is shown here so you’re on your own.

1 x = arima.sim(list(order=c(1,0,0), $\tt a r = . 9$ ), $\mathtt { \Pi } _ { \mathtt { n } = 1 0 0 } ) + 5 0$ # AR(1) w/mean 50   
2 x = arima.sim(list(order $\mathtt { \Omega } = \mathtt { \Omega }$ (2,0,0),ar=c(1,-.9)), $\mathtt { n } = 1 0 0$ ) # AR(2)   
3 x = arima.sim(list(order $\mathtt { \Omega } = \mathtt { \Omega }$ (1,1,1),ar=.9,ma=-.5), $\scriptstyle \mathtt { n } = 2 0 0$ ) # ARIMA(1,1,1)

Next, we’ll discuss ARIMA estimation. This gets a bit tricky because R is not useR friendly when it comes to fitting ARIMA models. Much of the story is spelled out in the “R Issues” page of the website for the text. In Chapter 3, we use the scripts acf2, sarima, and sarima.for that are included with tsa3.Rda. But we will also show you how to use the scripts included with R.

First, we’ll fit an ARMA(1,1) model to some simulated data (with diagnostics and forecasting):

1 set.seed(666)   
2 $\mathrm { ~ \tt ~ x ~ } = \mathrm { ~ 5 0 ~ } + \mathrm { ~ \tt ~ }$ arima.sim(list(order $\mathtt { \Omega } = \mathtt { \Omega }$ (1,0,1), $\mathtt { a r } \mathtt { = } . 9$ , ma=-.5), n=200)   
3 acf(x); pacf(x) # display sample ACF and PACF ... or ...   
4 acf2(x) # use our script (no output shown)   
5 (x.fit $=$ arima(x, order $=$ c(1, 0, 1))) # fit the model

Call: arima( $\texttt { x } = \texttt { x }$ , order $=$ c(1, 0, 1))

Coefficients:

```txt
ar1 ma1 intercept 0.8340 -0.432 49.8960 s.e. 0.0645 0.111 0.2452 
```

```txt
sigma^2 estimated as 1.070: log likelihood = -290.79, aic = 589.58 
```

Note that the reported intercept estimate is an estimate of the mean and not the constant. That is, the fitted model is

$$
\widehat {x} _ {t} - 4 9. 8 9 6 = . 8 3 4 \left(x _ {t - 1} - 4 9. 8 9 6\right) + \widehat {w} _ {t}
$$

where $\widehat { \sigma } _ { w } ^ { 2 } = 1 . 0 7 0$ . Diagnostics can be accomplished as follows,

4 tsdiag(x.fit, gof. $\mathtt { l a g } \mathtt { = } 2 0$ ) # ?tsdiag for details (don’t use this!!)

but the Ljung-Box-Pierce test is not correct because it does not take into account the fact that the residuals are from a fitted model. If the analysis is repeated using the sarima script, a partial output would look like the following (sarima will also display the correct diagnostics as a graphic; e.g., see Figure 3.17 on page 151):

```txt
1 sarima(x, 1, 0, 1)
Coefficients:
ar1 ma1 xmean
0.8340 -0.432 49.8960
s.e. 0.0645 0.111 0.2452
sigma^2 estimated as 1.070: log likelihood = -290.79, aic = 589.58
AIC [1] 1.097494 $AICc [1] 1.108519 $BIC [1] 0.1469684 
```

Finally, to obtain and plot the forecasts, you can use the following R code:

```txt
1 x.fore = predict(x.fit, n.ahead=10)
2 U = x.fore$pred + 2*x.fore$se # x.fore$spred holds predicted values
3 L = x.fore$pred - 2*x.fore$se # x.fore$selshds stnd errors
4 miny = min(x,L); maxy = max(x,U)
5 ts.plot(x, x.fore$spred, col=1:2,ylim=c(miny, maxy))
6 lines(U, col="blue", lty="dashed")
7 lines(L, col="blue", lty="dashed") 
```

Using the script sarima.for, you can accomplish the same task in one line. 1 sarima.for(x, 10, 1, 0, 1)

Example 3.46 on page 159 uses this script.

We close this appendix with a quick spectral analysis. This material is covered in detail in Chapter 4, so we will not discuss this example in much detail here. We will simulate an AR(2) and then estimate the spectrum via nonparametric and parametric methods. No graphics are shown, but we have confidence that you are proficient enough in R to display them yourself.

1 x = arima.sim(list(order=c(2,0,0), ar=c(1,-.9)), $\mathtt { n } = \mathtt { 2 } \hat { \cdot } \mathtt { 8 }$ ) # some data   
2 (u = polyroot(c(1,-1,.9))) # x is AR(2) w/complex roots

[1] 0.5555556+0.8958064i 0.5555556-0.8958064i

3 Arg(u[1])/(2*pi) # dominant frequency around .16

[1] 0.1616497

4 par(mfcol $= _ { \mathtt { C } }$ (4,1))   
5 plot.ts(x)   
6 spec.pgram(x,spans $\eqcirc$ (3,3),log="no") # nonparametric spectral estimate   
7 spec.ar(x, log="no") # parametric spectral estimate   
8 spec.arma(ar=c(1,-.9), log="no") # true spectral density

The script spec.arma is included in tsa3.rda. Also, see spectrum as an alternative to spec.pgram. Finally, note that R tapers and logs by default, so if you simply want the periodogram of a series, the command is spec.pgram(x, taper ${ \boldsymbol { \mathsf { \Pi } } } = 0$ , fast $=$ FALSE, detrend=FALSE, log="no"). If you just asked for spec.pgram(x), you would not get the raw periodogram because the data are detrended, possibly padded, and tapered, even though the title of the resulting graphic would say Raw Periodogram. An easier way to get a raw periodogram is:

9 per = abs(fft(x))^2/length(x)

This final example points out the importance of knowing the defaults for the R scripts you use.
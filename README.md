
**Question 1**

For this analysis we focus on the FTSE 100, which provides a representative benchmark of large-capitalisation firms in the UK market. The overall distribution reveals two pronounced spikes in 2008 and 2020, reflecting the impact of the global financial crisis in the former year and the economic shock caused by the pandemic in the latter.

**Stylized Fact 2: Returns are Stationarity**

We work with log returns because their distribution is unbounded and tends to resemble a normal distribution more closely than simple returns. Log returns are also additive over time, making statistical analysis more convenient. Standard inference typically requires the i.i.d. assumption, meaning observations should be independent and identically distributed. However, this condition rarely holds in financial time series. Even if today's average return has limited influence on tomorrow's, the variability of returns changes over time.

Financial data often display dependence in the magnitude of log returns: large movements cluster together, as do calmer periods. This behavior, known as volatility clustering, implies that the conditional variance of returns evolves over time, so observations are neither independent nor identically distributed. Volatility regimes reappear but not at regular intervals: phases of turbulence and tranquility alternate in an irregular, non-periodic way.

*Figure 1. Daily log-returns and squared daily log returns*

We can observe in Figure 1 that volatility clustering becomes especially evident in the squared returns, since removing the sign of returns highlights alternating phases of high variability and pronounced periods of low variability.

We therefore substitute the i.i.d. assumption with the weak stationarity, as this relaxes the hypothesis of the iid, making them more empirically verifiable, but still permits statistical inference. Whose conditions are verified even in cases of volatility clustering, as long as the long-run (unconditional) moments of the process remain stable over time. In other words, even if the conditional variance fluctuates, the unconditional variance stays constant in the long run. Thus, weak stationarity accommodates short-term dependence in volatility while preserving overall statistical stability, allowing consistent estimation and valid inference.

To see if the Weak Stationarity conditions are verified, we look at the distribution of daily and monthly log returns:

*Figure 2. Distribution of daily (top) and monthly (bottom) log returns*

We can see that the log daily and monthly returns' distribution of the FTSE 100 index demonstrate that, over the entire sample, both the mean and variance of returns remain approximately constant, supporting the weak stationarity.

*Table 1. Descriptive statistics table*

Besides the visual inspection, we can also look at Table 1, which shows that the mean and the variance do not change substantially when moving from a daily to a monthly frequency. This suggests a rather stable pattern in these measures over time.

**Stylized Facts 3 and 4**

Let's continue the analysis of the distribution of log returns. The third stylized fact states that the distribution of returns is asymmetric and often negatively skewed: this reflects the tendency for market declines to be sharper and more abrupt compared to recoveries, as investors generally respond more intensely to adverse news than to favourable developments. The fourth stylized fact states that the returns are leptokurtic, exhibiting greater tails than would be predicted by a normal Gaussian distribution. This phenomenon largely arises because financial markets are frequently affected by unexpected shocks and rapid booms, leading to a higher likelihood (i.e. heavier tails) of extreme price changes.

*Figure 3. Histogram and QQ plots (bottom) of daily, monthly log returns (left), Zoomed daily log returns*

The histograms provide visual evidence on the shape of the distribution, allowing assessment of skewness and kurtosis. As shown in Figure 3, the log returns exhibit excess kurtosis compared with the normal distribution (plotted in red). This is even more apparent in the zoomed histogram, which highlights deviations from the normal distribution in the central region. The Quantile-Quantile plot is a scatter plot of empirical quantiles of one dataset versus the quantiles of another and enable us to plot the empirical distribution of returns against the normal distribution.

If the two distributions were the same then the points in the Q-Q plots would lie on the red line of equation (1).

However, our daily Q-Q plot provides graphical evidence of the stylized fact 4 given the fact that the points representing the lower quantiles lie below the red reference line (see Equation (1)), indicating fatter lower tails than predicted under the normal distribution. Similarly, the points on the right that represents higher quantiles lies well above the quantile expected providing further evidence of positive excess kurtosis. Moreover, monthly log returns appear more symmetric; in contrast, daily log returns show signs of negative skewness, in line with stylized fact 3.

*Figure 4. Graphs of Rolling skewness on 252 days*

*Figure 5. Rolling kurtosis on 252 days*

Both rolling skewness and rolling kurtosis are calculated over a 252-day window to represent one year of trading. These rolling statistics illustrate how the symmetry (skewness) and the thickness of the tails (kurtosis) of the log returns distribution change over time. The two (colour) bars represent the upper and lower bounds of a 95% confidence interval under the hypothesis of normal returns.

The skewness plot shows evidence for stylized fact 3 when the rolling skewness falls below the confidence interval, signalling frequent negative asymmetry in returns. Similarly, the kurtosis plot supports the stylized fact 4, as rolling kurtosis is often above the confidence bounds, indicating persistent heavy tails in the log returns distribution compared to the normal case.

**Stylized Fact 5: Aggregational Gaussianity**

As we have previously stated by Stylized Facts 3 and 4, the distribution of log returns tends to be characterized by asymmetry and heavy tails.

*Figure 6. Histogram of daily and monthly log returns against the normal distribution*

Figure 6 compares the empirical distribution with a Normal distribution sharing the same mean and standard deviation, already suggesting departures from Gaussianity. The negative skewness, excess kurtosis and fat tails visible in histograms, kernel densities and QQ-plots reinforce this impression.

To formalise this, we rely on the Jarque-Bera test, focused solely on skewness and kurtosis, and on goodness-of-fit tests such as Kolmogorov-Smirnov and Lilliefors. The KS test requires fixing μ and σ ex ante, which is unrealistic, whereas the Lilliefors version overcomes this by estimating them from the sample. Our analysis therefore concentrates on Jarque-Bera and Lilliefors, drawing on the descriptive evidence presented under Stylized Fact 2.

Skewness offers little insight: although it fluctuates between -0.63 and -0.83 across frequencies, it shows no systematic movement toward zero and does not suggest increasing normality. The more informative pattern emerges from kurtosis and from the formal tests. Kurtosis declines sharply from 15.00 (daily) to 10.16 (monthly) and reaches 3.60 (annual), approaching the Gaussian benchmark of 3. This indicates that tail heaviness weakens as the time horizon grows and extreme outcomes become less frequent.

The test statistics confirm this interpretation. Jarque-Bera values for daily, weekly and monthly data (59,794; 25,655; 1,114) are extremely high with near-zero p-values, signalling strong non-normality. At the annual level, however, the statistic drops to 5.15 and the p-value rises to about 7.6%, above the 5% threshold, meaning we cannot reject that annual returns have skewness and kurtosis consistent with normality. The Lilliefors results follow the same pattern: p-values are essentially zero for daily, weekly and monthly returns, but increase to 44.26% annually, indicating no significant deviation from the Normal distribution at that horizon.

*Figure 7. QQ plots compared to the Normal distribution of daily, weekly, monthly and annual returns*

These plots show that moving from daily to monthly returns the distribution tends to assume an increasingly more similar form to the normal distribution.

**Stylized Fact 6**

Stylized fact 6 states that financial returns are typically not autocorrelated, meaning past returns do not provide meaningful information for predicting future returns. This lack of autocorrelation supports the efficient market hypothesis, making it very difficult to systematically profit from patterns in past returns.

However, the absence of autocorrelation does not mean that returns are independent. Autocorrelation only measures linear dependence between returns at different time steps. Independence is a much stronger property: two returns are independent if knowing one gives no information about the other in any form, including non-linear or higher-order relationships. In practice, financial returns are often not autocorrelated, but they are not fully independent because other forms of dependence such as volatility clustering are frequently observed. To evaluate autocorrelation and determine whether it can be considered statistically insignificant, we use the sample autocorrelation function (ACF). This function calculates autocorrelation for a range of lags, usually from lag 1 up to a chosen maximum value.

*Figure 8. Empirical autocorrelation function*

The ACFs allow us to visually assess the degree of serial dependence at various time intervals. In each plot, the blue Bartlett bands delimit the range of the 95% confidence interval. Autocorrelation bars that fall within this area are not statistically different from zero at the 5% significance level, while those that cross the boundary are considered significant. This ACF plot visually demonstrates the presence of autocorrelation in both daily and weekly returns, as several autocorrelation bars extend beyond the Bartlett bands. In contrast, the monthly returns show no evidence of autocorrelation, with all bars remaining well within the confidence intervals.

It is possible to test whether the autocorrelations are statistically different from zero using two methods: the individual asymptotic distribution of each estimated autocorrelation coefficient, and the distribution of their sum via a Q-test, specifically the Box-Pierce or the Ljung-Box test. Both the Box-Pierce and Ljung-Box test statistics are asymptotically distributed as a χ² with p degrees of freedom where p is the number of autocorrelation lags considered.

*Table 2. Box-Pierce and Ljung-Box test statistics for daily (left) and monthly (right) data*

For both daily and weekly log returns, the significant autocorrelation detected is evident both from the extremely low p-values in the test tables and the fact that several autocorrelation coefficients extend beyond the critical Bartlett bands in the ACFs graph. For monthly returns, both the Box-Pierce and Ljung-Box tests produce high p-values, and all autocorrelation coefficients fall well within the Bartlett intervals, so we cannot reject the null hypothesis of uncorrelated returns. This is expected when using lower frequency data and supports stylized fact 6.

**Stylized Fact 7: Volatility clustering and long-range dependence of squared returns**

Stylized Fact 7 states that large price changes, equivalent to returns with large absolute values, tend to occur in clusters rather than in isolation. This empirical regularity, known as volatility clustering, implies that periods of market turbulence, characterized by high volatility, are typically followed by other volatile periods, while tranquil phases tend to persist as well.

From a statistical perspective, volatility clustering is reflected in the significant and positive autocorrelation of squared and absolute returns, which persists over long ranges of lags k.

*Figure 9. Autocorrelation function for absolute returns at daily, weekly, and monthly frequency*

*Figure 10. Autocorrelation function for squared returns at daily, weekly, and monthly frequency*

From the graphs above we can also see that the phenomenon is particularly visible at high frequencies, such as daily or intra-day data, and gradually weakens as the observation interval increases.

*Table 3. Squared (Left) and Absolute (Right) Returns Ljung-Box and Box-Pierce Tests*

We can observe from Table 3 that, for both squared and absolute log returns and across all lags, the p-values of the Ljung-Box and Box-Pierce tests are equal to zero, while the corresponding test statistics are well above their critical values. This provides strong evidence against the null hypothesis of no autocorrelation, confirming that both squared and absolute returns display significant serial dependence. Consistent with these results, the graphical analysis also reveals clear patterns of volatility clustering, as periods of heightened variability tend to be followed by similarly volatile phases.

This dynamic is further highlighted by the following yearly rolling standard deviation for the daily log-returns, which shows alternating periods of high and low volatility. During market crises or major shocks, volatility spikes sharply and remains elevated for an extended period before gradually reverting, while in stable market phases the variance remains persistently low.

*Figure 11. Rolling standard deviation*

This graphical evidence confirms that volatility is not constant over time but evolves in persistent regimes of high and low intensity, fully consistent with the empirical definition of volatility clustering.

**Stylized Fact 8: Leverage Effect**

Stylized Fact 8, known as the leverage effect, states that past asset returns and subsequent changes in volatility exhibit a negative correlation. Empirical evidence consistently shows that when prices fall, volatility tends to increase.

*Figure 12. Cross-correlations between lagged returns and volatility*

As shown in Figure 12, the cross-correlations between lagged returns and volatility are predominantly negative, yet they remain within the Bartlett confidence bands across all lags. Specifically, during the first eight lags, the correlation consistently retains a negative sign for most observations, before gradually diminishing over time. This behaviour is still consistent with Stylized Fact 8, as equity indices often display a leverage effect that is visible in sign but too mild to reach statistical significance in this type of analysis. Further proof of the stylized fact 8, comparing the FTSE First Differences and Rolling Volatility Changes to the rolling volatility can be found on the python notebook under section "Stylized Fact 8".

---

**Question 2**

To assess risk drivers and performance of the FTSE 100 Index, we regressed its monthly excess returns on two foundational asset pricing models: the Capital Asset Pricing Model and the Fama French 3 Factor Model.

**Capital Asset Pricing Model**

According to the CAPM model, market-wide risk is the only systematic component expected to drive differences in asset returns.

*Figure 13. Graph returns FTSE 100 and Risk-free*

A visual representation of the CAPM's explanatory power is provided by the fitted line plot below, which illustrates how the FTSE 100's excess returns align with the model's predicted values:

*Figure 14. CAPM Scatterplot: Market Excess Return vs FTSE 100 Excess Return*

**Fama French 3 Factor Model**

The Fama-French Three Factor framework extends the traditional CAPM by incorporating two additional systematic risk sources: the size effect (SMB, Small Minus Big) and the value effect (HML, High Minus Low). These factors are introduced to capture components of return variation that the market factor alone is unable to explain.

**Analysis of Coefficients**

*Table 4. Regression results: FTSE100 CAPM vs FTSE100 Fama-French 3-Factor*

**CAPM**

The estimation shows that β is highly statistically significant (***), indicating that the FTSE 100's excess returns move in the same direction as broad market fluctuations. Since the coefficient remains below one, the index displays a moderately defensive sensitivity to aggregate market conditions, reacting less than proportionally to changes in the overall market. The model also reports a Jensen's α of -0.2714, which is statistically significant and negative, implying that, after adjusting for market exposure, the FTSE 100 generates systematically lower risk-adjusted returns than predicted by the CAPM. Finally, the R² = 0.5117 shows that the market factor explains about 51% of the variation in monthly excess returns. While this reflects a solid degree of explanatory power, it also suggests that nearly half of the index's return variability is driven by additional sources of risk not captured by the single-factor model.

**Fama French 3 Factor Model**

The estimated market beta is highly statistically significant, confirming that the FTSE 100's excess returns are strongly linked to market movements. The SMB coefficient of -0.0036 is not statistically significant, showing that the size premium does not meaningfully influence the index's behaviour, an expected result for a benchmark composed primarily of large, established firms rather than small-cap companies. Conversely, the HML coefficient = 0.0156 is statistically significant (***), indicating a positive exposure to the value factor. This suggests that the FTSE 100 tends to benefit during periods when value stocks outperform growth stocks, consistent with its sector composition, which includes banks, utilities, energy companies, and other value-oriented industries.

**Comparative Discussion and Alpha Significance**

Comparing the two specifications, the adjusted R-squared rises from 0.5106 under the CAPM to 0.5169 in the FF-3F model, indicating a modest improvement in explanatory power when SMB and HML are included. Despite this incremental gain, the behaviour of alpha remains the most notable feature. Both models produce negative and statistically significant alphas: -0.2714 for the CAPM and -0.2752 for the FF-3F. This persistent pattern of negative abnormal performance contradicts the theoretical expectation of zero alpha in a fully specified pricing model. The presence of such strongly negative and statistically robust alphas in both cases indicates that relevant sources of systematic risk are still missing from the models, and that the FTSE 100's returns are likely influenced by additional factors not captured by the included regressors.

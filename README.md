# False-Positive-Rate-for-Multiple-Tests-in-IAAF-Study-BJSM-2018

I don't create a lot of github files so forgive me for formatting errors.

The issue I would like to address here is the lack of multiple testing correction by Eklund et al. in their 2017 study and the followup 2018 study by Bermon et al, the latter titled "Serum androgen levels are positively correlated with athletic performance and competition results in elite female athletes".  http://dx.doi.org/10.1136/bjsports-2018-099700  The data is given in the supplementary information, available online (it's a Word document with a few tables).

The 2017 study says that no multiple testing correction was performed because the tests were independent.  This is 100% wrong.  If 100 independent tests are performed on null data, then 5 of them on average should produce false positives at the p<0.05 level by the definition of the p-value.

Bermon et al. redid their statistics in the 2018 study so I will focus on that.

43 statistical tests were performed.  21 on women, 22 on men.  The men produced no significant p-values (p<0.05).  The women produced 3 in their 2018 study.  By the definition of the p-value, you *expect* two false positives, on average.  How likely is it to produce 3 false positives?

To get a sense of this false positive rate, I simulated two sets of normally distributed data with no effect (you could pick a different distribution, I don't think the results will change too much), and tested them with t-tests.  First I show that the t-tests are well-calibrated under the null; the distribution of p-values is roughly uniform.  I also show what it would look like under the alternate, for comparison.  Then I simulate 43 tests on different events, and I do this 1000 times to see how often I get at least 3 false positives.  The answer is that I get at least 3 false positives 329 times out of 1000 simulations -- 1/3 of the time they perform such a study.

I also noticed that they use phrasing such as "a trend (p<0.09) towards significance".  I don't have data from the men for this statistic (in the 2017 study they said no men showed p<0.05 but they didn't talk about 0.09).  So let's just assume zero again for the sake of argument.  We find that *most* of the time (more than half) such a study is performed there are at least 4 false positives at the p<0.09 level.

Thus, their results bear no significant difference from null data and should NOT be taken as evidence of any sort of significant effect.  It suggests that if there is a significant effect then it's most likely to occur in the listed events, but it does not stand as an independent result on its own.

# False-Positive-Rate-for-Multiple-Tests-in-IAAF-Study-BJSM-2018

I don't create a lot of github files so forgive me for formatting errors.

I have provided some simple simulations here: https://github.com/davidasiegel/False-Positive-Rate-for-Multiple-Tests-in-IAAF-Study-BJSM-2018/blob/master/False%20Positive%20Rate%20for%20Multiple%20Tests%20in%20IAAF(%3F)%20Study%2C%20BJSM%202018.ipynb

The issue I would like to address here is the lack of multiple testing correction by Eklund et al. in their 2017 study and the followup 2018 study by Bermon et al, the latter titled "Serum androgen levels are positively correlated with athletic performance and competition results in elite female athletes".  http://dx.doi.org/10.1136/bjsports-2018-099700  The data is given in the supplementary information, available online (it's a Word document with a few tables).

The 2017 study says that no multiple testing correction was performed because the tests were independent.  This is 100% wrong.  If 43 independent tests are performed on null data, then 2 of them, on average, should produce false positives at the p<0.05 level by the definition of the p-value.

Bermon et al. redid their statistics in the 2018 study so I will focus on that.

43 statistical tests were performed.  21 on women, 22 on men.  The men produced no significant p-values (p<0.05) and the women produced 3 p-values with p<0.05 in their 2018 study.  The question I wanted to investigate is: how likely is it to produce 3 false positives, given 43 statistical tests?  In their 2018 paper (and much of their 2017 paper) they ignore the men's data because it doesn't provide any significant results, but focusing on and re-analyzing significant results doesn't make it more significant and doesn't eliminate the original multiple-testing burden.

To get a sense of the distribution of the false positive rate, I simulated two sets of normally distributed data with no effect (you could pick a different distribution and redo the simulation for yourself), and tested them with t-tests.  First I show that the t-tests are well-calibrated under the null; the distribution of p-values is roughly uniform.  I also show what it would look like under the alternate, for comparison.  Then I simulate 43 sets of null data to represent different events, and perform t-tests on each of them, recording the number of false positives.  I do this 1000 times to see how often I get at least 3 false positives.  The answer is that I get at least 3 false positives 329 times out of 1000 simulations -- roughly 1/3 of the time they perform such a study.

I also noticed that they use phrasing such as "a trend (p<0.09) towards significance".  I don't have data from the men for this statistic (in the 2017 study they said no men showed p<0.05 but they didn't talk about 0.09).  So let's just assume zero again for the sake of argument.  We find that *most* of the time (more than half) such a study is performed there are at least 4 false positives at the p<0.09 level.

The other analysis technique that I find completely unconvincing is this business of aggregating the most statistically significant data. To summarize, what they have done is taken the most statistically significant data and aggregated them into pooled events: 1. 400m and 400m hurdles, 2. 800m and 1500m, 3. 400m to 1500m.  However, this was only done AFTER the analysis showed them to be the most significant datasets, which is a biased way to do things.  Taking the top most significant hits and combining them will often give something even more significant -- you've done the work to ensure that by selecting the top most significant datasets.  The only interesting thing about this is that the sign of the effect is the same for each of these events, but this is again pretty likely by random chance for such a small number of positive hits. I'm also pretty sure that they wouldn't have included this aggregated statistic if it didn't help their argument (they didn't include the 200m, for instance).

Optimistically interpreted, their results suggest that *if* there is a significant effect then it is most likely to occur in the listed events; but these results should NOT be taken as evidence of any sort of significant effect in the listed events.

As a side note, I personally believe that testosterone does play an important role in performance in every track and field event, but I do not think this study provides evidence of that effect.

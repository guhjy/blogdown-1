+++
title = "My Journey From Frequentist to Bayesian Statistics"
date = 2017-02-19T10:23:00Z
updated = 2017-12-30T08:53:33Z
tags = ["inference", "p-value", "likelihood", "RCT", "bayes", "multiplicity", "posterior", "drug evaluation", "principles", "evidence", "hypothesis testing"]
+++

<small>
Type I error for smoke detector: probability of alarm given no fire=0.05<br>
Bayesian: probability of fire given current air data

Frequentist smoke alarm designed as most research is done:<br>
Set the alarm trigger so as to have a 0.8 chance of detecting an
inferno

Advantage of actionable evidence quantification:<br>
Set the alarm to trigger when the posterior probability of a fire
exceeds 0.02 while at home and at 0.01 while away
</small>

If I had been taught Bayesian modeling before being taught the
frequentist paradigm, I'm sure I would have always been a Bayesian.  I
started becoming a Bayesian about 1994 because of an [influential
paper](http://www.citeulike.org/user/harrelfe/article/13264891) by David
Spiegelhalter and because I worked in the same building at Duke
University as Don Berry.  Two other things strongly contributed to my
thinking: difficulties explaining p-values and confidence intervals
(especially the latter) to clinical researchers, and difficulty of
learning group sequential methods in clinical trials.  When I talked
with Don and learned about the flexibility of the Bayesian approach to
clinical trials, and saw Spiegelhalter's embrace of Bayesian methods
because of its problem-solving abilities, I was hooked.  [Note: I've
heard Don say that he became Bayesian after multiple attempts to teach
statistics students the exact definition of a confidence interval.  He
decided the concept was defective.]

At the time I was working on clinical trials at Duke and started to see
that multiplicity adjustments were arbitrary.  This started with a
clinical trial coordinated by Duke in which low dose and high dose of a
new drug were to be compared to placebo, using an alpha cutoff of 0.03
for each comparison to adjust for multiplicity.  The comparison of high
dose with placebo resulted in a p-value of 0.04 and the trial was
labeled completely "negative" which seemed problematic to me. [Note:
the p-value was two-sided and thus didn't give any special "credit" for
the treatment effect coming out in the right direction.]

I began to see that the hypothesis testing framework wasn't always the
best approach to science, and that in biomedical research the typical
hypothesis was an artificial construct designed to placate a reviewer
who believed that an NIH grant's specific aims must include null
hypotheses.  I saw the contortions that investigators went through to
achieve this, came to see that questions are more relevant than
hypotheses, and estimation was even more important than questions.  
With Bayes, estimation is emphasized.  I very much like Bayesian
modeling instead of hypothesis testing.  I saw that a large number of
clinical trials were incorrectly interpreted when p>0.05 because the
investigators involved failed to realize that a p-value can only provide
evidence against a hypothesis. Investigators are motivated by "we spent
a lot of time and money and must have gained something from this
experiment." The classic "[absence of evidence is not evidence of
absence](http://www.bmj.com/content/311/7003/485)" error results,
whereas with Bayes it is easy to estimate the probability of similarity
of two treatments.  Investigators will be surprised to know how little
we have learned from clinical trials that are not huge when p>0.05.

I listened to many discussions of famous clinical trialists debating
what should be the primary endpoint in a trial, the co-primary endpoint,
the secondary endpoints, co-secondary endpoints, etc.  This was all
because of their paying attention to alpha-spending.  I realized this
was all a game.

I came to not believe in the possibility of infinitely many repetitions
of identical experiments, as required to be envisioned in the
frequentist paradigm.  When I looked more thoroughly into the
multiplicity problem, and sequential testing, and I looked at Bayesian
solutions, I became more of a believer in the approach.  I learned that
posterior probabilities have a simple interpretation independent of the
stopping rule and frequency of data looks.  I got involved in working
with the FDA and then consulting with pharmaceutical companies, and
started observing how multiple clinical endpoints were handled.  I saw a
closed testing procedures where a company was seeking a superiority
claim for a new drug, and if there was insufficient evidence for such a
claim, they wanted to seek a non-inferiority claim on another endpoint.
 They developed a closed testing procedure that when diagrammed truly
looked like a train wreck.  I felt there had to be a better approach, so
I sought to see how far posterior probabilities could be pushed.  I
found that with MCMC simulation of Bayesian posterior draws I could
quite simply compute probabilities such as P(any efficacy), P(efficacy
more than trivial), P(non-inferiority), P(efficacy on endpoint A and on
either endpoint B or endpoint C), and P(benefit on more than 2 of 5
endpoints).  I realized that frequentist multiplicity problems came from
the chances you give data to be more extreme, not from the chances you
give assertions to be true.

I enjoy the fact that posterior probabilities define their own error
probabilities, and that they count not only inefficacy but also harm.
 If P(efficacy)=0.97, P(no effect or harm)=0.03.  This is the
"regulator's regret", and type I error is not the error of major
interest (is it really even an 'error'?).  One minus a p-value is P(data
in general are less extreme than that observed if H0 is true) which is
the probability of an event I'm not that interested in.

The extreme amount of time I spent analyzing data led me to understand
other problems with the frequentist approach.  Parameters are either in
a model or not in a model.  We test for interactions with treatment and
hope that the p-value is not between 0.02 and 0.2.  We either include
the interactions or exclude them, and the power for the interaction test
is modest.  Bayesians have a prior for the differential treatment effect
and can easily have interactions "half in" the model.  Dichotomous
irrevocable decisions are at the heart of many of the statistical
modeling problems we have today.  I really like penalized maximum
likelihood estimation (which is really empirical Bayes) but once we have
a penalized model all of our frequentist inferential framework fails us.
 No one can interpret a confidence interval for a biased (shrunken;
penalized) estimate.  On the other hand, the Bayesian posterior
probability density function, after shrinkage is accomplished using
skeptical priors, is just as easy to interpret as had the prior been
flat.  For another example, consider a categorical predictor variable
that we hope is predicting in an ordinal (monotonic) fashion.  We tend
to either model it as ordinal or as completely unordered (using k-1
indicator variables for k categories).  A Bayesian would say "let's use
a prior that favors monotonicity but allows larger sample sizes to
override this belief."

Now that adaptive and sequential experiments are becoming more popular,
and a formal mechanism is needed to use data from one experiment to
inform a later experiment (a good example being the use of adult
clinical trial data to inform clinical trials on children when it is
difficult to enroll a sufficient number of children for the child data
to stand on their own), Bayes is needed more than ever.  It took me a
while to realize something that is quite profound: A Bayesian solution
to a simple problem (e.g., 2-group comparison of means) can be embedded
into a complex design (e.g., adaptive clinical trial) **without
modification**.  Frequentist solutions require highly complex
modifications to work in the adaptive trial setting.

I met likelihoodist [Jeffrey
Blume](http://biostat.mc.vanderbilt.edu/JeffreyBlume) in 2008 and
started to like the likelihood approach.  It is more Bayesian than
frequentist.  I plan to learn more about this paradigm.  Jeffrey has an excellent [web site](http://statisticalevidence.com).

Several readers have asked me how I could believe all this and publish a
frequentist-based book such as *Regression Modeling Strategies*.  There
are two primary reasons.  First, I started writing the book before I
knew much about Bayes.  Second, I performed a lot of simulation studies
that showed that purely empirical model-building had a low chance of
capturing clinical phenomena correctly and of validating on new
datasets.  I worked extensively with cardiologists such as Rob Califf,
Dan Mark, Mark Hlatky, David Prior, and Phil Harris who give me the
ideas for injecting clinical knowledge into model specification.  From
that experience I wrote *Regression Modeling Strategies* in the most
Bayesian way I could without actually using specific  Bayesian methods.
 I did this by emphasizing subject-matter-guided model specification.
 The section in the book about specification of interaction terms is
perhaps the best example.  When I teach the full-semester version of my
course I interject Bayesian counterparts to many of the techniques
covered.

There are challenges in moving more to a Bayesian approach.  The ones I
encounter most frequently are:

1.  Teaching clinical trialists to embrace Bayes when they already do in
    spirit but not operationally.  Unlearning things is much more
    difficult than learning things.
2.  How to work with sponsors, regulators, and NIH principal
    investigators to specify the (usually skeptical) prior up front, and
    to specify the amount of applicability assumed for previous data.
3.  What is a Bayesian version of the multiple degree of freedom "chunk
    test"?  Partitioning sums of squares or the log likelihood into
    components, e.g., combined test of interaction and combined test of
    nonlinearities, is very easy and natural in the frequentist setting.
4.  How do we specify priors for complex entities such as the degree of
    monotonicity of the effect of a continuous predictor in a regression
    model?  The Bayesian approach to this will ultimately be more
    satisfying, but operationalizing this is not easy.

With new tools such as [Stan](http://mc-stan.org/) and well written
accessible books such
as [Kruschke's](http://www.citeulike.org/user/harrelfe/article/14172337) it's
getting to be easier to be Bayesian each day.  The R
[brms](https://cran.r-project.org/web/packages/brms) package, which uses
Stan, makes a large class of regression models even more accessible.

### Update 2017-12-29

Another reason for moving from frequentism to Bayes is that frequentist
ideas are so confusing that even expert statisticians frequently
misunderstand them, and are tricked into dichotomous thinking because of
the adoption of null hypothesis significance testing (NHST).   The
[paper](http://www.blakemcshane.com/Papers/jasa_dichotomization.pdf) by
BB McShane and D Gal in JASA demonstrates alarming errors in
interpretation by many authors of JASA papers.  If those with a high
level of statistical training make frequent interpretation errors could
frequentist statistics be fundamentally flawed?  Yes!  In McShane and
Gal's paper they described two surveys sent to authors of JASA, as well
as to authors of articles not appearing in the statistical literature
(luckily for statisticians the non-statisticians fared a bit worse). 
 Some of their key findings are as follows.

1.  When a p-value is present, (primarily frequentist) statisticians
    confuse population vs. sample, especially if the p-value is large. 
    Even when directly asked whether patients *in this sample* fared
    batter on one treatment than the other, the respondents often
    answered according to whether or not p<0.05.  Dichotomous
    thinking crept in.
2.  When asked whether evidence from the data made it more or less
    likely that a drug is beneficial in the population, many
    statisticians again were swayed by the p-value and not tendencies
    indicated by the raw data.  The failed to understand that your
    chances are improved by "playing the odds", and gave different
    answers whether one was playing the odds for an unknown person vs.
    selecting treatment for themselves.
3.  In previous studies by the authors, they found that "applied
    researchers presented with not only a p-value but also with a
    posterior probability based on a noninformative prior were less
    likely to make dichotomization errors."

The authors also echoed Wasserstein, Lazar, and Cobb's concern that we
are setting researchers up for failure: "we teach NHST because that's
what the scientific community and journal editors use but they use NHST
because that's what we teach them.  Indeed, statistics at the
undergraduate level as well as at the graduate level in applied fields
is often taught in a rote and recipe-like manner that typically focuses
exclusively on the NHST paradigm."

Some of the problems with frequentist statistics are the way in which
its methods are misused, especially with regard to dichotomization.  But
an approach that is so easy to misuse and which sacrifices direct
inference in a futile attempt at objectivity still has fundamental
problems.

------------------------------------------------------------------------

Go [here](https://news.ycombinator.com/item?id=13684429) for discussions about this article that are not on this blog.
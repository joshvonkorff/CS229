# CS229

This is an implementation of algorithms described in Stanford's CS 229 notes about Machine Learning.

http://cs229.stanford.edu/notes/

So far I have implemented:

**Notes 2 - Lecture IV - Generative Learning Algorithms.**  These are algorithms that estimate p(y | x) by modeling p(x | y) and then multiplying by p(y) / p(x) via Bayes' theorem.  I implemented Naive Bayes from this lecture.  There is also a Gaussian Discriminant Analysis section which I have not yet implemented.  A note on Naive Bayes: it seems to me that the estimated probabilities will often be 0 or 1 in the event that the data set is too small, or maybe even if it is large.  When you multiple a large number of highly variable probabilities, there may be a large variance in the outcome; e.g. 0.02 * 0.04 is eight times larger than 0.01 * 0.01.

**Notes 3 - Lecture V - Support Vector Machines.**  These algorithms define a hyperplane "road" that is supposed to separate the two sets of samples with y = 0 vs. y = 1.  It is possible to compute the road using a common algorithm called quadratic programming.  I borrowed the quadratic programming algorithm and did not implement it from scratch; but I did the rest of it.  The computation involves solving a "dual" quadratic programming problem where the variable of interest is called "alpha."  If you want to allow outliers to cross over the road, ordinary quadratic programming will not work anymore - I have not implemented this.  I have implemented kernel computations, which permit the use of a very high dimensional vector space for the samples.  The manifold of "allowed" samples in this high dimensional space is still the same dimension as it was before; but it is curled up in some complicated way.  For example, for a 1-dimensional sample value x, we could instead use $(x, x^2)$ as the sample, resulting in a 1-dimensional manifold of samples (a parabola) inside a 2-dimensional space.

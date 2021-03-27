# CS229

This is an implementation of algorithms described in Stanford's CS 229 notes about Machine Learning.

http://cs229.stanford.edu/syllabus-spring2020.html

So far I have implemented:

**Naive Bayes**: this is one type of Generative Learning Algorithm.  A GLA estimates p(y | x) by modeling p(x | y) and then multiplying by p(y) / p(x) via Bayes' theorem. See: Lecture 5, 4/20. 

**Multivariate Gaussian Distribution**: A MVG distribution is like a Gaussian or Normal distribution, but in multiple dimensions.

Mentioned in: Section 2, 4/17 (The Multivariate Gaussian Distribution, More on Gaussian Distribution); Lecture 5, 4/20 (Generative Algorithems); Lecture 11, 5/11 (Mixture of Gaussians, the EM Algorithm); Lecture 12, 5/13 (Lagrange Multipliers); Lecture 13, 5/18 (Factor Analysis).

**Support Vector Machines.**  These algorithms define a hyperplane "road" that is supposed to separate the two sets of samples with y = 0 vs. y = 1.  It is possible to compute the road using a common algorithm called quadratic programming. See: Lecture 6, 4/22 (Support Vector Machines). 

I borrowed the quadratic programming algorithm and did not implement it from scratch; but I did the rest of it.  The computation involves solving a "dual" quadratic programming problem where the variable of interest is called "alpha."  If you want to allow outliers to cross over the road, ordinary quadratic programming will not work anymore - I have not implemented this.  I have implemented kernel computations, which permit the use of a very high dimensional vector space for the samples.  The manifold of "allowed" samples in this high dimensional space is still the same dimension as it was before; but it is curled up in some complicated way.  For example, for a 1-dimensional sample value x, we could instead use (x, x^2) as the sample, resulting in a 1-dimensional manifold of samples (a parabola) inside a 2-dimensional space.


# Method of Variational Divergence Minimization

First we define divergence metrics between distributions.

## f-Divergence

f-Divergence is class of distributional divergence metrics.

Given two probability distribution functions, with the corresponding density functions denoted by $P_x$  and $P_\theta$, the f-divergence between them is defined as follows (assuming the associated random variable are continuous). 

$$
D_f(p_x \parallel p_\theta) = \int dx ~p_\theta(x)~ f\left(\frac{p_x(x)}{p_\theta(x)}\right)
$$

where $f(u): \mathbb{R}^+ \to R$ is a convex function, left semi-continuous and $f(1)=0$ and $x\in \mathbb{R}^d$ lies in a space on which the densities of $p_x$ and $p_\theta$ are supported. 

## Properties of f-Divergence

- $D_f() \geq 0$ for any choice of the functions $f$
- $D_f(p_x \parallel p_\theta) =0$ iff $p_x = p_\theta$

## Examples of f-Divergence

1. If $f(u) = u\log(u)$ on gets the Kullback–Leibler (KL) divergence. 

Note that KL divergence is not symmetric in its arguments

$$
D_{KL}(p_x \parallel p_\theta) \neq D_{KL}(p_\theta || p_x)~.
$$

$D_{KL}(p_x \parallel p_\theta)$ is also called the forward KL divergence and $D_{KL}(p_\theta \parallel p_x)$ is called the reverse KL divergence.

2. Jensen–Shannon divergence:

   $$f(u) = \frac12 \left( u \log u - (u+1)\log\left(\frac{u+1}{2}\right) \right)$$

3. Total variation distance.

   $$f(u) = \frac12 |u-1|$$

# Algorithm for f-divergence minimization

The objective is to minimise the f-divergence between $p_x$ and $p_\theta$ over $\theta$ for any choice of the function $f$ without having to know the explicit form of the two distribution functions. The minimization is to be done only using samples from both the distributions. Samples from $p_x$ is the dataset $D$ and samples from $p_\theta$ is the output of a parametrized deep-networks whos input is a random variable sampled from some arbitrary but easy-to-sample distribution (for instance $N(0,1)$ ). 

In order to describe this algorithm, we first need to define the *conjugate* of a convex function

## Conjugate of a convex function

Given a convex function $f: R^n \to R$ its conjugate function $f^* : R^n \to R$ is defined as follows

$$
f^*(y) = \sup_{x\in \text{dom} f} (y^T x-f(x))
$$
















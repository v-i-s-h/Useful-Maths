# Wasserstein Distance

## Definitions
Given two cummulative distribution functions (CDFs) $F_1$ and $F_2$ on $\mathbb{R}$, the Wasserstein distance between them is defined by
$$
    W_1(F_1,F_2) = \left[ \underset{F\in\Gamma(F_1,F_2)}{\inf} \int \limits_{\mathbb{R}^2} |x-y| dF(x,y \right],
$$
where $\Gamma(F_1,F_2)$ denotes the set of all joint distributions on $\mathbb{R}^2$ having $F_1$ and $F_2$ as marginals [Def. 1, 1].

---
Suppose $X$ and $Y$ are r.v.s having CDF $F_1$ and $F_2$, respectively. Then,
$$
    \sup | \mathbb{E}(f(X)-\mathbb{E(f(Y))})| = W_1(F_1,F_2) = \int \limits_{-\inf}^{\inf} |F_1(s)-F_2(s)|ds,
$$
where the supremum is over all functions $f: \mathbb{R} \rightarrow \mathbb{R}$ that are 1-Lipchitz [Lemma 1, 1].

---

## Concentration Bounds

#### Empirical Distribution function to underlying CDF
Let $X_1,\ldots,X_n$ be i.i.d samples from distribution $F$ of a random variable $X$. The empirical distribution function (EDF) $F_n$ is defined by
$$
    F_n(x) = \frac{1}{n} \sum \limits_{i=1}^{n} \mathbb{I}\{ X_i \leq x \}, \text{for any} X \in \mathbb{R}.
$$

Consider the conditions
- (C1) There exists $\beta > 0$ and $\gamma > 0$ such that $\mathbb{E}\left(\exp\left(\gamma |X|^\beta\right)\right) < \mathsf{T} < \infty$. _Sub-Gaussian r.v.s satisfies this condition with $\beta=2$_.
- (C2) There exists $\beta > 0$ such that $\mathbb{E}\left(|X|^\beta\right) < \mathsf{T} < \infty$. _Sub-exponential r.v.s satisfies this condition with $\beta \geq 2$_.

Let $X$ be a r.v. with CDF $F$. Suppose that either (i) $X$ satisfies (C1) with $\beta > 1$, or (ii) $X$ satisfies (C2) with $\beta > 2$. Then, for any $\epsilon \geq 0$, we have
$$
    \mathbb{P}(W_1(F_n,F)>\epsilon) \leq B(n,\epsilon),
$$
where, under (i),
$$
    B(n,\epsilon) = C\left( \exp(-cn\epsilon^2) \mathbb{I}\{\epsilon \leq 1\} + \exp(-cn\epsilon^\beta) \mathbb{I}\{\epsilon>1\}\right),
$$
for some $C,c$ that depends on the parameter $\beta,\gamma$ and $\mathsf{T}$ specified in (C1); under (ii)
$$
    B(n,\epsilon) = C\left( \exp(-cn\epsilon^2) \mathbb{I}\{\epsilon \leq 1\} + n(n\epsilon)^{-(\beta-\eta)/p} \mathbb{I}\{\epsilon>1\}\right),
$$
where $\eta$ could be chosen arbitrarily from $(0,\beta)$, while $C,c$ depend of the parameters $\beta, \mathsf{T}$ and $\eta$ specified in (C2) [Lemma 2, 1].

### References
1. Bhat, S. P. (2019). Improved Concentration Bounds for Conditional Value-at-Risk and Cumulative Prospect Theory using Wasserstein distance. arXiv preprint [arXiv:1902.10709](https://arxiv.org/pdf/1902.10709.pdf).

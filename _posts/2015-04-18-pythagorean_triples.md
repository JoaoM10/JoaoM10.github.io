---
layout: post
title: Counting Pythagorean Triples in $$Z_n$$
excerpt: "An algorithmic number theory approach to the problem of counting Pythagorean triples modulo n."
categories: articles, number theory
tags: [pythagorean-triples]
comments: true
---



To count the number of pythagorean triples in $$Z_n$$ we start by reducing this problem to the problem of counting pythagorean triples in $$Z_{p^k}$$, for some primes $$p$$ and positive integer $$k$$.
Lets start by define $F(n)$ as the number of solutions to the equation:
<br>
$$a^2 + b^2 \equiv c^2$$ (mod $$n$$){.centerit}
<br>
<br>

### Reduction to $$Z_{p^k}$$
To reduce our problem to the same one but in $$Z_{p^k}$$ we can apply the Chinese Remainder Theorem.
Let $$n = p_1^{e_1}...p_r^{e_r}$$ be the prime decomposition of $$n$$, with $$p_i \ne p_j \forall i, j$$. We have:
<br>
<div style="text-align: center;">$$F(n) = \prod_{i=1}^r F(p_i^{e_i})$$</div>
<br>
<br>

### Counting in $$Z_{p^k}$$
To count the pythagorean triples in $$Z_{p^k}$$ we will procede using case analysis. Lets start by define $$qr(i)$$ as the number of quadratic residues congruent to $$i$$ modulo $$p^k$$.
<br>
<br>

### Case #1: $$a \in Z_{p^k}^*$$
We start with:<br>
<span style="display:inline-block; width: 42px;"></span>$$a^2 + b^2 \equiv c^2$$ (mod $$p^k$$)<br>
Because $$a \in Z_{p^k}^*$$ we obtain:<br>
<span style="display:inline-block; width: 42px;"></span>$$(\frac{a}{a})^2 + (\frac{b}{a})^2 \equiv (\frac{c}{a})^2$$ (mod $$p^k$$)<br>
By using $$X = \frac{b}{a}$$ and $$Y = \frac{c}{a}$$ we get:<br>
<span style="display:inline-block; width: 42px;"></span>$$1 + X^2 \equiv Y^2$$ (mod $$p^k$$)<br>
And we get the number of solutions with $$a \in Z_{p^k}^*$$:<br>
<div style="text-align: center;">$$\sum_{i=0}^{p^k - 1} qr(i) * qr((i + 1) \% p^k) * (p^k - p^{k - 1})$$</div>
<br>
Note that $$i$$ represents $$X^2$$ (and $$i + 1$$ represents $$Y^2$$) and we need to multiply by $$(p^k - p^{k - 1})$$ which are the number of possibilities to $$a$$.
<br>
<br>

### Case #2: $$a \notin Z_{p^k}^*, b \in Z_{p^k}^*$$
We start with:<br>
<span style="display:inline-block; width: 42px;"></span>$$a^2 + b^2 \equiv c^2$$ (mod $$p^k$$)<br>
Because $$b \in Z_{p^k}^*$$ we obtain:<br>
<span style="display:inline-block; width: 42px;"></span>$$(\frac{a}{b})^2 + (\frac{b}{b})^2 \equiv (\frac{c}{b})^2$$ (mod $$p^k$$)<br>
By using $$X = \frac{a}{b}$$ and $$Y = \frac{c}{b}$$ we get:<br>
<span style="display:inline-block; width: 42px;"></span>$$X^2 + 1 \equiv Y^2$$ (mod $$p^k$$)<br>
And we get the number of solutions with $$a \notin Z_{p^k}^*, b \in Z_{p^k}^*$$:<br>
<div style="text-align: center;">$$\sum_{i=0}^{p^{k - 1} - 1} qr(p * i) * qr((p * i + 1) \% p^k) * (p^k - p^{k - 1})$$</div>
<br>
Note that $$p*i$$ represents $$X^2$$ (and $$p*i + 1$$ represents $$Y^2$$) and we need to multiply by $$(p^k - p^{k - 1})$$ which are the number of possibilities to $$b$$.
<br>
<br>

### Case #3: $$a,b \notin Z_{p^k}^*, c \in Z_{p^k}^*$$
This is not actually a case since $$a,b \notin Z_{p^k}^*$$ imply $$c \notin Z_{p^k}^*$$.
<br>
<br>

### Case #4: $$a,b,c \notin Z_{p^k}^*$$
Since $$a,b,c \notin Z_{p^k}^*$$ it implies that $$a = pa', b = pb', c = pc'$$. Also, we can write: $$a' = \alpha * p^{k - 2} + \alpha', b' = \beta * p^{k - 2} + \beta', c' = \delta * p^{k - 2} + \delta'$$.<br>
We now prove that $$a, b, c$$ is a solution in $$Z_{p^k}$$ if and only if $$\alpha', \beta', \delta'$$ is a solution in $$Z_{p^{k - 2}}$$:<br>
<span style="display:inline-block; width: 42px;"></span>$$a^2 + b^2 \equiv c^2$$ (mod $$p^k$$)<br>
<span style="display:inline-block; width: 42px;"></span>$$\Leftrightarrow (pa')^2 + (pb')^2 \equiv (pc')^2$$ (mod $$p^k$$)<br>
<span style="display:inline-block; width: 42px;"></span>$$\Leftrightarrow (pa')^2 + (pb')^2 - (pc')^2 \equiv 0$$ (mod $$p^k$$)<br>
<span style="display:inline-block; width: 42px;"></span>$$\Leftrightarrow p^2 * (a'^2 + b'^2 - c'^2) \equiv 0$$ (mod $$p^k$$)<br>
<span style="display:inline-block; width: 42px;"></span>$$\Leftrightarrow p^2 * (a'^2 + b'^2 - c'^2) = \phi * p^k$$<br>
<span style="display:inline-block; width: 42px;"></span>$$\Leftrightarrow (a'^2 + b'^2 - c'^2) = \phi * p^{k - 2}$$<br>
<span style="display:inline-block; width: 42px;"></span>$$\Leftrightarrow a'^2 + b'^2 - c'^2 \equiv 0$$ (mod $$p^{k - 2}$$)<br>
<span style="display:inline-block; width: 42px;"></span>$$\Leftrightarrow (\alpha * p^{k - 2} + \alpha')^2 + (\beta * p^{k - 2} + \beta')^2 - (\delta * p^{k - 2} + \delta')^2 \equiv 0$$ (mod $$p^{k - 2}$$)<br>
<span style="display:inline-block; width: 42px;"></span>$$\Leftrightarrow \alpha'^2 + \beta'^2 - \delta'^2 \equiv 0$$ (mod $$p^{k - 2}$$)<br>
<span style="display:inline-block; width: 42px;"></span>$$\Leftrightarrow \alpha'^2 + \beta'^2 \equiv \delta'^2$$ (mod $$p^{k - 2}$$)<br>
And we get the number of solutions with $$a,b,c \notin Z_{p^k}^*$$:<br>
<div style="text-align: center;">$$F(p^{k - 2}) * p^3$$</div>
<br>
We are not done yet since the base cases are missing. We have $$F(p) = p^2$$ by Jacobi Sums (consult [1] for a proof of this) and $$F(p^0) = F(1) = 1$$ which is the trivial solution only.
<br>
<br>

### Result
After analyzing all cases we obtain:<br>
$$F(p^0) = 1$$<br>
$$F(p^1) = p^2$$<br>
$$F(p^k) = \sum_{i=0}^{p^k - 1} qr(i) * qr((i + 1) \% p^k) * (p^k - p^{k - 1})$$<br>
<span style="display:inline-block; width: 42px;"></span>$$ + \sum_{i=0}^{p^{k - 1} - 1} qr(p * i) * qr((p * i + 1) \% p^k) * (p^k - p^{k - 1}) + F(p^{k - 2}) * p^3$$
<br>
<br>

### Complexity Analysis
Firstly, we need to consider the complexity to factorize $$n$$, which we need to reduce the problem from $$Z_n$$ to $$Z_{p^k}$$. It can be done in $$\mathcal{O}(\sqrt{n} * \log{}n)$$.
Then we consider the time to solve the problem in $$Z_{p^k}$$, which is $$\mathcal{O}(n)$$.<br>
So, we have a time complexity of $$\mathcal{O}(n)$$ and a space complexity of $$\mathcal{O}(n)$$ since we only need to pre-calculate $$qr$$.
<br>
<br>

### Implementation
You can consult an implementarion in C++ on [2].
<br>
<br>

### Conclusion
This paper shows an algorithmic number theory approach to a beautiful counting problem. Also, the method described is, as far as we know, the most efficient one (the approach using Discrete Fourier transform has linearithmic complexity).
<br>
<br>

### References
[1] K. Ireland and M. Rosen, "A Classical Introduction to Modern Number Theory"
[2] https://gist.github.com/JoaoM10/cf6337384f6ea653af2e



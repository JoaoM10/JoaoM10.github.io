---
layout: post
title: Bounded sequences of coprimes
excerpt: "A conjecture on bounded sequences of coprimes"
categories: articles number-theory
tags: [bounded-sequences-coprimes]
comments: true
---

Today I'm writing about a conjecture I've working in the last months.
Although I was not able to prove it yet, I will share it here with some
parts that I've proved and some ideas I've tried.


###So what is this conjecture about?

First an informal definition: Given two numbers $$a$$ and $$b$$ (both
positive integers with $$a < b$$), we want to find the minimal set of
numbers to add between $$a$$ and $$b$$ such that if we look at the ordered
sequence we see a sequence of coprimes, that is, the first number is coprime
with the second number, the second number is coprime with the third one,
and so on.

Now a more formal definition: Lets define $$f(a,b)$$, with $$a$$ and $$b$$
positive integers and $$a < b$$, as:
<span style="display:inline-block; width: 42px;"></span>
$$f(a,b) = min \{ \{x_1, ..., x_n\} \subset \mathbb{N} | a < x_1 < x_2 < ... < x_n < b \wedge gcd(a, x_1) = gdc(x_1, x_2) = ... = gcd(x_n, b) = 1 \}$$<br>

The conjecture is that: $$f(a,b) \leq 2$$ for all values $$a$$ and $$b$$.


###When $$b \geq 2*a$$

We can easily see that the conjecture is true when $$b \geq 2*a$$ because,
by the Bertrand's postulate, exists a prime $$p$$ such that $$a < p < b$$
when $$a > 1$$. We have $$gcd(a,p) \leq 1$$. Now we can have two cases: $$gcd(p,b) = 1$$
, which lead us to $$f(a,b) = 1$$; or $$gcd(p,b) = p$$ and, in this case, we
insert $$b - 1$$ in our sequence, leading us to $$f(a,b) \leq 2$$. Note that
if $$a = 1$$ then $$gcd(a,b) = 1$$ and $$f(a,b) = 0$$.


###When $$b < 2*a$$

Is this conjecture still true when $$b < 2*a$$? I do think so but I was not
able to give a proof, yet.

I've proved that the conjecture is true manually (that is, each case individually)
when $$b = a + d$$ with small $$d$$ but didn't find a way of generalize the proofs.
Computationally, I have already proved the conjecture for $$a \leq 100 000$$.


###Final remarks

If we believe that Oppermann's conjecture is true, then we can give a proof that
the conjecture is true for $$b \geq a + \sqrt{a}$$.

I have tried a lot of different ideas but non of them revealed to be helpful
to give a proof to the conjecture. Even if turns out that the conjecture is false,
can we find some upper bound on $$f(a,b)$$?

If you have any idea I would love to hear it!


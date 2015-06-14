---
layout: post
title: Bounded sequences of coprimes
excerpt: "A conjecture on bounded sequences of coprimes"
categories: articles number-theory
tags: [bounded-sequences-coprimes]
comments: true
---

Today I'm writing about a conjecture I've been working in the last months.
Although I was not able to prove it yet, I will share it here with some
parts that I've proved and some ideas I've tried.
<br><br>

### So what is this conjecture about?

First an informal definition: Given two numbers $$a$$ and $$b$$ (both
positive integers with $$a < b$$), we want to find the minimal set of
numbers to add between $$a$$ and $$b$$ such that if we look at the ordered
sequence we see a sequence of coprimes, that is, the first number is coprime
with the second number, the second number is coprime with the third one,
and so on.

Now a more formal definition: Lets define $$f(a,b)$$, with $$a$$ and $$b$$
positive integers and $$a < b$$, as:
<br><br>
$$f(a,b) \\ = min \{ |\{x_1, ..., x_n\}| : \{x_1, ..., x_n\} \subset \mathbb{N} \wedge a < x_1 < x_2 < ... < x_n < b \\ \wedge gcd(a, x_1) = gdc(x_1, x_2) = ... = gcd(x_n, b) = 1 \}$$<br>
<br>
The conjecture is that: $$f(a,b) \leq 2$$ for all values $$a$$ and $$b$$.
<br><br>

### Large gaps

We can easily see that the conjecture is true when $$b \geq 2*a$$ because,
by the Bertrand's postulate [1], exists a prime $$p$$ such that $$a < p < b$$
when $$a > 1$$. We have $$gcd(a,p) \leq 1$$. Now we can have two cases:
$$gcd(p,b) = 1$$ , which lead us to $$f(a,b) = 1$$; or $$gcd(p,b) = p$$
and, in this case, we insert $$b - 1$$ in our sequence, leading us to
$$f(a,b) \leq 2$$. Note that if $$a = 1$$ then $$gcd(a,b) = 1$$ and
$$f(a,b) = 0$$.

We can improve the previous proof with the following results:

In 1952, Jitsuro Nagura showed that there exists a prime in the interval
$$[n, 6n/5]$$ for every $$n \geq 25$$ [2]. So we have that this conjecture
is true for $$b \geq a + a/5$$, since we can easily check that the conjecture
is true for $$a < 25$$.

In 1998, Pierre Dusart showed in his Phd thesis that there exists a prime
in the interval $$[n, n + n/(2ln^2n)]$$ for every $$n \geq 3 275$$ [3].
This result gives a proof to our conjecture when $$b \geq a + a/(2ln^2a)$$.
Some years later, in 2010, Dusart proved that there exists a prime in the
interval $$[n, n + n/(25ln^2n)]$$ for $$n \geq 396 738$$ [4], improving his
previous result. Note again that it was verified computationally that the
conjecture is true for all $$a < 396 738$$.

We also have some other very interesting results like the work done by
Baker, Harman, and Pintz, in 2001, which proved that the interval
$$[n, n + n^{0.525}]$$ contains at least one prime number for sufficiently
large $$n$$ [5]. 
<br><br>

### Small gaps

Is this conjecture still true when $$b$$ is closer to $$a$$? I do think so
but I was not able to give a proof, yet.

I've proved that the conjecture is true manually (that is, each case
individually) when $$b = a + d$$ with small $$d$$ but didn't find a way
of generalize the proofs.
<br><br>

### Final remarks

I tried a lot of different ideas but non of them revealed to be helpful
to give a proof to the conjecture. Even if turns out that the conjecture is false,
can we find some upper bound on $$f(a,b)$$?

If you have any idea I would love to hear it!


### References
[1] Manoj Verma, "A more elementary proof of Bertrand's postulate", arXiv:1401.4368 [math.NT], 2013<br>
[2] Nagura, J. “On The Interval Containing At Least One Prime Number” Proceedings of the Japan Academy. 28(4), 177–181, 1952<br>
[3] Dusart, Autour de la fonction qui compte le nombre de nombres premiers, PhD Thesis, Université de Limoges, 1998<br>
[4] Dusart, "Estimates of Some Functions Over Primes without R.H.", arXiv:1002.0442 [math.NT], 2010<br>
[5] Baker, R. C.; Harman, G.; Pintz, J. “The Difference Between Consecutive Primes, II” Proceedings of the London Mathematical Society. 83(3), 532–562, 2001<br>
[6] Paz, G. A. "On Legendre’s, Brocard’s, Andrica’s, and Oppermann’s Conjectures", arXiv:1310.1323v2 [math.NT], 2014<br>
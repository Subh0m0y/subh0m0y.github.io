---
layout: post
title: Rational Arithmetic
tags:
    - rational
    - algorithm
comments: true
---

Floating-point arithmetic is the default way to provide support for representation of fractional numbers in most programming languages. However, they offer limited storage and fixed precision. Often, the accumulation of rounding-errors after a chain of operations makes them unsuitable for cases where accuracy matters, like in case of scientific computations.

One of the most common sources of rounding errors is *division*. Since we are allowed to work with only a limited number of bits, it is physically impossible to exactly represent certain numbers, such as $$\frac{1}{3}$$. We will need an infinite number of 3's after the decimal point to represent it. But we have no option to use infinite number of digits, for our hardware simply does not allow it. The result is that we only get an approximate value of $$ \frac{1}{3} $$.

Most of us have grown accustomed to this short-coming. Some of us even use [`BigDecimal`](https://docs.oracle.com/javase/8/docs/api/java/math/BigDecimal.html) from the `java.math` package to use to obtain more digits of precision (and hopefully accuracy). But this doesn't really solve the problem. What can be done is to review middle-school level maths: learn how to use *fractions* or **Rational Numbers**.

## Definition

A *rational* number is one which can be expressed as a *ratio* of two integers, say $$p$$ and $$q$$, where $$q \neq 0$$.

It is not required, but recommended to define a rational in the lowest terms possible and always use a positive value for $$q$$. This makes arithmetic operations easier (partly because we need to deal with only smaller numbers).

## Why should I care?

Before we go any further, it might be worthwhile to *why* do we even want to use a new type of number (or more specifically a form of representation)? Let's think about it progressively.

When we first learned how to count we were introduced to the **Natural Numbers** ($$\mathbb{N}$$), which is defined as the set of all positive integral numbers starting from $$1$$, and continuing till infinity. If we add $$0$$ to the set, we get the set of **Whole Numbers** ($$\mathbb{W}$$). A few years into Middle School and we realize that there is an entirely new concept of *negative numbers*. Thus, the set of **Integers** ($$\mathbb{Z}$$) follow.

Then comes a time when we start learning about fractions in two different ways simultaneously. We represent these *fractions* either with digits after the decimal point, or as the result of a division. (The latter form is the one we're after in this series.)

I'm sharing a personal experience that might be common to many of us. When in the seventh grade, I noticed that calculations tend to be simpler if not more accurate if we use fractions (especially in Physics). I used to keep all the intermediate results as fractions and perform only one division to get the final answer upto 2 decimal places. I noticed my friends took more time to finish their calculations just because they divided at every step, then wrestle with the complicated quotients and reach the answer after quite some effort.

There is a reason behind this: *division is expensive*. Especially if you're considering the grade school long-division algorithm, whose [time complexity](https://en.wikipedia.org/wiki/Time_complexity) is $$O(n^2)$$. Thereby, if you can delay the division, you can speed the process without sacrificing accuracy. That's pretty neat. :+1:

Hopefully now you understand the need of **Rational Numbers** ($$\mathbb{R}$$ or $$\mathbb{Q}$$).

## Are there any shortcomings?

Sure, the set of rational numbers has the capability to represent more numbers, but still there are some numbers that it cannot represent. How about $$\sqrt {2}$$ or $$\pi$$ or $$e$$? These numbers fall into the the compliment set of Rational Numbers: the **Irrational Numbers** ($$\mathbb{R} - \mathbb{Q}$$), which cannot be expressed as a ratio of two numbers. Their decimal expansion has no obvious cyclic pattern. These two sets combine to form **Real Numbers** ($$\mathbb{R}$$). There is also a set of **Imaginary or Complex Numbers** ($$\mathbb{C}$$), which includes numbers such as $$i=\sqrt{-1}$$, $$n$$th roots of unity and so on. We shall deal with all of them, but let's talk about rational numbers first.

## Conclusion

This post hopefully gives you an idea of what I'm trying to say, why should we considering using fractions and its shortcomings. In the next post, I'll explain the detailed algorithms for performing arithmetic.

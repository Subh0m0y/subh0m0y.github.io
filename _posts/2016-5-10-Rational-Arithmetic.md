---
layout: post
title: Rational Arithmetic
tags:
    - rational
    - algorithm
---

# Rational Arithmetic

## Introduction

Floating-point arithmetic is the default way to provide support for representation of fractional numbers in most programming languages. However, they offer limited storage and fixed precision. Often, the accumulation of rounding-errors after a chain of operations makes them unsuitable for cases where accuracy matters, like in case of scientific computations.

One of the most common sources of rounding errors is *division*. Since we are allowed to work with only a limited number of bits, it is physically impossible to exactly represent certain numbers, such as $$\frac{1}{3}$$. We will need an infinite number of 3's after the decimal point to represent it. But we have no option to use infinite number of digits, for our hardware simply does not allow it. The result is that we only get an approximate value of $$ \frac{1}{3} $$.

Most of us have grown accustomed to this short-coming. Some of us even use `BigDecimal` from the `java.math` package to use to obtain more digits of precision (and hopefully accuracy). But this doesn't really solve the problem. What can be done is to review middle-school level maths: learn how to use *fractions* or **Rational Numbers**.



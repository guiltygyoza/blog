---
layout: post
title:  "Characterizing a physics-centric rollup"
date:   2022-02-22 00:00:00 -0500
categories: crypto
published: false
---

1. Need to have efficient bit-shifting (using binary circuit??). Observation from Fountain engine: a single euler step takes ~450 steps because every multiplication of fixed-point numbers using `mul_fp` requires a `signed_div_rem`. It would be ideal if bit shifting is possible so that instead of using `FP=10**12`, we can use `FP=2**40` by shifting left/right 40 bits.

2. Need to deal with the sequential nature of physics simulation - potentially optimized the underlying circuit accordingly.
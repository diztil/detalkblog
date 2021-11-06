---
layout: post
title: 'Binary Bits - Memory Calculation'
description: Valuable chunks of information about computer memory and their base-N calculations.
tags:
  - computers
  - articles
  - learning
hero: https://miro.medium.com/max/700/0*1Nojyz_xFtg4jUH2
overlay: none
published: true
---

Photo by [Shubham Bombarde](https://unsplash.com/@shubhambombarde?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com/?utm_source=medium&utm_medium=referral)

Largest & Smallest Values
======================================
This here is a list of the largest and smallest possible values in each n-bit type of numbers which are possible to be represented as 2s-complements :


### n-bits (SMALLEST : LARGEST)

-   2-bits (-2 : 1)
-   3-bits (-4 : 3)
-   4-bits (-8 : 7)
-   5-bits (-16 : 15)
-   6-bits (-32 : 31)
-   7-bits (-64, 63)
-   8-bits (-128 : 127)
-   9-bits (-256 : 255)
-   10-bits (-512 : 511)
-   11-bits (-1024 : 1023)
-   12-bits (-2048 : 2047)
-   16-bits (-32,768 : 32,767)
-   32-bits (-2,147,483,648 : 2,147,483,647)
-   64-bits (-9,223,372,036,854,775,808 : 9,223,372,036,854,775,807)
-   70-bits (-590,295,810,358,705,651,712 : 590,295,810,358,705,651,711)

Thus, it is evident that for n-bits, the smallest possible value will be -(2^n) and the largest possible value would be ((2^n)-1).

Currently, our modern computers have operating systems running up to 64-bits. Exceeding 70-bits is going to cause a problem known as a 'floating point precision error' or 'floating point bug'. You can search that term up for better and detailed explanations, if you are curious.


Byte addressable or word addressable ?
======================================

When referring to a memory location, if the size of a 'word' is 8 bits (a byte), then it is conventionally called "byte addressable". It's counterpart --- word addressable --- exists when the size of a word is greater than 8 bits (i.e. 16 bits, 32 bits, 64 bits), the location is then "word addressable".

How to determine memory address bits ?
======================================

That's easy (kind of). For illustrative purposes, let's take a 1 GiB (gibibyte) module of RAM, that is composed of several smaller 64 MiB (mebibyte) pieces.

Firstly, we need to convert the memory to bytes for convenience. So, 1 GiB = 1073741824 bytes, 64 MiB = 67108864 bytes. Done! (Conversion processes will be explained later)

Now you take the logarithm of the main memory module's (the total memory value) value --- in bytes --- to base 2. You would get :

log(2, 1073741824) = 30

That means the 1 GiB memory module will be using 30-bit memory registers.

Now, since the whole 1 GiB memory module is actually made up of 64 MiB pieces --- just like smaller pieces of chocolate are manufactured joined up together to form a large chocolate bar --- we need to find exactly "how many" of those 64 MiB tiny modules/RAM chips we need to add up to the total of 1 GiB.

So we calculate it like this (simple unitary method) :

1073741824/67108864 = 16

or if the large and overly-detailed numbers is uncomfortable for you, you can rely on good old powers of 2 for all your calculations :

2³⁰/2²⁶ = 16

Phew. Feeling tired already? Hang on in there!

We know 2⁴ = 16, so the first 4 bits of the whole 30-bit memory register needs to be used for selecting which 'chip' among the sixteen chips used to build up the 1 GiB module. And the remaining 26 bits is used for the memory addressing.

Done.

How to calculate highest and lowest memory addresses ?
======================================================

Tough question. (Just joking)

Just remember this for now :

> Regardless of how many bits the memory has, the lowest address for it will always be zero.

That answers 50% of your question.

As for calculating the highest possible memory address for a defined byte range of memory, you can rely on this trend :

Consider there are 2ᵡ (2^x) bytes in memory.

So, if the word size is 8 bits, then the memory is *byte addressable (as explained above)*. The highest memory address would be = 2^x-1

If the word size is 16 bits, then the highest memory address would be = 2^(x-1)-1, because 16 bits is a 2-byte (2¹) word. And you'd be reducing the total number of available addresses by that amount. Thus, 1 is subtracted from the total x-bits.

If the word size is 32 bites, then the highest memory address would be = 2^(x-2)-1. The explanation is same as above. 32 bits is a 4-byte (2²) word. So the amount is subtracted from x-bits.

Once more, if the word size is 64 bits, the highest possible address is 2^(x-3)-1, as 64 is a 8-byte (2³) word.

This trend continues for as many increments of powers of 2 you need.

Voila! You've now understood the concept, I presume.

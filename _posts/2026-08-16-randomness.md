---
layout: post
title: Randomness
date: 2026-08-16
permalink: /posts/totients
---

# Randomness
Randomness is an important part of cybersecurity because cryptographic systems depend on values that attackers cannot predict. However, there are different types of randomness!
The main categories important to cybersecurity are:

- **True randomness**
- **Pseudorandomness**
- **Cryptographically secure pseudorandomness**


### Let’s get into an overview of each.

**True random number generators (TRNG)** can be made possible with physical processes that are almost impossible to predict, like electronic noise. They are great sources of entropy in cryptographic systems because they make it incredibly hard for attackers to determine the next number in a series of numbers used for encoding or etc. However, physical random-number sources can be slower, more difficult to implement, and may require specialized hardware.

- **Cloudflare's LavaRand system** is considered to be a TRNG. Cloudflare takes photos of a wall of lava lamps and uses their patterns as a source of entropy for their random number generation. The images are fed into a CSPRNG and combined with other randomness sources. Read more about it [here](https://blog.cloudflare.com/randomness-101-lavarand-in-production/)


**Pseudorandom number generators (PRNG)** use a deterministic algorithm and a starting value called a seed. ‘Seeds’ might sound familiar, because they are used to generate varied Minecraft worlds! The main advantage of PRNGs is that they are fast, so a relatively small amount of initial data can produce a large sequence of values. That quality makes PRNGs useful for simulations, games, and testing, where true unpredictability is not crucial. If a seed is discovered, however, the output (like a Minecraft world) could be reproduced, so an ordinary PRNG should not be used for cryptographic secrets.


**Cryptographically secure pseudorandom number generators (CSPRNG)** are somewhere in between the two previous categories. They have the efficiency of PRNGs with enough security designs to make their output decently unpredictable, but they are not truly unpredictable. They are the number generators most commonly used for generating keys, tokens, and other secret values. With CSPRNGs, knowing some outputs shouldn’t allow an attacker to predict other outputs, assuming the generator and its secret state remain secure. However, a compromised or predictable seed can undermine the security of the generator. NIST, the National Institute of Standards and Technology, emphasizes that the security strength of random number generation depends heavily on output unpredictability and entropy of a specific generator.


### Overall, PRNGs are fast and useful for non-security purposes, while CSPRNGs and physical sources of randomness are necessary when randomness serves a security function. 

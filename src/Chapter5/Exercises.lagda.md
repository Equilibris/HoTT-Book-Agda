---
title: Chapter 5. Induction - Exercises
---

# Chapter 5. Induction - Exercises

```agda
module Chapter5.Exercises where

open import Chapter5.Book public

-- Exercise 5.4.
ind𝟚 : (E : 𝟚 → 𝒰 𝒾) → (E ₀ × E ₁) → ((b : 𝟚) → E b)
ind𝟚 = ?

𝟚-ind-isequiv : (E : 𝟚 → 𝒰 𝒾)
              → isEquiv (ind𝟚 E)
𝟚-ind-isequiv = ?
```

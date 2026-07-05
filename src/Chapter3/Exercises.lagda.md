---
title: Chapter 3. Sets and logic - Exercises
---

# Chapter 3. Sets and logic - Exercises

```agda
module Chapter3.Exercises where

open import Chapter3.Book public

-- Exercise 3.3.
isSet-Σ : {A : 𝒰 𝒾}
        → {B : A → 𝒰 𝒿}
        → isSet A
        → ((x : A) → isSet (B x))
        → isSet (Σ B)
isSet-Σ = ?

-- Exercise 3.4.
isProp⇒isContr-endo : (A : 𝒰 𝒾) → isProp A → isContr (A → A)
isProp⇒isContr-endo = ?

isContr-endo⇒isProp : (A : 𝒰 𝒾) → isContr (A → A) → isProp A
isContr-endo⇒isProp = ?

-- Exercise 3.5.
isProp⇒inhab→isContr : {A : 𝒰 𝒾}
    → isProp A → (A → isContr A)
isProp⇒inhab→isContr = ?

inhab→isContr⇒isProp : {A : 𝒰 𝒾}
    → (A → isContr A) → isProp A
inhab→isContr⇒isProp = ?

isProp≃inhab→isContr : {A : 𝒰 𝒾}
    → isProp A ≃ (A → isContr A)
isProp≃inhab→isContr = ?

-- Exercise 3.6.
isProp⇒isProp-isDecidible : (A : 𝒰 𝒾) → isProp A
                          → isProp (A ⊎ (¬ A))
isProp⇒isProp-isDecidible = ?

-- Exercise 3.7.
isProp⇒isProp-isDecidible' : (A : 𝒰 𝒾) → (B : 𝒰 𝒿)
                           → isProp A → isProp B → ¬ (A × B)
                           → isProp (A ⊎ B)
isProp⇒isProp-isDecidible' = ?

-- Exercise 3.9.
LEM→Prop𝒰≃𝟚 : {𝒾 : Level} → LEM 𝒾 → (Prop𝒰 𝒾 ≃ 𝟚)
LEM→Prop𝒰≃𝟚 = ?

Prop𝒰≃𝟚→LEM : {𝒾 : Level} → (Prop𝒰 𝒾 ≃ 𝟚) → LEM 𝒾
Prop𝒰≃𝟚→LEM = ?

-- Exercise 3.18.
LEM→RAA : {𝒾 : Level} → LEM 𝒾 → RAA 𝒾
LEM→RAA = ?

RAA→LEM : {𝒾 : Level} → RAA 𝒾 → LEM 𝒾
RAA→LEM = ?

-- Exercise 3.20.
isContr-Σ⇒fiber-base : {A : 𝒰 𝒾} (P : A → 𝒰 𝒿)
                     → ((a , f) : isContr A)
                     → (Σ x ꞉ A , P x) ≃ P a
isContr-Σ⇒fiber-base = ?
```

---
title: Chapter 1. Type Theory - Exercises
---

# Chapter 1. Type Theory - Exercises

```agda
module Chapter1.Exercises where

open import Chapter1.Book public
open import Utils

-- Exercise 1.1
_∘_ : {X : 𝒰 𝒾} {Y : 𝒰 𝒿} {Z : Y → 𝒰 𝓀}
    → ((y : Y) → Z y)
    → (f : X → Y)
    → (x : X) → Z (f x)
g ∘ f = λ x → g (f x)
infixl 70 _∘_

-- Exercise 1.2.
prj⇒rec-Σ : {A : 𝒰 𝒾} {B : A → 𝒰 𝒿} {C : 𝒰 𝓀}
          → ((x : A) (y : B x) → C)
          → Σ B → C
prj⇒rec-Σ = {! !}

_ : {A : 𝒰 𝒾} {B : A → 𝒰 𝒿} {C : 𝒰 𝓀}
    → (g : (x : A) (y : B x) → C)
    → (p : Σ B) → (rec-Σ g p ≡ prj⇒rec-Σ g p)
_ = {! !}

-- As the following exercises need additional theorems about the identity type,
-- we will introduce some of them now in a private block. These will be later
-- redefined in Chapter 2.
private
  _⁻¹ : {A : 𝒰 𝒾} → {x y : A} → x ≡ y → y ≡ x
  (refl x)⁻¹ = refl x
  infix  40 _⁻¹

  _∙_ : {A : 𝒰 𝒾} {x y z : A} → x ≡ y → y ≡ z → x ≡ z
  (refl x) ∙ (refl x) = (refl x)
  infixl 30 _∙_

-- Exercise 1.3.
uniq-Σ' : {A : 𝒰 𝒾} {P : A → 𝒰 𝒿} (z : Σ P)
        → z ≡ (pr₁ z , pr₂ z)
uniq-Σ' = {! !}

ind-Σ' : {A : 𝒰 𝒾} {B : A → 𝒰 𝒿} {C : Σ B → 𝒰 𝓀}
       → ((x : A) (y : B x) → C (x , y))
       → ((x , y) : Σ B) → C (x , y)
ind-Σ' = {! !}

-- Exercise 1.4.
iter⇒rec-ℕ :
    (iter : (C : 𝒰 𝒾) → C → (C → C) → ℕ → C)
  → (C : 𝒰 𝒾)
  → C → (ℕ → C → C)
  → ℕ → C
iter⇒rec-ℕ = {! !}

iter⇒rec-ℕ-comp-0 :
    (iter : (C : 𝒰 𝒾) → C → (C → C) → ℕ → C)
  → (iter-comp-0 : (C : 𝒰 𝒾) (c₀ : C) (cₛ : C → C) →  iter C c₀ cₛ 0 ≡ c₀)
  → (iter-comp-succ : (C : 𝒰 𝒾) (c₀ : C) (cₛ : C → C) (n : ℕ)
    → iter C c₀ cₛ (succ n) ≡ cₛ (iter C c₀ cₛ n))
  → (C : 𝒰 𝒾) (c₀ : C) (cₛ : ℕ → C → C)
  → iter⇒rec-ℕ iter C c₀ cₛ 0 ≡ c₀
iter⇒rec-ℕ-comp-0 = {! !}

iter⇒rec-ℕ-comp-succ :
    (iter : (C : 𝒰 𝒾) → C → (C → C) → ℕ → C)
  → (iter-comp-0 : (C : 𝒰 𝒾) (c₀ : C) (cₛ : C → C) →  iter C c₀ cₛ 0 ≡ c₀)
  → (iter-comp-succ : (C : 𝒰 𝒾) (c₀ : C) (cₛ : C → C) (n : ℕ)
    → iter C c₀ cₛ (succ n) ≡ cₛ (iter C c₀ cₛ n))
  → (C : 𝒰 𝒾) (c₀ : C) (c'ₛ : ℕ → C → C) (n : ℕ)
  → iter⇒rec-ℕ iter C c₀ c'ₛ (succ n) ≡ c'ₛ n (iter⇒rec-ℕ iter C c₀ c'ₛ n)
iter⇒rec-ℕ-comp-succ = {! !}
```

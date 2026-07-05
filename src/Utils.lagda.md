---
title: Utils
---

# Utilities

```agda
module Utils where

open import Chapter1.Book public

private
  _⁻¹ : {A : 𝒰 𝒾} → {x y : A} → x ≡ y → y ≡ x
  (refl x)⁻¹ = refl x
  infix  40 _⁻¹

  _∙_ : {A : 𝒰 𝒾} {x y z : A} → x ≡ y → y ≡ z → x ≡ z
  (refl x) ∙ (refl x) = (refl x)
  infixl 30 _∙_

ap : {A : 𝒰 𝒾} {B : 𝒰 𝒿} (f : A → B) {x x' : A} → x ≡ x' → f x ≡ f x'
ap f {x} {x'} (refl x) = refl (f x)

tr : {A : 𝒰 𝒾} (P : A → 𝒰 𝒿) {x y : A} → x ≡ y → P x → P y
tr P (refl x) = id

begin_ : {A : 𝒰 𝒾} {x y : A} → x ≡ y → x ≡ y
begin_ x≡y = x≡y
infix  1 begin_

_≡⟨⟩_ : {A : 𝒰 𝒾} (x {y} : A) → x ≡ y → x ≡ y
_ ≡⟨⟩ x≡y = x≡y

step-≡ : {A : 𝒰 𝒾} (x {y z} : A) → y ≡ z → x ≡ y → x ≡ z
step-≡ _ y≡z x≡y = x≡y ∙ y≡z
syntax step-≡ x y≡z x≡y = x ≡⟨ x≡y ⟩ y≡z

step-≡˘ : {A : 𝒰 𝒾} (x {y z} : A) → y ≡ z → y ≡ x → x ≡ z
step-≡˘ _ y≡z y≡x = (y≡x)⁻¹ ∙ y≡z
syntax step-≡˘ x y≡z y≡x = x ≡˘⟨ y≡x ⟩ y≡z
infixr 2 _≡⟨⟩_ step-≡ step-≡˘

_∎ : {A : 𝒰 𝒾} (x : A) → x ≡ x
_∎ x = refl x
infix  3 _∎
```

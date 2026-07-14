---
transition: zoom
---

## Part I: The Four Worldviews

> **Watch out!** Paradigms are *not* mutually exclusive categories. A single language can — and most modern languages do — support multiple paradigms simultaneously. When we label a language "object-oriented," we mean that OO is its dominant style, not that you cannot write imperative loops in it.

## 1. Imperative and Object-Oriented

Think of imperative programming like a step-by-step recipe: "crack two eggs, whisk them, pour into pan, stir until cooked." You specify every action in order, and the state of the dish changes with each step. Object-oriented programming is more like a kitchen brigade — each station (the sauté cook, the pastry chef) owns its own tools and ingredients, responds to requests from the head chef, and hides the messy details of how it does its work.

**Imperative: a program is a sequence of state changes.** The core concepts are variables (named mutable cells), assignment, and control flow (sequencing, selection, iteration). The model matches the machine: memory cells change over time. C is the archetype; most languages contain an imperative heart.

**Object-oriented: a program is a society of objects exchanging messages.** State is *encapsulated* inside objects; behavior travels with the data it governs; **polymorphism** lets the same message mean different things to different receivers. OO answers the imperative paradigm's scaling problem: when everything can mutate everything, large programs become unpredictable, so OO draws fences.

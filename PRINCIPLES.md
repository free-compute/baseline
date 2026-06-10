# Baseline — Principles

These are the values that the Baseline specification is built on. Any implementation that follows the spec should also understand these principles — they explain the *why* behind every technical decision.

---

## The Problem

Modern applications increasingly require users to hand over their compute, their data, and their money to centralized services. AI has accelerated this. To use AI in most apps today you must create an account, accept terms, and pay a subscription — to the app developer, to an AI company, or both.

This is not inevitable. It is a design choice.

The alternative: the user provides the compute. The developer provides the software. Nobody stands in between.

---

## Core Principles

### You Own Your Compute

Most people don't own solar panels, so they can't own their electricity. But most people do own their phone. A phone is a computer. A computer is compute. Compute runs AI.

If you own your phone, you can run AI on it for free. No subscription. No account. No middleman.

As compute becomes commoditized — faster phones, local models, affordable home servers — this principle becomes more powerful, not less. Baseline is built for that future.

### Access Over Quality

A user with an older phone running a small local model will get a rougher experience than someone using a larger model. That is honest and expected.

What is not acceptable is locking that user out entirely.

> **Quality will vary by model. Access should not.**

### The Developer Takes Nothing

A Baseline-compliant application must not:
- Proxy AI requests through developer-owned infrastructure
- Generate revenue from user AI usage
- Collect data about what users ask their AI
- Require payment to the developer to unlock AI features

The developer writes the software. The user runs the compute. That is the entire relationship.

### No Centralized Server Required

If the developer's servers went offline tomorrow, every Baseline-compliant app must continue to work. The architecture cannot have a single point of control that belongs to anyone other than the user.

### Transparency

Users should be able to understand exactly how their data is being processed. This means:
- Open source code
- Published prompts and transformation logic
- Clear disclosure of which provider is receiving data
- No hidden behavior

A project about clarity should itself be clear.

---

### The Frontend Is the Same for Everyone

The user interface must behave identically regardless of which backend the user has configured. A user on a local 1B model and a user on a cloud API should see the same screens, the same options, and the same experience.

Implementations must not:
- Show degraded UI for users on smaller or local models
- Lock features behind specific provider types
- Display which provider is in use in a way that implies hierarchy
- Create "tiers" of experience based on how the user chose to provide compute

The only visible difference between backends is speed. Everything else is the same.

---

## What Baseline Is Not

Baseline is not a business. It does not provide AI services, host infrastructure, or generate revenue. It is a standard — like a building code. The standard exists to protect users, not to profit from them.

Baseline does not endorse any specific AI provider, model, or hardware. It only defines what it means to give users control over whichever of those they choose.

---

## On Open Source

The specification is released under CC0 (public domain) so there are no legal barriers to adoption. The reference implementations are released under AGPL-3.0 so no one can take the code and make it proprietary.

The combination is intentional: the ideas travel freely, the implementations stay open.

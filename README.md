# Baseline

**The standard for user-owned AI compute in applications.**

Baseline is an open specification that defines how applications should connect users to AI compute they own or control — without requiring subscriptions, centralized servers, or payment to the application developer.

It is not an app. It is the baseline that apps are built on.

---

## The Principle

Most people don't own solar panels, so they can't own their electricity — they rent it from a utility. But most people *do* own their phone. Your phone is your compute. If you own your compute, you can run AI on it. You should not have to pay anyone for that.

If you want to pay a company to host AI for you — that is your choice. But it must never be a requirement.

> **Information is public. Compute is owned. Access should not depend on either.**

---

## What Baseline Defines

- How applications discover AI compute available on a user's device
- How applications connect to user-managed remote servers
- How applications use third-party cloud APIs the user holds the keys to
- A unified interface so any provider is interchangeable
- Privacy guarantees that implementations must uphold
- What it means to be Free Compute compliant

See [`spec/FREE_COMPUTE.md`](./spec/FREE_COMPUTE.md) for the full specification.

---

## Who This Is For

**App developers** who want to give users full control over their AI compute without building the provider abstraction from scratch.

**Users** who want to understand what a Baseline-compliant app promises them.

**Anyone** who believes compute ownership matters.

---

## Implementations

Baseline is language and platform agnostic. Any developer can implement the specification in any stack.

| Name | Platform | Language | Description |
|------|----------|----------|-------------|
| *(reference implementation coming soon)* | iOS / Android | TypeScript / Ionic / Angular | Neutral news reader |

To add your implementation, open a pull request.

---

## Built With AI, Openly

Baseline was designed with the assistance of AI (Claude by Anthropic). This is disclosed openly — a project about transparency should be transparent about how it was made.

---

## License

- **Specification** ([`spec/FREE_COMPUTE.md`](./spec/FREE_COMPUTE.md)): [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) — public domain, no restrictions
- **Everything else**: [AGPL-3.0](./LICENSE) — forks must stay open source

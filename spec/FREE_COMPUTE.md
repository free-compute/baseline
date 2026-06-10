# Free Compute Specification

**Version:** 0.1  
**Status:** Draft  
**License:** CC0 1.0 Universal (public domain — no restrictions on use or implementation)

---

## Purpose

This specification defines how applications should connect users to AI compute they own or control, without requiring any centralized infrastructure, subscription, or payment to the application developer.

Any application, in any language or platform, that follows this specification allows users to bring their own compute — whether that is a model running on their phone, a server they manage at home, or a cloud API key they hold themselves.

The spec does not care how the AI is used. It only defines how it is discovered, connected, and called.

---

## Core Principles

**1. The user owns the compute.**
The application never provides or proxies AI compute on the user's behalf. All AI calls go directly from the user's device to a provider the user has configured.

**2. No centralized server is required.**
A compliant application must function without any server owned or operated by the application developer. Removing the developer's infrastructure should not break the application.

**3. The developer makes no money from AI usage.**
A compliant application must not insert itself between the user and their AI provider in a way that generates revenue or usage data for the developer.

**4. Configuration belongs to the user.**
The user decides which provider to use. The application must not choose a default provider that benefits the developer, sends data anywhere without the user's knowledge, or changes without the user's consent.

**5. Privacy is non-negotiable.**
Prompts, responses, and usage patterns must never be sent to the application developer. What a user asks their AI is between the user and the provider they chose.

---

## Provider Types

A compliant implementation must support at least one of the following provider types. Supporting all of them is strongly recommended.

### Type 1: On-Device Local LLM

An AI model running directly on the user's device, accessed via a local HTTP server on localhost.

Examples: Locally (LM Studio), PocketPal AI, Ollama, LM Studio desktop, Jan

**Discovery:** Scan known localhost ports for an OpenAI-compatible `/v1/models` or `/v1/chat/completions` endpoint. Common ports: `1234`, `11434`, `8080`, `8081`, `3000`.

**Connection:** Standard HTTP to `http://localhost:{port}/v1/`

**Auth:** Usually none required. API key field should be optional.

**Cost to user:** $0

---

### Type 2: User-Managed Remote Server

An AI server the user runs themselves — on a home computer, a VPS they pay for, or any machine they control. Accessed over a network.

Examples: Ollama on a home server, LM Studio with remote access enabled, LM Link

**Discovery:** User provides a URL. No automatic discovery.

**Connection:** Standard HTTP/HTTPS to user-provided URL.

**Auth:** Optional API key, set by the user on their own server.

**Cost to user:** Whatever they pay for their own hardware or VPS.

---

### Type 3: Third-Party Cloud API

A hosted AI service the user has an account with. The user holds the API key — the application never does.

Examples: Google Gemini, OpenAI, Anthropic, any OpenAI-compatible cloud API

**Discovery:** User provides an API key and optionally a base URL.

**Connection:** Standard HTTPS to the provider's API endpoint.

**Auth:** Bearer token (API key) in the Authorization header.

**Cost to user:** Whatever the provider charges. Free tiers exist (e.g. Gemini).

---

## The Provider Interface

Every provider type must be callable through the same interface. The implementation language determines the syntax, but the contract is the same:

```
complete(input) → output

input:
  - messages: list of { role: "system" | "user" | "assistant", content: string }
  - model: string (optional — use provider default if omitted)
  - max_tokens: integer (optional)

output:
  - content: string
  - provider: string (which provider was used)
  - error: string | null
```

All providers are called identically from the application's perspective. Switching providers requires no changes to the application logic — only the configuration changes.

---

## Provider Selection

1. Always use the provider the user has configured.
2. Never switch providers without the user's knowledge.
3. Never fall back silently to a different provider on failure. Fail loudly with a clear error.
4. Never contact a provider the user has not explicitly configured.

---

## First-Run Configuration

A compliant application should walk the user through provider setup on first launch. The flow must:

1. Attempt to auto-detect any running local LLM server (Type 1)
2. If found, offer to connect automatically
3. If not found, present all provider types clearly with their cost implications
4. Confirm the connection works before saving configuration
5. Never configure a provider silently or without user action

---

## Privacy Requirements

A compliant implementation must:

- Never send prompts, responses, or usage data to any server owned by the application developer
- Never log AI interactions in a way that leaves the user's device
- Never include user content in crash reports or analytics
- Store all configuration locally on the user's device
- Make it clear to the user which provider is receiving their data

---

## Frontend Consistency Requirement

A compliant implementation must present an identical user interface regardless of which provider type the user has configured.

- No features may be locked to specific provider types
- No UI state may indicate that one provider is superior to another
- The user experience must not degrade visibly based on provider choice
- Provider configuration is a settings concern — it must not surface in the main application UI

The only acceptable difference between provider types in the user interface is response speed. Everything else must be identical.

---

## What This Spec Does Not Cover

- The content or structure of prompts (application-specific)
- UI or UX beyond first-run configuration
- Model selection or quality
- Streaming responses (recommended but not required for v0.1)
- Authentication between applications (out of scope)

---

## Implementing This Spec

Any developer in any language can implement this specification. There is no registration, no certification, and no fee.

If your application follows these principles, it is Free Compute compliant.

Reference implementations:
- TypeScript / Ionic / Angular: [Baseline](https://github.com/your-org/baseline) *(this repo)*

To list your implementation, open a pull request adding it to this document.

---

## License

This specification is released under **CC0 1.0 Universal** (public domain). You may implement it, fork it, translate it, or build on it without restriction and without crediting this project. The goal is adoption, not attribution.

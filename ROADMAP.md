# Baseline — Specification Roadmap

---

## Spec v0.1 — Foundation ✓
*Current draft*

- Core principles documented
- Three provider types defined (on-device, user-managed server, third-party cloud)
- Unified provider interface contract
- Provider discovery (local LLM port scanning)
- First-run configuration requirements
- Privacy requirements

---

## Spec v0.2 — Validated by Implementation
*After the first reference implementation is built and running*

The spec should not be declared stable until at least one real implementation has tested it. v0.2 will refine based on what the reference implementation reveals.

- Resolve ambiguities found during implementation
- Define streaming response handling
- Define error codes and failure behavior more precisely
- Add guidance for platforms with restricted networking (iOS sandbox, etc.)
- Incorporate feedback from early implementors

---

## Spec v1.0 — Stable
*After at least two independent implementations exist*

- Stable, versioned spec that implementations can target without fear of breaking changes
- Formal compliance checklist
- Conformance test suite (language-agnostic, HTTP-based)
- Migration guide from v0.x

---

## Future Considerations
*Not committed, not scheduled*

- Spec v1.1: Guidance for desktop platforms (macOS, Windows, Linux)
- Spec v1.2: Guidance for server-side / headless implementations
- Multi-modal providers (image, audio)
- Provider capability negotiation (what models/features are available)
- Standardized model metadata format

---

## Reference Implementations

Spec versions and implementation status are tracked separately. An implementation targets a specific spec version.

| Repo | Spec Version | Status |
|------|-------------|--------|
| *(news reader — coming soon)* | v0.1 | In development |

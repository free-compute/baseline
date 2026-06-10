# Baseline — Roadmap

---

## v0.1 — Proof of Concept
**Goal:** Prove the end-to-end flow works. One feed, one AI provider, one article view.

- [ ] Scaffold React Native app (iOS + Android)
- [ ] Add an RSS feed by URL
- [ ] Fetch and parse feed articles
- [ ] Connect to Google Gemini (first AI provider — free tier, easy to test)
- [ ] Display a single article in the baseline format:
  - Original headline
  - Neutral headline
  - Key facts
  - Why it matters
  - Opinion / speculation
  - Link to original
- [ ] Basic settings screen (feed URL, API key)

---

## v0.2 — All AI Providers
**Goal:** Every user has a path in, regardless of what they own or what they pay.

- [ ] Local LLM app detection (auto-detect Locally, PocketPal AI on localhost)
- [ ] Ollama support
- [ ] OpenAI support
- [ ] Anthropic support
- [ ] Any OpenAI-compatible endpoint support
- [ ] First-run setup wizard (walks user through choosing a provider)
- [ ] Test call to confirm connection before saving settings

---

## v0.3 — Real Mobile Experience
**Goal:** The app feels like something you'd actually use every morning.

- [ ] Morning push notification ("Your digest is ready")
- [ ] User-configurable digest time
- [ ] Multiple feeds — add, remove, pause
- [ ] Curated starter feed list (user opts in, nothing added by default)
- [ ] Reader modes: Reporter, Analyst, Media Literacy
- [ ] Framing analysis (Media Literacy mode)
- [ ] Offline reading — cached digests available without internet

---

## v0.4 — Polish and Accessibility
**Goal:** Works well on every device, not just new ones.

- [ ] Performance testing on older phones (iPhone 11, mid-range Android)
- [ ] iOS background task handling — digest generates reliably at scheduled time
- [ ] Graceful degradation for small local models (shorter summaries, simpler prompts)
- [ ] Accessibility: dynamic text size, screen reader support
- [ ] Error handling: feed down, AI timeout, no internet
- [ ] App icon and basic visual design

---

## v1.0 — Public Launch
**Goal:** Ready for anyone to download and use.

- [ ] App Store submission (iOS)
- [ ] Google Play submission (Android)
- [ ] Contribution guide (CONTRIBUTING.md)
- [ ] Finalized prompts published in repo
- [ ] Basic documentation for self-builders (how to clone and run locally)

---

## v2.0 — Future
Ideas for after v1.0 ships. Not committed, not scheduled.

- YouTube channel transcript support
- Podcast feed support
- Newsletter parsing
- Custom prompt editing for power users
- Per-feed reader mode overrides
- Multiple digest schedules (morning + evening)

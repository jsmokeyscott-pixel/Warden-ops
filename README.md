# 🔒 WARDEN Ops

**Zero Trust for AI Agents**: a defensive reference model for securing autonomous AI agents, grounded in lessons learned from DARPA's AI Cyber Challenge (AIxCC), DARPA's DICE program, NIST CAISI agent-hijacking research and the DoD zero trust pillars.

> Never trust the agent. Verify every identity, every action and every output.

**Live site:** https://jsmokeyscott-pixel.github.io/Warden-ops/

**Scope:** defensive theory and architecture only. It contains no offensive techniques, tooling or attack instructions.

---

## Why it exists

Zero trust was built for users and devices. AI agents are a new kind of identity: they can **act**, they **read untrusted content**, and they **trust each other**. The IC CIO put the tension plainly: zero trust traditionally means least privilege, while agents are usually given whatever they need to operate independently. WARDEN extends zero trust to cover that gap.

## The model

Six pillars, **W-A-R-D-E-N**, plus two rails that run across all of them.

| | Pillar | Core question | Grounded in |
|---|---|---|---|
| **W** | Workload Identity | Who is this agent? | IC CIO's "digital birth certificate" for agents (DoDIIS 2026) |
| **A** | Access: Least & Just-in-Time | What may it touch, right now? | IC attribute-based enforcement; CISA guidance on over-permissioned agents |
| **R** | Runtime Containment | How far can damage spread? | AIxCC: stability decided rankings; resource-exhaustion crashes |
| **D** | Data & Context Integrity | Can what it reads steer it? | NIST CAISI: agent hijacking = indirect prompt injection |
| **E** | Evidence-Based Verification | Is its output actually right? | AIxCC: 37.7–45.6% of baseline AI patches that passed automated checks failed manual review |
| **N** | No Transitive Trust | Should it trust that other agent? | DARPA DICE: robust to compromised or rogue agents; agent trust bias |
| **M** | Continuous Monitoring *(rail)* | Would we see it go wrong? | SOCOM: detect compromise within minutes; AIxCC telemetry gaps |
| **H** | Human Authority *(rail)* | Who owns the call? | AIxCC: humans still needed to verify AI fixes; design for human imperfection |

### Zero trust tenets, agent edition
- **Never trust, always verify:** identities, actions *and* outputs
- **Assume breach:** any agent can be hijacked through what it reads
- **Least privilege, just-in-time:** autonomy inside the task, no standing power outside it
- **Data is never command:** untrusted content can't steer the agent
- **Evidence over confidence:** proof scales with consequence

---

## Features

- **Dashboard:** pillar board, rails, tenets and a link to HALO
- **Pillars:** each pillar's principle, rationale, defensive controls, warning signs, evidence and lessons learned, and its DoD ZT pillar mapping
- **Assess:** maturity self-assessment from Traditional to Optimal across all 8 areas, with GO / HOLD / NO-GO, per-pillar bars and the next priority step
- **Drill:** 12 randomized defensive scenarios scored against an 80% standard
- **Sources:** mapping to the DoD ZT pillars and the full source list, with print / save as PDF
- Light and dark mode, mobile-friendly, a single self-contained file, no build step

## Pairs with HALO

[HALO Ops](https://jsmokeyscott-pixel.github.io/halo-ops/) answers *who decides* (the human-in-the-loop layers). WARDEN answers *how much to trust the agent*. Use HALO to set the authority structure and WARDEN to secure the agents working inside it.

---

## Sources

1. Zhang et al., *SoK: DARPA's AI Cyber Challenge (AIxCC): Competition Design, Architectures, and Lessons Learned*, USENIX Security 2026. https://arxiv.org/abs/2602.07666
2. Georgia Tech, *Georgia Tech Researchers Share AI Cyber Challenge Lessons at USENIX Security 2026*. https://www.cc.gatech.edu/news/georgia-tech-researchers-share-ai-cyber-challenge-lessons-usenix-security-2026
3. DARPA, *DICE: Decentralized Artificial Intelligence through Controlled Emergence*, program Q&A. https://www.darpa.mil/sites/default/files/attachment/2026-06/programs-dice-q-a.pdf
4. NIST CAISI, technical blog on AI agent hijacking evaluations. https://www.nist.gov/node/1872381
5. Cloud Security Alliance, research note on CAISI's AI Agent Security Agenda (Apr 2026). https://labs.cloudsecurityalliance.org/wp-content/uploads/2026/04/CSA_research_note_nist-caisi-ai-agent-security-agenda-2026_20260414-csa-styled.pdf
6. Breaking Defense, *Agentic AI turning Zero Trust cybersecurity 'on its head'* (Aug 2026). https://breakingdefense.com/2026/08/agentic-ai-turning-zero-trust-cybersecurity-on-its-head/
7. GDIT, *National cyber strategy doubles down on zero trust, AI*. https://www.gdit.com/perspectives/latest/national-cyber-strategy-doubles-down-on-zero-trust-ai-and-protecting/
8. DoD CIO, *Zero Trust Overlays*. https://dodcio.defense.gov/Portals/0/Documents/Library/ZeroTrustOverlays.pdf
9. Congressional Research Service, IF13151, *Agentic Artificial Intelligence and Cyberattacks* (Jul 2026). https://www.everycrsreport.com/files/2026-07-06_IF13151_497c5e97f35d00235c284eb2322b4e1e4aba99c4.pdf

> WARDEN is an original conceptual model that synthesizes these public sources. It is **not** an official DARPA, NIST or DoD framework.

---

## Deploy (GitHub Pages)

1. Create a public repo named `warden-ops`.
2. Add `index.html` and `README.md` to the root.
3. Go to **Settings → Pages**, choose **Deploy from a branch**, then `main` / `(root)`, and **Save**.
4. The site appears at `https://<your-username>.github.io/warden-ops/`.

## Files

```
index.html   # the entire app (HTML + CSS + JS)
README.md    # this file
```

## Version

v1.0 · Concept model and application by Scotty.

# 00_INDEX: Who-am-I showcase site
Last verified: 2026-11-24 · Research depth: Quick (15 sources identified, 14 opened)

## Project question
Build a professional personal website that replaces a traditional resume. It should (1) show past products,
(2) show current projects, and (3) show how to collaborate and on which kinds of projects. It should be
visually impressive enough to attract recruiters AND collaborators (balanced audience, English, multi-disciplinary profile).

## Decisions (one line each; status in 05_decisions.md)
- D1 Motion strategy: Calm core + 1–2 signature scroll moments. **Proposed**
- D2 Architecture: one landing page with two audience paths + deep-linkable case-study pages. **Proposed**
- D3 Assets: user's real artifacts + code-drawn visuals; no kie.ai generation by default. **Proposed**
- D4 Hosting: GitHub Pages from this repo. **Proposed (low stakes)**

## File map
- `01_research_brief.md`: findings, design rules derived from them, conflicts, sources with read level
- `05_decisions.md`: decision log with options, scoring, kill criteria
- `07_security_review_scroll-craft.md`: third-party skill audit
- `../content/INVENTORY.md`: content the user must supply (projects, current work, collaboration offer)

## First build milestone (after the user approves D1–D3 and fills INVENTORY.md)
1. Brief + journey + score table (scroll-craft Steps 0–2), co-decided with the user.
2. Static skeleton first: hero (value proposition visible at < 10 s), proof strip, 3–5 case-study cards, Now, Work-with-me, contact.
   Known-answer test: with motion disabled (prefers-reduced-motion), every section is readable and every CTA reachable.
3. Add the signature move(s) only after the skeleton passes.
   Test: LCP ≤ 2.5 s, CLS ≤ 0.1 on a throttled mobile profile; sticky nav visible during any pinned section.
4. Verification pass (scroll-craft Step 5) and contact sheet at desktop, mobile, reduced motion.

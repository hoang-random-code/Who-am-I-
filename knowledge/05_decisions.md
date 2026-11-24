# 05: Decision log
Last verified: 2026-11-24 · Weights and scores are **Assumption** (set by Claude, to be confirmed by the user)

## D1. Motion strategy. Status: Proposed
Question: how much scroll-driven motion should the site use?
Criteria (weight): Clarity for time-poor, task-oriented evaluators (35%) · Memorability / "impress" (25%) ·
Accessibility and performance (20%) · Build and maintenance cost (20%)

| Option | Clarity | Impress | A11y/Perf | Cost | Weighted |
|---|---|---|---|---|---|
| A. Static, polished (no scroll effects) | 9 | 4 | 10 | 9 | 0.35·9+0.25·4+0.2·10+0.2·9 = **7.95** |
| B. Calm core + 1–2 signature scroll moments | 8 | 8 | 8 | 7 | 2.8+2.0+1.6+1.4 = **7.80** |
| C. Full cinematic scrollytelling (every section scroll-driven) | 4 | 9 | 4 | 3 | 1.4+2.25+0.8+0.6 = **5.05** |

- Sensitivity: A and B are within 0.15. If Impress weighs 30% and Clarity 30%, B wins (7.8 vs 7.7). C loses under any plausible weights.
- Recommendation: **B**, because the user's goal explicitly includes "impress". It stays close to A on clarity only if the rules hold:
  hero text is static and readable at once; pinned sections stay short and below the fold; key content (case-study summaries,
  contact) never sits inside a scrolljack; sticky nav; full `prefers-reduced-motion` fallback [S13, S14, S15].
- Reversible: yes (the engine is layered on a static skeleton). Confidence: Med.
- What would change it: a usability test where 2 of 3 non-designer testers fail to find "how to work with me" within 30 s → drop to A.
- Kill criterion: mobile LCP > 4 s or CLS > 0.25 after optimisation → remove the heaviest scroll moment [S9].

## D2. Information architecture. Status: Proposed
Options: (a) one long page only · (b) one landing page with two audience paths + a detail page per case study · (c) classic multi-page site.
Recommendation: **(b)**. The landing page answers the 10 s test and routes "Hiring" vs "Collaborating". Detail pages hold the
problem → role → process → result story [S1, S2], and each section and page has a stable URL to send [S10].
Confidence: Med.

## D3. Visual assets. Status: Proposed
Options: (a) the user's real artifacts (screenshots, charts, reports, photos) + code-drawn visuals (SVG/CSS/canvas) · (b) AI-generated
photoreal imagery via kie.ai (costs credits; uploads reference images to a third-party host).
Recommendation: **(a)**. Real artifacts are assessment signals [S8], cost nothing and send no data out.
Generated imagery can never stand in for real work and could mislead if it looks like the user's real output.
Revisit (b) only for a purely decorative hero plate, with explicit approval and a credit estimate first. Confidence: High.

## D4. Hosting. Status: Proposed (low stakes)
GitHub Pages from this repo (free, static, versioned). Alternatives: Vercel/Netlify. Decide at deploy time.

## Sitemap proposed under D2 (for review)
1. Hero: name, one-line positioning ("I build X for Y"), 2 CTAs (See work · Work with me), 1 proof line (headline metric/logo/result)
2. Proof strip: 3–4 verifiable facts, each linked to evidence
3. Selected work: 3–5 case studies (card → detail page: problem, role, process, result, constraints, artifacts)
4. Now: current projects with status and what help/partners are wanted
5. Work with me: engagement modes (hire full-time · project/contract · research collaboration · advisory), the kinds of projects you
   take, how a collaboration runs (steps), what you need from the partner
6. About: short story, principles, CV download (PDF) for recruiters
7. Contact: e-mail + calendar link + LinkedIn/GitHub. No form that collects more than needed.

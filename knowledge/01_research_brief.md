# 01: Research brief: what makes a personal showcase site work
Last verified: 2026-11-24 · Depth: Quick · Tags: **Fact** (sourced), **Theory**, **Assumption**

## 1. Question and decision it informs
How are personal showcase/portfolio sites structured, what content do evaluators look for, and how do visitors
actually interact with them? The answer sets the page architecture, content order and motion budget for the build.

## 2. Scope, search and coverage
- Searched: web search (general index) for HCI/UX peer-reviewed work, NN/g usability research, W3C/web.dev standards,
  recruiter surveys. Opened the primary pages/PDFs listed in §6. Search date 2026-11-24.
- Not searched: Google Scholar/ACM DL exhaustively, Scopus, non-English literature, paid industry reports.
- Saturation: not reached (Quick depth). Gap claims below are **Low** confidence.
- Note: a lot of the "portfolio advice" online is blogs (Tier 3). It was used only to find sources, never as evidence.

## 3. Findings (each with source IDs from §6)

### F1. You have ~10 seconds, and the aesthetic verdict comes first (Confidence: High)
- **Fact** Visual appeal is judged within 50 ms and agrees well with judgments made at 500 ms [S6, S7].
- **Fact** Visual complexity and colorfulness explain about half of the variance in 500 ms appeal ratings (with demographics).
  Participants >45 years preferred *low* complexity; PhD holders were most negatively affected by high colorfulness [S7].
- **Fact** Page-leaving probability is highest in the first 10 s. "To gain several minutes of user attention, you must clearly
  communicate your value proposition within 10 seconds." (Nielsen 2011, based on Liu, White & Dumais, SIGIR 2010; 2 billion+ dwell times) [S4].
- **Fact** Recruiters' first resume screen averages 7.4 s. Simple layouts, clear headings, F/E-pattern and bold titles held
  attention; cluttered layouts and multiple columns did not (Ladders 2018, industry study) [S12].
- → **Design rule**: the first viewport must state *who / what you do / for whom / proof* in plain text, with no animation gating it.

### F2. Attention is concentrated at the top; people scan, not read (Confidence: High)
- **Fact** 57% of viewing time is above the fold, 74% in the first two screenfuls, 81% in the first three (NN/g eyetracking 2018) [S3].
- **Fact** "Very rarely will hiring managers take the time to read your entire portfolio word for word" [S1].
- → **Design rule**: the strongest proof (best 1–2 projects, one headline metric) goes in screens 1–3. Everything else is optional depth.

### F3. Curate 3–5 case studies; tell problem → role → process → result (Confidence: Med, single organisation)
- **Fact** NN/g surveyed 204 hiring professionals. Recommendation: 3–5 detailed case studies, each covering problem/hypothesis,
  your specific role and collaborators, how you reached the solution, how it solved the problem, challenges and discarded options,
  and the effect on users and the business [S1].
- **Fact** For research-type work: 3–5 current projects, prioritised by impact and recency; state context, team, constraints and
  value demonstrated; "visual appeal is a secondary concern" [S2].
- Caveat: both from NN/g (UX field). Transfer to finance/data/research profiles is **Assumption** (plausible, since evaluators are also time-poor).

### F4. Verifiable evidence beats claims (Confidence: Med, single qualitative study)
- **Fact** Employers on GitHub (7 employers + 6 job seekers, interviews) trusted cues that are *costly to fake* and *easy to verify*
  (signaling theory). Side projects signalled passion (reliable). Project ownership signalled initiative (reliable, easy to verify).
  Star/fork counts signalled popularity (**unreliable**) [S8].
- **Theory** Signaling theory: *assessment signals* (costly to produce) are more credible than *conventional signals* (cheap to fake) [S8].
- → **Design rule**: every claim links to an artifact: live demo, repo, notebook, report PDF, chart from real data.
  Avoid skill-percentage bars, logo walls without context, and vanity counts.

### F5. Make sections deep-linkable for each audience (Confidence: Low–Med, single survey)
- **Fact** 85% (72/85) of recruiters said they would visit a link to *a relevant part* of an ePortfolio sent by e-mail.
  73% would visit a link in an e-mail signature or cover letter. Less-experienced recruiters were more likely to click [S10].
- → **Design rule**: stable anchors and URLs (`/#work-with-me`, `/work/<project>`) so you can send the exact part
  to a recruiter or a partner.

### F6. Looks drive perceived usability and credibility (Confidence: High)
- **Fact** Perceived aesthetics correlated strongly with perceived usability before and after use. Post-use perceptions were
  affected by aesthetics, not by actual usability (ATM simulation) [S5, abstract-level].
- **Fact** In 2,684 participants' credibility comments, "design look" was the most frequent theme (46.1% of comments) [S11, summary-level].
- → Supports investing in polish. Combined with F1, polish means *calm, low-complexity and consistent*, not *busy*.

### F7. Scroll-driven motion is a cost that must buy comprehension (Confidence: Med–High)
- **Fact** Scrolljacking (changing scroll pace/direction) hurt control, discoverability, efficiency and task success. It was worst when
  users had to read changing text. Task-oriented users were "highly annoyed". It worked when short and used for progressive disclosure
  (BBC). Sticky navigation served as an escape hatch. Mobile made everything worse [S13].
- **Fact** Parallax: content was missed or slow, and average users were indifferent ("aren't 'wowed'"). Designers and developers are
  the ones most impressed [S14].
- **Fact** WCAG 2.3.3 (AAA): non-essential motion triggered by interaction must be possible to disable. Parallax is named as typically
  non-essential. Vestibular reactions include dizziness, nausea and migraine [S15].
- **Fact** Core Web Vitals "good" at p75: LCP ≤ 2.5 s, INP ≤ 200 ms, CLS ≤ 0.1 [S9].

## 4. Conflicts and how they resolve
| Tension | Side A | Side B | Likely reason | Resolution for this build |
|---|---|---|---|---|
| "Impress" vs usability | Aesthetics drive credibility [S5, S6, S11] | Fancy scroll effects don't impress users and hurt tasks [S13, S14] | Aesthetics ≠ motion. Static polish is judged in 50 ms; motion costs time | Spend the "wow" on typography, composition and one functional signature move, not on many effects |
| Scrolljacking can help | BBC case aided comprehension [S13] | Most sites disoriented users [S13] | Functional, short, after the fold vs decorative and long | Allow 1–2 pinned moments that *explain* a project (e.g. data story), kept short, below the hero, with sticky nav |
| Visual stunning vs content | Designers feel pressure to be stunning [S2] | Evaluators want process and impact [S1, S2] | Different audiences (peers vs hiring managers) | Optimise for evaluators; the craft itself is a small proof for design-literate partners |

## 5. Known / contested / missing
- **Known**: 10 s value proposition; top-heavy attention; curated case studies; verifiable proof; reduced-motion support.
- **Contested**: whether scroll storytelling *increases* recruiter/partner conversion. No direct evidence found either way.
- **Missing** (Low confidence; search not exhaustive): peer-reviewed studies on *personal* websites for finance/research
  professionals, and on "work with me" pages converting collaborators. Treat that section's design as **Assumption** and measure
  it after launch (privacy-friendly analytics or simply track inbound e-mails per source link).

## 6. Sources (all opened in this session unless noted)
| ID | Citation | Link | Tier | Read level |
|---|---|---|---|---|
| S1 | Krause, R. (2019-08-04). 5 Steps to Creating a UX-Design Portfolio. Nielsen Norman Group. | https://www.nngroup.com/articles/ux-design-portfolios/ | 1 (industry research) | Full text |
| S2 | Kane, L. (2019-03-10). Portfolios for UX Researchers: Top 10 Recommendations. NN/g. | https://www.nngroup.com/articles/ux-researcher-portfolio/ | 1 (industry) | Full text |
| S3 | Fessenden, T. (2018-04-15). Scrolling and Attention. NN/g. | https://www.nngroup.com/articles/scrolling-and-attention/ | 1 (industry) | Full text |
| S4 | Nielsen, J. (2011-09-11). How Long Do Users Stay on Web Pages? NN/g (reports Liu, White & Dumais, SIGIR 2010). | https://www.nngroup.com/articles/how-long-do-users-stay-on-web-pages/ | 1 (secondary report of peer-reviewed study) | Full text of article; SIGIR paper not opened |
| S5 | Tractinsky, N., Katz, A.S., Ikar, D. (2000). What is beautiful is usable. *Interacting with Computers* 13(2), 127–145. | https://doi.org/10.1016/S0953-5438(00)00031-X | 1 | Metadata verified (Crossref). Findings from abstract excerpts only |
| S6 | Lindgaard, G., Fernandes, G., Dudek, C., Brown, J. (2006). Attention web designers: You have 50 milliseconds to make a good first impression! *Behaviour & Information Technology* 25(2), 115–126. | https://doi.org/10.1080/01449290500330448 | 1 | Metadata verified (Crossref). Findings from abstract excerpts only |
| S7 | Reinecke, K., Yeh, T., Miratrix, L., et al. (2013). Predicting users' first impressions of website aesthetics with a quantification of perceived visual complexity and colorfulness. CHI 2013, 2049–2058. | https://kgajos.seas.harvard.edu/papers/reinecke13aesthetics.pdf | 1 | Full text |
| S8 | Marlow, J., Dabbish, L. (2013). Activity traces and signals in software developer recruitment and hiring. CSCW 2013, 145–156. | https://doi.org/10.1145/2441776.2441794 | 1 | Full text (author PDF) |
| S9 | web.dev. How the Core Web Vitals metrics thresholds were defined. | https://web.dev/articles/defining-core-web-vitals-thresholds | 1 (official) | Full text |
| S10 | Leahy, R.L., Filiatrault, A. (2017). Employers' perceptions of the benefits of employment electronic portfolios. *International Journal of ePortfolio* 7(2), 217–223. | https://files.eric.ed.gov/fulltext/EJ1159830.pdf | 1 (quartile [Unverified]) | Full text |
| S11 | Fogg, B.J., et al. (2002). How Do People Evaluate a Web Site's Credibility? Consumer WebWatch / Stanford. | https://advocacy.consumerreports.org/research/how-do-people-evaluate-a-web-sites-credibility | 1–2 (institutional report) | Summary page only |
| S12 | HR Dive (2018). Eye tracking study shows recruiters look at resumes for 7 seconds (reports Ladders 2018). | https://www.hrdive.com/news/eye-tracking-study-shows-recruiters-look-at-resumes-for-7-seconds/541582/ | 2–3 (trade press on an industry study) | Full article; Ladders report not opened |
| S13 | Paul, S. (2023-08-06). Scrolljacking 101. NN/g. | https://www.nngroup.com/articles/scrolljacking-101/ | 1 (industry) | Full text |
| S14 | Sherwin, K. (2019-01-20). What Parallax Lacks. NN/g. | https://www.nngroup.com/articles/parallax-usability/ | 1 (industry) | Full text |
| S15 | W3C WAI. Understanding SC 2.3.3: Animation from Interactions (Level AAA). | https://www.w3.org/WAI/WCAG21/Understanding/animation-from-interactions | 1 (standard) | Full text |

Excluded: CareerBuilder 2017 social-screening survey (page returned 403, not opened). HackerRank Developer Skills Report
(only secondary coverage found). Blog portfolio guides (Tier 3).

# AI-Powered Assistance in Formulating Research Questions

**[Live site](https://ethical-tech-colab.github.io/ai-research-question-assistant/)** ·
**[Research report](ResearchQuestions-Paper.md)** (plain-language, non-technical)

An [Ethical Tech CoLab](https://github.com/Ethical-Tech-CoLab) project on how AI supports researchers in developing rigorous, answerable research questions — and what guardrails that use requires.

**🔗 Live site: https://ethical-tech-colab.github.io/ai-research-question-assistant/**

Yorke E. Rhodes III, Nathaniel Fossella, Alexa Shamie, Kirsten Co, Taylor Badt, Amanda Lindsey, Grace Driscoll, Mohagani Townsend, Pegi Bracaj, Vedant Jain

> **Abstract:** AI is increasingly used to help academic researchers pose relevant research questions by mining vast literature for insights. This paper is an overview of how AI techniques and tools address key tasks in a researcher's workflow, such as finding research gaps and comparing results.

## Contents

- **[docs/paper.md](docs/paper.md)** — the full paper, covering gap identification, question formulation, state-of-the-art summarization, contradiction detection, integrated research assistants, the emotional dimension of scholarship, guardrails, and conflict-of-interest detection.
- **[docs/researcher-prompt.md](docs/researcher-prompt.md)** — the reusable prompt instructions, ready to paste into Microsoft Copilot's Researcher tool or another LLM session.
- **[docs/journal-rubric.md](docs/journal-rubric.md)** — an example journal-credibility rubric produced by that prompt.

## What the paper covers

The paper surveys five mechanisms by which AI assists question formulation:

1. **Identifying research gaps** — NLP gap finders (GapFinder), keyword co-occurrence graphs, and knowledge graph analysis surface topics that are under-investigated.
2. **Formulating new questions** — systems like SCIMUSE (a 58M-paper knowledge graph plus GPT-4) and AGATHA generate candidate questions and hypotheses; roughly 25% of SCIMUSE's ideas were rated highly interesting by expert reviewers.
3. **Summarizing the state of the art** — tools like Elicit, Scispace, and Consensus condense literature so questions are grounded in current knowledge.
4. **Comparing and contrasting findings** — Scite and NLP contradiction detectors expose disagreements in the literature, which often make for the most productive questions.
5. **Integrated research assistants** — end-to-end platforms that combine search, summarization, and suggestion in one workflow.

## Guardrails

The paper is explicit that these capabilities carry parallel risks: AI can hallucinate citations, fabricate conceptual linkages, overstate consensus, and shift a researcher's framing toward what the model predicts rather than what the literature supports. It asks researchers to:

- Independently review core sources rather than relying solely on AI summaries
- Confirm that AI-generated citations and claims are accurate and grounded in original texts
- Treat AI-suggested research questions as exploratory starting points, not final conclusions
- Reflect on and document how AI shaped their thinking, assumptions, or direction

It also proposes a **red-team agent** — a second AI acting as a quality-assurance layer that audits citations, flags unsupported claims, and surfaces missing perspectives. AI for ideation, AI for critical interrogation.

## Source

Published via Google Docs: [AI-Powered Assistance in Formulating Research Questions](https://docs.google.com/document/d/e/2PACX-1vSvmcQY-2oere7kNU0Uc5YgKTsf3bKVPVPBCHxH-Mb10rZIzksvaFkcHXFfWZFkWmB6ME8OeMEZrDso/pub). The Markdown in `docs/` is a faithful conversion of that document; the published doc remains the source of truth.

Citation markers in the text (e.g. `[scholink.org]`) appear as plain-text domain hints in the source document, which carries no hyperlinks behind them. They are preserved as-is.

**Acknowledgements:** This paper is supported by AI-enabled research assistance. Specifically, the M365 Copilot Researcher Agent running OpenAI GPT v5 model was used to partially generate and check content.

## Status

A static landing page is live on GitHub Pages at **https://ethical-tech-colab.github.io/ai-research-question-assistant/**, served from [index.html](index.html). The repository also holds the full paper and its accompanying prompt materials in `docs/`. A richer Next.js web application is planned.

---

## Peer Review

The full independent academic peer review of this report is in [PEER-REVIEW.md](PEER-REVIEW.md) (also available as [Word](peer-review/ai-research-assistant-Peer-Review.docx) under [`peer-review/`](peer-review/)).

**Recommendation:** Major revisions

**What the review found:**

- A paper whose thesis is that citations must be verifiable carries partly-wrong citations: SCIMUSE is misattributed to NeurIPS 2024 (it is ICML 2024 / arXiv:2405.17044) and the 25% figure is unsourced (S4.2, S9.4-9.5). — **Venue fixed; 25% figure still needs a located citation.**
- Genre and unit of contribution are unresolved: the document is at once "the paper" and a plain-language review of a separate repository (Foreword, S1). — *Open.*
- The central artifact, the prompt, is entirely unevaluated; every effect claim is design argument, not evidence (S1.4 vs S9.2, S7.5). — *Open.*

**Noted strength:** Lucid, intellectually honest exposition that correctly identifies its own crux: the score-plus-link pairing that makes an LLM's weakest point checkable by a non-expert (S12.1).

### Revisions applied

- **SCIMUSE venue corrected** from NeurIPS 2024 to **ICML 2024 (Gu & Krenn, preprint arXiv:2405.17044)**, with the citation added at the point of claim in `index.html`, `ResearchQuestions-Paper.md`, and `docs/paper.md` rather than only in the reference list.
- **AGATHA** is now attributed to CIKM 2020, which the paper previously left unstated.
- **S9.5 rewritten** from "some bibliographic details could not be confirmed" to a statement of the corrected attributions, keeping one item explicitly open: the ~25% highly-interesting figure is not yet located to a numbered result in the SCIMUSE paper and does not appear in its abstract. It is flagged as approximate at each point of use until pinned down.

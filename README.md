# AI-Powered Assistance in Formulating Research Questions

An [Ethical Tech CoLab](https://github.com/Ethical-Tech-CoLab) project on how AI supports researchers in developing rigorous, answerable research questions — and what guardrails that use requires.

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

The Next.js web application for this project is planned but not yet scaffolded. The repository currently holds the paper and its accompanying prompt materials.

# AI-Powered Assistance in Formulating Research Questions

Yorke E. Rhodes III<sup>a</sup>, Nathaniel Fossella<sup>a,b</sup>, Alexa Shamie<sup>a</sup>, Kirsten Co<sup>a</sup>, Taylor Badt<sup>a</sup>, Amanda Lindsey<sup>a</sup>, Grace Driscoll<sup>a</sup>, Mohagani Townsend<sup>a</sup>, Pegi Bracaj<sup>a</sup>, Vedant Jain<sup>a</sup>

**Abstract:** AI is increasingly used to help academic researchers pose relevant research questions by mining vast literature for insights. This paper is an overview of how AI techniques and tools address key tasks in a researcher's workflow, such as finding research gaps and comparing results.

**Acknowledgements:** This paper is supported by AI-enabled research assistance. Specifically, the M365 Copilot Researcher Agent running OpenAI GPT v5 model was used to partially generate and check content.

---

## 1. AI for Identifying Research Gaps

One of the first steps in posing a new research question is recognizing what hasn't been answered yet. AI can analyze large volumes of literature to detect gaps – unexplored or under-investigated topics – much faster than manual reading.

**NLP-Based Gap Finders:** Tools like GapFinder (Pessin et al. 2025) use Natural Language Processing to scan academic texts and map out "research gaps". GapFinder mines unstructured paper content (PDFs) to identify areas that are not well-covered by existing studies. This AI solution highlights topics or questions that remain unanswered in the current literature, acting as an automatic "gap analysis" for researchers. [scholink.org]

**Keyword Co-occurrence Graphs:** Another approach is to leverage network algorithms on publication data. For example, Chatterjee et al. (2024) construct keyword co-occurrence graphs from databases and then algorithmically detect structures that indicate a potential gap. Their method finds strongly connected clusters of concepts (keywords) that have not been jointly explored, i.e. "interconnected, yet uncharted" research themes. By identifying combinations of topics that appear related but lack corresponding studies, such graph-mining techniques point researchers to plausible gaps that conventional reviews might overlook. [researchgate.net]

**Knowledge Graph Analysis:** Similarly, large-scale knowledge graphs (networks of research concepts and their relationships) can be analyzed to spot missing links. If two areas are connected indirectly through known links but no direct research exists tying them together, that suggests a gap. Modern AI systems can traverse these graphs to suggest which conceptual connections lack supporting studies (and thus could be fertile ground for new research). This is aligned with earlier "literature-based discovery" methods, now enhanced by AI for scale and depth.

By automating gap discovery, AI tools give researchers a focused starting point – the not-yet-answered questions or unexplored topic intersections – on which to formulate new research questions.

## 2. AI for Formulating New Research Questions

Once gaps or novel idea spaces are identified, AI can help in formulating concrete research questions or hypotheses. Recent advancements in large language models and knowledge integration have led to systems that generate research ideas or suggest next steps, effectively acting as brainstorming partners grounded in data:

**LLM-Generated Research Ideas:** A cutting-edge example is SCIMUSE (Gu & Krenn, NeurIPS 2024), which combines a massive literature-derived knowledge graph with GPT-4 (a powerful LLM) to propose new research directions. SCIMUSE distilled knowledge from 58 million papers and then prompted GPT-4 to generate novel research project ideas tailored to a scientist's interests. The system was tested with over 100 senior researchers, who evaluated 4,451 AI-proposed ideas. Impressively, roughly 25% of these AI-generated ideas were rated as highly interesting (score 4 or 5 out of 5) by the experts. This suggests that AI can inspire creative and relevant research questions that human experts find worthwhile. Not only can such models suggest topics, they can formulate them as concrete research proposals or questions (often including contextual details like potential methodologies or collaborations). [ml4physica….github.io], [ml4physica….github.io] [ml4physica….github.io]

**Automated Hypothesis Generation:** Even prior to the latest LLMs, AI frameworks were introduced to generate hypotheses from existing findings. For instance, AGATHA (Sybrandt et al. 2020) is a system that uses a combination of graph mining and deep learning to propose new biomedical hypotheses. It analyzes millions of scientific statements (e.g. interactions between genes, diseases, chemicals) and learns to rank which unexplored connections are most plausible as potential discoveries. In a validation, AGATHA could predict research links that were later confirmed by papers published after 2015, demonstrating its ability to foresee meaningful research questions earlier. These AI-generated hypotheses provide researchers with data-driven ideas for experiments or inquiries that they might not have conceived manually. [sybrandt.com]

**Frameworks and Methodologies:** The general methodology behind these tools is to leverage vast corpora (papers, databases, knowledge graphs) and use algorithms to recombine existing knowledge into new statements. Some rely on co-occurrence patterns (e.g. discovering an intermediate concept that links two previously unrelated concepts), and others use language models to creatively assemble known facts into an innovative question or idea. The common thread is that AI can traverse and connect dots across the literature in ways a human might overlook, thereby proposing relevant and original research questions grounded in existing knowledge.

By using AI in this generative way, researchers get a systematic means of ideation. Instead of starting from scratch, they can explore a menu of AI-suggested questions/hypotheses that align with identified gaps and then use their expertise to refine or pursue the most promising ones.

## 3. AI for Summarizing the State of the Art

To pose a relevant question, a researcher must understand current knowledge: what is already known and what remains uncertain. AI assists here through advanced summarization, condensing the ever-growing literature into digestible syntheses of the state of the art:

**Automated Literature Summaries:** AI tools have emerged that can ingest multiple papers on a topic and produce a concise summary of key findings, methods, and consensus. For example, LLM-powered literature search platforms (such as Elicit, Scispace, and Consensus) allow users to ask a research question in natural language and then return a list of relevant papers each with a brief summary of its contribution. These summaries might highlight, for instance, the paper's main result or how it relates to the query. By instantly summarizing top publications, the AI gives a quick overview of the current state of knowledge without the researcher reading each paper in full. [link.springer.com]

**State-of-the-Art (SOTA) Overviews:** Some AI systems go further by performing multi-document summarization – synthesizing information across many papers into one coherent overview. Research in this area includes using models like BERT/SciBERT for scientific text summarization and even efforts to generate literature reviews automatically. For instance, recent studies (Altmami & Menai 2022) survey techniques for summarizing scientific articles using machine learning, indicating that it's feasible to produce accurate summaries of a field's developments. There are also shared tasks (e.g. the Multidocument Summarization for Literature Review challenge by Allen AI) aiming to train AI to write an aggregated summary from dozens of papers (which could serve as a draft "related work" section). [link.springer.com]

**Knowledge Graphs & Semantic Summaries:** Another approach uses structured representations. Systems like AIDA or Open Research Knowledge Graph (ORKG) represent scholarly knowledge as interconnected data (papers, methods, results as linked entries). AI can traverse such graphs to produce a summary (for example, listing all known approaches to a problem and their outcomes). This yields a high-level comparative view of the state of the art, and importantly, can highlight which nodes are missing, tying back into gap detection.

The upshot is that AI-driven summarization tools dramatically speed up literature review. A researcher can quickly learn "what is known about X" or "what methods have been tried for Y" through an AI summary, rather than spending weeks reading papers. This focused understanding helps in formulating a sharp and informed research question. It ensures that new questions are grounded in current knowledge – building on what's known and specifically targeting what is not well understood.

## 4. AI for Comparing and Contrasting Research Findings

Academic researchers often need to reconcile conflicting results in literature. AI can assist by comparing publications and flagging where their findings diverge or disagree, which is crucial for refining research questions (e.g. identifying controversies to investigate):

**Citation Analysis for Disagreements:** One prominent tool is Scite, an AI-powered citation index. Scite employs deep learning to classify the context of citations in papers as supporting, mentioning, or contrasting the cited work. In practical terms, Scite can tell you how one paper cites another – does it provide evidence that supports the earlier result, or does it present contradictory evidence? Using a database of over 800 million citation statements from papers, Scite's algorithms determine when a study's results have been challenged by subsequent studies. For a researcher, this means instead of manually collating hints of disagreement, the AI can directly show that "Paper B contradicts Paper A's conclusion about X." This capability makes it much easier to pinpoint debates or inconsistencies in the field. [jmla.pitt.edu]

**Natural Language Contradiction Detection:** Beyond citation context, AI can compare the content of findings. For example, Tawfik & Spruit (2018) developed a model for automated contradiction detection in biomedical literature. Their system first extracts the key outcome statements from studies (e.g. "Drug A improves condition B" vs. "Drug A has no effect on condition B"), then uses semantic features – like negation words, antonyms, and numeric result comparisons – to judge if two statements conflict. Applied to a corpus of clinical studies, it was able to identify when different papers answered the same question with opposing conclusions. This kind of NLP-driven approach helps surface controversies. If two high-quality papers disagree, that often leads directly to a follow-up research question ("Why do they disagree? Under what conditions does one result hold?"). [rd.springer.com]

**Cross-Paper Evidence Synthesis:** AI is also employed in systematic reviews to ensure all angles are considered. For example, machine learning classifiers can cluster papers by their outcomes or stances. In evidence-based fields, this can semi-automatically separate studies into those that support a hypothesis and those that don't. The researcher is then alerted to any clusters of contradictions that might warrant investigation.

By quickly exposing inconsistencies and debates in the literature, AI tools inform researchers where the science is not settled. These contentious areas often make for important research questions. For instance, if most studies show effect X except a few that don't, a relevant question might be: "What explains the divergent results regarding X?" AI essentially does the heavy lifting of identifying such knowledge conflicts, so the researcher can focus on resolving them.

## 5. Integrated AI Systems for Research Question Generation

Bringing all these capabilities together, modern AI research assistants aim to make it easier overall to pose relevant questions by providing end-to-end support: from mapping out existing knowledge to highlighting gaps and inconsistencies, often in an interactive workflow.

**Consolidated Platforms:** New research assistant tools (often commercial or experimental platforms like Semantic Scholar's AI, IBM Watson Discovery for science, or academic prototypes) integrate search, summarization, and analysis. For example, some AI writing assistants (e.g. Jenni.ai, Silatus) allow a user to input a tentative research topic and then automatically fetch relevant literature, summarize it, and even suggest next questions. As described by F. Bolaños et al. (2024), such systems can iteratively build a literature review: the user enters a prompt, the AI generates a draft with cited references and a brief summary of each reference's claim. This not only saves time but can surface gaps or open questions during the writing process. The assistant might note, for instance, "few studies address Z," cueing the researcher that Z is a potential new question. [link.springer.com]

**Hypothesis & Idea Suggestion:** Integrated AI agents can also directly propose questions in context. Imagine uploading a set of papers and asking "what is a good next research question here?" The AI could combine the papers' findings, point out a missing piece, and phrase a possible research question. Some experimental systems use Retrieval-Augmented Generation (RAG) – they retrieve specifics from documents and have an LLM draft a question or a set of "open problems" paragraphs. This guides researchers by explicitly listing unsolved problems gleaned from the literature. In fact, the identification of new scientific hypotheses is envisioned as a standard feature in next-gen scholarly assistants. For example, an AI might conclude a summary with: "Given the conflicting evidence on X and the lack of studies in Y, a relevant research question would be: 'How does X behave under Y conditions?'". [link.springer.com]

**Workflow Efficiency:** The overall impact of these integrated tools is on efficiency and comprehensiveness. They ensure that when formulating a question, the researcher has already seen the summarized state-of-the-art, the known gaps, and any controversial findings. This reduces the chance of proposing a question that is trivial or already answered, and instead helps focus on truly relevant, novel questions. As one survey notes, while current AI tools are not flawless (issues like possible hallucinations or missing data coverage exist), the trend is that AI will handle more of the heavy lifting in literature analysis, allowing researchers to concentrate on creative and critical thinking. Human insight remains crucial – the AI provides options and evidence, but the researcher chooses and refines the question to ensure it's meaningful and feasible. [link.springer.com], [link.springer.com]

In summary, AI contributes at every stage of the question-formulation process. It can scout the landscape of knowledge, spotlight what's unknown or disputed, and even propose draft questions. For an academic researcher, these tools act like a smart assistant, ensuring that the questions they eventually pose are informed, significant, and address genuine gaps. The end result is a faster, more focused path to developing high-impact research questions.

### Comparison of AI capabilities and example tools

Below is a comparison of AI capabilities and example tools/frameworks relevant to each aspect of posing research questions:

| AI Application | Example Tools/Methods | Capabilities & Approach |
| --- | --- | --- |
| Identifying Research Gaps | GapFinder (NLP text mining); Keyword Graph Mining (Chatterjee 2024) | Extracts under-explored topics from literature by parsing papers for unanswered questions [scholink.org]. Graph algorithms on co-occurrence networks find "hidden" topic combinations that lack studies [researchgate.net], signaling gaps. |
| Formulating New Questions | SCIMUSE (Knowledge graph + GPT-4); AGATHA (Graph + Transformer) | Generates novel research ideas or hypotheses by leveraging massive publication data and AI. SCIMUSE combines a 58M-paper graph with LLMs to propose research projects (many rated highly by experts) [ml4physica….github.io], [ml4physica….github.io]. AGATHA ranks plausible new connections in biomedical data to recommend research directions [sybrandt.com]. |
| Summarizing State-of-the-Art | LLM-Based Literature Search Tools (e.g. Elicit, Scispace); Scientific Summarization Models | Produces concise summaries of relevant papers to outline current knowledge. Given a query, tools return key papers with short summaries of findings [link.springer.com]. Multi-document summarization models synthesize multiple studies, enabling quick understanding of a field's consensus and open issues. |
| Contrasting Research Findings | Scite (Smart Citations); NLP Contradiction Detectors | Identifies agreements or conflicts between papers. Scite classifies citation statements to show if a later paper supports or contradicts an earlier result [jmla.pitt.edu]. NLP models analyze study conclusions (negations, opposing outcomes) to flag contradictory results in bodies of text [rd.springer.com], alerting researchers to unresolved disputes. |
| AI-Assisted Research Planning | Integrated Writing Assistants (e.g. Jenni.ai, Silatus); Knowledge Graph Q&A (ORKG, AIDA) | Integrates search, summarization, and suggestion in one workflow. These tools fetch and summarize relevant literature as you write, and can highlight missing pieces or suggest new questions to explore [link.springer.com]. Knowledge graph question-answering can directly pinpoint what is known vs. unknown on a topic, guiding the formulation of research questions. |

Each of these AI-driven approaches, especially when used together, enables a focused and efficient path from literature to research question – ensuring that new questions are grounded in evidence and truly push the boundaries of current knowledge. [link.springer.com], [ml4physica….github.io]

## 6. The Emotional Dimension of Research and Writing in the Age of AI

While AI-powered tools can streamline the formulation of research questions and accelerate literature analysis, their growing presence does not diminish the emotional gratification traditionally associated with academic work. Rather, it redefines how that sense of relief, pride, and satisfaction is experienced. The emotional fulfillment that arises from the process of researching and writing, through effort, reflection, and perseverance remains intact when scholars engage intentionally and thoughtfully with AI. The time invested in interpreting, refining, and shaping ideas continues to enhance both intellectual rigor and personal reward.

Instead of reducing the depth or authenticity of scholarly effort, AI research assistants can preserve and even amplify the emotional dimensions of academic inquiry. By relieving researchers of repetitive or mechanical tasks, AI allows greater focus on the creative, analytical, and interpretive aspects that form the heart of scholarship. The gradual movement from uncertainty to clarity which is the hallmark of intellectual discovery still occurs; it simply unfolds through collaboration between human judgment and machine assistance. The researcher's sense of accomplishment now stems not only from producing results but from orchestrating and curating the knowledge process itself.

Protecting and cultivating emotional satisfaction in this new environment requires recognizing that human agency remains central. AI can efficiently identify relevant literature or summarize findings, but the researcher continues to decide what matters, why it matters, and how it contributes to the broader conversation. The source of pride and fulfillment thus shifts from labor-intensive information gathering to higher-order critical thinking through evaluating, connecting, and creating meaning.

Moreover, many researchers choose to maintain elements of manual engagement, such as drafting outlines or annotating papers independently before consulting AI tools. These deliberate choices reinforce the personal connection to one's work and sustain the emotional gratification that comes from intellectual perseverance. The presence of AI does not erase these experiences; instead, it reframes them within a more collaborative and dynamic process of knowledge creation.

Ultimately, AI research assistants do not weaken the emotional core of academic work but more so they evolve it. Relief, pride, and satisfaction remain grounded in the same human capacities that have always driven scholarship: curiosity, discernment, and creativity. As AI becomes more deeply integrated into research workflows, the challenge is not to preserve emotion against technology but to recognize how these tools can extend the very sense of fulfillment that comes from thinking deeply, questioning critically, and contributing meaningfully to human understanding.

## 7. Guardrails for AI-Assisted Research Questioning

These advances demonstrate the growing role of AI in shaping scholarly inquiry and research design. However, these capabilities introduce parallel risks that necessitate structured guardrails. While AI can assist in aligning research questions with documented gaps in the literature, it is equally capable of hallucinating citations, fabricating conceptual linkages, or overstating consensus where none exists. The same generative power that enables AI to suggest high-value research inquiries can also generate plausible-sounding but incorrect premises, or subtly shift researcher framing toward what the model predicts rather than what existing literature supports. Moreover, when AI tools summarize or frame literature analysis, researchers may be tempted to rely on output without independently engaging foundational texts – risking second-order understanding and a loss of methodological rigor.

Given these dynamics, responsible adoption requires AI systems that do more than generate ideas: they must also support verification, transparency, and careful acknowledgement of uncertainty. Guardrails are not barriers to innovation; rather, they are mechanisms to ensure that efficiency gains do not erode scholarly integrity. Structured controls help ensure that AI serves as a catalyst for deeper inquiry rather than a shortcut that weakens critical thinking or validity. These controls include expectations that researchers:

- Independently review core sources rather than relying solely on AI summaries
- Confirm that AI-generated citations and claims are accurate and grounded in original texts
- Treat AI-suggested research questions as exploratory starting points, not final conclusions
- Reflect on and document how AI shaped their thinking, assumptions, or direction

Establishing these practices is essential for maintaining academic rigor, particularly as graduate-level research increasingly intersects with intelligent systems capable of shaping epistemic direction.

## 8. AI-Enabled Detection of Conflicts of Interest in Scholarly Research

Conflicts of interest undermine the credibility of academic research and weaken trust in scientific institutions. Financial ties, organizational affiliations, or personal relationships can influence how results are framed or interpreted, and manual review alone is not equipped to keep pace with the volume and complexity of today's scholarly output. AI systems offer a scalable, systematic way to identify signals of undisclosed or inaccurately reported COIs, strengthening transparency across the publication process.

AI systems can be used to scan manuscripts for references to companies, products, funding sources, and affiliations, and compare those details with the information listed in author disclosures. If the system notices discrepancies—such as prominent discussion of a commercial product without a corresponding disclosure—it can flag the passage for further review.

Beyond individual papers, AI can detect broader patterns across publications, including recurring collaborations or concentrated citation behavior that may indicate undisclosed relationships. These signals are not conclusions, but they prompt a closer look upon which a researcher can decide whether a follow-up is needed. This expands a researcher's analytical capacity and strengthens transparency in the academic publishing process.

### Red-Team AI Agent Specifications (Microsoft Copilot "Researcher" Structure)

#### Role of a Red-Team Agent

In this context, a dedicated "red-team" research agent functions as a quality-assurance layer. Rather than merely generating content, such an agent actively challenges and audits AI outputs by:

- Checking that citations correspond to real sources
- Retrieving relevant passages from those sources to verify claims
- Flagging inconsistencies or unsupported statements
- Identifying potential speculative leaps in reasoning
- Surfacing opposing or missing perspectives that the initial output may have overlooked
- Confirming whether suggested research questions are grounded in real literature gaps

By building verification into the workflow, a red-team model operationalizes responsible AI use – supporting creativity and acceleration while preserving scholarly integrity. This dual-system approach reflects an emerging best practice: AI for ideation, and AI for critical interrogation. Together they form a balanced foundation for human-centered, ethically rigorous research in the era of machine-augmented scholarship.

### Researcher Prompt Instructions

The full prompt is reproduced in [researcher-prompt.md](researcher-prompt.md), along with the journal-credibility rubric it scores against.

## Journal credibility rubric (fixed scale)

See [journal-rubric.md](journal-rubric.md).

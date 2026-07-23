# AI-Powered Assistance in Formulating Research Questions

### A Research Report on the Use of Artificial Intelligence to Help Researchers Frame Better Questions

*Prepared as a plain-language review of the research materials in this repository*
*based on the paper, the prompt instructions, and the rubric it contains*

---

## Foreword

Every piece of research begins with a question. Whether the subject is the
resettlement of displaced families, the pricing of fertiliser, or the safety of
a medicine, the quality of the answer is limited by the quality of the question
that was asked. A question that is too broad cannot be answered. A question
that has already been settled wastes years of effort. A question that rests on
a false assumption produces findings that look rigorous and are quietly wrong.

Choosing a good question has always been difficult, and it has become harder as
the volume of published research has grown beyond what any individual can read.
A scholar entering a field now faces millions of papers and no reliable way to
know which corners of it are genuinely unexplored.

This report examines a set of materials produced by the Ethical Tech CoLab that
addresses that difficulty. The materials describe how artificial intelligence
tools are being used to help researchers find unanswered questions and phrase
them well, and they set out the safeguards that such use requires. The report
is written for a policy, academic-administration, and general professional
audience rather than a technical one, and it explains each technical term the
first time it appears.

---

## 1. Executive Summary

1.1 This repository holds a short academic paper and two practical documents
that accompany it. The paper surveys how artificial intelligence is currently
used to help researchers formulate research questions. The practical documents
are a reusable set of instructions for an AI assistant, and an example of the
scoring rubric that those instructions produce.

1.2 Artificial intelligence, in this context, means a large language model. That
is a computer system trained on very large amounts of written text, which
responds to a written instruction by producing text that continues it
plausibly. Such a system does not know anything in the way a person does. It
predicts language. Everything else in this report follows from that fact.

1.3 The paper identifies five distinct jobs that these systems are being used
for in the earliest stage of research: finding gaps in the literature,
proposing candidate questions, summarising what is currently known, exposing
places where published studies contradict one another, and combining all of the
above into a single working environment.

1.4 The most concrete contribution in the repository is not the survey but the
prompt. A prompt is simply the written instruction a person gives to an AI
assistant. This one is several pages long and specifies, in advance, what the
assistant must do, what it must refuse to do, and what it must include in every
answer. It converts a general-purpose chatbot into a narrow instrument with
stated standards.

1.5 Those standards are the variables of this project. The prompt requires that
every proposed research question be specific, feasible, and grounded in theory.
It requires that every source cited be scored for credibility on a five-point
scale, that the score be shown to the user, and that a web link be supplied so
that the citation can be checked. It requires that any recommended research
method be ranked against alternatives, with its data requirements and
assumptions stated. Section 5 explains each of these in turn.

1.6 The paper is candid that the same capability that generates useful questions
also generates convincing false ones. It records four expectations of the
researcher and proposes a second AI assistant, described as a red-team agent,
whose only job is to attack the output of the first.

1.7 The materials are an academic survey and a set of working instructions
produced by a student cohort. They are not a software product, they contain no
running code beyond a single web page that presents them, and they have not
been evaluated experimentally. They should be read as a considered practitioner
guide, not as evidence of effectiveness.

---

## 2. Background and Rationale

2.1 The problem. The first stage of any research project is the least
supported. A researcher must survey a field, work out what is missing, and
commit to a question, usually before they have any real command of the
literature. The volume of published work makes an exhaustive survey impossible,
so in practice the question is chosen from the small slice of the field the
researcher happens to have read, or from what a supervisor happens to suggest.

2.2 The gap. Existing academic infrastructure supports later stages well.
There are databases for finding papers, software for managing references,
statistical packages for analysis, and peer review for checking conclusions.
There is very little that helps at the point where the question itself is
chosen, which is the point where the largest and least recoverable errors are
made.

2.3 The response. Language models are unusually well suited to this stage,
because the task is one of recombination rather than truth. Suggesting that two
established bodies of work have never been examined together is a proposal, not
a claim, and a proposal can be checked cheaply by the researcher before any
commitment is made. The paper's position is that this is where AI assistance is
most valuable and least dangerous, provided the researcher retains the decision.

2.4 The corresponding risk is that the same stage is where a researcher is least
equipped to detect an error. Someone who does not yet know the literature cannot
tell a real gap from a fabricated one, or a genuine consensus from an
overstated one. The paper treats this asymmetry as the central problem of
AI-assisted question formulation and builds its guardrails around it.

---

## 3. Objectives

The materials in this repository are intended to:

3.1 Describe, for an academic audience, the specific tasks in question
formulation that artificial intelligence tools can now perform, with named
examples rather than general claims.

3.2 Supply a reusable instruction set that a researcher can paste into an AI
assistant and use immediately, without technical knowledge.

3.3 Make the quality of cited evidence visible by requiring that every source be
scored and every citation be linked for checking.

3.4 State plainly the failure modes of language models in a research design
role, including invented citations and overstated agreement between studies.

3.5 Propose a division of labour in which one AI system generates ideas and a
second, separately instructed system audits them.

3.6 Establish an expectation that researchers record how AI shaped their
thinking, so that the influence is documented rather than invisible.

---

## 4. How the Assistance Works

The paper groups current practice into five mechanisms. They are described here
in the order a researcher would encounter them.

### 4.1 Finding gaps in the literature

A research gap is a question that the published literature has not answered.
The paper describes three ways of finding one automatically.

The first reads the text of papers directly and looks for statements of
limitation or unanswered questions, the sentences in which authors say what
their study could not establish. The paper cites a tool named GapFinder as an
example of this approach.

The second builds what is called a keyword co-occurrence graph. Imagine a large
diagram in which every research concept is a dot, and a line is drawn between
two dots whenever a published paper discusses both. Dense clusters of lines show
where research is concentrated. Missing lines between otherwise well connected
dots show pairs of concepts that ought to have been studied together but have
not been. The paper cites work by Chatterjee and colleagues from 2024 using
this method.

The third works on a knowledge graph, which is a similar diagram but records
what kind of relationship exists between concepts rather than merely that one
exists. If concept A is known to affect B, and B is known to affect C, but
nothing has ever examined A and C together, that absence is a candidate gap.
This is a computational form of an older technique in library science called
literature-based discovery.

### 4.2 Proposing candidate questions

Once a gap is identified, a language model can be asked to phrase it as a
research question. The paper's principal example is SCIMUSE, a system developed
by Xuemei Gu and Mario Krenn at the Max Planck Institute for the Science of
Light (Gu and Krenn, ICML 2024; preprint arXiv:2405.17044). SCIMUSE builds a knowledge graph from more than 58 million scientific
papers, identifies a given scientist's interests from their recent
publications, and then asks GPT-4 to write research proposals connecting
concept pairs drawn from that scientist's part of the graph. More than one
hundred research group leaders at the Max Planck Society rated over four
thousand of the resulting ideas. The repository's paper reports that roughly one
quarter were rated four or five out of five for interest (Gu and Krenn, ICML
2024; arXiv:2405.17044 -- see 9.5 on locating this figure).

An earlier system, AGATHA, published by Sybrandt and colleagues in 2020, works
in biomedicine. It ranks unexamined connections between genes, diseases, and
chemicals by how plausible they appear given everything published so far. Its
authors validated it by training it only on literature published before 2015 and
checking whether it predicted connections that later papers confirmed.

The common principle is that these systems do not discover anything. They
recombine what is already recorded and put the results in front of a human
expert, who decides which are worth pursuing. A twenty-five per cent hit rate is
a useful yield precisely because the cost of discarding the other
seventy-five per cent is a few minutes of reading.

### 4.3 Summarising what is already known

A question cannot be judged novel by someone who does not know the field. The
paper describes tools including Elicit, Scispace, and Consensus, which accept a
question in ordinary language, retrieve relevant papers, and return a short
summary of each. Other systems attempt multi-document summarisation, meaning a
single coherent account synthesised across many papers rather than one summary
per paper.

This is the mechanism the paper is most cautious about, and rightly so. A
summary is a compression, and compression discards the qualifications, sample
sizes, and stated limits that determine whether a finding actually applies to
the researcher's case. A researcher who reads only summaries acquires what the
paper calls a second-order understanding of their own field.

### 4.4 Exposing contradictions between studies

Where two credible studies disagree, there is usually a research question worth
asking. The paper describes two ways of finding such disagreements.

The first examines citations. When one paper cites another, it may be agreeing,
disagreeing, or simply noting its existence. The tool Scite classifies citation
statements into supporting, contrasting, and mentioning categories across a very
large body of citation text, which allows a researcher to see at a glance
whether a finding has been challenged since publication.

The second compares the findings themselves. The paper cites work by Tawfik and
Spruit from 2018 which extracts outcome statements from studies and compares
them for logical conflict, using cues such as negation words, opposites, and
differing numerical results.

The value here is diagnostic. A field in which the evidence is genuinely
divided is a field where a well designed study can settle something.

### 4.5 Integrated assistants

The final category combines the previous four into one workflow, so that
searching, summarising, and suggesting happen in a single session. The paper
notes that some of these systems use a technique called retrieval-augmented
generation, in which the assistant first retrieves specific passages from real
documents and then writes its answer with those passages in front of it. This
reduces, though it does not eliminate, the tendency to invent material, because
the model is working from retrieved text rather than from memory alone.

---

## 5. The Researcher Prompt and Its Variables

5.1 The prompt in this repository is the part of the project a reader can
actually use. It is written for Microsoft Copilot's Researcher tool but works in
any comparable AI assistant. The document states that researchers are encouraged
to edit it, and marks certain instructions as ones that should survive any
edit. What follows explains each requirement in plain terms, why it is there,
and what it changes about the answer.

5.2 The researcher's level is declared at the start. The prompt opens by
telling the assistant that the user is a doctoral-level researcher. This is not
flattery. A language model adjusts its register and its assumed shared knowledge
to its reader, and without this instruction it will default to explaining
familiar concepts and recommending introductory sources. Declaring the level
raises the technical floor of every subsequent answer.

5.3 Three tests are applied to every proposed question: specific, feasible, and
grounded in theory. These are the core quality variables of the whole
instrument.

   Specific means the question names a defined population, intervention, or
   relationship rather than a broad subject area. It is the difference between
   asking about the effect of a named subsidy on a named crop in a named country
   and asking about agricultural policy. Specificity is what makes a question
   answerable at all, because it determines what evidence would count as an
   answer.

   Feasible means the study the question implies could actually be carried out
   with available data, time, and access. This is the test that most often
   eliminates otherwise excellent questions, and it is the one a researcher
   working alone is most likely to postpone until too late.

   Grounded in theory means the question connects to an existing explanatory
   framework rather than describing an isolated correlation. A question with
   theoretical grounding produces a finding that other researchers can use,
   because it either supports or challenges something they already rely on.

   These three overlap substantially with an established framework in research
   methods known as FINER, proposed by Hulley and colleagues in Designing
   Clinical Research, which holds that a good research question is feasible,
   interesting, novel, ethical, and relevant. The repository does not cite FINER,
   and the correspondence is partial rather than exact: the prompt's grounding
   requirement does work that FINER splits between novelty and relevance, and
   the prompt leaves the ethical test to the researcher. The comparison is
   offered here as orientation for a reader who knows the established framework,
   not as a claim about the prompt's origins.

5.4 The journal credibility score is a five-point scale from one to five,
described in Section 6. The prompt requires the assistant to construct such a
scale itself, then apply it to every source it cites and display the resulting
number alongside the citation. The purpose is to stop all sources looking
equally authoritative in a list. Without a score, a blog post and a top-tier
journal article occupy the same visual weight on the page.

5.5 A verification link is required for every cited article. This is the single
most important instruction in the document, and the prompt states its reason
outright: to verify there are no hallucinations. A hallucination, in this
context, is a citation the model has invented. Fabricated references are the
best documented failure of language models in academic use, and they are
dangerous because they are plausible. An invented paper will have a real-sounding
title, a real author working in the right field, and a real journal. Requiring a
working link makes the fabrication checkable in seconds instead of requiring
expertise to detect.

5.6 Absence must be stated explicitly. If no peer-reviewed work exists on the
specific topic, the assistant is required to say so rather than substitute
something adjacent and present it as a match. It must then offer the closest
credible work and label it clearly as an imperfect match. This addresses a
specific and subtle failure: a model asked for evidence will supply evidence,
and the natural way to comply with an impossible request is to relax the
criteria silently. Making the admission of absence an explicit requirement
removes the incentive to do so.

5.7 The field context is requested alongside the question. The prompt asks not
only for questions but for the current controversies, points of consensus, and
open problems in the surrounding field. This gives the researcher the material
needed to judge the suggestions, rather than receiving a list of questions with
no way to assess which matters.

5.8 Methodologies must be ranked, not recommended. When asked how to
investigate a question, the assistant must identify the underlying logic of the
question, specifically whether it is asking what causes what or asking what is
the case, and then supply three to five methods ordered from most to least
appropriate. Each must come with why it fits, what data it needs, minimum
sample size where relevant, its key assumptions, and, for causal questions, its
identification strategy, meaning the argument for why an observed association
should be read as cause rather than coincidence. Methods that do not fit must be
named and excluded with reasons.

   Ranking rather than recommending is a deliberate design choice. A single
   recommendation hides the trade-off and invites the researcher to accept it. A
   ranked list with stated assumptions forces the trade-off into view and leaves
   the judgment where it belongs.

5.9 A final consistency check is required before any answer is returned. The
prompt instructs the assistant to review its own output against every rule
above before presenting it. This is a recognised technique: a model asked to
check its work against explicit criteria catches a meaningful share of its own
violations, because evaluating a finished text is an easier task than producing
one correctly the first time. It is not a guarantee, and the prompt does not
present it as one.

5.10 Source restriction is discussed with its cost. The prompt notes that the
assistant can be confined to reputable publishers and databases such as Springer
Nature, Elsevier, Wiley, and government working-paper repositories including the
United States National Institutes of Health and the National Bureau of Economic
Research. It also warns that doing so narrows the pool of retrievable work, and
therefore does not simply recommend it. Presenting the trade-off rather than the
setting is characteristic of the document as a whole.

---

## 6. Reading the Results: The Journal Credibility Rubric

6.1 The repository includes an example of the scoring scale that the prompt
produces, generated during a session on agricultural economics. It is presented
as illustrative rather than fixed: a different field would produce different
examples at each level, because the top journals in one discipline are not the
top journals in another.

6.2 The scale runs from five down to one, and each level is defined by the
strength of the review a publication applies before printing an article.

   Five means a highly selective journal using rigorous double-blind peer
   review, where neither the author nor the reviewers know each other's
   identities, with high citation impact and general recognition in the field.
   The examples given are the American Economic Review, the Economic Journal,
   the Journal of Political Economy, and the American Journal of Agricultural
   Economics.

   Four means a well regarded journal specific to a field, with a strong review
   process and consistent citation impact, though less selective than the top
   tier. Agricultural Economics, Energy Policy, and Energy Research and Social
   Science are given as examples.

   Three means a reputable journal that does conduct peer review but is less
   selective or has more variable impact. The example given is that many
   open-access titles sit here.

   Two means limited peer review or editorial oversight, including conference
   proceedings and trade publications.

   One means no peer review at all: news articles, press releases, promotional
   material, and advocacy websites. The rubric states plainly that these are not
   suitable for academic citation.

6.3 What the scale is for. Peer review means that other specialists examined
the work before publication and could require changes or refuse it. It is the
principal quality filter in academic publishing, and it varies enormously in
strictness between journals. A researcher who knows a field can judge this
instantly from the journal name. A researcher entering a new field cannot, and
that is precisely the researcher this prompt is written for. The number makes an
invisible distinction visible.

6.4 What the scale is not. The score describes the venue, not the article. A
weak paper can appear in a strong journal and an important one in a modest
journal, and a score of five is not a warrant that a particular finding is
correct. Impact factor, which the top two levels rely on, measures how often a
journal's articles are cited, which correlates with quality but also with the
size and fashionability of the field. The rubric is a triage aid for deciding
what to read first. It does not replace reading.

6.5 A further caution applies to the rubric's origin. The prompt asks the AI
assistant to create the scale, which means the assistant is grading sources
using standards it generated itself. Its placements will reflect the general
reputation of journals as represented in its training text, which is
approximately right for well known titles and unreliable for obscure or new
ones. A researcher should treat the scale as a first draft to be corrected by a
supervisor or a subject librarian.

---

## 7. Guardrails

7.1 The paper is direct about the risks. It states that AI can hallucinate
citations, fabricate conceptual linkages, and overstate consensus where none
exists, and that the same generative capacity that produces valuable
suggestions also produces plausible but incorrect premises. It identifies a
further and less obvious risk: that a model may shift a researcher's framing
toward what the model predicts rather than what the literature supports. Because
the model produces the language most likely to follow the prompt, it tends
toward the conventional, and a researcher who accepts its framing may
unknowingly abandon the unusual angle that made the project worth doing.

7.2 Four expectations are placed on the researcher:

   - review core sources independently rather than relying on AI summaries;
   - confirm that AI-generated citations and claims are accurate and present in
     the original texts;
   - treat AI-suggested questions as exploratory starting points rather than
     conclusions; and
   - reflect on and document how AI shaped their thinking, assumptions, or
     direction.

7.3 The fourth expectation deserves particular attention, because it is the one
with no technical solution. Disclosure norms in academic publishing currently
focus on AI-generated text. Influence on the choice of question is harder to see
and arguably matters more, since it determines what was studied rather than how
it was written. The paper asks researchers to record it. It offers no mechanism
for doing so, and this is an open problem rather than a solved one.

7.4 The red-team agent. The paper's structural proposal is to run a second AI
assistant against the output of the first. The term red team comes from security
practice, where a designated group attacks a system to find its weaknesses
before an adversary does. This agent generates nothing. Its instructions are to
check that cited sources exist, retrieve passages from those sources to confirm
the claims attributed to them, flag statements the sources do not support,
identify leaps in reasoning, surface perspectives the first output omitted, and
test whether a proposed question really does address a gap in the literature.

7.5 The reasoning behind the split is sound. A single system asked both to
propose and to critique has an inherent conflict, since the same predictive
tendencies that produced a claim will tend to endorse it. A separate assistant
given only adversarial instructions and no stake in the original output is more
likely to find the fault. The limitation is equally clear and the repository
does not fully state it: both systems share the same underlying weaknesses, and
a fabrication convincing enough to survive one model's judgment may well survive
another's. The red-team agent raises the cost of an undetected error. It does
not remove the researcher's obligation to open the source.

7.6 Conflict-of-interest detection. The paper's final section describes a
related application. A conflict of interest arises when a financial tie, an
institutional affiliation, or a personal relationship could influence how
results are framed. Journals require authors to declare these, and the
declarations are checked, if at all, by hand. The paper proposes that AI systems
scan manuscripts for mentions of companies, products, and funding sources and
compare them against what the authors declared, flagging discrepancies such as
sustained discussion of a commercial product with no corresponding disclosure.
It also notes that patterns across many publications, such as recurring
collaborations or unusually concentrated citation behaviour, can be detected the
same way. The paper is careful to describe these as signals prompting human
review rather than findings, which is the correct framing: an undeclared
affiliation may be an oversight, and treating an automated flag as an accusation
would do real harm.

---

## 8. The Human Dimension

8.1 One section of the paper departs from the technical survey to consider what
AI assistance does to the experience of scholarship. Its argument is that the
satisfaction of academic work comes from the movement from confusion to
clarity, and that this movement still occurs when AI is involved, though its
location shifts. The researcher's contribution moves from gathering information
toward deciding what matters and why, and the paper suggests the sense of
accomplishment moves with it.

8.2 It also observes that many researchers deliberately retain manual steps,
drafting outlines or annotating papers themselves before consulting any tool,
and treats this as a reasonable choice rather than inefficiency.

8.3 This section is reflective rather than evidenced, and it should be read as
such. It cites no studies of researcher experience and reports no interviews.
Its inclusion is nonetheless defensible, because the question of what these
tools do to the people who use them is one that surveys of capability do not
reach, and it bears directly on whether the guardrails in Section 7 will be
observed in practice. Guardrails that require effort are followed by researchers
who still feel ownership of their work.

---

## 9. Limitations and Caveats

9.1 The repository contains no functioning tool. It holds a paper, a prompt, a
rubric, and a single web page that presents them. The README describes a
richer web application as planned. A reader expecting software will not find it,
and the prompt's usefulness depends entirely on the AI assistant it is pasted
into.

9.2 The prompt has not been evaluated. There is no record of testing it against
an unguided assistant, no measurement of whether it reduces fabricated
citations, and no comparison of the questions it produces against questions
produced without it. Its design choices are well argued but they remain
arguments.

9.3 The rubric was generated in a single session on one subject. It is labelled
as illustrative, and it should not be treated as a validated instrument. Its
placement of open-access publishing at level three is a defensible generalisation
that is also unfair to several rigorous open-access journals.

9.4 The citations are hard to verify. The source document was published through
Google Docs and its citation markers survive only as plain-text domain hints
such as one naming a publisher's website, with no links behind them. The
repository states this openly and preserves the markers unchanged, which is
honest, but it means a reader wanting to check a specific claim must search for
the source themselves. In a paper whose central recommendation is that citations
be verifiable, this is an uncomfortable gap.

9.5 Bibliographic details, corrected. An earlier draft attributed SCIMUSE to
NeurIPS 2024. That was wrong: the work is by Gu and Krenn and was presented at
ICML 2024, with the preprint available as arXiv:2405.17044. AGATHA was published
at the ACM Conference on Information and Knowledge Management (CIKM) in 2020,
which the paper now states. One item remains open: the figure of roughly one
quarter of ideas rated highly interesting is not located to a specific section
of the SCIMUSE paper, and it does not appear in the preprint abstract. Until it
is pinned to a numbered result it should be read as approximate. Neither error
affects the paper's argument, but both illustrate how easily citation detail
degrades in AI-assisted writing, including in a paper about that very risk.

9.6 The paper acknowledges its own AI assistance. It states that a Microsoft
365 Copilot Researcher agent running an OpenAI GPT model was used to partially
generate and check its content. This is the disclosure the paper asks of others
and it is to the authors' credit that they made it. It also means the survey is
partly a product of the technique it describes, and the imprecise citations noted
above are consistent with that.

9.7 The field moves quickly. The tools named here, and the specific systems
described, will change or disappear on a timescale of months. The reasoning about
what makes a good question and where the risks lie will last considerably
longer than the product names.

---

## 10. Practical Nature of the Materials

10.1 The materials require no installation and no technical skill. The prompt
is a text document that can be copied into an AI assistant in a browser and
edited freely. The paper and the rubric are ordinary documents. A public web
page presenting all three is published through GitHub Pages, a free hosting
service that serves files directly from the repository.

10.2 The prompt is designed to be modified. Its authors mark the instructions
they consider essential and invite everything else to be adapted to the
researcher's own field, which is appropriate for an instrument whose value
depends on fitting a particular discipline's conventions.

---

## 11. Intended Audience and Use

11.1 The materials address doctoral and masters researchers, their supervisors,
and those responsible for research integrity policy. The prompt is written for
the researcher. The guardrails and the disclosure expectation concern anyone
setting institutional standards for AI use.

11.2 Their value lies in making a set of standards explicit at a stage of
research where standards are usually tacit. What counts as a good question,
what counts as a credible source, and what a researcher must check before
trusting an AI suggestion are all matters normally learned slowly by
apprenticeship. Writing them down is useful whether or not an AI assistant is
involved.

---

## 12. Conclusion

12.1 The most useful thing in this repository is not the survey of tools but the
insistence that every AI-suggested source arrive with a score and a link. That
single pairing does most of the work. It makes the weakest point of a language
model, its willingness to invent a convincing reference, checkable by someone
who does not yet know the field well enough to spot the invention. The rest of
the prompt follows the same logic: state the criteria, show the reasoning, rank
the options rather than choosing, and leave the decision with the person.

12.2 The materials are modest in what they claim. They are a student cohort's
survey and working instructions, unevaluated, with citation detail that does not
always hold up under checking. Their argument is nonetheless the right one. A
research question is a commitment of years, and a tool that helps choose one
must earn trust by exposing its reasoning rather than by sounding confident.
Whether a second AI can reliably audit the first remains genuinely unsettled,
and the repository would be stronger for saying so. What it does say, clearly
and repeatedly, is that the researcher who cannot defend the question without
the assistant does not yet own it.

---

## Attribution

Developed by Yorke E. Rhodes III, Nathaniel Fossella, Alexa Shamie, Kirsten Co,
Taylor Badt, Amanda Lindsey, Grace Driscoll, Mohagani Townsend, Pegi Bracaj, and
Vedant Jain as part of masters research at the NYU Center for Global Affairs
(2026), under the Ethical Tech CoLab. The repository was assembled and published
by Carolina Moron.

> Note: This report is a plain-language summary of an academic survey and its
> accompanying prompt materials. The materials are for academic use and
> discussion. They are not a validated instrument, and their outputs are not a
> substitute for independent review of primary sources, disciplinary expertise,
> or supervision.

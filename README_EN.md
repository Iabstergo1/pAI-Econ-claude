<a href="https://doi.org/10.5281/zenodo.20686025"><img src="https://zenodo.org/badge/1268830527.svg" alt="DOI"></a>
# pAI-Econ-claude

<p align="center">
  <img alt="Status" src="https://img.shields.io/badge/status-theory--harness-blue">
  <img alt="Claude Code" src="https://img.shields.io/badge/Claude_Code-skill-blueviolet">
  <img alt="Domain" src="https://img.shields.io/badge/domain-theoretical--economics-0A66C2">
  <img alt="Human in the Loop" src="https://img.shields.io/badge/human--in--the--loop-required-orange">
  <img alt="License" src="https://img.shields.io/badge/license-MIT-lightgrey">
</p>

<p align="center">
  <b>A Claude Code Skill for human-in-the-loop theoretical economics research</b><br>
  pAI-Econ-claude bridges empirical findings and theoretical modeling — it helps empirical
  researchers translate economic phenomena, mechanism intuitions, and empirical findings into
  clearer theoretical questions, canonical model references, testable propositions, and auditable
  research frameworks.
</p>

<p align="center">
  <a href="./README.md">中文版本</a> ·
  <a href="#quick-start">Quick Start</a> ·
  <a href="#use-cases">Use Cases</a> ·
  <a href="#model-library">Model Library</a> ·
  <a href="#workflow">Workflow</a>
</p>

> pAI stands for principal Agentic Investigator (Abdelmoneum, Beneventano, & Poggio, 2026).

---

## Authors

**Authors:**

Chen Zhu (China Agricultural University)

Xiaolu Wang (China Agricultural University)

Weilong Zhang (University of Cambridge)

**Last updated:** June 15, 2026 (testing phase)

---

## Acknowledgements

This project is inspired by **pAI/MSc** and adapts its research pipeline ideas into a Claude Code Skill for theoretical economics.

Original pAI/MSc:
- Mahmoud Abdelmoneum
- Pierfrancesco Beneventano
- Tomaso Poggio
- MIT + Perseus Labs

Reference:
- [pAI/MSc: ML Theory Research with Humans on the Loop](https://arxiv.org/abs/2604.20622)
- [PoggioAI_MSc GitHub Repository](https://github.com/PoggioAI/PoggioAI_MSc-claude)

**Feedback:  Gin**

---

## Overview

**pAI-Econ-claude** is a **human-in-the-loop Claude Code Skill** designed for empirical economists who want to strengthen the theoretical foundations of their research.

It does not attempt to replace the original work of theoretical economists, nor does it claim to automatically discover new theoretical frontiers. Instead, it bridges theory and empirics: helping empirical researchers identify appropriate canonical model families, clarify core economic mechanisms, pinpoint what a model extension adds beyond existing theory, and translate empirical questions into more rigorous theoretical frameworks.

Many empirical papers do not lack data, identification strategies, or estimation results — what is often weak is the theoretical mechanism: Why should this phenomenon hold? Which canonical model does it correspond to? What does adding a new variable change? Are propositions merely implied by assumptions? Do welfare implications extend beyond estimation results?

pAI-Econ-claude provides a structured workflow for these questions. Through canonical model matching, theory lineage checks, model primitive generation, assumption audits, candidate propositions, proof sketches, and counterexample checks, it helps researchers transform an empirical puzzle into a theoretical framework that can be discussed, reviewed, and collaboratively developed.

In short, it is not an AI theoretical economist — it is a theory modeling scaffold for empirical researchers:

> Helping you understand where your empirical findings fit in the theoretical literature, what mechanism is missing, and what questions to bring to a theory collaborator.

---

## What Problem Does It Solve?

The theoretical analysis component of economics research often stalls not at "how to write it" but at much earlier stages:

- Is the research question actually clear?
- Which canonical model tradition does this idea belong to?
- What exactly does the new mechanism add relative to the canonical model?
- Are assumptions too strong — included only to deliver the desired conclusion?
- Are propositions non-trivial, or merely implied by assumptions?
- What are the gaps in proof sketches?
- Do simple counterexamples exist?
- Does the economic interpretation extend beyond the formal results?

**pAI-Econ-claude's role is to make the theory modeling process explicit, documented, and traceable, while preserving human judgment at critical decision points.**

---

## Target Users & Usage Responsibility

### Target Users

This Skill is designed for **junior researchers with foundational training in economic theory**, including:

- Graduate students (Master's or PhD) in economics, management, or related fields
- Assistant professors or postdoctoral researchers whose primary work is empirical but who want to strengthen theoretical mechanisms
- Researchers familiar with microeconomic foundations (utility maximization, equilibrium concepts, information structures)

Using this Skill requires the following baseline competencies:

- Ability to independently judge whether an equilibrium concept (e.g., BNE, SPE, competitive equilibrium) is appropriate for a given research setting
- Ability to assess whether a proposition is non-trivial or merely implied by assumptions
- Ability to evaluate whether a theoretical mechanism has a meaningful correspondence with an empirical identification strategy

**This Skill is not designed for researchers with no background in economic theory modeling.** Users who cannot independently assess the quality of AI-generated model structures and propositions cannot take appropriate academic responsibility for the outputs.

### Usage Responsibility

> **Users bear full responsibility for any work they publish.**

This Skill is an assistive tool. All outputs — including model primitives, propositions, proof sketches, manuscript frameworks, and references — must be independently reviewed by the user before being used for any academic writing or publication purpose.

Specifically:

- **Proof sketches are not formal proofs.** Steps labeled `GAP` or `FALSE_RISK` must be independently derived and verified by the researcher before being written into a paper.
- **References must be independently verified.** Although Stage 2 and the pre-PDF generation step include mandatory web verification nodes, the researcher bears full responsibility for the accuracy of the final published citation list.
- **Theoretical contribution requires researcher judgment.** AI cannot determine whether a proposition has sufficient novelty to meet journal standards — this judgment must be made by the researcher and collaborators based on thorough knowledge of the relevant literature.
- **Model selection requires researcher evaluation.** Canonical Model Matching recommendations are advisory only; the researcher must make the final selection based on their own understanding of the relevant theoretical tradition.

The authors of this project accept no responsibility for the accuracy, originality, or sufficiency of any content generated using this Skill in academic publication.

---

## Quick Start

### Installation

```bash
git clone https://github.com/maxwell2732/pAI-Econ-claude.git
cd pAI-Econ-claude
```

Open Claude Code in that directory — the slash command is immediately available:

```text
/theoretical-economics-claude-skill "Your theoretical economics research idea"
```

---

## Use Cases

pAI-Econ-claude supports theoretical ideas at different stages of maturity. You don't need to run the full pipeline every time — choose the entry point that fits your task.

### 1. Model Extension Mode: Extend a Canonical Model with a New Mechanism

Use this mode when you already know the approximate model family and want to add a new mechanism.

Example:

```text
/theoretical-economics-claude-skill "
mode: model_extension

Extend a search model by adding product healthfulness and costly attention to nutrition labels.
Can a front-of-package label increase the probability that consumers choose healthier food?
"
```

The Skill will help you answer:

- Which canonical search model does this idea inherit from?
- What does the new healthfulness mechanism change?
- When will consumers actively check nutrition labels?
- Does reducing information costs necessarily increase purchases of healthy food?
- Are there counterexamples or boundary cases?
- Does this extension have sufficient theoretical contribution?

---

### 2. Phenomenon-to-Model Mode: Match a Theoretical Model to an Economic Phenomenon

Use this mode when you have a phenomenon or mechanism intuition but are unsure which theoretical model to use.

Example:

```text
/theoretical-economics-claude-skill "
mode: phenomenon_to_model

I want to incorporate genetic endowment into a health capital framework.
Genetic endowment affects productivity through childhood environment, health investment,
and human capital formation. Which theoretical model is most suitable?
"
```

The Skill will compare multiple candidate model families, such as:

- Grossman health capital model
- Becker / Ben-Porath human capital investment model
- Cunha-Heckman skill formation framework
- Roy model of comparative advantage
- Lifecycle investment model
- Intergenerational human capital model

It will then recommend a baseline model and explain why others do or do not fit.

---

### 3. Model Critique Mode: Audit an Existing Theoretical Model

If you already have model primitives, assumptions, or propositions, you can ask the Skill to review them like a theory journal referee.

```text
/theoretical-economics-claude-skill "
mode: model_critique

Here is my model setup:
[Paste model primitives, timing, utility function, equilibrium definition, and propositions]

Please audit model coherence, assumptions, non-triviality, proof gaps, and possible counterexamples.
"
```

Key checks include:

- Is the model closed?
- Is the timing clear?
- Is the information structure complete?
- Is the equilibrium concept appropriate?
- Are assumptions included merely to deliver desired conclusions?
- Are propositions non-trivial?
- Are there logical jumps in proof sketches?
- Do simple 2-agent, 2-period, binary-action counterexamples exist?

---

### 4. Full Pipeline Mode: Run the Complete Theory Workflow from a Research Idea

Use the full pipeline when you have only an early-stage idea and want to go from intuition all the way to a paper framework.

```text
/theoretical-economics-claude-skill "
mode: full_pipeline

Investigate whether a principal facing a privately informed agent can achieve first-best efficiency
through a forcing contract when the agent's outside option is type-dependent.
"
```

Full output includes:

- Refined research puzzle
- Literature positioning plan
- Canonical model match
- Model primitives
- Assumption audit
- Candidate propositions
- Proof sketches
- Counterexamples
- Economic interpretation
- Manuscript skeleton (markdown + LaTeX source + academic PDF compiled with pdflatex)

---

### 5. Manuscript Skeleton Only: Generate a Paper Framework

Use this mode when the model, propositions, and main conclusions are reasonably clear and you just need to organize them into a working paper structure.

```text
/theoretical-economics-claude-skill "
mode: manuscript_skeleton_only

Here are my model, propositions, and proof sketches:
[Paste existing content]

Please organize them into a theoretical economics working paper skeleton.
"
```

---

## Workflow

pAI-Econ-claude uses a staged, traceable human-AI collaboration process.

```mermaid
flowchart TD
    A["0. Intake<br/>Research Idea"] --> B["1. Puzzle Refinement"]
    B --> C["2. Literature Positioning"]
    C --> D["3. Persona Council<br/>Theory Review Committee"]
    D --> E["3b. Canonical Model Matching"]
    E --> F["4. Model Primitives"]
    F --> G["5. Assumption Audit"]
    G --> H["6. Proposition Generator"]
    H --> I["7. Proof Sketch"]
    I --> J["8. Counterexample Finder"]
    J --> K["9. Economic Interpretation"]
    K --> L["10. Manuscript Skeleton<br/>Markdown + PDF"]
```

---

## Core Stages

| Stage | Name | Primary Output |
|---|---|---|
| 0 | Intake | `research_intake.md` |
| 1 | Puzzle Refinement | `research_puzzle.md` |
| 2 | Literature Positioning | `literature_positioning.md` |
| 3 | Theory Persona Council | `persona_council.md` |
| 3b | Canonical Model Matching | `canonical_model_match.md` |
| 4 | Model Primitives | `model_primitives.md` |
| 5 | Assumption Audit | `assumption_audit.md` |
| 6 | Proposition Generator | `candidate_propositions.md` |
| 7 | Proof Sketch | `proof_sketches.md` |
| 8 | Counterexample Finder | `counterexamples_and_edge_cases.md` |
| 9 | Economic Interpretation | `economic_interpretation.md` |
| 10 | Manuscript Skeleton | `manuscript_skeleton.md` + `manuscript_skeleton.tex` + `manuscript_skeleton.pdf` |

---

## Model Library

pAI-Econ-claude includes a `model_library/` for matching canonical theoretical model families before formal modeling begins.

This step is critical because theoretical economics research should not start from scratch by "inventing models from thin air" — it should first answer:

> What canonical model does the current research idea most closely resemble?  
> What does it inherit? What does it change? Where is the new mechanism?

### General Theoretical Model Library

| Model Family | Applicable Questions |
|---|---|
| Consumer Choice | Consumer choice, utility maximization |
| Indirect Utility / Expenditure Minimization | Duality problems in consumer theory |
| Discrete Choice / Random Utility | Discrete choice, heterogeneous preferences |
| Search Models | Search costs, stopping rules, information acquisition |
| Costly Information Acquisition | Attention costs, cognitive costs, information processing |
| Rational Inattention | Limited attention, information capacity constraints |
| Signaling | Signaling, education signals, quality signals |
| Screening | Mechanism design under adverse selection |
| Moral Hazard | Hidden action, incentive contracts |
| Adverse Selection | Lemon markets, unobservable quality |
| Hotelling / Product Differentiation | Product differentiation, spatial competition |
| Disclosure / Persuasion | Information disclosure, Bayesian persuasion |
| Mechanism Design | Revelation principle, incentive compatibility |
| Matching Models | Two-sided matching, assignment markets |
| Social Learning | Herding behavior, information cascades |
| Dynamic Optimization | Bellman equations, lifecycle choices |
| OLG / Life-Cycle Models | Overlapping generations, lifecycle investment |
| Principal-Agent | Contract design, delegation |
| General Equilibrium | Competitive equilibrium, market clearing |
| Political Economy | Voting, collective choice, institutional design |

---

### Human Capital and Labor Economics Library

For human capital, education, labor markets, automation, and AI impact, the Skill includes a specialized library of structural theoretical models — all with explicit equilibrium concepts and provable propositions.

| Model Family | Applicable Questions |
|---|---|
| Becker Human Capital | General vs. specific human capital investment |
| Ben-Porath Model | Lifecycle human capital accumulation |
| Roy Model | Sector selection, occupational choice, comparative advantage |
| Cunha-Heckman Skill Formation | Skill formation, early investment, dynamic complementarity |
| Technology of Skill Formation | Skill production function (CES) |
| Self-Productivity & Dynamic Complementarity | Self-productivity and dynamic complementarity in skill formation |
| Early Childhood Investment | Early childhood development investment and optimal policy |
| Intergenerational Transmission | Intergenerational transmission of human capital |
| Education under Credit Constraints | Education choice under credit constraints |
| Occupational Choice & Comparative Advantage | Occupational choice and comparative advantage |
| Acemoglu-Restrepo Task-Based Framework | Task-based production, automation, and new tasks |
| Automation Displacement / Reinstatement | Displacement effects, reinstatement effects, new task creation |
| Human Capital Adaptation to AI | Human capital adjustment under AI shocks |
| Directed Technical Change / SBTC | Directed technical change and skill-biased technological change |

---

## Quality Control Gates

The Skill includes multiple quality gates to avoid the problem of work that "looks like theory but has no theoretical contribution."

| Gate | Name | Checks | On Failure |
|---|---|---|---|
| Gate 1 | Novelty Risk | Whether the question may already be answered in the literature | Return to puzzle refinement |
| Gate 2b | Canonical Fit | Whether model family matches; whether it is just a renamed canonical model | Return to canonical model matching |
| Gate 2c | Theory Lineage | Whether theoretical ancestors, inherited content, and new mechanisms are explicit | Return to canonical model matching |
| Gate 2 | Model Coherence | Whether model primitives, timing, and information structure are consistent | Return to model primitives |
| Gate 3 | Non-triviality | Whether propositions are non-trivial, not merely implied by assumptions | Return to assumptions or propositions |
| Gate 4 | Proof Integrity | Whether proof sketches honestly flag gaps | Return to propositions or proofs |
| Gate 5 | Economic Meaning | Whether economic interpretation extends beyond formal results | Return to economic interpretation |

Gate failures are never hidden or repackaged as passes. The Skill explicitly outputs:

- Failure reason
- Severity
- Recommended loopback stage
- Whether a human override is possible

---

## Human-in-the-Loop Checkpoints

Critical judgments in theoretical economics should not be made automatically by an agent. The Skill therefore includes mandatory researcher-confirmation nodes.

| Checkpoint | Location | Researcher Must Decide |
|---|---|---|
| HiL-1 | After Puzzle Refinement | Whether to accept the research question |
| HiL-2 | After Literature Positioning | Whether to accept the literature positioning |
| HiL-3 | After Persona Council | Whether to accept the theory review conclusions |
| HiL-4 | After Model Primitives | Confirm the equilibrium concept — this is a hard stop |
| HiL-5 | After Proposition Generator | Which propositions to carry into subsequent analysis |
| HiL-6 | After Counterexample Finder | How to handle counterexamples and boundary cases |

**HiL-4 is a hard stop.** Equilibrium concepts — Nash, SPE, BNE, PBE, competitive equilibrium, etc. — must be confirmed by the researcher before advancing.

---

## Five Theory Reviewer Personas

In the Persona Council stage, the Skill simulates five types of theory economics reviewers in two rounds of discussion.

| Persona | Focus |
|---|---|
| Mechanism Theorist | Is the mechanism clear, interesting, and non-trivial? |
| Mathematical Referee | Can the model be formalized? Is the proof likely to hold? |
| Economic Intuition Referee | Do the results have genuine economic meaning? |
| Journal Positioning Referee | More like a theory or applied-theory journal target? |
| Brutal Skeptic | What is the strongest objection? |

The Brutal Skeptic's role is not to support the project but to attack it. If an idea can withstand this persona's critique, it is more worth pursuing.

---

## Output Structure

All project outputs are stored under `Exploration/`, named with a sequential project number and model abbreviation:

```text
Exploration/
└── Project_NNN_<ModelAbbrev>/        ← e.g., Project_001_HumanCapitalAutomation
    ├── state.json
    ├── initial_context/
    │   └── hypothesis.md
    ├── outputs/
    │   ├── research_intake.md
    │   ├── research_puzzle.md
    │   ├── literature_positioning.md
    │   ├── persona_council.md
    │   ├── canonical_model_match.md
    │   ├── model_primitives.md
    │   ├── assumption_audit.md
    │   ├── candidate_propositions.md
    │   ├── proof_sketches.md
    │   ├── counterexamples_and_edge_cases.md
    │   ├── economic_interpretation.md
    │   ├── manuscript_skeleton.md
    │   ├── manuscript_skeleton.tex    ← LaTeX source (pdflatex + Computer Modern)
    │   └── manuscript_skeleton.pdf    ← Academic PDF (pdflatex + Computer Modern)
    ├── gates/
    │   ├── gate-01-novelty-risk.md
    │   ├── gate-02b-canonical-fit.md
    │   ├── gate-02c-theory-lineage.md
    │   ├── gate-02-model-coherence.md
    │   ├── gate-03-non-triviality.md
    │   ├── gate-04-proof-integrity.md
    │   └── gate-05-economic-meaning.md
    └── logs/
        └── stage-log.md
```

---

## Design Principles

### 1. Human-in-the-Loop, Not Fully Automated Research

Core judgments in theoretical economics — whether a research question is meaningful, whether an equilibrium concept is appropriate, whether a proposition is worth pursuing, whether a counterexample is fatal — must be made by the researcher.

AI can assist with generation, review, and rebuttal, but should not substitute for researcher judgment on irreversible decisions.

---

### 2. Match Canonical Models First, Then Build New Ones

Before formally defining model primitives, the Skill runs **Canonical Model Matching**.

This step forces an answer to:

- What is the closest canonical model?
- What structural elements does the current model inherit?
- What is the new mechanism?
- Are the new results derivable from the canonical model alone?

This reduces the risk of "canonical model with a new name."

---

### 3. Honestly Label Uncertainty

The Proof Sketch stage does not package sketches as rigorous proofs. Each proof step is labeled:

- `SOLID`
- `PLAUSIBLE`
- `GAP`
- `FALSE_RISK`

This allows researchers to clearly see what is relatively secure and what remains conjecture-level.

---

### 4. Actively Search for Counterexamples

Stage 8 specifically searches for counterexamples and boundary cases, including:

- 2-agent case
- 2-period case
- Binary-action case
- Corner solution
- Alternative equilibrium
- Violation of key assumptions

The goal of this step is not to make the model look better, but to find early where it might fail.

---

## File Structure

```text
pAI-Econ-claude/
├── SKILL.md                              # Pipeline orchestration: stage routing, Gate logic, HiL protocol
├── CLAUDE.md                             # Project-level rules (citation verification, PDF style standards)
├── README.md                             # Chinese documentation
├── README_EN.md                          # English documentation (this file)
├── THEORETICAL_ECON_MIGRATION_PLAN.md    # Design record for migration from pAI/MSc
├── LICENSE
├── .claude/
│   └── commands/
│       └── theoretical-economics-claude-skill.md  # Slash command entry point
├── model_library/                        # Canonical theoretical economics model library (structural models only)
│   ├── consumer-choice.md
│   ├── indirect-utility-expenditure-minimization.md
│   ├── discrete-choice-random-utility.md
│   ├── search-models.md
│   ├── costly-information-acquisition.md
│   ├── rational-inattention.md
│   ├── signaling.md
│   ├── screening.md
│   ├── moral-hazard.md
│   ├── adverse-selection.md
│   ├── hotelling-product-differentiation.md
│   ├── disclosure-persuasion-information-design.md
│   ├── mechanism-design.md
│   ├── matching-models.md
│   ├── social-learning-information-cascades.md
│   ├── dynamic-optimization-bellman.md
│   ├── overlapping-generations-life-cycle.md
│   ├── principal-agent.md
│   ├── general-equilibrium-basics.md
│   ├── political-economy-collective-choice.md
│   └── human_capital_and_labor/
│       ├── becker-human-capital.md
│       ├── ben-porath-lifecycle.md
│       ├── roy-model.md
│       ├── cunha-heckman-skill-formation.md
│       ├── technology-of-skill-formation.md
│       ├── self-productivity-dynamic-complementarity.md
│       ├── early-childhood-investment.md
│       ├── intergenerational-transmission.md
│       ├── education-credit-constraints.md
│       ├── occupational-choice-comparative-advantage.md
│       ├── task-based-production-acemoglu-restrepo.md
│       ├── automation-displacement-reinstatement.md
│       ├── human-capital-adaptation-automation-ai.md
│       └── directed-technical-change-sbtc.md
├── prompts/
│   ├── 00-intake.md
│   ├── 01-puzzle-refinement.md
│   ├── 02-literature-positioning.md
│   ├── 03-persona-council.md
│   ├── 03b-canonical-model-match.md
│   ├── 04-model-primitives.md
│   ├── 05-assumption-audit.md
│   ├── 06-proposition-generator.md
│   ├── 07-proof-sketch.md
│   ├── 08-counterexample-finder.md
│   ├── 09-economic-interpretation.md
│   ├── 10-manuscript-skeleton.md
│   ├── gate-01-novelty-risk.md
│   ├── gate-02b-canonical-fit.md
│   ├── gate-02c-theory-lineage.md
│   ├── gate-02-model-coherence.md
│   ├── gate-03-non-triviality.md
│   ├── gate-04-proof-integrity.md
│   └── gate-05-economic-meaning.md
├── templates/
│   ├── state.json
│   ├── academic-econ.latex               # Legacy PDF template (deprecated; pipeline now writes .tex directly)
│   ├── author_style_guide_econ.md
│   └── author_style_guide_default.md
└── Exploration/                          # All project workspaces (auto-generated, contents not committed)
    └── Project_NNN_<ModelAbbrev>/
```

---

## Applicable and Not Applicable

### Applicable

- Early-stage theoretical economics brainstorming
- Canonical model extension
- Mechanism modeling
- Theoretical questions in human capital, labor economics, information economics, industrial organization, behavioral economics, etc.
- Initial working paper framework
- Review of propositions and proof sketches
- Counterexample and boundary case checking

### Not Applicable

- Real data cleaning and empirical analysis
- Automatically completing rigorous mathematical proofs
- Automatically confirming literature novelty
- Automatically generating papers ready for submission
- Substituting for researcher judgment on theoretical decisions

---

## Known Limitations

1. **Citation verification requires researcher oversight.**
   Stage 2 now uses web search to verify that proposed citations actually exist, and a mandatory verification gate runs before PDF generation. However, researchers must still judge whether the literature positioning is accurate and whether recent papers are covered. LLM-generated citations can be hallucinated (plausible author, title, and journal but wrong details); the pipeline's verification steps are a safeguard, not a substitute for researcher judgment.

2. **Proof sketches are not formal proofs.**
   Steps marked `GAP` or `FALSE_RISK` must be further derived by the researcher.

3. **The model library is not an encyclopedia.**
   `model_library/` is a modeling template library, not a complete textbook. The library includes only structural models with economic equilibrium concepts and provable propositions — econometric identification frameworks (e.g., MTE, Heckman Selection) are intentionally excluded.

4. **Theoretical contribution requires researcher judgment.**
   Gates can flag novelty risk but cannot ultimately determine a paper's contribution.

---

## Contributing

Contributions are welcome in the following areas:

- Specialized model libraries for auction theory, macro, IO, political economy, etc.
- More rigorous proof integrity gates
- Richer counterexample templates
- Additional manuscript PDF template styles
- Explore mode: multi-round theoretical model space exploration

Basic workflow:

```text
1. Fork this repository
2. Edit prompt files, model_library, or SKILL.md routing logic
3. Test on a research hypothesis end-to-end
4. Submit a PR describing what changed and why
```

---

## License

MIT License.

Copyright © 2026 Chen Zhu, Xiaolu Wang, Weilong Zhang.

Based on pAI/MSc by Mahmoud Abdelmoneum, Pierfrancesco Beneventano, and Tomaso Poggio.

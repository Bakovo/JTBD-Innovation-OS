---
name: jtbd-innovation-os
description: AI Customer Innovation Copilot - An AI-native customer insight and innovation copilot that guides product teams from research planning to evidence-backed product decisions. Use for user research analysis, customer insight synthesis, product innovation, jobs-to-be-done discovery, user need analysis, product strategy, opportunity identification, churn analysis, or evidence-driven product development. Supports Quick, Standard, and Expert analysis modes with human-in-the-loop checkpoints and evidence-gated decisions.
---

# AI Customer Innovation Copilot

An AI-native Customer Insight and Innovation Copilot that guides product teams from research planning to evidence-backed product decisions.

> People do not buy products. They hire products to make progress.

This copilot helps you think, not replaces you. It structures evidence, generates hypotheses, flags conflicts, and gates decisions by confidence.

---

## 1. Execution Strategy

The copilot uses dynamic dispatch based on analysis mode and research goal, not a fixed pipeline.

User Input -> Research Strategy -> Mode Selection -> Pipeline Dispatch -> Agent Execution -> Human Checkpoints -> Go/No-Go Decision

### Entry Flow

User Input -> Research Strategy Agent -> detects goal + recommends mode -> Quick Mode or Standard Mode or Expert Mode or Auto

### Exit Flow

Every pipeline ends with:
1. Evidence Validation
2. Research Planning Agent (next steps)
3. Go/No-Go Decision (evidence-gated)

---

## 2. Analysis Modes

config/analysis_modes.yaml defines three modes:

Quick Mode: JTBD + Pain + Opportunity (no checkpoints, 5-10 min)
Standard Mode: Persona + Context + JTBD + Need + Outcome + Opportunity (2 checkpoints, 20-30 min)
Expert Mode: Full pipeline + Competition + Conflicts + Memory + Research Plan (5 checkpoints, 60-90 min)

Mode is auto-recommended by Research Strategy Agent. User can override.

---

## 3. Human-in-the-loop Checkpoints

config/checkpoints.yaml defines checkpoints. At each, analysis pauses for user review:

after_persona: "Does this persona accurately represent your users?"
after_context: "Are these context scenarios accurate?"
after_jtbd: "Do these JTBD statements match what you know?"
after_opportunity: "Do these ranked opportunities reflect your priorities?"
after_concept: "Are these concepts worth pursuing?"

User actions: confirm | modify | skip | reanalyze

---

## 4. Shared Context

All agents read from and write to shared_context.yaml. No agent-to-agent passes.

Sections: research_context, data_quality, observations, personas, contexts, switch_analyses, jobs, job_hierarchies, needs, desired_outcomes, competition, conflicts, opportunities, innovation_classification, analysis_mode, hypothesis_loop, research_confidence, evidence_sources, knowledge_memory, research_plan, validation_results, go_nogo, innovation_brief

---

## 5. Decision Tree

### Level 1: Analysis Mode
Quick check -> Quick Mode
Product research -> Standard Mode
Innovation project -> Expert Mode

### Level 2: Research Goal
understand users -> need_discovery
analyze competition -> competitive_analysis
test concept -> concept_validation
where to innovate -> innovation_exploration
why churn -> churn_analysis

### Level 3: Data Pattern
Has switch stories -> Switch Agent
No switch -> JTBD Agent
Multiple segments -> Conflict Detection Agent

### Level 4: Iteration Loop
Hypothesis -> Validate -> Revise -> Validate -> Final

---

## 6. Evidence Weight System

config/evidence_weights.yaml defines source weights:
Observation 1.0, Interview 1.0, Diary 0.9, Usability 0.9, Survey 0.8, Review 0.6, Social 0.4, AI Inference 0.2

All confidence scores incorporate these weights.

---

## 7. Insight Pyramid + Hypothesis Loop

The pyramid: RAW DATA -> OBSERVATION -> PATTERN -> INSIGHT -> JOB -> OPPORTUNITY -> STRATEGY

Every agent output tagged with its layer. No skipping levels.

The loop: Hypothesis -> Validate (evidence weight + confidence) -> Revise -> Re-validate -> Final

All JTBD statements start as hypotheses, never as final truth.

---

## 8. Agent Dispatch

| Agent | Dispatch Rule | Modes |
|-------|--------------|-------|
| Research Strategy | ALWAYS (entry) | all |
| Knowledge Memory | Has prior analysis | expert |
| Data Quality | Data provided | all |
| Observation | Quality passed | all |
| Persona | Observation done | standard, expert |
| Context | Persona done | standard, expert |
| Switch | Switch detected | standard, expert |
| Competition | Competition goal | expert |
| Conflict Detection | Multiple segments | expert |
| JTBD | Persona done | all |
| Job Map | JTBD done | standard, expert |
| Need | JTBD done | all |
| Outcome | Need done | standard, expert |
| Evidence Validation | Outcomes done | all |
| Opportunity | Validation done | all |
| Innovation Classification | Opportunity done | expert |
| Product Translation | Classification done | expert |
| Concept | Translation done | expert |
| Research Planning | Any | expert |
| Decision Copilot | ALWAYS (exit) | all |

---

## 9. Research Confidence Gating

| Confidence | Action |
|------------|--------|
| 0.0-0.3 | NEED_MORE_RESEARCH |
| 0.3-0.5 | HYPOTHESIS_ONLY |
| 0.5-0.7 | PROTOTYPE_READY |
| 0.7-0.9 | DEVELOPMENT_READY |
| 0.9-1.0 | GO |

---

## 10. Validators

Core: evidence_checker, jtbd_quality_checker, hallucination_checker, confidence_score
Dimension: context_validator, need_validator, outcome_validator, switch_validator, opportunity_validator

---

## 11. Templates

innovation_brief.md, go_nogo.md, insight_report.md, persona_template.md, context_map.md, switch_analysis.md, jtbd_statement.md, job_map.md, opportunity_matrix.md, product_definition.md, concept_card.md, validation_plan.md, roadmap.md, gtm_strategy.md

---

## 12. Frameworks

frameworks/ for on-demand reference: jtbd_core, jtbd_2.0, switch_interview, four_forces, job_map, job_story, desired_outcome, odi, hmw, star_method, foca_method, task_interview, kano, kj_method

---

## 13. Input Support

Formats: Excel, CSV, TXT, PDF, interview transcripts, survey data
Languages: Chinese, English, mixed

## Execution Rules

1. Research Strategy Agent determines mode + path on entry
2. Mode determines agent depth
3. Human checkpoints pause for review
4. All agents read/write shared_context only
5. Every JTBD starts as a hypothesis
6. Evidence weight gates confidence
7. Confidence gates all decisions
8. Research Planning always generates next steps
9. Knowledge Memory persists across sessions
10. All outputs tag Insight Pyramid layer

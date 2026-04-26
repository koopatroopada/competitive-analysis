---
name: competitive-analysis-master
description: "You MUST use this before making any product/feature decision that requires understanding the competitive landscape. Triggers on: deciding whether to enter a market, prioritizing features for next release, responding to competitor moves, or evaluating an AI product's differentiation. Blocks any conclusion or recommendation until at least 2 cross-validated evidence sources and a forced action (test/copy/avoid/abandon) are provided per insight."
---

# Competitive Analysis Master

## HARD GATE

<HARD-GATE>
Do NOT output any conclusion, recommendation, or "key insight" unless:
1. You have specified which decision question this analysis answers
2. You have classified at least 3 competitors (direct/indirect/alternative) 
3. Each insight is backed by ≥2 evidence sources with stated confidence
4. Each insight maps to an executable action (test/copy/avoid/abandon)

If any of these conditions are missing, you MUST ask for clarification or mark the insight as [UNVERIFIABLE HYPOTHESIS] with a way to validate.
</HARD-GATE>

## Anti-Pattern: "I'll Just Compare Features"

If you find yourself writing a table of features ("竞品A有X功能，竞品B有Y功能") without answering *why* that matters for the decision, stop. Feature tables are forbidden unless they lead directly to a **test/copy/avoid/abandon** action. The user has already seen basic feature lists.

## Checklist

You MUST create a task for each of these items and complete them in order:

1. **Clarify decision context** — ask user: decision question, reader (exec/team/self), output format (1-page memo/PPT/detail)
2. **Scan & filter competitors** — use app stores/reports/communities/AI hubs to produce a table (max 10), filter out stale/low-score/irrelevant, present 3-4 candidates for user approval
3. **Confirm final competitors** — ensure they cover direct/indirect/alternative (at least one of each)
4. **Define analysis dimensions** — tailor to decision (for AI products: must include model boundaries, cost/latency, data flywheel)
5. **Collect cross-validated evidence** — from ≥2 sources (public data, user reviews, hands-on testing, earnings). Mark confidence (high/medium/low). Never rely on official marketing copy alone.
6. **Apply analysis models** — use SWOT (against US) + Feature-Verdict Matrix (copy/test/avoid/abandon). Optional: Porter's Five Forces for entry decisions.
7. **Produce 1-page report** — including: 1-sentence summary, ≤3 insights (phenomenon→attribution→action), prioritized action list (P0/P1/P2 with owner/time/success metric)

## Flowchart (Branching and Loops)

```dot
digraph competitive_analysis {
  rankdir=TB;
  start [label="Start", shape=ellipse];
  clarify [label="Clarify decision context"];
  scan [label="Scan & filter competitors"];
  confirm [label="User confirms 3-4 candidates?"];
  dimensions [label="Define dimensions"];
  evidence [label="Collect ≥2 evidence sources per insight"];
  models [label="Apply SWOT + Feature Matrix"];
  report [label="Draft 1-page report"];
  hard_gate_check [label="HARD GATE conditions met?", shape=diamond];
  missing_info [label="Ask for missing sources or mark hypothesis", shape=box];
  user_accept [label="User accepts report?", shape=diamond];
  revise [label="Revise based on feedback", shape=box];
  done [label="Actionable output delivered", shape=ellipse];

  start -> clarify -> scan -> confirm;
  confirm -> dimensions [label="yes"];
  confirm -> scan [label="no, rescan"];
  dimensions -> evidence -> models -> report -> hard_gate_check;
  hard_gate_check -> missing_info [label="no"];
  missing_info -> evidence;
  hard_gate_check -> user_accept [label="yes"];
  user_accept -> revise [label="no"];
  revise -> report;
  user_accept -> done [label="yes"];
}
---
name: engineering-experiments
description: "Design, run, or review controlled engineering experiments, including protocols, setup validation, result interpretation, and decisions about further investigation."
---

# Engineering experiments

Use the eight steps below to connect a testable hypothesis to an engineering decision. Start at the stage requested, reuse existing artifacts, and produce the requested brief, implementation, results review, or conclusion. Scale documentation to the experiment; eight steps do not require eight documents.

## Select the entry point

- **Design:** steps 1–3, plus a validation plan for step 4. Adapt the [experiment brief](assets/experiment-brief.md).
- **Execute:** steps 4–5 under an agreed protocol. Adapt the [results summary](assets/results-summary.md).
- **Review:** steps 6–8 using existing results. Adapt the results summary and [decision record](assets/decision-record.md); do not require another run merely to complete a review.

Read only the resources needed for the task. The [worked example](references/worked-example.md) illustrates the framework; its settings and sample results are not defaults or evidence for another investigation.

Inspect existing requirements, protocols, results, and authorization before asking questions. Distinguish requirements, constraints, proposed choices, and assumptions. Ask about unresolved choices that materially affect cost, validity, or scope; continue independent work when possible. A request to design or review an experiment does not authorize executing it. Reuse spending authorization already granted rather than introducing repeated approval gates.

## 1. Formulate the hypothesis

Separate the broader thesis from a testable prediction. State the proposed effect, conditions, competing explanations, and decision the experiment should inform. Identify outcomes that would challenge the hypothesis. Distinguish exploratory investigation from confirmatory testing; match the strength of the intended claim to the study design.

## 2. Design the experiment

Define requirements, the intervention, comparison condition, controls, architecture, and environment. Selecting a baseline chooses the starting version; it does not measure its performance. Record the rationale for consequential choices, alternatives left untested, and what stays fixed. Choose a credible baseline rather than weakening it to manufacture improvement. When applicable, distinguish the system performing the task from the mechanism proposing changes to it.

## 3. Specify the protocol

Define metrics, acceptance criteria, cases, repetitions, evaluation order, state isolation, resource limits, and stopping rules. Separate development from evaluation where applicable. Explain why the protocol can answer the question and what uncertainty it will leave. A useful effect, a continuation target, and statistical support are different judgments.

Estimate the costs of development and evaluation, including candidate generation when relevant. Obtain authorization for any spending not already covered. Specify budget enforcement, incomplete-run accounting, and failure/retry rules. Do not import thresholds, candidate counts, or budgets from an example.

## 4. Validate the experimental setup

Validate tools, graders, test data, task feasibility, and starting conditions before interpreting experimental outcomes. Use component and integration tests as appropriate, including known correct and incorrect outcomes. Check actual effects and relevant action traces when final answers alone are insufficient. Record completed checks and remaining limitations separately from planned checks. Reference solutions establish feasibility, not optimality.

## 5. Execute the experiment

Follow the agreed scope and freeze the protocol, configuration, and intervention before evaluation. Preserve the records needed to inspect outcomes: results, traces, timing, usage, costs, and relevant version identifiers. Keep original predictions and record amendments, incomplete work, and deviations.

Do not silently add candidates, change criteria, exclude observations, or repeat runs until successful. Follow the agreed stopping and retry rules. Seek a new decision when continuation would exceed the authorized scope.

## 6. Analyze the results

Evaluate outcomes against predictions, baseline results, and predefined criteria. Report individual-case patterns, aggregates, denominators, and unsuccessful-work costs. Separate comparison execution cost from development or proposal overhead, and estimated usage costs from confirmed charges. Consider caching and other conditions affecting comparability.

Keep measurements separate from explanations and adoption decisions. Do not pool incompatible workloads or combine percentage gains from different cohorts into a measured cumulative saving.

## 7. Interpret the findings

Assess hypothesis support, alternative explanations, measurement validity, uncertainty, and transfer to other conditions. Distinguish independent starting state, new data values, and new task families. Better measured performance does not by itself explain its cause. A missed continuation target does not erase an observed benefit, and a small passing evaluation does not establish broad reliability.

State what remains untested and what fresh evaluation a revised claim would require. Distinguish actual practice from recommendations.

## 8. Conclude and determine next steps

Answer the original question within the tested scope: retain, revise, or reject the hypothesis, or leave it unresolved. Then justify whether to continue, redesign, investigate an alternative, or stop. If another experiment is warranted, specify what it would resolve and why that information is worth its resource cost. Stopping an investigation is not universal disproof of its thesis.

## Iterate and report

Use findings to revise the relevant hypothesis, design, or protocol for the next experiment. Keep each comparison fixed during evaluation; do not retrofit it to the outcome or continue merely because iteration is possible.

Lead with the requested deliverable or conclusion. Preserve user edits and original artifacts. Separate observations, explanations, and recommendations, and link supporting records rather than turning the main summary into a run audit. Claim only work and validation actually completed.

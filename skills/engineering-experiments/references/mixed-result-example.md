# Measured example: fewer controller reads without faster task completion

This is a measured exploratory pilot completed November 4, 2026, not an illustrative success story. The settings and results are not defaults or evidence for another workload. It illustrates analysis and interpretation; it does not prescribe an API implementation.

## Question and controlled change

Experiment 9 asked whether consuming completed streamed answers directly, instead of routinely retrieving session status and saved items, would reduce controller requests and task latency. Both versions already used streaming. The revised controller retained current-state approval checks. Model settings, instructions, business tools, policies, customer inputs, initial databases, and grading stayed fixed.

Four paired repetitions used one fixed simulated Jewelry inspection scenario, with alternating execution order and isolated starting state. These are repeated executions of one scenario, not four independent task families.

## Measurements and boundaries

Task time began with input submission in a ready sandbox and ended with parsed completion and deterministic customer handling. It excluded environment startup, post-task grading, evidence downloads, trace publication, and cleanup. Those phases were recorded separately.

Controller reads count task-time session-state retrievals and turn/item listings. They are HTTP operations by the harness, not business-tool invocations or model generations. Business-tool calls were counted independently.

| Pair | Current task seconds | Revised task seconds | Current reads | Revised reads |
|---|---:|---:|---:|---:|
| 1 | 67.440 | 100.613 | 23 | 2 |
| 2 | 67.515 | 76.759 | 20 | 2 |
| 3 | 64.643 | 68.000 | 17 | 2 |
| 4 | 76.033 | 59.294 | 17 | 2 |

Both versions passed 4/4 conversations and 16/16 item outcomes, with zero prohibited actions. Controller reads totaled 77 versus 8, an 89.6% reduction. Median task time was 67.5 versus 72.4 seconds, about 7.3% higher for the revision. Business-tool invocations totaled 60 versus 67. No model task was rerun or excluded.

## Interpretation and decision

The targeted request-reduction mechanism worked; the predicted latency benefit was not demonstrated. Three pairs were slower and one faster. Four pairs do not establish a general slowdown, superiority, or production reliability.

An unchanged control-file upload took 27.3 seconds in the first revised run. That observation and the different model-selected tool paths offer possible explanations; they do not isolate the cause of the overall difference or justify excluding the run. Summed request await times include network, queueing, and server work, and may overlap other activity. Subtracting their reduction from task wall time would not establish a speed saving.

The harness checked complete turn/final-item events rather than partial text or idle status. Streamed output was reconciled against independently saved items, while business effects were graded against persisted state. Missing-stream recovery was checked offline; no live fallback occurred. Offline validation is not evidence of live recovery reliability.

The decision was to retain the mixed finding, make no general latency claim, and require further evidence before performance-based adoption. Meeting business requirements and reducing requests were separate from demonstrating faster completion. No additional experiment was automatically authorized.

## Evidence provenance and retention lesson

The source investigation retained the protocol, operation journals, raw events, official spans, saved-item reconciliation, business-state snapshots, grading, and cost records. It recorded evidence collection separately from task latency. This skill package includes the paired measurements above, not the raw traces or databases.

Source artifacts in that investigation: `docs/experiment-09-results.md` and `runs/experiment-09-paired-001/comparison-audited.json`. The audited JSON's SHA-256 is `f45c6e69828f89d7efcb8ee7f1c2af1aaae326762853cc6164951f26b35598d9`. These identifiers document provenance; the source artifacts are not bundled here and the hash alone is not independent validation.

For a new experiment, specify which hosted records will remain accessible, which evidence needs exporting for the agreed analysis or reproduction, and when access may expire. Neither downloading everything nor retaining only hosted links is a universal requirement.

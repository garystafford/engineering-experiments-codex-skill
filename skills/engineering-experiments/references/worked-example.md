# Worked example: evaluating a response cache

This is an illustrative scenario with supplied sample results, not a record of an executed experiment. Its case count, target, and measurements are not defaults.

## 1. Formulate the hypothesis

An application repeatedly retrieves reference records. The hypothesis is that adding a response cache will reduce median request latency by at least 20% without changing the returned records. The engineering decision is whether to adopt the cache. Competing explanations include a warmer underlying service or a different mix of requests.

## 2. Design the experiment

Select the current uncached implementation as the comparison baseline and the cached implementation as the intervention. Hold the service, request sequence, machine, and correctness checks fixed. Include repeated reads and record updates; otherwise an always-return-the-old-value cache could appear effective. Alternatives such as changing the database or batching requests remain untested.

## 3. Specify the protocol

Reserve evaluation fixtures that were not used to tune the cache. Use 100 requests per version, with matched starting data and recorded initial cache state. Specify execution order and cache warm-up treatment before running. Measure correctness, median latency, and stale responses. The acceptance criteria are unchanged correctness, no stale responses, and at least 20% lower median latency. Set local run-time and memory limits; no paid service is needed for this example.

The selected request sequence tests a defined workload. It does not estimate the frequency of real production traffic patterns.

## 4. Validate the experimental setup

Check that known correct and stale responses receive the expected grades. Verify that record updates reach the underlying service, timing includes the intended operations, and one version's run does not alter the other's starting state. Record which checks pass before execution. A benchmark that never updates records cannot test cache invalidation correctly.

## 5. Execute the experiment

Run both frozen implementations under the agreed protocol. Retain request outcomes, timing, cache events, and configuration identifiers. Do not retune expiration settings after seeing evaluation results and present the rerun as the original comparison.

## 6. Analyze the results

Suppose the supplied results show both versions returned the correct record for 100/100 requests, with no stale responses. Median latency changed from 120 ms to 90 ms, a 25% reduction. These observations meet the selected workload's acceptance criteria. Inspect individual requests as well as the median; a lower median does not imply every request improved.

## 7. Interpret the findings

The results support the cache's benefit on the tested sequence. They do not establish production reliability, performance under concurrency, or correctness across every update pattern. A single run per version cannot establish repeatable latency savings, and the execution conditions may leave warm-up effects unresolved.

## 8. Conclude and determine next steps

Conclude that the cache met the pilot criteria, within the tested conditions. A further experiment might test concurrent reads and writes or repeat the comparison with controlled warm-up. Explain why the additional information is needed for adoption instead of automatically running more tests or declaring the system production-ready.

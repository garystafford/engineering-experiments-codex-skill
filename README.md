# Engineering Experiments for Codex

A Codex skill for designing, running, and reviewing controlled engineering experiments. It connects a testable hypothesis to an engineering decision through eight steps: hypothesis, design, protocol, setup validation, execution, analysis, interpretation, and conclusion.

Use it to compare implementations, evaluate performance or cost changes, investigate agent behavior, or review existing experimental results. It emphasizes credible baselines, predefined criteria, resource limits, retained evidence, and conclusions bounded by what was tested. Timing boundaries, harness validation, precise call counts, and separate mechanism and outcome measures help prevent misleading efficiency claims.

For more details on the framework, read [From Hypothesis to Understanding: A Practical Framework for Applied AI Engineering Experiments](https://blog.latentthoughts.com/from-hypothesis-to-understanding-a-practical-framework-for-engineering-experiments).

## Install

In Codex, ask the built-in skill installer:

```text
$skill-installer install the engineering-experiments skill from https://github.com/garystafford/engineering-experiments-codex-skill/tree/main/skills/engineering-experiments
```

Alternatively, clone this repository and copy the skill into your user skill directory:

```sh
git clone https://github.com/garystafford/engineering-experiments-codex-skill.git
mkdir -p ~/.agents/skills
cp -R engineering-experiments-codex-skill/skills/engineering-experiments ~/.agents/skills/
```

For installation in a single project, copy the folder into that project's `.agents/skills/` instead. If a copy is already installed, update that copy rather than creating a second skill with the same name. If the skill does not appear, restart Codex.

See the [official OpenAI skill documentation](https://learn.chatgpt.com/docs/build-skills) for discovery locations and installation details.

## Use

Invoke the skill with the stage and context you need:

```text
$engineering-experiments Design an experiment to compare a response cache with our current implementation. Start with a hypothesis and protocol; do not run it yet.
```

```text
$engineering-experiments Execute the agreed protocol in experiment-brief.md and retain the results and traces within the authorized budget.
```

```text
$engineering-experiments Review these benchmark results, assess what they support, and recommend whether to continue or stop.
```

The skill can start in design, execution, or review mode. It reuses existing artifacts and scales documentation to the task. A design or review request does not authorize execution or additional spending.

## Included

- [Skill instructions](skills/engineering-experiments/SKILL.md)
- [Experiment brief template](skills/engineering-experiments/assets/experiment-brief.md)
- [Results summary template](skills/engineering-experiments/assets/results-summary.md)
- [Decision record template](skills/engineering-experiments/assets/decision-record.md)
- [Illustrative response-cache example](skills/engineering-experiments/references/worked-example.md)
- [Measured mixed-result example](skills/engineering-experiments/references/mixed-result-example.md)

This is an instruction-only skill; it includes no executable scripts and requires no additional packages to install. Running a particular experiment may require its own tools or services. The response-cache example contains illustrative sample results. The mixed-result example summarizes a measured pilot with paired observations and source provenance; neither example supplies default settings or evidence for another workload.

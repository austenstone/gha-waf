# The GitHub Actions Well-Architected Framework

## Introduction

The GitHub Actions Well-Architected Framework is a design framework that can improve the quality of a workload by helping it to:

* Be resilient, available, and recoverable.
* Be as secure as you need it to be.
* Deliver a sufficient return on investment.
* Support responsible development and operations.
* Accomplish its purpose within acceptable timeframes.
* The framework is founded on the five pillars of architectural excellence, which are mapped to those goals. They are: Reliability, Security, Cost Optimization, Operational Excellence, and Performance Efficiency.

Each pillar provides recommended practices, risk considerations, and tradeoffs. The design decisions must be balanced across all pillars, given the business requirements. The technical and actionable guidance is broad enough for all workloads and applies to a specific scenario. This guidance is centered on GitHub Actions.

Workload architecture isn't the same as its implementation. The Well-Architected Framework can set you up for success through architectural design, but the implementation choices depend on the business requirements and constraints of your organization.

## Pillars

The pillars dive into the five key areas of the Well-Architected Framework.

### 1. Reliability



### 2. Security

#### [Security hardening for GitHub Actions](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)

### 3. Cost Optimization

#### Jobs round up to the nearest minute

When you run a job GitHub Actions spins up a new VM for the job to run on. The job is billed by the minute, and any fraction of a minute is rounded up to the nearest minute. For example, a job that runs for 61 seconds is billed for two minutes.

#### [Caching dependencies to speed up workflows](https://docs.github.com/en/actions/using-workflows/caching-dependencies-to-speed-up-workflows)

Caching dependencies can significantly reduce the time it takes to run a workflow. For example, if you're building a Node.js project, you can cache the `node_modules` directory to avoid reinstalling dependencies every time you run a workflow.

#### [Set timeouts for workflows](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idtimeout-minutes)

You can set a timeout for each [job](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idtimeout-minutes) or [step](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idstepstimeout-minutes) in a workflow to prevent it from running for longer than it should. If the timeout is reached, the job or step is cancelled.

### 4. Operational Excellence

### 5. Performance Efficiency

### 6. Scale

#### Reusable workflows & Composite Actions

[Reusable Workflows](https://docs.github.com/en/actions/learn-github-actions/reusing-workflows) and [Composite Actions](https://docs.github.com/en/actions/creating-actions/creating-a-composite-run-steps-action) can help you reuse logic across multiple workflows.

| Feature | [Reusable workflows](https://docs.github.com/en/actions/learn-github-actions/reusing-workflows) | [Composite Actions](https://docs.github.com/en/actions/creating-actions/creating-a-composite-run-steps-action) |
|---------|--------------------|-------------------|
| Definition | Reusable jobs | Reusable steps |
| Nesting Depth | 3 layers | 10 layers |
| Use of Secrets | Can use secrets from the caller workflow | Must be passed in as inputs |
| Can specify the `runs on` label | Yes | No |
| Can add additional steps to job | No | Yes |

## Conclusion

Summarize the key points of the framework and its benefits.

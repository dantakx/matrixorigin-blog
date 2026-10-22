---
title: "MatrixOrigin Releases the Enterprise AI Infrastructure White Paper 2026"
author: MatrixOrigin
description: "When AI moves from generating answers to carrying business tasks, the hard problem is state, not the model. This white paper presents AI State lifecycle management, the six components of the MOI platform, and measured results from four customer scenarios."
tags: ["Whitepaper"]
keywords: ["Enterprise AI Infrastructure", "AI State", "MOI", "White Paper", "MatrixOne"]
date: "2026-10-22T17:00:00+08:00"
publishTime: "2026-10-22T17:00:00+08:00"
image:
  "1": "/images/blog-covers/whitepaper.png"
  "235": "/images/blog-covers/whitepaper.png"
lang: en
status: published
translations:
  zh: enterprise-ai-infrastructure-white-paper-2026
---

# MatrixOrigin Releases the Enterprise AI Infrastructure White Paper 2026

*When AI moves from generating answers to carrying business tasks, the hard problem is state, not the model.*

MatrixOrigin has released the Enterprise AI Infrastructure White Paper 2026.

For the past two years, across procurement, document processing, bid preparation, recruiting, and many other enterprise settings, we kept confirming one thing. When AI moves from generating an answer to carrying a business task that continues, what an enterprise has to manage is no longer the model. It is the data, the context, the memory, and the execution state the AI depends on.

This white paper is our view of that problem, and a record of what we have learned in practice.

## From generating an answer to carrying the task

Enterprise AI is moving past the single application, toward business tasks that cross systems and continue over time.

Consider a purchase. Someone checks the specification, compares quotes, waits for approval, and then calls a business system to create the request. The task crosses several systems and several points in time. A change in any fact, any permission, or any execution state along that path can change the outcome.

In customer work, the same failures kept coming back. A task is interrupted, and no one knows where it stopped. A model is upgraded, and knowledge that had already been confirmed does not carry forward. A conclusion is wrong, and the basis it was drawn from at the time cannot be found.

These problems share a root: state management, at the infrastructure layer. That is the question this white paper is written to answer.

## Managing the full life of AI State

Many teams assume that connecting data to a model finishes the job of AI infrastructure. In our judgment, that is only the first step. Whether AI can keep running reliably inside an enterprise depends on continuous management of two kinds of assets.

AI-Ready data assets are data and knowledge that AI can understand inside a specific business, use under the right permissions, and maintain over time. A quote has to state quantity, tax, and validity. A contract rule has to state the scope it applies to, and the source it came from. Only when those conditions are clear can the material be reused reliably on a later task.

AI State covers more than context. Beyond the information actually used on this turn, it includes task progress, memory, and tool results, and the prompts, skills, policies, and model configuration that shape behavior. Saving state is not enough. The whole lifecycle has to be managed: creation, storage, retrieval, experiment, validation, and invalidation.

The white paper is explicit on one point. Writing state down is not management.

A quote can be stored correctly and still be applied to the wrong quantity, or the wrong version. A platform can restore an earlier state while the order in the procurement system has already taken effect. Data consistency has to work together with business correctness. Otherwise the AI takes an action in which every piece looks right, and the combination is wrong.

## MOI: six components, with state running through them

MatrixOrigin is an enterprise AI infrastructure company. The technical approach is built around the full lifecycle of AI State. For that, we built MatrixOne Intelligence (MOI). The platform has six components. Each has a defined job.

| Component | Role | Primary responsibility |
| --- | --- | --- |
| MatrixPipeline | Compiler for enterprise business context | Multi-source ingestion, semantic extraction, and construction of context assets |
| Astra | Open-source agent runtime | Task execution, tool calls, permissions, and run records |
| Memoria | Open-source long-term memory and version management | Accumulating, retrieving, sharing, and correcting memory |
| Genesis | Model access and AI service infrastructure | Model serving, routing, and management of usage and cost |
| Morpheus | Evaluation and continuous improvement | Evaluation, feedback, and organized validation of domain improvement |
| MatrixOne | Unified foundation for data and persistent state | The foundation for data management, query, isolation, and versioning |

Persistent state management runs through the way these components work together. MatrixPipeline turns scattered material into business context that can be understood and updated. Astra selects those assets and uses them inside a specific task. Memoria manages experience that can be reused. Morpheus organizes evaluation and improvement. Genesis supplies the models. MatrixOne provides the foundation for the data and the state.

## Open, and what the enterprise builds stays with the enterprise

Models and agent frameworks change quickly. The knowledge an enterprise accumulates takes time. The principle we hold is this: infrastructure should preserve an asset’s identity, its meaning, and the rules for using it, so that a new component can connect to assets that already exist.

Astra and Memoria are open source under the Apache-2.0 license. Morpheus is not yet open source. Customers can keep the tools they already use. Memoria can connect to other agents through the Model Context Protocol (MCP). Astra Gateway can connect to different agent CLIs.

A connected interface is only the first step. Change the component, and the state still has to make sense.

When a component reads “completed,” it has to know whether what finished was a model call, a tool execution, or a formal business action. When it reads a memory, it has to know the source, the scope, and the version that is valid. Business facts and confirmed experience can be migrated in an explicit format. Model inference blocks, caches, and framework checkpoints may not be convertible. Replacing a component is not the same as moving a model’s entire internal state across unchanged.

## Figures from customer work

We believe the value of infrastructure has to be proved, in the end, in real business work. The white paper records the results of work with customers across four scenarios.

| Scenario | What the project recorded | Assets that can still be used |
| --- | --- | --- |
| Training and contract review | More than 20 systems connected. Time to prepare data for a new application cut by about 80%. Contract review reduced from 16 days to about one minute. | Product and marketing knowledge, clause rules, and source material |
| Intelligent sourcing and price comparison | Project procurement cost down by about 15%. | Supplier records, quote terms, and the basis for the purchase |
| Intelligent bid preparation | Time to prepare bid documents reduced from one to two weeks to one to two days. Output efficiency up by about 10×. | Product material, qualifications, past responses, and project cases |
| First-pass resume screening | About 2,000 resumes processed per hour. First-pass screening throughput up by about 100×. | Role rules, candidate evidence, and human feedback |

Each figure belongs to the scope it was measured in.

The contract figures refer to the review step in that case. They do not include every legal approval and signature. The procurement reduction refers to that project’s purchasing scope and its baseline. The recruiting figures describe processing capacity. They do not represent the quality of hires. For bid preparation, cycle time and efficiency were recorded as separate metrics. A ratio of those range endpoints is not the efficiency figure.

We state those boundaries as they are. We also suggest that an enterprise evaluate an AI infrastructure by the full cost of a qualified task, not by the price of a single call.

## Who the white paper is for

It is written for enterprise technology leaders, architects, and platform teams.

If your organization is in the middle of any of the following, the paper is worth reading:

- Moving AI from a point tool to business tasks that cross systems
- Reusing knowledge, rules, and experience across applications
- Worrying that a model upgrade, or a change of component, will force a start from scratch

The companion Playbook adds configuration steps, worked business calculations, and acceptance methods. It covers procurement, document processing, bid preparation, and recruiting.

## Continuous operation is the proof

The value of enterprise AI has to be proved by continuous operation. After state grows, it can still be queried and reclaimed. Under concurrent change, isolation still holds. After a component is replaced, an existing task can still be explained and continued.

This white paper is how we think about building AI infrastructure, and the experience accumulated across a large number of real scenarios.

The full Enterprise AI Infrastructure White Paper 2026 and the companion Playbook are available now.

📥 **[Download the white paper](https://matrixorigin.io/whitepaper)** — the full Enterprise AI Infrastructure White Paper 2026 and companion Playbook are available now at the MatrixOrigin whitepaper center.

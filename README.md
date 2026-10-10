# Agent Harness Workshop — Learning Repository

A hands-on learning repository exploring how to design modular, model-agnostic AI agent harnesses using TypeScript. This repository documents my learning journey through agent control loops, tool orchestration, execution policies, human approval, memory, and observability.

## Overview

An agent harness is the execution and control layer around an AI model. It manages how an agent makes decisions, invokes tools, processes feedback, and completes tasks within defined limits and safety controls.

Through this workshop, I explored how to move beyond basic LLM applications toward structured, controlled, and extensible agent systems.

## Key Concepts Learned

- **Agent Control Loops:** Implementing bounded execution loops with objectives, structured model decisions, and termination conditions.
- **Tool Calling and Feedback:** Building the decide–act–observe cycle, where tool results inform subsequent model decisions.
- **Tool Registry:** Registering and resolving tools by name while handling unknown and duplicate tool registrations.
- **Execution Engine:** Separating agent reasoning from tool execution and representing failures as explicit observations.
- **Policy Enforcement:** Checking tool risk and execution limits before allowing an operation.
- **Human-in-the-Loop Approval:** Separating general execution permissions from approval for individual actions.
- **Context and Memory:** Understanding how conversation context, stored information, and agent-visible information differ.
- **Tracing and Observability:** Recording execution steps to understand and debug agent behavior.
- **Model Provider Adapters:** Exploring how provider-specific integrations can be separated from the core agent architecture.
- **Runtime Code Execution:** Understanding how agents can generate and execute code in a controlled workspace.
- **Extensible Tool Architecture:** Exploring how browser, file, MCP, and other integrations can be added as tools without redesigning the agent core.

## Workshop Modules

| Stage | Module | Key Learning |
|---|---|---|
| 1 | Bounded Agent Loop | Objectives, decision contracts, and step limits |
| 2 | Tool Feedback Loop | Tool execution and observation feedback |
| 3 | Tool Registry | Name-based tool lookup and validation |
| 4 | Execution Engine | Controlled execution and failure handling |
| 5 | Policy Before Execution | Risk assessment and execution limits |
| 6 | Human Approval Gate | Policy enforcement and per-action approval |
| 7 | Traces and Observability | Understanding and tracing agent runs |
| 8 | Enterprise Marketing Harness | Runtime code execution and CSV-based analysis |

## Architecture Principles

The workshop emphasizes several important design principles:

1. **Separation of concerns:** Keep the agent core, tool registry, execution engine, and policy layer independent.
2. **Controlled execution:** Bound agent runs and validate operations before execution.
3. **Least privilege:** A model's request to invoke a tool does not automatically grant permission.
4. **Explicit failure handling:** Tool failures should be surfaced accurately rather than represented as successful results.
5. **Human oversight:** Sensitive operations can require approval before execution.
6. **Observability:** Preserve execution traces to make agent behavior easier to inspect and debug.
7. **Modularity:** Allow model providers and tool integrations to evolve without rewriting the core harness.

## Technology Stack

- TypeScript
- Node.js
- npm
- Azure AI Foundry / GPT integration
- Model-provider adapters
- Tool orchestration and runtime execution

## Learning Outcomes

By working through this workshop, I am developing a practical understanding of:

- How an AI agent's control layer differs from the underlying language model.
- How to design modular tool-calling workflows.
- Why authorization, policy enforcement, and human approval are distinct controls.
- How context, memory, and traces serve different purposes.
- How to structure agent systems for extensibility, reliability, and controlled execution.

## Getting Started

```bash
git clone https://github.com/karthikeyanVK/agentharness-workshop.git
cd agentharness-workshop
npm install
npm run dev
```

To validate the TypeScript project:

```bash
npm run build
```

For the Azure AI Foundry integration, configure the environment variables described in `.env.example`. Keep API keys and other secrets out of version control.

## Acknowledgment

This repository is based on concepts and exercises covered in the Agent Harness Workshop. The original workshop repository is available at [karthikeyanVK/agentharness-workshop](https://github.com/karthikeyanVK/agentharness-workshop).

My goal is to strengthen my understanding of production-oriented AI agent architecture through hands-on implementation and experimentation.

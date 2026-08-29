# AI-research-decision-agent
AI-powered multi-step research and decision agent built with n8n, Gemini, HTTP API tools, and Calculator.

# AI Research & Decision Agent

An AI-powered multi-step problem-solving agent built with n8n and Google Gemini.

The agent accepts a complex question, determines the required sub-tasks,
uses external research and calculation tools, analyzes the returned
information, and produces a structured decision report.

---

## 🎯 Assignment

**AI Automation Intern — 24 Hour Challenge**

### Selected Option

**Option B — The Multi-Step Problem Solver**

The assignment asks for an agent that:

- breaks a complex task into sub-steps
- uses at least two tools
- reaches a final answer
- demonstrates the reasoning/tool-use trail
- can be presented as a working prototype

---

## 💡 Problem

Many real-world questions cannot be answered reliably with a single
LLM response.

For example, a business decision may require:

1. external information
2. numerical calculations
3. comparison
4. analysis
5. a final recommendation

The goal of this project is to demonstrate an AI agent that can
coordinate multiple tools to solve this type of problem.

---

## 🚀 Solution

The system uses an n8n AI Agent connected to:

1. Google Gemini Chat Model
2. HTTP Request Research Tool
3. Calculator Tool

The AI Agent determines which tools are required for the user's task.

The returned information is then synthesized into a structured
Research & Decision Report.

---

## 🏗️ Architecture


                    ┌─────────────────────┐
                    │     User / Chat     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │    Chat Trigger     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      AI Agent       │
                    │                     │
                    │ Understand           │
                    │ Decompose            │
                    │ Select Tools         │
                    │ Analyze              │
                    └──────────┬──────────┘
                               │
                    ┌──────────┴──────────┐
                    │                     │
                    ▼                     ▼
             ┌──────────────┐      ┌─────────────┐
             │ HTTP Request │      │ Calculator  │
             │ Research Tool│      │    Tool     │
             └──────┬───────┘      └──────┬──────┘
                    │                     │
                    └──────────┬──────────┘
                               ▼
                    ┌─────────────────────┐
                    │   AI Agent Analysis │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Final Report      │
                    │                     │
                    │ Research            │
                    │ Calculations        │
                    │ Analysis            │
                    │ Recommendation      │
                    └─────────────────────┘

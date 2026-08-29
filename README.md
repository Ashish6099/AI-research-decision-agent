# AI Research & Decision Agent    # Demo link: https://www.loom.com/share/6e4b6fa4e2134b6e864004df1e99363a

An AI-powered multi-step problem-solving agent built with n8n and Google Gemini.

The agent accepts a complex question, determines the required sub-tasks,
uses external research and calculation tools, analyzes the returned
information, and produces a structured decision report.

---

## 🎯 The Multi-Step Problem Solver**

The task asks for an agent that:

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
🧠 Agent Workflow

The agent follows this high-level process:

1. Understand

Understand the user's objective and identify the required information.

2. Decompose

Break the complex question into smaller sub-tasks.

3. Select tools

Determine which available tools are appropriate.

4. Research

Use the HTTP Research Tool when external information is required.

5. Calculate

Use the Calculator whenever numerical calculations are required.

6. Analyze

Combine the returned information and evaluate the relevant options.

7. Recommend

Generate a structured final answer and recommendation.

🛠️ Tools
Google Gemini Chat Model

Used as the reasoning and language model powering the AI Agent.

HTTP Request Tool

Used as the external research capability.

The prototype currently uses the Wikipedia API through an HTTP
Request Tool.

The search query can be dynamically provided by the AI Agent.

Calculator

Used for deterministic numerical calculations.

The AI Agent delegates mathematical operations to the Calculator
instead of relying on mental arithmetic.

🔍 Example Task

Example user request:

I am designing an AI lead management system for a small business.
Research PostgreSQL, MySQL, and MongoDB and compare their suitability
for storing structured lead data. A hypothetical SaaS service costs
$49 per month. Calculate the annual cost. Based on the research and
calculation, recommend the most suitable database approach for a
small business and explain why. Use the available tools.

This requires multiple sub-tasks:

research PostgreSQL
research MySQL
research MongoDB
compare the technologies
calculate $49 × 12
analyze the results
provide a recommendation
🧮 Example Calculation
Monthly cost = $49

Annual cost = $49 × 12

Annual cost = $588

The Calculator tool performs the calculation.

📊 Final Output

The final response is formatted as a:

Research & Decision Report

It contains:

Objective
Agent Process
Research Findings
Calculations
Analysis
Recommendation
Tools Used
Limitations

This makes the result easier for a user to understand than raw JSON
or an unstructured LLM response.

🧠 Tool-Use Trail

The execution can be observed in the n8n execution view.

Example:

User
 ↓
Chat Trigger
 ↓
AI Agent
 ├──→ HTTP Research Tool
 │       ↓
 │    Research Results
 │
 └──→ Calculator
         ↓
      Calculation
 ↓
AI Agent Analysis
 ↓
Final Report

The exact order of tool calls is determined by the AI Agent based on
the task.

⚠️ Error Handling

The agent is instructed not to fabricate information when a tool fails.

If the research tool fails:

Research Tool
      ↓
     Error
      ↓
AI Agent detects unavailable information
      ↓
Does not fabricate research
      ↓
Reports the limitation

If the Calculator fails:

Calculator
     ↓
   Error
     ↓
AI Agent reports that the calculation could not be completed

The final response identifies limitations when required information
could not be retrieved.

🔐 Security

No API keys, passwords, tokens, or private credentials are included
in this repository.

Credentials are configured separately inside n8n.

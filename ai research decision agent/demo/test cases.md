# Test Cases

## Test Case 1 — Research + Calculation

### Input

I am designing an AI lead management system for a small business.
Research PostgreSQL, MySQL, and MongoDB and compare their suitability
for storing structured lead data. A hypothetical SaaS service costs
$49 per month. Calculate the annual cost. Based on the research and
calculation, recommend the most suitable database approach for a
small business.

### Expected behavior

The agent should:

- perform external research
- use the Calculator
- analyze the information
- produce a recommendation

---

## Test Case 2 — Calculation

### Input

A SaaS platform costs $125 per month. Calculate the yearly cost and
explain the calculation.

### Expected behavior

The Calculator should be used.

Expected result:

$125 × 12 = $1,500/year

---

## Test Case 3 — Research

### Input

Research PostgreSQL and explain its primary use cases.

### Expected behavior

The HTTP Research Tool should be used and the result summarized.

---

## Test Case 4 — Tool Failure

### Input

Research a topic while the research API is unavailable.

### Expected behavior

The agent should:

- detect the unavailable research
- avoid fabricating research
- explain the limitation
- continue with any independently solvable part
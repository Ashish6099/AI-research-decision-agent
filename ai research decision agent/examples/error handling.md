# Error Handling

The prototype explicitly instructs the AI Agent not to fabricate
information when a tool fails.

## Research Tool Failure

Expected behavior:

```text
Research Request
      ↓
     FAIL
      ↓
Agent detects missing information
      ↓
No fabricated research
      ↓
Limitation reported
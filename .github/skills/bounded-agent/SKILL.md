# Implement a Bounded Repository Agent

## Apply when

Use this skill for local Ollama integration, agent skills, orchestration, prompts, or policy enforcement.

## Workflow

1. Define the agent's input, output, capabilities, timeout, and resource limits.
2. Add an explicit skill manifest with required and granted permissions.
3. Keep model calls behind an adapter interface.
4. Validate model output against a typed schema.
5. Log session, policy decision, tool call, and result without logging secrets.
6. Add deny-by-default tests for permission escalation.

## Validation

- unit test policy allow/deny decisions;
- integration test a mock model adapter;
- test malformed model output;
- test timeout and cancellation;
- run the workspace test suite.

## Constraints

- no autonomous privileged GitHub or shell writes;
- no unrestricted tool access;
- no prompt text that requests credential disclosure;
- no unbounded context or retries;
- no silent execution of generated instructions.

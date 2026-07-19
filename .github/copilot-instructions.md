# AI Engineering Directives: Aura TCK

You are an implementation assistant (Copilot / Devin) working on the **Aura Protocol Technology Compatibility Kit (TCK)**.

## CORE INVARIANTS (NEVER VIOLATE):
1. **Zero Float Runtime:** Never use `float` or `double`. All numeric values are strictly integers.
2. **Deterministic Execution:** No hidden state. Do not use random number generators (`uuid`, `random`) or internal timestamps (`time.now()`) during serialization.
3. **Strict Unicode:** Never apply implicit Unicode normalization (NFC/NFD). Preserve raw code points.
4. **Byte-Level Truth:** The final arbiter of correctness is the raw `canonical.bin` byte stream compared against the Oracle signature, not Python object equality.

## WORKFLOW BOUNDARIES:
- **No Architectural Changes:** You do not design the protocol. You implement the exact constraints defined in the `/spec/` documents. Follow the normative documents under `/spec/`. Never infer or redefine protocol behavior.
- **TCK Scope:** This repository is the Conformance Kit. Do NOT implement business logic, databases, or API servers here.
- **Tooling:** Use `ruff` for linting/formatting and `mypy` for typing. Ignore `flake8`.

## STOP CONDITION:
If a requirement is ambiguous, DO NOT GUESS. Halt execution and request clarification from the human Technical Architect.

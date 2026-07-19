# DECISIONS

Tu będziemy zapisywać decyzje architektoniczne projektu (ADR). Każda decyzja powinna zawierać: kontekst, opcje, wybór i uzasadnienie.

---

DEC-001: Repository starts from a clean baseline

Status: Accepted

Context:
The project must avoid contamination from legacy PoC repositories and unclear history. Starting from a clean baseline ensures design decisions are explicit and traceable.

Decision:
Initialize the repository without importing legacy PoC code. The initial commits will contain only project scaffolding, documentation, and manifests. Any useful code from previous PoC must be explicitly reviewed and reintroduced via new commits referencing a contract.

Consequences:
- Easier auditing and review of each introduced component.
- Reduced risk of hidden technical debt being carried into production.
- Slight upfront cost to reimplement or adapt prior work if needed, but higher long-term maintainability.

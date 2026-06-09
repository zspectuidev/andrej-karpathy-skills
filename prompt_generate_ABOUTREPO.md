# Generate ABOUTREPO.md

Analyze the entire repository and generate a comprehensive `ABOUTREPO.md`.

The document is NOT a README, changelog, roadmap, marketing document, or developer guide.

Its purpose is to serve as the repository memory layer for future AI agents and engineers.

A new session should be able to read ONLY:

* graphify-out/GRAPH_REPORT.md
* ABOUTREPO.md

and quickly understand how the repository works without re-discovering the architecture.

---

## Requirements

Produce a repository snapshot describing the CURRENT state of the codebase.

Focus on facts, implementation details, architecture, data flow, invariants, and extension points.

Do not write aspirational content.

Do not describe planned features.

Do not invent architecture that does not exist.

If something cannot be determined from the code, explicitly state that.

---

# Required Sections

## 1. What

* What the project does
* Primary purpose
* Intended users
* Scope
* Out-of-scope items

---

## 2. Why

* Problem being solved
* Design goals
* Key differentiators
* Major tradeoffs

---

## 3. Architecture

Describe:

* High-level architecture
* Core subsystems
* Boundaries
* Responsibilities
* Ports/adapters/layers (if applicable)

Include diagrams using ASCII when useful.

---

## 4. Module Relationships

Map major modules and dependencies.

For each major module:

* Responsibility
* Inputs
* Outputs
* Dependencies
* Consumers

Show how modules interact.

---

## 5. Code Layout

Document the repository structure.

For important files/directories:

* Purpose
* Responsibilities
* Special behavior
* Ownership within architecture

Example:

```text
src/
├── api/
├── services/
├── storage/
└── ...
```

Include explanations.

---

## 6. Execution Flow

Describe the primary runtime paths.

Examples:

* CLI flow
* Request lifecycle
* Background jobs
* Processing pipeline
* Startup sequence

Use step-by-step flow diagrams where useful.

---

## 7. Data Model

Document:

* Core entities
* Data structures
* DTOs
* Models
* Database schema
* Relationships

Explain which objects move through the system.

---

## 8. Tech Stack

Document:

* Languages
* Frameworks
* Databases
* Build tools
* Packaging
* Infrastructure
* External services

Separate mandatory vs optional dependencies.

---

## 9. Configuration

Document:

* Config files
* Environment variables
* Runtime flags
* Secrets handling
* Configuration precedence rules
* Validation behavior

---

## 10. Functionality Inventory

List all major capabilities.

For each capability:

* What it does
* Entry point
* Main modules involved
* Outputs produced

This section should act as a feature catalog.

---

## 11. Conventions

Document project conventions:

* Naming
* Patterns
* Architectural rules
* Coding standards enforced by the repository
* Plugin mechanisms
* Dependency rules

Include any repository-specific practices.

---

## 12. Deployment Model

Document:

* Build process
* Packaging
* Runtime environments
* Deployment targets
* CI/CD
* Operational assumptions

---

## 13. Outputs

Document generated artifacts:

* Reports
* Files
* APIs
* Databases
* Logs
* Side effects

Include formats and locations.

---

## 14. Extension Cookbook

Document how to add:

* New modules
* New integrations
* New plugins
* New features
* New workflows

Focus on existing extension mechanisms.

---

## 15. Key Invariants

List rules that must never be broken.

Examples:

* Schema guarantees
* Security guarantees
* Architectural guarantees
* Data consistency guarantees

These should be concise and actionable.

---

## 16. Known Tradeoffs

Document intentional compromises:

* Performance vs simplicity
* Flexibility vs safety
* Static vs dynamic approaches
* Architectural decisions

---

## 17. Graphify Summary

Summarize insights from graphify:

* Major communities
* Highly connected nodes
* Central abstractions
* Architectural hotspots

Do not duplicate the full graph report.

---

# Output Rules

* Prefer concrete implementation details over general descriptions.
* Prefer architecture over marketing.
* Prefer actual code behavior over documentation claims.
* Use ASCII diagrams where useful.
* Include file names, classes, functions, modules, and execution paths.
* Capture repository reality, not intent.
* Write as a living repository snapshot.
* Future updates should modify sections surgically rather than rewriting the document.

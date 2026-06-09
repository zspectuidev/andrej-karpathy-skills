# Generate ABOUTREPO.md

Your task is to create a comprehensive `ABOUTREPO.md` that serves as the long-term repository memory layer for future AI agents and engineers.

This document must allow future sessions to quickly understand the repository without re-discovering architecture, code flow, design decisions, module relationships, or project structure.

The goal is NOT to create a README.

The goal is NOT to create a changelog.

The goal is NOT to create marketing documentation.

The goal is to create an accurate repository audit and implementation snapshot.

---

# Primary Objective

A future AI session should be able to read only:

* graphify-out/GRAPH_REPORT.md
* ABOUTREPO.md

and rapidly understand:

* what the project does
* how it works
* how components interact
* where functionality lives
* how data flows
* how to safely modify it

without needing to re-audit the repository from scratch.

---

# Repository Discovery Requirements

Before writing ABOUTREPO.md:

1. Recursively inspect the entire repository.
2. Traverse all source directories.
3. Analyze all major modules and packages.
4. Analyze configuration files.
5. Analyze build files.
6. Analyze deployment files.
7. Analyze infrastructure definitions.
8. Analyze CI/CD files.
9. Analyze scripts and tooling.
10. Analyze test suites.
11. Analyze entry points.
12. Analyze dependency definitions.
13. Analyze generated graphify output.
14. Trace execution flows through actual code.
15. Infer architecture primarily from implementation, not documentation.

Do NOT generate ABOUTREPO.md after inspecting only a subset of files.

Repository reality takes precedence over README files and comments.

If implementation conflicts with documentation:

* trust implementation
* document the discrepancy

---

# Documentation Philosophy

Document:

* what exists
* what is implemented
* what is observable
* what is enforced

Do NOT document:

* aspirations
* future plans
* speculative architecture
* unimplemented ideas

If something cannot be confidently determined:

* explicitly state that

Never invent architecture.

Never assume patterns that are not visible in code.

---

# Required Sections

## 1. What

Describe:

* project purpose
* primary capabilities
* intended users
* scope
* out-of-scope responsibilities

---

## 2. Why

Describe:

* problem being solved
* design goals
* key differentiators
* major architectural tradeoffs

---

## 3. Architecture

Describe:

* high-level architecture
* architectural style
* layers
* services
* subsystems
* boundaries
* responsibilities

Include ASCII diagrams where useful.

Example:

```text
CLI
  ↓
Orchestrator
  ↓
Processors
  ↓
Storage
  ↓
Outputs
```

Focus on actual implementation.

---

## 4. Module Relationships

For each major module:

* responsibility
* inputs
* outputs
* dependencies
* consumers

Show how modules interact.

Include dependency diagrams when useful.

---

## 5. Code Layout

Document repository structure.

For important directories and files:

* purpose
* responsibilities
* notable implementation details

Example:

```text
src/
├── api/
├── services/
├── storage/
└── ...
```

Explain why each exists.

---

## 6. Execution Flow

Document runtime behavior.

Examples:

* startup flow
* CLI flow
* request lifecycle
* background jobs
* processing pipelines
* event handling

Use step-by-step execution traces.

Example:

```text
main()
 → config load
 → dependency initialization
 → processing
 → output generation
```

---

## 7. Data Model

Document:

* entities
* models
* DTOs
* schemas
* database structures
* contracts

Describe how data moves through the system.

---

## 8. Tech Stack

Document:

* languages
* frameworks
* libraries
* databases
* build systems
* packaging systems
* infrastructure

Separate:

* required dependencies
* optional dependencies

---

## 9. Configuration

Document:

* config files
* environment variables
* runtime flags
* secrets management
* configuration precedence
* validation rules

Include configuration invariants.

---

## 10. Functionality Inventory

Create a complete feature inventory.

For each capability:

* name
* purpose
* entry point
* major modules involved
* outputs

This should serve as a functionality catalog.

---

## 11. Conventions

Document repository-specific conventions:

* naming conventions
* code organization patterns
* dependency rules
* plugin mechanisms
* extension patterns
* architectural rules

Include conventions that contributors must follow.

---

## 12. Deployment Model

Document:

* build process
* packaging process
* deployment targets
* runtime environments
* CI/CD
* operational assumptions

---

## 13. Outputs

Document generated artifacts:

* reports
* files
* databases
* APIs
* logs
* manifests
* side effects

Include formats and locations.

---

## 14. Extension Cookbook

Document how to add:

* new modules
* new plugins
* new integrations
* new features
* new workflows

Focus on existing extension mechanisms.

---

## 15. Key Invariants

List rules that must never be broken.

Examples:

* schema guarantees
* security guarantees
* architectural guarantees
* privacy guarantees
* compatibility guarantees

Keep these concise and actionable.

---

## 16. Known Tradeoffs

Document intentional tradeoffs:

* simplicity vs flexibility
* performance vs maintainability
* static vs dynamic behavior
* security vs usability

Only document tradeoffs visible in implementation.

---

## 17. Graphify Summary

Summarize important findings from:

graphify-out/GRAPH_REPORT.md

Include:

* major communities
* central abstractions
* highly connected nodes
* architectural hotspots

Do not duplicate the full graph report.

---

## 18. Operational Notes

Document:

* common maintenance tasks
* expected workflows
* debugging entry points
* operational assumptions

Include only information observable from the repository.

---

## 19. Coverage Report

At the end of the document include:

### Repository Coverage

Directories analyzed:

* ...

Major modules analyzed:

* ...

Configuration files analyzed:

* ...

Build/deployment files analyzed:

* ...

Tests analyzed:

* ...

Files intentionally skipped:

* ...

Documentation sources used:

* ...

### Confidence Assessment

For each major section provide:

* High confidence
* Medium confidence
* Low confidence

If a section contains inferred information, explicitly identify it.

---

# Output Quality Requirements

The generated ABOUTREPO.md must:

* be based on actual repository contents
* be based on recursive repository analysis
* be implementation-focused
* be architecture-focused
* be useful to future AI sessions
* be useful to future engineers
* contain concrete details
* contain file names
* contain module names
* contain execution flows
* contain dependency relationships
* contain extension guidance
* contain operational knowledge

Prefer:

implementation > documentation

code > comments

observed behavior > assumptions

repository reality > stated intent

---

# Success Criteria

A new AI session should be able to read ABOUTREPO.md and answer:

* What does this project do?
* How is it structured?
* Where does functionality live?
* How does data flow?
* How do I add a feature?
* What must never be broken?
* What files should I modify?
* What architecture exists today?

without needing to re-audit the entire repository.

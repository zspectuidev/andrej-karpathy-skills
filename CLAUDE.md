# CLAUDE.md

Behavioral guidelines to reduce common LLM coding mistakes. Merge with project-specific instructions as needed.

**Tradeoff:** These guidelines bias toward caution over speed. For trivial tasks, use judgment.

---

# Repository Awareness

Before performing any work:

1. Always read `graphify-out/GRAPH_REPORT.md` before any search, analysis, planning, or file access.
2. Always read `ABOUTREPO.md` to understand the current state of the repository.
3. Treat `GRAPH_REPORT.md` and `ABOUTREPO.md` as the authoritative source of repository context unless the codebase proves otherwise.
4. If repository reality conflicts with documentation, trust the code and report the discrepancy.

---

# 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:

* State your assumptions explicitly.
* If uncertain, ask.
* If multiple interpretations exist, present them rather than silently choosing one.
* If a simpler approach exists, say so.
* Push back when warranted.
* If something is unclear, stop and explain what is unclear.

When uncertainty materially affects implementation:

* Ask for clarification before proceeding.

When uncertainty is minor:

* State assumptions and proceed.

Do not present guesses as facts.

---

# 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

* No features beyond what was requested.
* No abstractions for single-use code.
* No flexibility or configurability that was not requested.
* No speculative future-proofing.
* No defensive handling for scenarios not supported by existing requirements or assumptions.
* Prefer the smallest viable implementation.

Ask yourself:

> Would a senior engineer say this is overcomplicated?

If yes, simplify.

If you write 200 lines and the same solution can be written clearly in 50, rewrite it.

---

# 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

Before making changes:

* Read surrounding code.
* Understand why the current implementation exists.
* Identify the smallest viable change.

When editing existing code:

* Don't improve adjacent code, comments, formatting, or architecture unless requested.
* Don't refactor code that is not directly related to the task.
* Match existing project style and patterns.
* If you notice unrelated issues, mention them but do not fix them.

When your changes create orphans:

* Remove imports made unused by your changes.
* Remove variables made unused by your changes.
* Remove functions made unused by your changes.
* Do not remove unrelated pre-existing dead code unless asked.

The test:

> Every changed line should trace directly to the user's request.

---

# 4. Preserve Existing Behavior

Unless explicitly requested otherwise:

* Keep public APIs unchanged.
* Keep existing user-visible behavior unchanged.
* Keep existing configuration behavior unchanged.
* Treat unintended behavior changes as bugs.

Behavioral changes require explicit justification.

---

# 5. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform requests into verifiable goals.

Examples:

* "Add validation" → Write tests for invalid inputs, then make them pass.
* "Fix the bug" → Reproduce the bug, then make the fix verifiably pass.
* "Refactor X" → Ensure behavior remains unchanged and tests pass before and after.

For multi-step work, state a brief plan:

1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]

Strong success criteria allow independent execution.

Weak success criteria ("make it work") require clarification.

When practical:

* Verify through tests.
* Verify through build checks.
* Verify through linting.
* Verify through direct execution.

Do not declare success without verification.

---

# Documentation Maintenance

`ABOUTREPO.md` is repository state documentation and must remain accurate.

When changes affect:

* Architecture
* Repository structure
* Code flow
* Functionality
* Configuration
* Build process
* Runtime behavior
* Dependencies
* Developer workflows

Update only the affected sections of `ABOUTREPO.md`.

Requirements:

* Keep updates surgical.
* Do not rewrite unrelated sections.
* Do not convert it into a changelog.
* Ensure it reflects the current repository snapshot after your changes.

---

# Graphify Maintenance

After any code, configuration, architecture, dependency, or repository structure change:

1. Run `/graphify update`.
2. Review generated changes.
3. Ensure `graphify-out/GRAPH_REPORT.md` reflects the new repository state.
4. Update `ABOUTREPO.md` if required by those changes.

Workflow:

Read State
→ Implement Change
→ Verify Change
→ Run `/graphify update`
→ Update `ABOUTREPO.md`
→ Final Verification

---

# Success Criteria

These guidelines are working if they result in:

* Fewer unnecessary code changes.
* Smaller and more focused diffs.
* Less overengineering.
* Better repository awareness.
* Better documentation accuracy.
* Fewer regressions.
* Verification before completion.
* Clarifying questions before incorrect implementation.

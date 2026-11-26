# FOX Roadmap

**Status:** Proposed roadmap. Dates and release milestones are not commitments.

## Phase 0 — Design foundation

- [ ] Define language goals and non-goals.
- [ ] Specify syntax and grammar.
- [ ] Specify static type system.
- [ ] Specify numeric and evaluation semantics.
- [ ] Specify memory and concurrency models.
- [ ] Record unresolved design decisions.

## Phase 1 — Frontend prototype

- [ ] Lexer.
- [ ] Parser.
- [ ] AST.
- [ ] Name resolution.
- [ ] Basic type checking.
- [ ] Diagnostics and source locations.
- [ ] Initial HIR.

**Exit criterion:** parse and type-check a small, documented subset of FOX programs.

## Phase 2 — Native compilation

- [ ] Define MIR.
- [ ] Generate LLVM IR.
- [ ] Link executable programs.
- [ ] Add basic standard runtime support.
- [ ] Add automated compiler tests.
- [ ] Establish reproducible build instructions.

**Exit criterion:** compile and run small FOX programs on the first supported host platform.

## Phase 3 — EVOLVE foundation

- [ ] Source and semantic analysis.
- [ ] Conservative optimization proposals.
- [ ] Proposal IDs and metadata.
- [ ] Review, approve and reject workflow.
- [ ] Separate `.evolved.fox` output.
- [ ] Source comparison and patch history.

**Exit criterion:** propose, review and emit a small set of semantics-preserving transformations.

## Phase 4 — PROOF and testing

- [ ] Transformation validation framework.
- [ ] Differential testing.
- [ ] Property-based testing.
- [ ] Static safety checks.
- [ ] Explicit verification status reporting.
- [ ] Test corpus for edge cases.

**Exit criterion:** each supported transformation has documented correctness conditions and automated tests.

## Phase 5 — Deep optimization

- [ ] Loop transformations.
- [ ] Escape and lifetime analysis.
- [ ] Copy and allocation elimination.
- [ ] Function specialization.
- [ ] Algorithmic optimization research.
- [ ] Parallelization analysis.
- [ ] Profile-guided optimization.

**Exit criterion:** each optimization is individually benchmarked and enabled only when its preconditions are met.

## Phase 6 — EVOLVE LAB

- [ ] Generate alternative implementations.
- [ ] Bound search time and resource usage.
- [ ] Verify candidates.
- [ ] Benchmark candidates reproducibly.
- [ ] Present trade-offs to developers.

## Phase 7 — Developer ecosystem

- [ ] Package manager.
- [ ] Formatter.
- [ ] Test runner.
- [ ] Debugger.
- [ ] Language Server Protocol support.
- [ ] Documentation generator.
- [ ] Initial standard library.

## Phase 8 — Preview and stabilization

- [ ] Cross-platform testing.
- [ ] Security review.
- [ ] Public benchmark suite.
- [ ] Documentation audit.
- [ ] Compatibility policy.
- [ ] Community preview.
- [ ] Stable release criteria.

## Guiding rule

Correctness and safety come before optimization. Performance claims require reproducible evidence.

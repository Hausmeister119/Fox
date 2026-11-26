# FOX — Language & Platform Specification

**Status:** Draft / design baseline  
**Version:** 0.1.0  
**Last updated:** 2026-11-25

This document records the current design direction. It is not a claim that the features have been implemented. Decisions may change as prototypes, benchmarks and security reviews provide evidence.

## 1. Design goals

1. Native performance through ahead-of-time compilation.
2. Strong safety guarantees in safe code.
3. Readable, Python-inspired syntax.
4. Static typing with useful type inference.
5. General-purpose applicability.
6. Developer-controlled source optimization.
7. Reproducible builds and transparent tooling.

## 2. Language model

FOX is intended to be a statically typed, general-purpose language. The initial syntax direction uses indentation-based blocks and explicit function signatures where useful.

Illustrative example:

```fox
fn add(a: Int, b: Int) -> Int:
    return a + b

fn main():
    print(add(20, 22))
```

The formal grammar, integer overflow rules, evaluation order, error model and module semantics remain to be specified.

## 3. Type system

Planned capabilities:

- Static type checking.
- Local type inference.
- Structs and enums.
- Generic types and functions.
- Pattern matching.
- Explicit mutability rules.
- Well-defined numeric types and conversions.

The specification must define implicit conversions narrowly to avoid surprising behavior.

## 4. Memory and safety

FOX aims for memory safety in safe code without requiring a traditional tracing garbage collector. The proposed direction is ownership and borrowing with compiler-assisted inference.

See [Memory Model](docs/memory-model.md).

## 5. Concurrency

Planned design areas:

- Structured concurrency.
- Tasks and threads.
- Message passing.
- Safe shared state.
- Data-race prevention.
- SIMD and parallel iteration.

The concurrency model must integrate with ownership and the memory model.

## 6. Compilation

Planned pipeline:

```text
Source -> Lexer/Parser -> AST -> Semantic Analysis
       -> HIR -> (EVOLVE review) -> MIR
       -> LLVM IR -> Native executable
```

FOX will initially investigate LLVM as its code-generation backend. HIR and MIR are proposed FOX-owned representations.

See [Compiler Architecture](docs/compiler-architecture.md).

## 7. Optimization policy

Compiler optimizations must preserve the language's specified observable behavior. The specification must define:

- Integer overflow behavior.
- Floating-point and rounding semantics.
- Evaluation order.
- Side-effect rules.
- Aliasing and mutation.
- Concurrency and memory-ordering rules.
- Unsafe operation boundaries.

FOX EVOLVE source transformations require separate review and verification. Backend optimizations remain a distinct compiler stage.

## 8. EVOLVE policy

- Original source files are never overwritten by default.
- Approved transformations are emitted to separate files.
- Each proposal records its source revision and transformation details.
- Correctness status and performance measurements are reported separately.
- A measured speedup must not be inferred from static analysis alone.

See [FOX EVOLVE Engine](docs/evolve-engine.md).

## 9. Targets

Initial target candidates:

- x86_64
- AArch64
- WebAssembly (later milestone)

Target support will be prioritized based on available toolchains, testing infrastructure and contributor capacity.

## 10. Open design questions

These must be resolved before the language can be considered stable:

- Exact grammar and indentation rules.
- Numeric types and overflow semantics.
- Error handling and exception policy.
- Ownership and borrowing details.
- Generic constraints and trait/interface model.
- Async and concurrency semantics.
- Module and package resolution.
- ABI and foreign-function interface.
- Standard library scope.
- Unsafe code and verification boundaries.

## 11. Compatibility policy

Until a stable language release exists, syntax and semantics may change. Once a stable release is declared, compatibility rules and a formal versioning policy should be published.

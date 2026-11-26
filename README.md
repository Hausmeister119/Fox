[README.md](https://github.com/user-attachments/files/35439097/README.md)
# FOX

<p align="center">
  <strong>A new generation of programming languages.</strong><br>
  <em>Fast. Safe. Effortless.</em>
</p>

FOX is an ambitious, general-purpose programming language project. It aims to combine native performance, strong safety guarantees, readable syntax and an ecosystem that can support many kinds of software.

> **Project status:** Early design stage. The language, compiler and tools described here are planned features, not yet implemented or benchmark-verified.

## Vision

- **Performance:** native compilation and advanced optimization.
- **Safety:** static typing, memory safety and safe concurrency.
- **Simplicity:** a readable, Python-inspired syntax.
- **Universality:** systems software, applications, AI, web services, embedded software and more.
- **Developer experience:** modern tooling and developer-controlled optimization.

## A first look

```fox
fn main():
    let name: String = "FOX"
    print("Hello, ${name}!")
```

The syntax shown here is illustrative. The formal grammar will be defined in the language specification.

## What makes FOX different?

### FOX EVOLVE

An opt-in source optimization system that analyzes FOX code, proposes transformations and lets developers review them before applying them to separate `.evolved.fox` files.

EVOLVE will provide two modes:

- **Conservative:** localized, structure-preserving changes.
- **Deep:** broader transformations, including algorithmic and parallelization opportunities where correctness can be established.

### FOX PROOF

A verification subsystem intended to check transformation correctness and safety properties. Reports will distinguish formal proofs, static checks, tests and unverified assumptions.

### FOX NATIVE

The native compilation pipeline. FOX plans to use LLVM as its initial backend while keeping its frontend and intermediate representations independent.

## Architecture at a glance

```text
FOX source
   |
   v
Frontend -> AST -> HIR
                  |
                  v
             FOX EVOLVE
                  |
                  v
              FOX PROOF
                  |
                  v
       reviewed .evolved.fox
                  |
                  v
             FOX MIR
                  |
                  v
               LLVM
                  |
                  v
          Native executable
```

## Project documentation

| Document | Description |
|---|---|
| [Language design](docs/language-design.md) | Syntax, types, modules and language principles |
| [Compiler architecture](docs/compiler-architecture.md) | Frontend, HIR, MIR, LLVM and build pipeline |
| [Memory model](docs/memory-model.md) | Ownership, borrowing, lifetimes and safety goals |
| [FOX EVOLVE](docs/evolve-engine.md) | Optimization modes, proposals, verification and file format |
| [Full specification](SPECIFICATION.md) | Current design requirements and open decisions |
| [Roadmap](ROADMAP.md) | Planned development phases |
| [Contributing](CONTRIBUTING.md) | How to participate |

## Development status

FOX is currently a design project. No claim is made that it is already faster or safer than C, C++ or Rust. Those are long-term goals that must be evaluated through public, reproducible tests and benchmarks.

## Getting involved

The project will welcome discussion and contributions as the language specification and implementation take shape. See [CONTRIBUTING.md](CONTRIBUTING.md) for the proposed contribution process.

---

**FOX — Write simple code. Build powerful software.**

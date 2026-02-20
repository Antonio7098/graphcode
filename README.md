# Graphcode

> The filesystem is an implementation detail.
> The dependency graph is the real structure.

---

## The Thesis

Modern software pretends that:

* Files are primary
* Folders define architecture
* Imports define relationships

But in reality:

* **Symbols depend on symbols**
* **Behaviors depend on behaviors**
* **Types constrain edges**
* **Architecture is directionality**

Files are packaging.

The true structure of a system is its **dependency graph**.

Graphcode proposes a simple but radical inversion:

> Make the semantic dependency graph the canonical representation of software.
> Treat files as projections.

---

## Why This Exists

Today, the workflow looks like this:

Human → edits text → compiler → builds graph internally → discards graph.

The semantic structure is created, optimized, and thrown away.

Graphcode flips the pipeline:

Human/Agent → edits graph → system → emits deterministic text projections.

The graph becomes the source of truth.
The filesystem becomes an artifact.

---

## What This Means

Instead of:

```text
edit src/application/login.rs lines 42–98
```

You would:

```text
edit symbol auth::LoginService::validate_credentials
```

Instead of:

```text
import utils/date.ts
```

You would:

```text
add edge from OrderService → DateUtils
```

Instead of refactoring folders, you would:

```text
re-partition subgraph into new bounded context
```

Programming becomes **graph transformation**.

---

## Core Principles

### 1. Architecture Is Directionality

Layering is not convention.
It is a constraint system over edges.

Example:

* Forbid edges from `domain → infrastructure`
* Enforce acyclic subgraphs
* Enforce bounded contexts as partitions

Architecture becomes enforceable, not aspirational.

---

### 2. Refactoring Is Structural

Rename a symbol → change a node property.
Move functionality → reattach a node.
Split a module → partition a subgraph.

Text updates are projections, not manual edits.

---

### 3. Files Are Projections

The filesystem is preserved for:

* Compiler compatibility
* Build tooling
* Git integration
* Human familiarity

But it is no longer canonical.

Graph → deterministic pretty-printer → files.

Not the other way around.

---

### 4. Context Is Subgraph Selection

AI systems and static tooling don’t “search files.”
They traverse adjacency.

Context window = selected subgraph.
Refactor scope = induced subgraph.
Review diff = edge delta.

---

## What This Enables

If the graph is canonical:

* Architecture constraints become first-class
* Cross-language systems share one structural model
* Refactors become safe structural rewrites
* Merge conflicts become graph conflicts
* PR review becomes topology diffs
* Observability can map to semantic structure
* Agents operate over structure, not text

This aligns software representation with how compilers and AI systems already reason.

---

## Not a Text Editor Replacement

Graphcode does not eliminate files.

It demotes them.

Compilers expect files.
Build tools expect directories.
Git expects line diffs.

Graphcode integrates with the existing ecosystem while shifting authority upward to the semantic layer.

Evolutionary compatibility.
Revolutionary abstraction.

---

## The Long-Term Vision

Graphcode aims to become:

* A semantic source-of-truth layer for codebases
* A graph-native refactoring engine
* A constraint-driven architecture enforcement system
* A topology-aware diff and merge model
* A graph-first interface for human and AI collaboration

Not just better navigation.

A different programming model.

---

## Open Questions

* Should Git operate on graph diffs?
* Can architecture constraints be declared declaratively?
* How should multi-language graphs be unified?
* What is the minimal viable projection engine?
* How do humans interact with a graph-first system?

These are research questions as much as engineering problems.

---

## Status

Graphcode is a vision and exploration of a graph-native programming paradigm.

It challenges the assumption that text files are the fundamental unit of software.

They are not.

The graph is.

---

If software is fundamentally relational,
its primary representation should be relational.

Graphcode begins there.

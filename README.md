# personal-os

Version-controlled specification for how I operate my personal engineering environment.

## Scope

`personal-os` defines cross-tool conventions, workflows, interfaces, and architectural decisions.

It does not own implementation-specific configuration.

```text
intent
  ↓
convention / workflow
  ↓
interface
  ↓
implementation
```

## Ownership

```text
personal-os          operating model and conventions
dotfiles             workstation configuration
personal-automation  scripts and automation primitives
forge-cli            capture, review, and query tooling
personal-cloud       services and infrastructure
```

Do not duplicate implementation here. Link to the owning repository where useful.

## What belongs here

* shortcut conventions
* naming conventions
* filesystem conventions
* Git conventions
* command/interface semantics
* capture and review workflows
* writing workflows
* development workflows
* cross-tool behaviour
* architectural decisions

## What does not belong here

* dotfiles
* application config
* scripts
* source code
* Docker Compose files
* machine provisioning
* Stream Deck profiles
* secrets

## Principles

### Intent before implementation

Define the behaviour before choosing the tool.

### One source of truth

Specification lives here. Implementation lives with its owner.

### Usage earns structure

Do not create abstractions for hypothetical requirements.

### Stable vocabulary

Use the same terms for the same concepts across tools.

Examples:

```text
OPEN
SEARCH
CAPTURE
REVIEW
MOVE
BUILD
```

### Prefer native conventions

Do not override established platform behaviour without a clear benefit.

### Automate proven workflows

Run manually until the workflow is understood and stable.

### Prefer reversible decisions

Keep uncertain choices cheap to change.

## Structure

Initial:

```text
personal-os/
├── README.md
├── conventions/
│   └── shortcuts.md
└── workflows/
    └── README.md
```

Add only when needed:

```text
interfaces/
architecture/
decisions/
```

## Conventions

Define reusable behaviour across tools.

Each convention should capture:

```text
intent
rule
rationale
implementation references
```

## Workflows

Define repeatable operating sequences.

Examples:

```text
capture → review → decide → act / retain / discard

seed → develop → draft → publish

observe friction → capture → review → automate
```

## Interfaces

Interfaces expose capabilities.

Examples:

```text
CLI
Stream Deck
Raycast
Obsidian
editor shortcuts
```

Different interfaces may implement the same intent differently.

Optimise for semantic consistency, not identical mechanics.

## Decisions

Use lightweight ADRs for decisions that are:

* cross-cutting
* expensive to reverse
* likely to be revisited

Do not ADR trivial or easily reversible choices.

## Evolution

```text
use
  ↓
observe friction or inconsistency
  ↓
capture
  ↓
review
  ↓
define or refine
  ↓
implement
  ↓
repeat
```


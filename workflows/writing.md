# Writing Workflow

Defines the operating workflow for developing and publishing written material.

## Goals

* Capture ideas with minimal friction.
* Separate idea generation from drafting.
* Promote only ideas with enough signal.
* Keep drafts in version control.
* Preserve a clear lifecycle from seed to publication.
* Avoid accumulating unreviewed or permanently half-finished work.

## Canonical stages

```text
seed
  ↓
grow
  ↓
draft
  ↓
review
  ↓
publish
  ↓
archive
```

Current repository structure:

```text
writing/
├── 0-Seeds/
├── 1-Growing/
├── 2-Drafts/
└── 3-Published/
```

Stage is represented by location.

Do not duplicate the same piece across stages.

---

## Seed

Location:

```text
0-Seeds/
```

Purpose:

Capture an idea before it is lost.

A seed should be cheap to create and incomplete by design.

Typical structure:

```text
Trigger
Thesis
Sparks
Stories
Related
```

### Trigger

What caused the idea.

Examples:

* observed behaviour
* repeated engineering problem
* conversation
* frustration
* decision
* experience
* unexpected result

### Thesis

The central claim or useful idea.

Prefer one sentence.

### Sparks

Supporting thoughts, fragments, arguments, analogies, questions, or possible sections.

### Stories

Concrete experiences or examples that may support the thesis.

### Related

Connections to:

* previous writing
* future writing
* external concepts
* recurring themes

### Promotion criteria

Move to `1-Growing/` when:

* the thesis remains interesting after capture
* additional ideas continue accumulating
* there is enough substance to justify development

Kill or leave dormant if the idea does not develop.

Do not draft weak ideas solely because they were captured.

---

## Growing

Location:

```text
1-Growing/
```

Purpose:

Develop the thinking before committing to a full draft.

Typical activity:

* clarify thesis
* collect examples
* test counterarguments
* add supporting evidence
* identify structure
* connect related ideas
* remove weak branches

A growing note does not need polished prose.

Optimise for thinking quality, not readability.

### Promotion criteria

Move to `2-Drafts/` when:

* thesis is clear
* argument has enough support
* likely structure is visible
* there is a useful conclusion
* drafting is now cheaper than further note accumulation

If the core argument weakens during development:

```text
merge
archive
return to seed
discard
```

Do not force promotion.

---

## Draft

Location:

```text
2-Drafts/
```

Purpose:

Turn developed thinking into publication-quality prose.

Primary writing environment:

```text
Markdown
Git
Typora
```

A draft should have a clear:

```text
opening
thesis
argument
evidence/examples
conclusion
```

Prefer:

* direct language
* concrete claims
* first-hand examples where useful
* strong structure
* short paragraphs
* explicit reasoning
* useful abstractions
* practical implications

Avoid:

* generic advice
* filler introductions
* repeated conclusions
* unnecessary headings
* inflated language
* writing that sounds more certain than the evidence supports
* content added only to increase length

## Voice

Default style:

```text
direct
technical where useful
reflective where earned
specific
low-fluff
judgement-oriented
systems-oriented
```

Prefer explaining:

```text
why
trade-offs
failure modes
second-order effects
```

over merely explaining:

```text
what
```

The objective is not to sound authoritative.

The objective is to demonstrate clear reasoning.

---

## Review

Review before publication.

### Content review

Check:

* Is the thesis obvious?
* Is the piece saying something non-trivial?
* Is every section supporting the thesis?
* Are claims backed by evidence or clearly framed as judgement?
* Are examples concrete?
* Are counterarguments or trade-offs missing?
* Is anything repetitive?
* Is anything present only because it sounds good?
* Can sections be removed without losing value?

### Voice review

Check:

* Does this sound like me?
* Is the language direct?
* Is jargon earning its place?
* Are abstractions grounded in real examples?
* Is the tone overly polished or generic?
* Has AI-generated phrasing survived unnecessarily?

### Structural review

Check:

```text
title
description
opening
section order
transitions
ending
metadata
links
```

### Compression pass

Remove:

* redundant qualifiers
* repeated arguments
* filler sentences
* unnecessary scene-setting
* generic conclusions
* duplicated examples

Prefer shorter unless additional detail materially improves the argument.

---

## Metadata

Published posts use frontmatter similar to:

```yaml
---
title: ""
description: ""
slug: ""
pubDate: YYYY-MM-DD
modDate: YYYY-MM-DD
draft: false

category: engineering

tags:
  - tag-1
  - tag-2
---
```

Before publishing verify:

```text
title
description
slug
dates
category
tags
draft=false
```

Do not allow metadata work to become a reason to delay publication.

---

## Publish

Canonical flow:

```text
2-Drafts/
  ↓
final review
  ↓
move to 3-Published/
  ↓
commit
  ↓
push
  ↓
GitHub Actions
  ↓
blog repository
  ↓
site deployment
  ↓
verify
```

Publishing is automated through GitHub Actions.

The `writing` repository remains the source of writing content.

The blog repository owns site implementation and deployment.

Do not manually maintain duplicate post content between repositories.

---

## Post-publish verification

After deployment verify:

* page renders
* title is correct
* description is correct
* formatting is intact
* links work
* code blocks render correctly
* metadata/date is correct
* mobile layout is acceptable

Fix publishing defects immediately.

Minor prose improvements can wait for a later edit.

---

## Promotion

Promotion is optional.

Potential channels:

```text
LinkedIn
direct sharing
future internal references
related blog posts
```

Do not optimise the writing itself for social media distribution.

Write the durable article first.

Promotion should point to the article, not distort it.

---

## Editing published work

Published content may be updated when:

* facts change
* errors are found
* wording materially improves
* a new insight strengthens the argument
* links or references break

Update:

```text
modDate
```

when making meaningful changes.

Do not continuously polish published work without a clear benefit.

Prefer writing the next useful piece.

---

## Linking

Prefer explicit links between related posts when they improve context.

Use previous writing as:

* prerequisite context
* supporting argument
* contrast
* continuation
* evidence of evolving thinking

Avoid forced internal linking.

---

## Series

Use a series when multiple posts share a clear larger problem but remain independently useful.

Example:

```text
Securing GitHub Actions Within an Enterprise
```

A series should:

* have a clear scope
* avoid repeating introductory material
* allow individual posts to stand alone
* deepen the topic progressively

Do not declare a series before enough material exists.

---

## Idea sources

Common inputs:

```text
engineering work
personal projects
friction
technical decisions
operating principles
career observations
system design
security
developer experience
automation
personal infrastructure
AI-assisted engineering
```

Repeated explanations are strong writing candidates.

Repeated friction is strong writing material when it exposes a broader system problem.

---

## AI usage

AI may assist with:

* critique
* structure
* counterarguments
* compression
* title generation
* description generation
* gap analysis
* editing
* research support

AI should not own:

```text
thesis
judgement
experience
claims presented as personal insight
```

Treat AI as:

```text
editor
reviewer
sparring partner
research assistant
```

not the authorial source.

Remove generic AI phrasing during review.

---

## Stop conditions

Do not continue developing a piece because effort has already been invested.

Stop when:

* thesis is weak
* argument is derivative
* evidence is insufficient
* another post already covers the point
* the idea is better merged elsewhere
* interest has disappeared
* the piece no longer provides useful signal

Valid outcomes:

```text
publish
merge
archive
discard
```

Not every seed needs to become a post.

---

## Operating rules

```text
capture quickly
develop slowly
draft when the argument is ready
review aggressively
publish once useful
verify deployment
move on
```

Prefer a body of durable work over a backlog of permanently unfinished drafts.


# Shortcuts

Canonical keyboard shortcut conventions for `personal-os`.

## Principles

* Prefer semantic consistency across applications.
* Preserve platform-native shortcuts where sensible.
* Reserve premium shortcuts for high-frequency operations.
* Promote commands to shortcuts only after repeated use proves value.
* Prefer intent-based bindings over plugin-specific bindings.
* Avoid duplicate meanings for the same shortcut.

## Core vocabulary

| Intent  | Binding          | Meaning                        |
| ------- | ---------------- | ------------------------------ |
| OPEN    | `Cmd+O`          | Open or navigate to an object  |
| SEARCH  | `Cmd+Shift+F`    | Search globally                |
| COMMAND | `Cmd+Shift+P`    | Command palette / escape hatch |
| CREATE  | `Cmd+N`          | Create new object              |
| MOVE    | `Option+Up/Down` | Reorder current object         |
| CAPTURE | `Ctrl+Option+C`  | Capture new input              |
| REVIEW  | `Ctrl+Option+R`  | Open review workflow           |

Platform equivalents may replace `Cmd` with `Ctrl`.

---

# Obsidian

## Navigation

| Action                     | Binding           |
| -------------------------- | ----------------- |
| Quick switcher             | `Cmd+O`           |
| Command palette            | `Cmd+Shift+P`     |
| Global search              | `Cmd+Shift+F`     |
| New note                   | `Cmd+N`           |
| New note from template     | `Cmd+Shift+N`     |
| Open daily note            | `Cmd+D`           |
| Toggle edit / reading view | `Cmd+E`           |
| Open link under cursor     | `Cmd+Enter`       |
| Open link in new tab       | `Cmd+Shift+Enter` |
| Close tab                  | `Cmd+W`           |
| Reopen closed tab          | `Cmd+Shift+T`     |
| Navigate back              | `Cmd+[`           |
| Navigate forward           | `Cmd+]`           |
| Move current note          | `Cmd+Shift+M`     |

## Editing

| Action                 | Binding             |
| ---------------------- | ------------------- |
| Move line up           | `Option+Up`         |
| Move line down         | `Option+Down`       |
| Duplicate line         | `Option+Shift+Down` |
| Delete line            | `Cmd+Shift+K`       |
| Select line            | `Cmd+L`             |
| Indent                 | `Tab`               |
| Outdent                | `Shift+Tab`         |
| Toggle checkbox        | `Cmd+Enter`         |
| Find / replace in note | `Cmd+Option+F`      |
| Delete previous word   | `Option+Backspace`  |
| Move one word left     | `Option+Left`       |
| Move one word right    | `Option+Right`      |

## Folding

| Action                      | Binding        |
| --------------------------- | -------------- |
| Toggle fold current section | `Option+[`     |
| Fold more                   | `Option+Left`  |
| Fold less                   | `Option+Right` |
| Fold all headings / lists   | `Cmd+Option+[` |
| Unfold all headings / lists | `Cmd+Option+]` |

### Conflict

`Option+Left/Right` is also useful for native word navigation.

Do not assign both behaviours simultaneously.

Preferred resolution:

```text
word navigation      Option+Left/Right
fold current         Option+[
fold all             Cmd+Option+[
unfold all           Cmd+Option+]
```

Assign alternative bindings for `Fold more` / `Fold less` only if progressive folding proves useful.

## Capture and review

Reserved semantic bindings:

| Intent  | Binding         |
| ------- | --------------- |
| Capture | `Ctrl+Option+C` |
| Review  | `Ctrl+Option+R` |

Implementation may use:

* Obsidian command
* template
* QuickAdd
* Obsidian URI
* Forge
* external automation

The binding represents the intent. The implementation may change.

## UI

Low-priority candidate bindings:

| Action               | Binding       |
| -------------------- | ------------- |
| Toggle left sidebar  | `Cmd+Shift+[` |
| Toggle right sidebar | `Cmd+Shift+]` |

Do not reserve these bindings if they conflict with higher-value editing or navigation commands.

## Priority set

Memorise first:

```text
Cmd+O                  open
Cmd+Shift+F            search
Cmd+Shift+P            command palette
Cmd+N                  new note

Option+Up/Down         move line
Tab / Shift+Tab        indent / outdent

Option+[               toggle fold
Cmd+Option+[           fold all
Cmd+Option+]           unfold all

Cmd+[ / Cmd+]          back / forward
```

Everything else remains command-palette accessible until repeated use justifies a dedicated binding.

## Structural editing

Line movement handles simple reordering.

Moving an entire heading subtree is a separate operation:

```markdown
## Architecture

content

### Components

content
```

A future heading/outliner extension may be justified if moving complete heading sections becomes frequent.

Do not add a plugin solely to provide speculative functionality.


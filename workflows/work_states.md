# Work States

Work states will use Rectangle Pro layouts for window arrangement, with Raycast and Stream Deck as launch surfaces.

Work states are still emerging. Document concrete states here only once they become repeated and useful.

## Architecture

```text
Raycast / Stream Deck
        ↓
Rectangle Pro deep link
        ↓
Saved Rectangle Pro layout
```

Rectangle Pro owns window layout.

Raycast and Stream Deck trigger the layout.

## Rectangle Pro

Invoke a saved layout using:

```text
rectangle-pro://execute-layout?name=<LAYOUT>
```

Example:

```text
rectangle-pro://execute-layout?name=Writing
```

## Raycast

Create one Quicklink per work state.

Naming:

```text
State: <Name>
```

Target:

```text
rectangle-pro://execute-layout?name=<LAYOUT>
```

Example:

```text
State: Writing
→ rectangle-pro://execute-layout?name=Writing
```

## Stream Deck

Use Stream Deck as an additional physical launcher.

Preferred path:

```text
Stream Deck
    ↓
Raycast command / Quicklink
    ↓
Rectangle Pro
```

Avoid duplicating layout logic in Stream Deck.

## Future Orchestration

If a work state later requires more than window placement:

```text
Raycast / Stream Deck
        ↓
personal-automation
        ↓
Rectangle Pro + other setup
```

Use `personal-automation` only when activation needs additional behaviour such as launching apps, opening documents, or configuring other environment state.

## Work States

Add validated work states here as they emerge.


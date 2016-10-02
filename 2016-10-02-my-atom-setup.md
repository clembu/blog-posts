---
title: My Atom setup
tags:
  - meta
  - atom
  - setup
---
# Atom is awesome.

Right now I'm typing, and the screen is shaking at each press on a key, with particles flying everywhere.

It's fun 5 minutes, but I'm getting tired of it, so I'll disable it with `ctrl+alt+o`, and uninstall the package.

There. It's gone.

---
# Installed packages

## The Bare necessities

### building blocks
These are packages kind of every atom user I know has installed. It's simply unpleasant without them.

-   [minimap](https://atom.io/packages/minimap) gives you a bird's view of your file
-   [linter](https://atom.io/packages/linter) tells you when you mess things up
-   [pigments](https://atom.io/packages/pigments) tells you that `#000000` is black and `#ffffff` is white
-   [tool bar](https://atom.io/packages/tool-bar) gives you a side-bar swiss-army knife
-   [highlight selected](https://atom.io/packages/highlight-selected) highlights clones of your words so that you know when you repeat yourself
-   [tabs to spaces](https://atom.io/packages/tabs-to-spaces) because not every parser understand whitespaces the way you do
-   [unicode input](https://atom.io/packages/unicode-input) for all those `―` and `㙔` and `đ`

Only two of them work fine out of the box though. So you gotta give them some flavor:

### Minimap plugins

-   [minimap git diff](https://atom.io/packages/minimap-git-diff) for git overviewing
-   [minimap pigments](https://atom.io/packages/minimap-pigments) because having them on the editor is not enough
-   [minimap bookmarks](https://atom.io/packages/minimap-bookmarks) for reference
-   [minimap cursor line](https://atom.io/packages/minimap-cursorline) because knowing where you are on a map is always a good thing
-   [minimap highlight selected](https://atom.io/packages/minimap-highlight-selected) if you want to track your clones down
-   [minimap linter](https://atom.io/packages/minimap-linter) to know where you're wrong
-   [minimap selection](https://atom.io/packages/minimap-selection) extension of the cursor line one.
-   [minimap code glance](https://atom.io/packages/minimap-codeglance) no need to jump 1000 lines for a glance, take a peek.

### Linter flavors

-   [markdown](https://atom.io/packages/linter-markdown)
-   [html](https://atom.io/packages/linter-htmlhint)

### Tool bar config

This one, ideally I'd do it myself when I have time. Until then I installed [@jeselxe's toolbar](https://atom.io/packages/tool-bar-atom) for common actions.

## Some more useful stuff

These are not essential to editing, but they are useful.
-   imdone, [core](https://atom.io/packages/imdone-atom) and [github](https://atom.io/packages/imdone-atom-github), to manage tasks and issues from atom.
-   [docblockr](https://atom.io/packages/docblockr) helps create documentation comment blocs.
-   [project manager](https://atom.io/packages/project-manager) I don't use often, but can help remind you what's on your machine that needs a check up.

## Git stuff

When you're blogging on github, you'd better have some git utilities. Atom gives you a nice git integration, but that's read-only.

-   [git+](https://atom.io/packages/git-plus) allows to easily run git commands. I have yet to setup some keystrokes though.
-   [time machine](https://atom.io/packages/git-time-machine) is a fancy little timeline showing you the git activity on the file you're currently working on.

## languages support

Atom supports a lot of languages out of the box. I only added [react's jsx](https://atom.io/packages/react) for working with [ReactJS](https://facebook.github.io/react/).

## Pretty code is pretty

I never found any theme better than Seti. That means both [UI](https://atom.io/themes/seti-ui) and [Syntax](https://atom.io/themes/seti-syntax). They're just a visual orgasm to me.

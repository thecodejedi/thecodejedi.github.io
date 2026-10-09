---
layout: post
title: "Keep track of what container you are using with Konsole's Context Awareness feature"
date: 2026-10-09
---

You know the moment. You open a terminal, enter your Distrobox dev container, install a few packages, tweak some configs - and then, half an hour later, you type `sudo dnf update` and realize with a sinking feeling that this tab was never a container. It was your host. All along.

If you juggle host sessions and dev containers (Distrobox, Toolbox, Kapsule) in Konsole, you have probably lived this moment more than once. Terminals all look the same - black background, blinking cursor - and nothing tells you where your keystrokes are actually landing. Split views make it worse: with two or three panes side by side, "wait, which pane am I typing in?" becomes a real question.

## Konsole now tells you

Konsole 26.08, released as part of KDE Gear 26.08, comes with a new feature called Container Context Awareness ([merge request !1186](https://invent.kde.org/utilities/konsole/-/merge_requests/1186)), and it makes your surroundings visible at a glance:

- **Automatic detection.** Konsole detects whether a session is running on your host or inside a dev container - Distrobox, Toolbox and Kapsule are supported - with no configuration needed.
- **Color-coded tabs.** Tabs running inside a container get a color derived from that container, so container sessions stand out from host sessions immediately.
- **A badge in every pane.** Each split pane shows a small footer badge with the container type and name, e.g. `Distrobox: fedora-dev`. The active container also shows up in the window title, so you can see it in Alt+Tab, too.

Because the badge lives in each pane, a split layout tells the truth: every pane shows its own context, so you always know where your keystrokes are going. The tab color is stable, too - it doesn't flip when you move focus between panes, and if the panes run different containers, the tab stays uncolored instead of showing a misleading color.

<!-- SCREENSHOT 1: tabs with container-derived colors - save as images/konsole-container-tabs.png -->
![Tabs with container-derived colors - host tabs stay neutral, container tabs are colored](/images/konsole-container-tabs.png)

<!-- SCREENSHOT 2: split panes each showing their own footer badge - save as images/konsole-split-badges.png -->
![Split panes, each showing its own container badge in the footer](/images/konsole-split-badges.png)

<!-- SCREENSHOT 3: 2x2 split mixing host and container panes - save as images/konsole-2x2-split.png -->
![A 2x2 split mixing host and container panes](/images/konsole-2x2-split.png)

## Try it

The feature is already released: it shipped in Konsole 26.08 as part of KDE Gear 26.08 and works out of the box. Update, open a container session - and the next time you reach for `sudo dnf install`, the badge at the bottom of the pane will tell you whether you are about to do it on your host or inside your container.

Feedback and ideas are welcome on the [merge request](https://invent.kde.org/utilities/konsole/-/merge_requests/1186).

- Markus (oberfreak on Invent)

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a personal knowledge base of deep learning paper notes, focused on robotics and dexterous manipulation (recent years) and computer vision / object detection (earlier years). There is no build system, tests, or executable code — it is a pure Markdown documentation repository.

## Repository Structure

- `papers/` — Individual paper notes, one `.md` file per paper (or per paper series)
- `lectures/` — Notes on talks and lectures
- `classic/` — Notes on classic RL papers (DQN, policy gradient)
- `QuickScaned/` — Brief notes on papers that were only skimmed
- `img/` — Images referenced in notes
- `README.md` — Chronological reading list (most recent at top), organized by date read
- `Categorized.md` — Index of notes organized by field/topic
- `Chronologized.md` — Alternative chronological index
- `Abbreviations.md` — Domain abbreviation reference
- `ToLearn.md` — Reading backlog and resources to study later
- `paper_template.md` — Template for new paper notes

## Note Format

New paper notes follow the template in `paper_template.md`:

```markdown
[Title](arxiv_url) [Venue]
---------------

__TL;DR__: one-sentence summary

__keywords__: comma-separated terms

__Resources__: [[Github](url)]

__Other Notable Info__: [Project Page](url)

General Comments:
------
* 

Key ideas and technical details:
------
* 

My thoughts:
------
* 

Questions:
------
* 

Screenshots:
------
```

## Conventions

- Paper entries in `README.md` use the format: `* Paper Title [[Note](papers/filename.md)]` with optional venue badge `<kbd>CVPR 25</kbd>` and topic tag
- Entries are grouped under date headings (e.g., `#### 2026-03`) in reverse chronological order
- `Categorized.md` groups entries by research area (e.g., Dexterous Manipulation, VLA, Sim2Real, Object Detection)
- Abbreviations for topic tags are defined in `Abbreviations.md`
- Papers without notes yet appear in `README.md` without a `[[Note]]` link, or with a placeholder path like `papers/.........`

## Current Research Focus

The repository has shifted over time from autonomous driving / computer vision (2019–2024) to robotics and embodied AI (2025–present), with emphasis on:
- Dexterous manipulation and hand retargeting
- Vision-Language-Action (VLA) models
- Teleoperation and human-to-robot skill transfer
- Humanoid locomotion and loco-manipulation

---
title: The Beauty of Cellular Automata
slug: cellular-automata
description: Exploring the fascinating world of cellular automata, from Conway's Game of Life to elementary automata like Rule 45.
readTime: 5
featured: false
timestamp: 2024-12-11
tags: ["cellular automata", "mathematics", "visualization"]
---

If you've visited my homepage, you might have noticed the animations running along the margins. Those are **cellular automata**—simple rule-based systems that create surprisingly complex behavior.

I did a [research project on Pattern Periodicity in Rule 45 Cellular Automata](https://community.wolfram.com/groups/-/m/t/1733073) at the Wolfram High School Summer Research Program, which is why the margin design uses this pattern.

## What is a Cellular Automaton?

A cellular automaton is a grid of cells that evolve over time based on simple rules. Each cell is either "alive" (black) or "dead" (white), and its next state depends on its neighbors.

<img src="https://upload.wikimedia.org/wikipedia/commons/e/e5/Gospers_glider_gun.gif" alt="Conway's Game of Life - Glider Gun" style="max-width: 400px; margin: 1rem auto; display: block;">

*A "glider gun" in Conway's Game of Life—a pattern that continuously generates moving gliders. ([source](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life))*

## Conway's Game of Life

**Conway's Game of Life** follows four simple rules:

1. Live cell with <2 neighbors dies (underpopulation)
2. Live cell with 2-3 neighbors survives
3. Live cell with >3 neighbors dies (overpopulation)
4. Dead cell with exactly 3 neighbors becomes alive (reproduction)

From these rules emerge **gliders** that travel, **oscillators** that pulse, and even patterns that can compute.

## Elementary Cellular Automata & Rule 45

While Game of Life is 2D, **elementary cellular automata** work in 1D. They start with a single cell and grow downward like a pyramid.

<img src="https://upload.wikimedia.org/wikipedia/commons/9/9d/CA_rule30s.png" alt="Rule 30 Elementary Cellular Automaton" style="max-width: 300px; margin: 1rem auto; display: block;">

*Rule 30 cellular automaton—each row depends only on the row above it. ([source](https://en.wikipedia.org/wiki/Rule_30))*

**Rule 45** produces complex patterns from simple rules. Each cell's next state depends on itself and its two neighbors (8 possible combinations), following a lookup table derived from the binary representation of 45.

In my [research project](https://community.wolfram.com/groups/-/m/t/1733073), I analyzed how patterns repeat along diagonals of Rule 45, discovering period doubling and unexpected period tripling in the data.

## Why They Matter

Cellular automata show that **complexity emerges from simplicity**. You don't need complicated rules to create interesting behavior—simple primitives can compose into rich patterns.

This idea influences how I think about software and AI: the most elegant solutions often come from finding the right simple building blocks.

## Try It Yourself

Play with the patterns on my homepage! Use the dropdown in the bottom-right to switch between automata. Resources:
- [LifeWiki](https://conwaylife.com/wiki/) - Game of Life patterns encyclopedia
- [Golly](https://golly.sourceforge.io/) - Cellular automata simulator


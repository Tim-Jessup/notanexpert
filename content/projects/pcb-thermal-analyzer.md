---
title: "PCB Thermal Analyzer"
date: 2025-11-02
github: Currently private
---

A Python tool for analyzing thermal performance of PCB designs. Started because I wanted to predict hotspots on ESC boards before fabrication.

## What it does

Takes a PCB layout and copper layer stack-up, runs thermal simulations with adaptive meshing to find problem areas. Only a basic prototype so far. Mostly I was just testing Claude's coding abilities on a complex problem.

## Current status

- Basic adaptive meshing works
- Can import KiCAD PCB file formats
- Probably lying to me

## What I learned

Size of grid makes a huge difference in simulation time. Claude is getting very impressive. Need an adaptive grid to get good details for PCB work. Lots of potential for future projects with Kicad.

## Next steps

- Check if outputs are actually legit
- Work on better visualisation
- Validate against real measurements

Probably non-functional. Do not trust.

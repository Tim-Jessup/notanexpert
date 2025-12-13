---
title: "PCB Thermal Analyzer"
date: 2024-11-15
github: "https://github.com/yourusername/pcb-thermal-analyzer"
---

A Python tool for analyzing thermal performance of PCB designs. Started because I needed to predict hotspots on ESC boards before fabrication.

## What it does

Takes a PCB layout and copper layer stack-up, runs thermal simulations with adaptive meshing to find problem areas. Still rough around the edges but getting useful results.

## Current status

- Basic adaptive meshing works
- Can import common PCB file formats
- Thermal visualization needs work
- Documentation is... aspirational

## What I learned

Thermal analysis is harder than it looks. Convection modeling is tricky. Adaptive meshing makes a huge difference in simulation time.

## Next steps

- Better visualization
- Support for multi-layer boards
- Validate against real measurements
- Actually write the documentation

This is very much a work in progress. Use at your own risk.

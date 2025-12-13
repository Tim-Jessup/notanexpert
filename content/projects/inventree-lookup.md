---
title: "InvenTree Email Lookup Extension"
date: 2024-12-10
github: "https://github.com/yourusername/inventree-lookup"
---

Chrome extension that finds part numbers in emails and looks them up in our company's InvenTree system. Built because I was tired of manually copying and searching part numbers all day.

## How it works

Scans emails for patterns that look like part numbers, adds little popup buttons next to them, clicking opens the part in InvenTree. Supports multiple lookup methods and keyboard shortcuts.

## Features

- Pattern recognition for various reference formats
- Keyboard shortcuts (Ctrl+Shift+L)
- Works with Gmail, Outlook
- Configurable patterns

## Lessons learned

Regular expressions are both powerful and painful. Chrome extension APIs are surprisingly well-documented. JavaScript's type coercion still catches me out sometimes.

## Could be better

- Firefox support would be nice
- Better pattern customization UI
- More robust error handling

Works for what I need it for. Maybe it'll help someone else too.

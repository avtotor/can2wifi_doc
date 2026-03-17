# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

This is a **documentation-only repository** for a CAN-to-WiFi bridge project (ESP32-S3 + TJA1050 transceiver). It contains static HTML pages written in Russian that document the firmware, hardware wiring, CAN bus signals, GVRET protocol, and FreeRTOS architecture of the companion `can_wifi` firmware project.

There is no build system, no tests, and no application code in this repo -- only `.html` files served as a static site.

## Repository structure

- `index.html` -- Main page: project overview, hardware config, build commands, routing diagram
- `wiring.html` -- Wiring schematics (ESP32 + TJA1050 + voltage divider + OBD-II pinout)
- `signals.html` -- Physical CAN bus signals, TWAI timing, voltage levels, GVRET protocol details
- `can_frames.html` -- CAN 2.0 frame structure, OBD-II PIDs, SavvyCAN usage
- `freertos.html` -- FreeRTOS task architecture, main loop timing, memory map
- `howto.html` -- Beginner-friendly explanations of TJA1050, voltage divider, bidirectional CAN

## Key conventions

- All content is in **Russian** (`lang="ru"`). Maintain Russian language when editing content.
- Pages share a common dark-theme design using inline `<style>` blocks (IBM Plex Mono font, CSS custom properties for colors). There is no shared CSS file -- styles are duplicated per page.
- Diagrams are inline SVGs embedded directly in the HTML (no external image files).
- Navigation bar is duplicated in each file with the `class="active"` marker on the current page's link.
- Alert boxes use classes: `.ok` (green), `.info` (blue), `.warn` (yellow), `.danger` (red).
- The documented firmware targets **ESP32-S3** with **ESP-IDF v5.3.1**, using the built-in **TWAI** CAN controller (not SPI-based MCP2515).

## When editing pages

- Keep inline styles consistent across all pages -- if changing the design system, update all 6 HTML files.
- Navigation links must stay in sync: Главная, Подключение, Сигналы, CAN фреймы, FreeRTOS, HOWTO.
- SVG diagrams use the same color palette defined in `:root` CSS variables (`--g`, `--r`, `--b`, etc.).

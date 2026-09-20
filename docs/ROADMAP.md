# Roadmap

## Phase 0 — Foundation

- Confirm neutral project name and governance.
- Freeze draft Universal Punch Protocol v1.
- Document licence boundaries and contribution rules.

## Phase 1 — Tabletop proof

- Import Sportiduino tag data through a USB master station.
- Validate START, control, FINISH, duplicate, missing-control, and clock cases.
- Run with 10–20 test tags and two base stations.

## Phase 2 — Event engine

- Implement organisers, events, participants, teams, courses, waves, and classes.
- Add versioned presets and deterministic result calculation.
- Provide audit logs and repeatable imports.

## Phase 3 — Operations

- Add local operator console and live-results API.
- Add offline queue and delayed cloud synchronisation.
- Publish Docker-based self-hosting instructions.

## Phase 4 — Additional hardware

- ESP32 + PN532 station adapter.
- Android NFC reader.
- Online gateway and device-health telemetry.

## First field reference

Use CHUMPHON ARDF 2026 as a deployment and validation case while keeping all
event-specific rules in configuration.

# Architecture

## Scope

OpenPunch is a multi-event, multi-organiser competition platform. It supports
offline, online, and hybrid punching without assuming a particular sport or
station design.

## Layers

### Hardware

Readers, tags, control stations, master stations, phones, and gateways. A
hardware implementation must not define competition rules.

### Adapter

Converts a vendor or device representation into the Universal Punch Protocol.
Adapters also report import warnings, provenance, and device capabilities.

### Ingestion

Validates envelopes, authenticates devices, provides idempotency, accepts
offline replay, and preserves the original source payload for audit.

### Event engine

Applies a versioned event preset to immutable punch observations. Reprocessing
the same observations with the same preset version must produce the same result.

### Presentation

Operator console, live results, exports, and public APIs consume computed
results. Presentation code must not silently change sporting decisions.

## Data ownership modes

| Mode | Authoritative trail | Example |
|---|---|---|
| Tag-first | Participant tag | Sportiduino |
| Station-first | Station log | Connected ESP32 control |
| Hybrid | Tag plus station log | Resilient championship deployment |

## Non-negotiable guarantees

1. Events continue while the Internet is unavailable.
2. Imports are idempotent and safe to repeat.
3. Raw observations are retained and never overwritten by scoring decisions.
4. Clock source, receive time, and correction history are auditable.
5. Presets are versioned once an event begins.
6. Organisation and event data are isolated by identifiers and authorisation.

## Deployment profiles

- Local: one laptop, USB reader, local database.
- Gateway: local operation with delayed cloud synchronisation.
- Cloud: hosted control plane with offline-capable field clients.
- Self-hosted: containerised deployment under the organiser's control.

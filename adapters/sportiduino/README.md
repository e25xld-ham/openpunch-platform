# Sportiduino Adapter

This directory defines the interoperability boundary between OpenPunch and the
independent Sportiduino project.

## Planned responsibilities

- Read exported card and master-station data.
- Preserve source station identifiers and timestamps.
- Map records to the Universal Punch Protocol.
- Detect duplicate imports through deterministic observation identifiers.
- Report malformed, incomplete, or clock-suspect data without discarding it.

## Licence boundary

Do not copy Sportiduino source code into the Apache-2.0 core. If implementation
requires modification or reuse of GPL-3.0 code, place that work in an explicitly
GPL-3.0 component and retain original copyright and licence notices.

Upstream: https://github.com/sportiduino/sportiduino

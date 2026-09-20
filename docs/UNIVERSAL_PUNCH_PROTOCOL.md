# Universal Punch Protocol

## Purpose

The protocol represents an observed punch independently of hardware, transport,
sport, and scoring rules.

## Envelope

```json
{
  "schema_version": "1.0.0-draft",
  "observation_id": "01JQEXAMPLE00000000000000",
  "organisation_id": "org-example",
  "event_id": "event-2026-001",
  "participant_id": "team-015",
  "station_id": "control-03",
  "station_role": "control",
  "punched_at": "2026-12-05T09:42:18+07:00",
  "received_at": "2026-12-05T10:31:02+07:00",
  "clock_source": "station_rtc",
  "source": {
    "adapter": "sportiduino",
    "device_id": "station-103",
    "mode": "tag_first"
  },
  "sequence": 4,
  "offline": true,
  "raw_reference": "sha256:example",
  "integrity": {
    "status": "unverified"
  }
}
```

## Rules

- `observation_id` is globally unique and is the idempotency key.
- `punched_at` records the event observation time with an explicit offset.
- `received_at` records ingestion time and must never replace `punched_at`.
- Unknown station roles are preserved rather than guessed.
- An adapter must retain or hash the original payload for later audit.
- Scoring status such as valid, duplicate, late, or disqualified is computed
  separately and is not written into the raw observation.

## Station roles

Initial roles are `clear`, `check`, `start`, `control`, `finish`, and `custom`.
Events may label controls as FOX, checkpoint, gate, or another local term without
changing the protocol.

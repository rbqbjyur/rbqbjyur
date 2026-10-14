# outis

DFIR practitioner. I script incident response and evidence-handling work so
the methodology is fixed, written down and checkable: every run follows the
same procedure, leaves a record, and can be audited, repeated and defended
later. Those for collection and evidence handling run on a fresh or
locked-down host with nothing but what ships with it.

## Tools

| Repository | What it does |
|---|---|
| [defender-live-response-collector](https://github.com/rbqbjyur/defender-live-response-collector) | Collects timeline-relevant Windows triage artefacts into one zip (split into 1 GiB volumes when larger) through Microsoft Defender for Endpoint Live Response - one PowerShell script, no binaries, no child processes. |
| [triage-analyser](https://github.com/rbqbjyur/triage-analyser) | Runs targeted artefact parsers against Windows triage collections for quick answers without waiting for a full timeline. Currently EVTX: EvtxECmd with per-log event ID filters, one CSV per log. |
| [evidence-robocopy](https://github.com/rbqbjyur/evidence-robocopy) | Copies digital evidence with robocopy: always logged and SHA-256 verified, with chain-of-custody records that travel with the evidence - built-in tools only. |

## How they're built

- **Evidence first.** Chain of custody comes first. The aim is always a log
  and always SHA-256: forensic behaviour is the default, and anything less
  is opt-in, labelled and confirmed.
- **Auditable and readable.** UTC timestamps throughout, the tool's own
  version recorded, warnings up front, results that say exactly what they
  cover, and footprint and limitations stated plainly. The code is written
  to be read by other examiners: full-word names that say what each thing
  is, no clever constructs, table-driven settings and comments for intent.
- **Minimal dependencies.** Collection and evidence-handling tools use
  built-in tools only (no installers, modules or third-party binaries), so
  they run on any current Windows install; analysis tools drive established
  open-source parsers such as EvtxECmd.
- **Best effort, never brittle.** One failure skips one item, not the run.
- **Open.** 0BSD-licensed: use them for anything, no attribution required.

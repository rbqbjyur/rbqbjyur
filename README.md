# outis

DFIR practitioner. I write small, dependable tools for incident response and
forensic evidence handling on Windows. Those for collection and evidence
handling run on a fresh or locked-down host with nothing but what ships with
it.

## Tools

| Repository | What it does |
|---|---|
| [defender-live-response-collector](https://github.com/rbqbjyur/defender-live-response-collector) | Collects timeline-relevant Windows triage artefacts (artifacts) into one zip (split into 1 GiB volumes when larger) through Microsoft Defender for Endpoint Live Response - one PowerShell script, no binaries, no child processes. |
| [triage-analyser](https://github.com/rbqbjyur/triage-analyser) | Runs targeted artefact (artifact) parsers against Windows triage collections for quick answers without waiting for a full timeline. Currently EVTX: EvtxECmd with per-log event ID filters, one CSV per log. |
| [evidence-robocopy](https://github.com/rbqbjyur/evidence-robocopy) | Copies digital evidence (E01/EWF images and loose files) with robocopy, SHA-256 verification and chain-of-custody records - built-in tools only. |

## How they're built

- **Minimal dependencies.** Collection and evidence-handling tools use
  built-in tools only (no installers, modules or third-party binaries), so
  they run on any current Windows install; analysis tools drive established
  open-source parsers such as EvtxECmd.
- **Best effort, never brittle.** One failure skips one item, not the run.
- **Evidence-minded.** UTC timestamps throughout, hashes where they matter,
  the tool's own version recorded, warnings up front, results that say
  exactly what they cover, and footprint and limitations stated plainly.
- **Easy to extend.** Table-driven, with small helper functions, so adding an
  artefact or a check is a row, not a rewrite.
- **Open.** 0BSD-licensed: use them for anything, no attribution required.

# outis

DFIR practitioner. I write small, dependable tools for incident response and
forensic evidence handling on Windows: the kind you can run on a fresh or
locked-down host with nothing but what ships with it.

## Tools

| Repository | What it does |
|---|---|
| [defender-live-response-collector](https://github.com/rbqbjyur/defender-live-response-collector) | Collects timeline-relevant Windows triage artefacts (artifacts) into one zip (split into 1 GiB volumes when larger) through Microsoft Defender for Endpoint Live Response - one PowerShell script, no binaries, no child processes. |
| [evidence-robocopy](https://github.com/rbqbjyur/evidence-robocopy) | Copies digital evidence (E01/EWF images and loose files) with robocopy, SHA-256 verification and chain-of-custody records - built-in tools only. |

## How they're built

- **Built-in tools only.** No installers, modules or third-party binaries, so
  they run on any current Windows install.
- **Best effort, never brittle.** One failure skips one item, not the run.
- **Evidence-minded.** UTC timestamps throughout, hashes where they matter,
  the tool's own version recorded, warnings up front, results that say
  exactly what they cover, and footprint and limitations stated plainly.
- **Easy to extend.** Table-driven, with small helper functions, so adding an
  artefact or a check is a row, not a rewrite.
- **Open.** 0BSD-licensed: use them for anything, no attribution required.

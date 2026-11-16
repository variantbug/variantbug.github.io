---
layout: page
title: "How I work"
---

**Nguyen Thanh Tin**, Independent security researcher, running [VariantBug](https://variantbug.com)

Most bugs that matter are found twice: once by whoever wrote the code, once by whoever reads the fix. I work the second way.

## The loop

1. **Read the patch, not the advisory headline.** A public fix names the bug class and the exact lines that changed. That is a specification of what to look for, written by the vendor, for free.
2. **Map the siblings.** The same check is usually missing in more than one place: a second route, a fork, a downstream product, a copy of the file. The advisory often lists which surfaces were already clean, which shrinks the candidate set to something readable in an hour.
3. **Prove it end to end.** No repro, no report. A candidate that cannot be demonstrated against a running instance stays a note, not a submission.
4. **Chain before reporting.** One finding is priced by what it reaches. If it lowers the barrier for something else, that belongs in the same report.
5. **Report once, honestly.** Severity is what the impact supports, not what the CVSS calculator allows. A Medium reported as a Medium is worth more than a Critical that gets argued down.

## What that looks like in practice

The first public advisory on this site came from step 1 and 2: a vendor fixed a missing ownership check on one route, and the same check was still absent on a second route in the same controller family. The fix took a day; the write-up is [here](/writeups/2026-civiform-ghsa-6w4r).


## Human in the loop

Tools are part of this work: watching fix feeds, reading large diffs, enumerating sibling surfaces. But Google says it best in its own toolkit for AI-assisted bug hunting, [google/mantis](https://github.com/google/mantis), first paragraph: **all findings must be manually verified by a security expert before being reported.** Big Sleep, Google's AI vulnerability researcher, runs the same rule: every finding is reproduced by the agent, then reviewed by a human expert before it reaches a vendor.

That is the line I hold too. Three gates, fail-closed:

<div class="gates">
  <div class="gate"><span class="g-tag">GATE 1</span><strong>Re-derived by hand.</strong> Every candidate is confirmed against the code by a person before it is written down. A tool's guess is a lead, not a finding.</div>
  <div class="gate"><span class="g-tag">GATE 2</span><strong>Repro or it does not exist.</strong> Nothing ships without a working reproduction a triager can run. Machine does breadth; a human signs the report.</div>
  <div class="gate"><span class="g-tag">GATE 3</span><strong>Nothing files itself.</strong> No report leaves this desk without a human reading every line. Google paused its own bounty program over unverified AI slop; being the opposite of that is the whole brand.</div>
</div>

<style>
.gates{display:grid;gap:12px;margin:20px 0}
.gate{background:var(--card,#fff);border:1px solid var(--line,#e8e2d8);border-radius:12px;padding:14px 16px;position:relative}
.g-tag{display:inline-block;font-family:ui-monospace,SFMono-Regular,Menlo,monospace;font-size:11px;letter-spacing:.14em;color:var(--green,#3d9a63);background:var(--green-soft,#e7f4ec);border-radius:6px;padding:2px 8px;margin-right:8px;transform:rotate(-2deg)}
.gate strong{color:inherit}
@media (prefers-color-scheme: dark){.gate{background:#1d2025;border-color:#2e3238}.g-tag{background:#233127}}
</style>

## What I do not do

- No scanning at scale against programs that forbid it. Depth over volume.
- No unverified submissions. A triager's time is not a testing ground.
- No disclosure without the vendor's window. Credit is not worth a zero-day.

## Contact

Bugs, private program invites, or a patch you want a second pair of eyes on: [hello@variantbug.com](mailto:hello@variantbug.com).

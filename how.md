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

Tools do breadth. A person does the verdict.

<div class="loop">
  <div class="row"><span class="who tool">tool</span> finds a candidate <span class="verdict lead">a lead</span></div>
  <div class="row"><span class="who human">human</span> re-derives it against the code <span class="verdict ok">a finding</span></div>
  <div class="row"><span class="who human">human</span> runs the repro, reads every line <span class="verdict ok">a signature</span></div>
</div>

<style>
.loop{display:grid;gap:8px;margin:18px 0}
.row{background:var(--card,#fff);border:1px solid var(--line,#e8e2d8);border-radius:10px;padding:10px 14px;font-size:15px}
.who{font-family:ui-monospace,SFMono-Regular,Menlo,monospace;font-size:12px;font-weight:700;letter-spacing:.08em;padding:2px 9px;border-radius:6px;margin-right:4px;display:inline-block;transform:rotate(-2deg)}
.tool{background:var(--green-soft,#e7f4ec);color:var(--green,#3d9a63)}
.human{background:#f6e9d8;color:#b0782a}
.verdict{font-weight:700;margin-left:auto;float:right}
.verdict.lead{color:#b0782a}
.verdict.ok{color:var(--green,#3d9a63)}
@media (prefers-color-scheme: dark){.row{background:#1d2025;border-color:#2e3238}.tool{background:#233127}.human{background:#33291a;color:#d9a552}.verdict.lead{color:#d9a552}}
</style>

## What I do not do

- No scanning at scale against programs that forbid it. Depth over volume.
- No unverified submissions. A triager's time is not a testing ground.
- No disclosure without the vendor's window. Credit is not worth a zero-day.

## Contact

Bugs, private program invites, or a patch you want a second pair of eyes on: [hello@variantbug.com](mailto:hello@variantbug.com).

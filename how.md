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

## What I do not do

- No scanning at scale against programs that forbid it. Depth over volume.
- No unverified submissions. A triager's time is not a testing ground.
- No disclosure without the vendor's window. Credit is not worth a zero-day.

## Contact

Bugs, private program invites, or a patch you want a second pair of eyes on: [hello@variantbug.com](mailto:hello@variantbug.com).

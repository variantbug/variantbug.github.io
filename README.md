New File at / · variantbug/variantbug.github.io# VariantBug

Independent security research — **variant analysis & patch-diffing**.

When a vendor fixes one bug, the same root cause often survives elsewhere in the codebase. We diff the patch, re-derive the flaw class, and hunt its siblings.

## Research focus

- **Patch-diff → variant** — upstream fixes as a map to unpatched code paths in the same project, forks, and downstream vendors.
- **Chain assembly** — single findings are priced by what they reach; we test whether one finding lowers the barrier for another before reporting either.
- **Verified only** — every report ships with a reproduction. If it cannot be reproduced and observed, it is not reported.

## Advisories & write-ups

- [Finding a bug variant in CiviForm: same missing check, different route](./writeups/2026-civiform-ghsa-6w4r.md) — GHSA-6w4r-8x7p-2hm5 · CWE-639 · CVSS 4.3 · fixed in 3.36.0. Found by variant-hunting the patch of GHSA-qv7c-9hjr-9rv7.

## Contact

**Nguyen Thanh Tin** — Independent security researcher
hello@variantbug.com · [variantbug.com](https://variantbug.com)

*Disclosure timelines and embargo terms honored at all times.*

New File at / · variantbug/variantbug.github.io# VariantBug

Independent security research — **variant analysis & patch-diffing**.

When a vendor fixes one bug, the same root cause often survives elsewhere in the codebase. We diff the patch, re-derive the flaw class, and hunt its siblings.

## Research focus

- **Patch-diff → variant** — upstream fixes as a map to unpatched code paths in the same project, forks, and downstream vendors.
- **Chain assembly** — single findings are priced by what they reach; we test whether one finding lowers the barrier for another before reporting either.
- **Verified only** — every report ships with a reproduction. If it cannot be reproduced and observed, it is not reported.

## Advisories & write-ups

Starting fresh — first advisory lands after vendor embargo clears. Index will live in [`writeups/`](./writeups).

## Contact

**Nguyen Thanh Tin** — Independent security researcher
hello@variantbug.com · [variantbug.com](https://variantbug.com)

*Disclosure timelines and embargo terms honored at all times.*# variantbug.github.io
Independent security research - variant analysis and patch-diffing

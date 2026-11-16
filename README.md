# VariantBug

**We find the bugs a patch left behind.**

Independent security research by Nguyen Thanh Tin â variant analysis & patch-diffing.

<style>
@media (prefers-color-scheme: dark) {
  body { background:#0d1117; color:#e6edf3; }
  a { color:#58a6ff; }
  h1,h2,h3 { color:#f0f6fc; border-color:#30363d; }
  hr { border-color:#30363d; }
  blockquote { color:#8b949e; border-color:#30363d; }
}
</style>

Independent security research â **variant analysis & patch-diffing**.

When a vendor fixes one bug, the same root cause often survives elsewhere in the codebase. We diff the patch, re-derive the flaw class, and hunt its siblings.

## Research focus

- **Patch-diff â variant** â upstream fixes as a map to unpatched code paths in the same project, forks, and downstream vendors.
- **Chain assembly** â single findings are priced by what they reach; we test whether one finding lowers the barrier for another before reporting either.
- **Verified only** â every report ships with a reproduction. If it cannot be reproduced and observed, it is not reported.

## Advisories & write-ups

- **[Finding a bug variant in CiviForm](./writeups/2026-civiform-ghsa-6w4r.md)**
  GHSA-6w4r-8x7p-2hm5 Â· CWE-639 Â· CVSS 4.3 Â· fixed in 3.36.0 â found by variant-hunting the patch of GHSA-qv7c-9hjr-9rv7.

## Contact

**Nguyen Thanh Tin** â Independent security researcher
hello@variantbug.com Â· [variantbug.com](https://variantbug.com)

*Disclosure timelines and embargo terms honored at all times.*

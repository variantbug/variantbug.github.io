# VariantBug

**We find the bugs a patch left behind.**

Independent security research by Nguyen Thanh Tin — variant analysis & patch-diffing.

<style>
@media (prefers-color-scheme: dark) {
  body { background:#0d1117; color:#e6edf3; }
  a { color:#58a6ff; }
  h1,h2,h3 { color:#f0f6fc; border-color:#30363d; }
  hr { border-color:#30363d; }
  blockquote { color:#8b949e; border-color:#30363d; }
}
</style>

When a vendor fixes one bug, the same root cause often survives elsewhere. We diff the patch, re-derive the flaw class, and hunt its siblings.

## Research focus

- **Patch-diff → variant** — upstream fixes as a map to unpatched paths in the same project, forks, and downstream vendors.
- **Chain assembly** — one finding is priced by what it reaches; we test whether it lowers the barrier for another before reporting either.
- **Verified only** — every report ships with a reproduction. No repro, no report.

## Advisories & write-ups

- **[Finding a bug variant in CiviForm](./writeups/2026-civiform-ghsa-6w4r.md)**
  GHSA-6w4r-8x7p-2hm5 · CWE-639 · CVSS 4.3 · fixed in 3.36.0 — variant of GHSA-qv7c-9hjr-9rv7.

## Contact

hello@variantbug.com — **Nguyen Thanh Tin**, independent security researcher.
Disclosure timelines and embargo terms honored at all times.

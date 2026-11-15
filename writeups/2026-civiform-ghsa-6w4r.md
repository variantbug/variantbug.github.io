# Finding a bug variant in CiviForm: same missing check, different route

<style>
@media (prefers-color-scheme: dark) {
  body { background:#0d1117; color:#e6edf3; }
  a { color:#58a6ff; }
  h1,h2,h3 { color:#f0f6fc; border-color:#30363d; }
  hr { border-color:#30363d; }
  blockquote { color:#8b949e; border-color:#30363d; }
}
</style>

**Nguyen Thanh Tin** — Independent security researcher, running [VariantBug](https://variantbug.com)
Advisory: [GHSA-6w4r-8x7p-2hm5](https://github.com/civiform/civiform/security/advisories/GHSA-6w4r-8x7p-2hm5) · CWE-639 · CVSS 4.3 (Medium) · Fixed in CiviForm 3.36.0

Every public advisory is a map to the next bug. This one came from reading a patch.

## Summary

CiviForm lets trusted intermediaries (TI) act on behalf of applicants. A previously disclosed advisory, [GHSA-qv7c-9hjr-9rv7](https://github.com/civiform/civiform/security/advisories/GHSA-qv7c-9hjr-9rv7), described a route that performed the role check but not the ownership check. Reading that patch raised an obvious question: **how many other routes share this authorization pattern, and are they all checked?**

One wasn't. `GET /applicants/:applicantId/programs/:programName` verified the requester was a TI or admin, but never verified the applicant belonged to them. Fixed in v3.36.0.

## The variant angle

The original advisory did half the enumeration work for free:

1. It named the bug class — act-on-behalf-of routes missing the applicant-ownership check.
2. It listed which routes were already clean — the review and edit pages had the check.

So the candidate set was small: every route carrying `:applicantId` in its path, minus the ones the advisory said were safe. `programs/:programName` was left over. Reading its controller confirmed the shape: a role gate, no ownership gate — the same "check at the wrong layer" pattern as the original bug.

Applicant IDs are sequential, so enumeration was trivial: a TI for organization A could open the program page of any applicant served by organization B, and see their name, email, and program enrollments.

## Impact — honestly rated

This is a Medium, and the advisory says so plainly: identity and enrollment details across organizations, not application answers; requires a TI account; CVSS 4.3. Nothing in the answers, no privilege escalation. I reported it as such and the vendor rated it the same way — which is how the process should work.

## Takeaways

- **A patch for bug N is the spec for bug N+1.** Read the diff, extract the authorization pattern, and look for siblings that never got the fix.
- **Advisories are high-quality free intelligence.** Vendors name the bug class and often list which surfaces are already clean — the enumeration is half-done before you start.
- **The tooling here was reading and ten minutes of manual testing.** No infrastructure required.

## Timeline

- Reported to the CiviForm security team via their disclosure process.
- Patched in v3.36.0 ([#13931](https://github.com/civiform/civiform/pull/13931)).
- Published as GHSA-6w4r-8x7p-2hm5. Credit: tinhien11.

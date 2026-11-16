# PRODUCT.md — VariantBug (assumptions labeled)

## Product
VariantBug = public-facing brand site of an independent security researcher
(Nguyen Thanh Tin). Lane: variant analysis & patch-diffing — take a vendor
patch, re-derive the flaw class, find its surviving siblings, report with a
working repro. [ASSUMPTION: solo researcher, no paid service yet.]

## Audience
Two readers, ranked:
1. Security triagers / program managers deciding whether to trust a report
   — need instant proof of competence: real advisories, honest severity.
2. Other researchers / potential collaborators scanning the niche.

## Success
A visitor in 10 seconds knows: what VariantBug hunts, what it has found
(linked GHSA), and that nothing unverified is claimed. Credibility over
flash. [ASSUMPTION: conversion = "read the write-up", not a contact form.]

## Voice
Blunt, evidence-first, honest severity ("Medium, because that is what it
is"). No AI-hype words. Tagline fixed: "We find the bugs a patch left
behind." (user decision 2026-11-16: never change).

## Mode
Persuade (landing) — the write-ups are the product.

## Constraints
- GitHub Pages, Jekyll-processed static; no build step, no framework,
  no external fonts/JS (privacy + durability). Dark-first aesthetic.
- Must remain readable as a README fallback too (GitHub blob view).

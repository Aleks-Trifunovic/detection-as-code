# ADR 0001: Rule format

## Context

- Every rule needs the same format, so tests can check all rules the same way
- Sigma is the standard format for detection rules
- My rules run in Defender XDR, and the first ones (brute force, spray) need aggregation

## Decision

I decided that the rules I will write will differ slightly from Sigma rules. Structure and field names come from Sigma but i added a field where raw KQL is written. Repo is Microsoft focused and I write the rules directly in Advanced Hunting, and raw KQL can be pasted in easily, in this case. I didn't use pure Sigma because it can't easily express aggregation.

## Consequences

Good: full KQL, testable directly in Advanced Hunting.

Bad: will have to rewrite for other SIEMs.

# Affidavit / Proof-of-Service State Data (50 States + DC + FED)

JSON datasets for generating **affidavits and declarations of service** that match each U.S. state's rules of civil procedure — qualification recitals, required return fields, county/venue data, and a full rules build with per-fact citations.

## Files

| File | Size | What it is |
|------|------|------------|
| `stateReturnQualifications.json` | 52 entries (AL–WY + DC + FED) | Sworn **qualification text** per state (the "I, {serverName}, declare…" recital), required body clauses, required footer fields, and whether a general unsworn-declaration statute exists |
| `usCounties.json` | 57 keys | County names per state, including **parish** (LA) and **borough** (AK) venue types |
| `state-rules.json` | ~900 KB full build | Schema v2: proof type (affidavit / verified return / certificate / signed return), notary requirement, declaration-allowed + exact jurat wording, server authority model + age, substitute service, posting, required return fields, return deadlines — **every fact carries `{value, citation, source_url, verified, effective_from}`** |

## Provenance & verification

- Research compiled **2026-10-24** from each state's **primary sources** (rules of civil procedure, state statutes, official court form pages). Qualification data last touched **2026-11-23** (prior verified ports: MO/OR/FL/MT/WI/IN/GA/NJ/NM/NE/SC; re-verified 2026-11-23 vs primary sources: UT SB 149 PI-disclosure + return-ID clauses; WY 9/21/26 alternative-service rewrite with exact 4(n)(2) quote; NJ R. 4:4-4(a)(9); MS 2026-07-01 MRCP; OK SB 1876; TX JBCC 26-9067).
- Three research passes. A `verified: true` flag means the fact was confirmed against the primary source URL recorded on the fact itself; anything unconfirmed stays `verified: false` and the consuming engine **falls back fail-closed** (defaults to a notarized affidavit).
- Counties file compiled **2026-10-16**.

## License

No formal license or terms — use freely, including in commercial products. Credit is appreciated but not required.

*No attorney has reviewed this data. Verify against current state law before relying on it in a filed court document.*

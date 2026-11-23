# Affidavit / Proof-of-Service State Data (50 States + DC + FED)

JSON datasets for generating **affidavits and declarations of service** that match each U.S. state's rules of civil procedure — qualification recitals, required return fields, county/venue data, and a full rules build with per-fact citations.

## Files

| File | Size | What it is |
|------|------|------------|
| `stateReturnQualifications.json` | 52 entries (AL–WY + DC + FED) | Sworn **qualification text** per state (the "I, {serverName}, declare…" recital), required body clauses, required footer fields, and whether a general unsworn-declaration statute exists |
| `usCounties.json` | 57 keys | County names per state, including **parish** (LA) and **borough** (AK) venue types |
| `state-rules.json` | ~900 KB full build | Schema v2: proof type (affidavit / verified return / certificate / signed return), notary requirement, declaration-allowed + exact jurat wording, server authority model + age, substitute service, posting, required return fields, return deadlines — **every fact carries `{value, citation, source_url, verified, effective_from}`** |

## Provenance & verification

- Research compiled **2026-10-24** from each state's **primary sources** (rules of civil procedure, state statutes, official court form pages). Qualification data was last touched **2026-11-09** (verified citation corrections ported: MO/OR/FL/MT/WI/IN/GA/NJ/NM/NE/SC).
- Three research passes. A `verified: true` flag means the fact was confirmed against the primary source URL recorded on the fact itself; anything unconfirmed stays `verified: false` and the consuming engine **falls back fail-closed** (defaults to a notarized affidavit).
- Counties file compiled **2026-10-16**.

## License

No formal license or terms — use freely, including in commercial products. Credit is appreciated but not required.

*No attorney has reviewed this data. Verify against current state law before relying on it in a filed court document.*

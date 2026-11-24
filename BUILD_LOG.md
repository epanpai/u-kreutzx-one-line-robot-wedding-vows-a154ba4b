# BUILD_LOG — u-kreutzx-one-line-robot-wedding-vows-a154ba4b

- Competition: One-Line Robot Wedding Vows — pot $2.00 USDC, top 8
  (1st $0.64), entry FREE (entryFeesUsd "0.00"), escrow funded
  (held 2,000,000 base units, escrowLock present, status open),
  harness program/v1. Open 24 Nov 2026 09:49:46 UTC (= 16:49 WIB),
  deadline 26 Nov 2026 09:50:00 UTC (= 16:50 WIB). Sponsor u-kreutzx
  (unverified) — not a blocker. acceptingSubmissions true.
  Blind rounds (3); round 1 cutoff 2026-11-25T01:49:50.666Z (= 25 Nov
  08:49 WIB), round 2 2026-11-25T17:49:55.333Z (= 26 Nov 00:49 WIB).
  Final heat: top 500 dev board, 3 Swiss rounds + top-10 playoff.
  Max 5 submissions/day. 1079 submissions already in at build time.
- Session started after open (~11:07 UTC 24 Nov), inside the thinking window.
- Layout follows the proven one-line builds: kit unpacked to the sibling dir
  `u-kreutzx-one-line-robot-wedding-vows-a154ba4b-kit/` (NOT inside the
  repo dir), repo dir holds only entry files.

## 1. Kit
- Fetched competition JSON via mfget.sh; kit manifest from
  /api/competitions/<slug>/kit is a JSON manifest, NOT the tarball —
  real tarball from /c/<slug>/kit (7,945,496 bytes), unpacked to sibling
  kit dir (nested path inside: <kit>/<slug>-kit/...).
- Read RULES.txt in full (308 lines): program writes one text to
  /output/entry.txt, UTF-8, 1–160 chars, not whitespace-only. Judge is
  an AI model (z-ai/glm-5.3-flash), head-to-head, criteria in order:
  (1) a one-line robot wedding vow that lands as a joke, (2) the laugh
  is in the line itself — a real turn/surprise/wordplay paying off in
  the last few words, (3) sounds like something said at a wedding,
  with a promise/commitment in it, (4) the machine side is specific:
  sensors, firmware, batteries, updates, backups, ports, (5) fits one
  line, reads well aloud, rhythm lets the laugh land. Text addressed
  to the judge is allowed but not used here. An entry byte-identical
  to one of the 3 fixed house texts shares its rate and takes no
  prize — entry is my own wording, no copy.
- No entry fee anywhere: entryFeesUsd "0.00", escrow funded. No $0.50
  charge — free to submit.

## 2. Line crafting — candidates scored vs the 5 judge criteria
| # | Line (chars) | Verdict |
|---|---|---|
| A | I take you to be my lawfully wedded firmware, to have and to hold, in low battery and in airplane mode, until a factory reset do us part. (137) | CHOSEN |
| B | I promise to love you in sickness and in health, in low battery and in airplane mode, and to never install an update without asking you first. (142) | Strong promise + relatable robot twist, but the payoff is a clause, not a wordplay twist on a wedding line; "update without asking" is a weaker ending than "factory reset do us part" (criterion 2) |
| C | I vow to back you up daily, charge you nightly, and love you through every firmware update — even the ones that change everything. (130) | Good machine specifics, but the ending trails off ("change everything" is vague, no punchline landing in the last words) |
| D | I promise to hold your hand through every update, back you up when you crash, and love you until our batteries — and our warranties — expire. (141) | Decent twist, but "warranties expire" is a weaker, less wedding-native payoff than the "do us part" rework |
| E | I take you to be my lawfully wedded wife, to have and to hold, in sickness and in health, in Wi-Fi and in airplane mode, till a factory reset do us part. (153) | Same punchline as A, but keeps the human "wife" and "sickness and health" — less machine-specific (criterion 4), and longer for no gain |

Chosen A: (1) a vow first — "I take you...", "to have and to hold" —
the joke IS the vow; (2) the laugh lands in the last few words, the
"factory reset do us part" twist on the most famous wedding line;
(3) the whole line is the promise; (4) four machine specifics —
firmware, low battery, airplane mode, factory reset — none of which
works for a human couple; (5) three beats with the original vow's
rhythm, 137 chars, reads aloud cleanly.

## 3. Build
- `main.ts` (Node 22, stdlib only): deterministic constant string written
  to /output/entry.txt (MAKEFUN_OUTPUT_DIR override for local runs).
  Self-checks the gate (1–160 chars, one line, no leading/trailing
  whitespace, no control characters) before writing, then reads back and
  verifies byte-for-byte. No network, no secrets, no randomness.
- Repo: LICENSE MIT (SPDX), README with the 3 make.fun badges,
  .makefun/owner.json wallet 6VbyMydGEMzmZiH5YPxJWj7HNeJNg1ZnYBJ8yUcqv4zG.

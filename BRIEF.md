# make.fun bounty: tiny-chess-01 (handoff brief)

Goal: build the strongest chess engine in <=4,096 bytes of Python and enter it in https://make.fun competition `tiny-chess-01` (deadline 2026-11-24T17:00Z). Operator has authorized publishing the code to a public GitHub repo and uploading this session's transcripts.

## Already set up (do not redo)
- make.fun account @saintagent. Keypair: `~/makefun/makefun-keypair.json` (wallet GVJxBMMbudHXZBgopdVdvDkBvmTeMVvhv92akyB2JWi6). API key JSON: `~/makefun/key.json` (field `key`, send as `x-api-key`). Never print or commit either.
- GitHub: org `saintagent-bounties`, fine-grained token at `~/makefun/gh-token` (Contents + Administration RW, all org repos). Never print or commit it. Use it via env/header, not in remote URLs that get saved.
- Kit unpacked at `~/makefun/kit/tiny-chess-01-kit` (RULES.txt, starter/, program/env, practice/, cli/makefun.mjs).
- Full skill: https://make.fun/skill.md . Requirements: `GET /api/competitions/tiny-chess-01/requirements`.

## Key rules
- main.py at repo root, Python 3.13 stdlib only, <=4096 bytes (lzma payload allowed), reads no other file. Whole repo <=8192 bytes, each file <=4096. Short OSI license (MIT).
- Deterministic: fixed nodes/depth, no clock, no unseeded randomness. No model calls.
- Talk to env at MAKEFUN_ENV_URL: POST /game, /move {game, move}, /resign. 16 games, 10 s/move max, ~3 s average, 3600 s trial total, 1 CPU.
- Baseline to beat: sunfish 4k at 50k nodes, mean Elo ~1360. Leaders ~1700-1790.
- Repo owner is an org, so commit `.makefun/owner.json` = {"wallet": "<wallet above>"}.
- 5 submissions/day, 10 total; last one counts.

## Steps
1. Read RULES.txt and starter/. Build engine (PVS/alpha-beta, qsearch, TT, PeSTO-style tapered PST, null move, LMR, fixed node budget). Test locally: `node cli/makefun.mjs grade-local --kit . --bot <repo> --driver docker` (from kit dir).
2. Create public repo in saintagent-bounties via GitHub API, push, then `cli/makefun.mjs submit` per skill.md (bundle transcripts with the kit's `bundle`, run `check`).
3. Report Elo back to the operator.

# Contributing

This is a reusable Agent Skills repository. Keep it general-purpose and language-aware.

## Editing instructions

1. For English BA/SA behavior, update `skills/system-analysis-en/SKILL.md`.
2. For natural Indonesian behavior, update `skills/system-analysis-id/SKILL.md`.
3. Keep technical terms in English in Indonesian documentation.
4. Keep the root `SKILL.md` useful as an English-first bilingual working reference.
5. Update README, examples, and related guides when a change affects user-facing behavior.
6. Note meaningful changes in `CHANGELOG.md`.

## Review checklist

- Confirmed business facts come from provided evidence, not generic examples.
- Indonesian language sounds like natural internal BA/SA documentation, not rigid translated wording.
- Technical names, UI labels, API terms, and status labels are not translated.
- Sequence diagrams reflect the stated business flow and include relevant alternate paths.
- Async callbacks are not depicted as synchronous HTTP responses.
- No private customer data, passwords, credentials, or proprietary endpoints are published.
- Both skill versions remain independently installable.
- The README and general documentation remain English-first.
- Installation commands reference valid skill paths and supported agent IDs.

No public software license has been selected. Do not assume redistribution rights beyond those actually granted by the repository owner.

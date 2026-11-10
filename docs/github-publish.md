# Publishing and updating the repository

This repository contains two reusable language editions of the same BA/SA method.

## Main skill entry points

- `skills/system-analysis-en/SKILL.md`
- `skills/system-analysis-id/SKILL.md`

The root `SKILL.md` is a bilingual-aware English-first working reference. It is not the recommended direct path for CLI installation when you want one specific language.

## Publishing through GitHub

1. Create the repository.
2. Keep each skill in its own directory, with a valid `SKILL.md` containing `name` and `description` frontmatter.
3. Commit the documentation and examples.
4. Verify that the language-specific SKILL files are readable through their GitHub URLs.
5. Use a skills-compatible CLI to install the exact folder you want.

## Publishing through Git CLI

```bash
git add README.md SKILL.md skills docs examples AGENTS.md CLAUDE.md CHANGELOG.md
git commit -m "docs: maintain bilingual system analysis skill"
git push origin main
```

The command above assumes the repository is already configured with an authenticated remote and the working tree has no conflicting changes.

## Release checks

- Both language editions remain general-purpose.
- All real technical terms remain in English in the Indonesian skill.
- No secret credentials or real customer information are published.
- Code fences, Mermaid examples, and links render correctly.
- Installation commands use supported agent IDs.
- GitHub README and standard documentation remain English.

[Install instructions](installation.md) · [CLI upstream docs](https://github.com/vercel-labs/skills/blob/main/docs/commands.md)

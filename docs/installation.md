# Installation guide — English and Indonesian

This repository publishes two **standalone Agent Skills**:

- [`system-analysis-en`](../skills/system-analysis-en/SKILL.md): English writing and documentation
- [`system-analysis-id`](../skills/system-analysis-id/SKILL.md): natural Indonesian writing, with technical terms kept in English

Each directory contains its own complete `SKILL.md`, so you can install either language without depending on the rest of this repository.

## Requirements

Install [Node.js](https://nodejs.org/) **22.20.0 or newer** and use the [skills CLI](https://github.com/vercel-labs/skills). The commands below run in **PowerShell, Bash, or other shells that support `npx`**.

**What the flags do:** `-g` installs globally for all projects, `-a` selects your agent, `--copy` avoids symlinks (convenient on Windows), and `-y` skips interactive prompts. Remove `-g` to install into the current project only.

**Important:** Review a skill's source before installing it. A skill is an instruction package, not executable code by default, but agents may act on instructions they load.

## Claude Code

English:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-en -g -a claude-code --copy -y
```

Indonesia:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-id -g -a claude-code --copy -y
```

Documentation: [Claude Code skills](https://code.claude.com/docs/en/skills).

## OpenAI Codex CLI

English:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-en -g -a codex --copy -y
```

Indonesia:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-id -g -a codex --copy -y
```

Documentation: [OpenAI Codex](https://developers.openai.com/codex).

## Gemini CLI

English:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-en -g -a gemini-cli --copy -y
```

Indonesia:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-id -g -a gemini-cli --copy -y
```

Documentation: [Gemini CLI](https://geminicli.com/docs/).

## Cursor

English:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-en -g -a cursor --copy -y
```

Indonesia:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-id -g -a cursor --copy -y
```

Documentation: [Cursor](https://docs.cursor.com/).

## GitHub Copilot

English:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-en -g -a github-copilot --copy -y
```

Indonesia:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-id -g -a github-copilot --copy -y
```

Documentation: [GitHub Copilot](https://docs.github.com/en/copilot).

## OpenCode

English:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-en -g -a opencode --copy -y
```

Indonesia:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-id -g -a opencode --copy -y
```

Documentation: [OpenCode](https://opencode.ai/docs/).

## Install for several agents at once

For the English edition:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-en -g -a claude-code -a codex -a gemini-cli -a cursor -a github-copilot --copy -y
```

For the Indonesian edition:

```bash
npx skills add https://github.com/Ducklazy231/system-analysis-skill/tree/main/skills/system-analysis-id -g -a claude-code -a codex -a gemini-cli -a cursor -a github-copilot --copy -y
```

To install both versions, run the English and Indonesian commands separately. This creates two distinct skill names and makes language selection explicit.

## Verify, update, and switch versions

List installed global skills:

```bash
npx skills list -g
```

Check for updates:

```bash
npx skills check
```

Update installed skills:

```bash
npx skills update
```

Inspect available skills in the repository:

```bash
npx skills add Ducklazy231/system-analysis-skill -l --full-depth
```

Newly installed skills may need a new agent session or a skills reload, depending on the client.

## ChatGPT web and mobile app

The `npx skills` command targets **local compatible agent environments**. It does **not** install a skill into the ChatGPT web/mobile app.

For ChatGPT, open the selected file and add it to a ChatGPT Project or attach it to a chat if supported:

- [Open English SKILL.md](../skills/system-analysis-en/SKILL.md)
- [Open Indonesian SKILL.md](../skills/system-analysis-id/SKILL.md)

Then ask, for example: "Use the attached SKILL.md for this BA/SA document and keep the current project's facts separate from proposals." Whether the file is kept in context between chats depends on the product features and settings.

## Examples of invocation

**English:**

> Use system-analysis-en. Review this API integration and create an implementation-ready sequence diagram with validation, callback, and error handling.

**Indonesian:**

> Pakai system-analysis-id. Buat Jira dari error ini, lengkap dengan As-Is, To-Be, dan Acceptance Criteria. Technical terms tetap English, enggak perlu intro panjang.

## References

- [skills CLI reference](https://github.com/vercel-labs/skills/blob/main/docs/commands.md)
- [Official skills CLI supported agent IDs](https://github.com/vercel-labs/skills/blob/main/docs/agents.md)
- [Agent Skills specification](https://agentskills.io/specification)

CLI flags, agent identifiers, and supported paths can change across versions. Recheck the linked upstream documentation if a command stops working.

# claude-skills

Shared Claude Code skills & plugin. Install via one of the methods below.

## Skills

- **grill-me** — Relentlessly interview users about plans/designs until reaching shared understanding.

---

## Install Methods

### A. Plugin marketplace (recommended for teams)

Add the community marketplace (once):

```sh
claude plugin marketplace add anthropics/claude-plugins-community
```

Then install:

```sh
claude plugin install claude-skills@claude-community
```

Or inside a session:

```
/plugin marketplace add anthropics/claude-plugins-community
/plugin install claude-skills@claude-community
```

Skills are namespaced under the plugin: `/claude-skills:grill-me`

### B. Direct git install (no marketplace)

```sh
git clone https://github.com/nugrahaAdhitama/claude-skills.git
cp -r claude-skills/skills/grill-me ~/.agents/skills/grill-me
```

Windows (cmd):

```cmd
git clone https://github.com/nugrahaAdhitama/claude-skills.git
xcopy /E /I claude-skills\skills\grill-me %USERPROFILE%\.agents\skills\grill-me
```

### C. --plugin-dir (testing / local)

```sh
git clone https://github.com/nugrahaAdhitama/claude-skills.git
claude --plugin-dir ./claude-skills
```

Then use `/claude-skills:grill-me` in the session.

---

## Publish your own skill

1. Fork this repo
2. Add your skill under `skills/<name>/SKILL.md`
3. Update `.claude-plugin/plugin.json` version
4. Submit to community marketplace: https://platform.claude.com/plugins/submit

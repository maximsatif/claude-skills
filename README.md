# Claude Skills Collection

A collection of installable skills for [Claude](https://claude.ai) — extending what Claude can do with reusable, shareable instructions.

## What are skills?

Skills teach Claude how to handle specific tasks in a consistent, high-quality way. Install a skill once and Claude uses it automatically whenever it's relevant — no need to re-explain your preferences each time.

Compatible with **Claude desktop (Cowork)** and **Claude Code**.

---

## Skills

| Skill | Description | Install |
|-------|-------------|---------|
| [tabulate](./skills/tabulate/) | Auto-formats any data as clean Markdown tables | [📦 Download](./skills/tabulate/tabulate.skill) |

---

## Installation

### Option A — Install via `.skill` file (easiest)
1. Download the `.skill` file from the table above
2. Double-click it in Claude desktop to install, or drag it into the skills panel

### Option B — Manual install
Copy the skill's folder into your Claude skills directory:

| Platform | Path |
|----------|------|
| Mac | `~/.claude/skills/` |
| Windows | `%APPDATA%\Claude\skills\` |

Then restart Claude.

### Option C — Install all skills at once (Mac/Linux)
```bash
git clone https://github.com/YOUR_USERNAME/claude-skills.git
cp -r claude-skills/skills/* ~/.claude/skills/
```

---

## Adding a new skill

See [CONTRIBUTING.md](./CONTRIBUTING.md) for the full process. The short version:

1. Copy the [`template/`](./template/) folder into `skills/your-skill-name/`
2. Edit the `SKILL.md` — fill in the name, description, and instructions
3. Add a row to the table above
4. Open a pull request

---

## License

MIT — free to use, modify, and share.

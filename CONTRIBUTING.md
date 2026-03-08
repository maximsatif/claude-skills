# Contributing a Skill

Anyone can add a skill to this collection. Here's how.

## What makes a good skill?

A skill is worth adding when:
- It's something you'd want Claude to do consistently, not just once
- The instructions aren't obvious — Claude behaves meaningfully better with the skill than without
- It's general enough to be useful to others, not hyper-specific to one person's setup

## Step-by-step

### 1. Start from the template

```bash
cp -r template/ skills/your-skill-name/
```

Name the folder using lowercase and hyphens — e.g. `meeting-notes`, `code-reviewer`, `tone-adjuster`.

### 2. Fill in SKILL.md

Open `skills/your-skill-name/SKILL.md` and fill in:

- **`name`** — same as the folder name
- **`description`** — this is the most important field. Claude reads this to decide whether to load the skill. Be specific about *when* to trigger it, not just *what* it does. Make it a little pushy — err on the side of over-triggering.
- **The body** — instructions Claude follows when the skill is active. Explain the *why* behind each instruction, not just the *what*.

### 3. (Optional) Add bundled resources

If your skill needs scripts, reference docs, or asset files, add them as subdirectories:

```
skills/your-skill-name/
├── SKILL.md
├── scripts/       ← Python/bash scripts Claude can run
├── references/    ← Docs Claude loads as needed
└── assets/        ← Templates, fonts, icons, etc.
```

### 4. Package the skill

From the repo root, run the packager to produce a `.skill` installer file:

```bash
# If you have the skill-creator skill available via Claude:
# Ask Claude to package it for you

# Or manually zip:
cd skills/your-skill-name
zip -r ../your-skill-name.skill .
```

Place the `.skill` file inside `skills/your-skill-name/` so users can download it directly.

### 5. Update the README

Add a row to the skills table in `README.md`:

```markdown
| [your-skill-name](./skills/your-skill-name/) | What it does in one sentence | [📦 Download](./skills/your-skill-name/your-skill-name.skill) |
```

### 6. Open a pull request

Push your branch and open a PR. In the description, include:
- What the skill does
- Why it's useful
- Any test cases you ran

## Skill quality checklist

Before submitting, make sure:

- [ ] `name` in frontmatter matches the folder name
- [ ] `description` explains both *what* the skill does and *when* to use it
- [ ] The body explains the *why* behind instructions, not just the *what*
- [ ] SKILL.md is under 500 lines (move large content to `references/`)
- [ ] A `.skill` file is included for easy installation
- [ ] The README table has been updated

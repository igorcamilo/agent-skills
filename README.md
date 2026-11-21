# Personal Agent Skills

My personal collection of reusable skills, packaged as an agentic coding plug-in
for Xcode Intelligence. Each skill captures instructions and conventions for a
specific task so I can use them consistently across projects.

## Skills

| Skill | Description |
| --- | --- |
| [create-commits](skills/create-commits/SKILL.md) | Organize changes into small, logical Git commits with Unicode gitmoji messages. |

## Install in Xcode Intelligence

In an Xcode version that supports agentic coding plug-ins:

1. Open **Xcode > Settings > Intelligence**.
2. Under **Agents in Xcode**, open **Plug-ins** and click **Add Plug-in**.
3. Choose the local import option and select this repository's root folder
   (the folder containing `.claude-plugin` and `skills`).
4. Continue, select the `create-commits` skill, and click **Install**.

Once this repository is hosted at a Git URL, you can instead choose **Add from
URL** and enter that repository URL. Local changes must be reimported or updated
in Xcode before relying on them in an installed copy.

In the coding assistant, type `/` to discover installed skills, or ask the agent
to use `create-commits` to organize and commit your changes. The skill creates
local commits and only pushes when explicitly requested.

See Apple's [agentic coding plug-in installation instructions](https://developer.apple.com/documentation/xcode/extending-and-customizing-agents#Install-agentic-coding-plug-ins).

## Repository structure

The plug-in manifest supplies metadata. Xcode discovers skills in the standard
`skills/` directory, each with a `SKILL.md` entry point:

```text
agent-skills/
├── .claude-plugin/
│   └── plugin.json
├── README.md
└── skills/
    └── create-commits/
        └── SKILL.md
```

Skills can also include supporting scripts, references, and templates when needed.

## Using a skill

Open a skill's `SKILL.md` to read its purpose and workflow. To make it available to
an agent, install or link the skill directory using that agent's supported skill
setup, then invoke it by name or ask for the task it describes.

## Adding a skill

1. Create a directory under `skills/` with a short, descriptive name, such as
   `skills/review-changes`.
2. Add a `SKILL.md` with YAML front matter containing `name` and `description`.
3. Write focused instructions covering the workflow, constraints, and expected
   result. Keep supporting resources alongside the skill.
4. Add the skill to the table above.

Example entry point:

```markdown
---
name: review-changes
description: Review pending changes for correctness and maintainability.
---

# Review changes

Instructions for carrying out the task.
```

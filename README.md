# Agent skills

Agent skills for **WordPress plugin work** (review, security, WordPress.org readme) and **developer blog writing**. Install via the [skills CLI](https://github.com/sabbirxprt/skills) or Cursor’s learn flow.

## Skills

### wp-plugin-review

Audits WordPress plugins for **WordPress.org compliance and security** (PHP, JS, readme, enqueue, SQL, XSS, nonces, capabilities, etc.). Use when reviewing a plugin for submission to WordPress.org, preparing for plugin review, or auditing plugin code for guidelines and security.

### wp-security-scan

Runs a **security-only audit** of WordPress plugins (PHP, JS, etc.): SQL injection, XSS, unsanitized input, nonces, capability checks, arbitrary code/script insertion, direct file access, REST API permission callbacks, and sensitive data exposure. Use when you need a focused security scan before deployment or submission.

### wp-plugin-readme

Generates **WordPress.org–compliant `readme.txt`** files and reviews existing ones for violations. Reads plugin source when provided to extract name, features, hooks, and third-party dependencies. Use when writing, updating, auditing, or fixing a plugin readme, listing metadata, banners/icons, trademarks, third-party disclosure, or preparing a WordPress.org submission.

### blog-writer

Produces **publication-ready developer blog posts** about software (apps, libraries, CLIs, APIs, WordPress or browser extensions, infra, security, tutorials, etc.). **Code-first** when a repo or paths exist; **topic-first** with cited research when only a brief is given. Default output is structured for a **WordPress** blog (headings, excerpt, slug, categories/tags, featured-image brief) unless the user asks for another platform.

## Install a Skill

Using the [skills CLI](https://github.com/sabbirxprt/skills) (open agent skills ecosystem). CLI options and scope below are based on the [Skills CLI documentation](https://skills.sh/docs/cli).

```bash
npx skills add sabbirxprt/skills
```

### Options

| Option                    | Description                                           |
| ------------------------- | ----------------------------------------------------- |
| `-g, --global`            | Install to user directory instead of project          |
| `-a, --agent <agents...>` | Target specific agents (e.g. `cursor`, `claude-code`) |
| `-s, --skill <skills...>` | Install specific skills by folder name (e.g. `blog-writer`, `wp-plugin-readme`, `wp-plugin-review`, `wp-security-scan`) |
| `-l, --list`              | List available skills without installing              |
| `--copy`                  | Copy files instead of symlinking                      |
| `-y, --yes`               | Skip confirmation prompts                             |

### Examples

```bash
# List skills in this repository
npx skills add sabbirxprt/skills --list

# Install only the full plugin review skill
npx skills add sabbirxprt/skills --skill wp-plugin-review

# Install only the security scan skill
npx skills add sabbirxprt/skills --skill wp-security-scan

# Install only the WordPress.org readme skill
npx skills add sabbirxprt/skills --skill wp-plugin-readme

# Install only the blog writer skill
npx skills add sabbirxprt/skills --skill blog-writer

# Install to Cursor only
npx skills add sabbirxprt/skills -a cursor

# Non-interactive (CI-friendly)
npx skills add sabbirxprt/skills --skill wp-plugin-review -a cursor -y
```

### Scope

| Scope       | Flag      | Use case                                      |
| ----------- | --------- | --------------------------------------------- |
| **Project** | (default) | Skills live in `./<agent>/skills/`, share with team |
| **Global**  | `-g`      | Skills in `~/<agent>/skills/`, all projects   |

## Install in Cursor (Cursor UI)

In Cursor you can also load skills via the learn command:

```
/learn @sabbirxprt/skills
```

## Links

- [Agent Skills specification](https://agentskills.io)
- [Skills directory](https://skills.sh)
- [Cursor skills docs](https://cursor.com/docs/context/skills)

# WordPress Plugin Review Skills

Agent skills for auditing WordPress plugins: WordPress.org compliance and security.

## Skills

### wp-plugin-review

Audits WordPress plugins for **WordPress.org compliance and security** (PHP, JS, readme, enqueue, SQL, XSS, nonces, capabilities, etc.). Use when reviewing a plugin for submission to WordPress.org, preparing for plugin review, or auditing plugin code for guidelines and security.

### wp-security-scan

Runs a **security-only audit** of WordPress plugins (PHP, JS, etc.): SQL injection, XSS, unsanitized input, nonces, capability checks, arbitrary code/script insertion, direct file access, REST API permission callbacks, and sensitive data exposure. Use when you need a focused security scan before deployment or submission.

## Install a Skill

Using the [skills CLI](https://github.com/sabbirxprt/skills) (open agent skills ecosystem). CLI options and scope below are based on the [Skills CLI documentation](https://skills.sh/docs/cli).

```bash
npx skills add sabbirxprt/skills
```

Example:

```bash
npx skills add sabbirxprt/skills
```


### Options

| Option                    | Description                                           |
| ------------------------- | ----------------------------------------------------- |
| `-g, --global`            | Install to user directory instead of project          |
| `-a, --agent <agents...>` | Target specific agents (e.g. `cursor`, `claude-code`) |
| `-s, --skill <skills...>` | Install specific skills by name (e.g. `wp-plugin-review`, `wp-security-scan`) |
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

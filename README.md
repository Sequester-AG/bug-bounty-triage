# bug-bounty-triage

`bug-bounty-triage` is an agent skill for rigorous bug bounty report triage, independent validation, impact escalation, and submission-ready reporting.

It is designed to help an agent:

- reproduce findings end to end when testing is authorized;
- separate observed evidence from inference;
- reject weak or non-actionable reports before submission;
- pursue the highest defensible impact without overstating severity; and
- produce concise, evidence-heavy Markdown reports for bug bounty platforms.

## Responsible use

Use this skill only on systems you own or are explicitly authorized to test. Invoking the skill does not grant permission to test a target, exceed a program's scope, access unrelated data, or perform destructive actions.

The skill may preserve sensitive evidence in generated reports when the user supplies it. Review generated files before sharing or committing them, and follow the applicable bug bounty program's rules.

## Installation

### Skills CLI

```bash
npx skills add Sequester-AG/bug-bounty-triage --skill bug-bounty-triage
```

The repository must be public, or the installer must have access to the private repository.

### Codex

```bash
git clone https://github.com/Sequester-AG/bug-bounty-triage.git ~/.codex/skills/bug-bounty-triage
```

### Agent skills directory

```bash
git clone https://github.com/Sequester-AG/bug-bounty-triage.git ~/.agents/skills/bug-bounty-triage
```

Private-repository access is required until the repository is made public.

## Supporting skills and CLIs

The full live-validation workflow uses [agent-browser](https://www.skills.sh/vercel-labs/agent-browser/agent-browser) for browser automation and [agent-email-cli](https://www.skills.sh/zaddy6/agent-email-skill/agent-email-cli) for disposable test inboxes.

Install both agent skills:

```bash
npx skills add https://github.com/vercel-labs/agent-browser --skill agent-browser
npx skills add https://github.com/zaddy6/agent-email-skill --skill agent-email-cli
```

The skills provide agent instructions. Install their corresponding command-line tools for live execution:

```bash
npm install -g agent-browser
agent-browser install
npm install -g @zaddy6/agentemail
```

## skills.sh listing

After this repository is public, install it once with telemetry enabled using the Skills CLI command above. skills.sh discovers public repository skills from installation telemetry and lists them automatically; no separate submission is required.

## Usage

Invoke the skill with a report, vulnerability description, or target and finding:

```text
Use $bug-bounty-triage to validate this report and determine whether it is ready to submit: <report>
```

For live validation, provide the relevant authorization and scope. The complete workflow can use browser automation, direct HTTP requests, and disposable email accounts when those capabilities are available in the host environment. If live testing is unavailable, the skill should state what remains unverified.

## Output

For a supported, submission-ready finding, the skill writes a Markdown report named from the target and vulnerability class, such as:

```text
example-com-idor.md
```

Internal triage commentary stays outside the submission file.

## Repository contents

- `SKILL.md` — skill metadata, workflow, validation gates, escalation guidance, and report format
- `LICENSE` — MIT License

## License

MIT

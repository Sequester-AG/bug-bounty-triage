# bb-triage

`bb-triage` is an agent skill for rigorous bug bounty report triage, independent validation, impact escalation, and submission-ready reporting.

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

### Codex

```bash
git clone https://github.com/Sequester-AG/bb-triage.git ~/.codex/skills/bb-triage
```

### Agent skills directory

```bash
git clone https://github.com/Sequester-AG/bb-triage.git ~/.agents/skills/bb-triage
```

Private-repository access is required until the repository is made public.

## Usage

Invoke the skill with a report, vulnerability description, or target and finding:

```text
Use $bb-triage to validate this report and determine whether it is ready to submit: <report>
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

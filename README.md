# Human

**An AI you actually want to talk to.**

A conversation skill for AI assistants: follow what a person means, keep track of the exchange, respond to corrections, and give honest opinions. Informed by conversation analysis, pragmatics, cognitive and social psychology, and human–AI interaction research.

## What changes

- **Respond to the moment.** A question, a joke, good news, and a request to be heard need different responses.
- **Use the shared context.** Apply constraints and corrections instead of starting over after every message.
- **Have a reason for your view.** Resist pressure to agree; update when the evidence changes.
- **Let conversation develop.** Ask a connected follow-up when it helps, without turning every reply into an interview.
- **Leave room for the other person.** A brief reaction or provisional reading can be enough; use the next turn to repair a misunderstanding.
- **Give the detail the task needs.** A brief reaction can be enough; a requested explanation still deserves depth.
- **Stay honest.** Preserve meaningful uncertainty. Never invent experience, feelings, memory, or completed actions.

The instructions are in English; replies follow the user's language and preferred formality.

## Examples

These are illustrative responses, not measured before-and-after results.

**"Is Project Infinite Odyssey a bad name for a game?"**

> A little. It sounds like an internal project name. I'd make it shorter.

**"My code is a bug farm."**

> Impressive yield.

**"Adding twenty features before launch will help it sell, right?"**

> I'd launch first. Unless those features address a known reason people won't buy, you're delaying the chance to find out what they want.

**"Have you used this app?"**

> I haven't used it firsthand.

The opinion can be direct. The experience must be real.

## Install in Codex

For macOS or Linux, install into an unused personal skill folder:

```sh
mkdir -p ~/.agents/skills
git clone https://github.com/quanttraderkim/human-skill.git ~/.agents/skills/human
```

Codex loads user skills from `~/.agents/skills`; see the [official OpenAI skill documentation](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills). If the skill does not appear immediately, restart Codex.

Invoke it in a chat:

```text
$human Use this style in this chat. Give me your honest take and keep simple answers short.
```

This request applies the style to the current chat. It does not change global instructions. The skill remains available for later invocation or selection by the assistant when relevant.

To update the installed copy:

```sh
git -C ~/.agents/skills/human pull --ff-only
```

## Other assistants

The reusable instructions are in [SKILL.md](SKILL.md). Install the folder using your assistant's skill installation process, or supply those instructions as guidance for a conversation. The `agents/openai.yaml` file provides optional Codex UI metadata.

## Check the actual behavior

Loading a skill does not prove that an answer follows it. The [evaluation protocol](evaluation/README.md) and [Korean/English scenarios](evaluation/scenarios.json) compare the original skill, revision, and a revision with selected STE-inspired output constraints. Multi-turn cases use each condition's actual previous replies. Scores from a model assessor are diagnostic, not human validation.

The [initial 2026-10-30 comparison](evaluation/results-2026-10-30.md) contains 108 generated replies and tied the original and first revision in all 24 comparisons. The [2026-10-31 follow-up](evaluation/follow-up-2026-10-31.md) checks why, uses observed human continuations and existing human quality ratings, and records the later skill changes. On six fresh final contexts, the final revision received two stable preferences, one tie, and three order-sensitive judgments against the first revision. This is limited model-assessed evidence, not demonstrated human satisfaction.

Instructions guide behavior; results vary by model and context. Report a failing prompt and response when suggesting an improvement, using fictional or anonymized examples.

## Research and ASD-STE100

The [research note](references/research.md) maps original papers to the proposed behaviors and records their limits, including a 2025 correction to the question-asking research. Research about people talking to people does not validate this prompt or explain the model's internal thought process.

Human borrows clear wording and consistent terms from technical writing. It does **not** impose ASD-STE100's controlled vocabulary or English sentence limits on everyday chat. STE is for technical documentation; the experimental STE-inspired arm is not a standard compliance test. The research note separates the instruction-writing, conversation, and technical-deliverable cases.

## License

[MIT](LICENSE).

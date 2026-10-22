# Human

**An AI you actually want to talk to.**

A conversation skill for AI assistants: have a take, get the joke, push back when warranted, and know when to stop. Be confident in opinions and accurate about facts.

## What changes

- **Have a take.** Recommend something when asked, with a reason.
- **Live with small uncertainties.** Mention the conditions that could change the answer; skip ritual disclaimers about taste.
- **Get the joke.** Recognize humor without forcing it into every reply.
- **Earn agreement.** Give specific praise and honest disagreement, with no contrarian quota.
- **Know when to stop.** Match the answer to the moment. A simple question usually deserves a short answer.

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

Loading a skill does not prove that an answer follows it. Try the same opinion question, joke, disagreement, and factual question with and without the skill, keeping the model and context comparable. Judge the actual responses: Is the opinion clearer? Is unnecessary explanation gone? Are facts and experience still honest?

Instructions guide behavior; results vary by model and context. Report a failing prompt and response when suggesting an improvement, using fictional or anonymized examples.

## License

[MIT](LICENSE).

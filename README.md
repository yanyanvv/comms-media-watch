<p align="center">
  <img src="assets/banner.png" alt="Comms and Media Watch banner" width="100%">
</p>

# Comms and Media Watch

Comms and Media Watch is an agent skill that turns Claude or Codex into a working media and telecom analyst. It creates current, source-backed reports on important changes in communications, media, and telecom: regulation, ownership, distribution, advertising, audience behavior, and technology. It groups related coverage into events and explains the business effect in plain English.

It does the work an analyst would otherwise do inside a market intelligence platform: monitor the sector, check claims against filings, dockets, and measurement data, and turn a week of news into one clear page.

## Works with

- **OpenAI Codex.** Reads the `SKILL.md` skill format and the Codex interface metadata.
- **Anthropic Claude.** Claude Code and other Claude agents read the same `SKILL.md` directly.

The skill uses the open agent skills format, so any agent that supports `SKILL.md` can run it.

## Use

- In Codex, run `$comms-media-watch`.
- In Claude Code, run `/comms-media-watch`, or simply ask what changed in media and telecom this week. The skill triggers on its description.

You can name a company, market, topic, or date range when you want narrower coverage.

The default run produces a weekly brief in the conversation and a polished one-page PDF. It includes the main development, supporting events, source links, and a short watch list.

## Install

Copy the [`comms-media-watch`](comms-media-watch) folder into your agent's skills directory:

```bash
git clone https://github.com/yanyanvv/comms-media-watch
cp -r comms-media-watch/comms-media-watch ~/.codex/skills/comms-media-watch    # Codex
cp -r comms-media-watch/comms-media-watch ~/.claude/skills/comms-media-watch   # Claude Code
```

Keep the repository README and banner at the repository root.

## Contents

- [`SKILL.md`](comms-media-watch/SKILL.md) contains the research and writing workflow.
- [`communications-media.md`](comms-media-watch/references/communications-media.md) defines the sector map and source priorities.
- [`openai.yaml`](comms-media-watch/agents/openai.yaml) provides the Codex interface metadata. Claude ignores it.

## License

MIT. See [LICENSE](LICENSE).

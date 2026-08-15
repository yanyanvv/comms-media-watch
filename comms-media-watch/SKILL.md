---
name: comms-media-watch
description: Create current communications and media briefs, alerts, company reviews, earnings analyses, source searches, comparisons, landscapes, and deep dives. Use when a user asks what changed in streaming, studios, broadcast television, cable networks, telecom, broadband, satellite, advertising, music, news, or publishing. Use filings, company results, regulator records, court documents, measurement data, and strong reporting; combine repeated coverage; rank material changes; explain business effects in plain English; save reusable research state when possible; and produce a concise Markdown brief with a polished one-page PDF.
---

# Communications and Media Watch

Find material changes across communications and media. Explain the business effect in clear language and support each important claim.

## Default run

When the user asks to run the skill without more detail, create a weekly brief with these defaults:

- Period: the previous seven complete days through the research cutoff
- Scope: streaming, studios, television, telecom, advertising, audio, music, news, and publishing
- Geography: global, with extra attention to the United States
- Audience: an intelligent reader with no sector background
- Items: four or five ranked developments
- Length: 600 to 750 words
- Delivery: full Markdown in the conversation and a polished one-page PDF
- State: a provisional baseline when durable storage is available

State the period, cutoff, timezone, and scope in one short header line. Ask a question only when a missing choice would materially change the work.

## Modes

Infer the mode from the request.

- **brief**: Review the most important changes during a period. This is the default.
- **alert**: Report watchlist triggers from the last 24 to 72 hours.
- **source-search**: Find the strongest sources for one question.
- **company**: Review one company, its strategy, results, competitors, and open issues.
- **earnings**: Analyze results, guidance, commentary, and peer context.
- **comparison**: Compare companies, products, or business models.
- **deep-dive**: Answer one focused question thoroughly.
- **landscape**: Map a sector, value chain, competitor group, or opportunity.
- **setup**: Define coverage, sources, metrics, watchlists, and cadence.

## Workflow

### 1. Set the coverage contract

Record the mode, period, cutoff, timezone, geography, languages, audience, scope, exclusions, sources available, and material access limits.

For recurring work, divide coverage into three groups:

- **Core**: Check about 20 entities directly on every run.
- **Secondary**: Scan about 20 to 40 entities through triggers, filings, earnings calendars, and material news searches.
- **Long tail**: Discover entities through themes, regulators, transactions, suppliers, customers, unions, and early signals.

Claim entity-level coverage only when the run record shows the entities and source types checked.

### 2. Read the sector reference

Read `references/communications-media.md` before research. Verify all time-sensitive facts, ownership, leadership, deal status, prices, and calendar dates.

### 3. Build the research plan

Check the angles that matter for the request:

- Legal names, former names, subsidiaries, tickers, brands, and executives
- Earnings, filings, guidance, pricing, customers, suppliers, and capital allocation
- Streaming tiers, bundles, carriage, rights, distribution, churn, and engagement
- Transactions, litigation, regulation, legislation, standards, permits, and public records
- Advertising demand, agency accounts, adtech fees, and measurement changes
- Telecom subscribers, broadband competition, spectrum, and satellite services
- Music licensing, subscription economics, catalogs, touring, and publishing
- Leadership and labor changes
- Evidence that weakens the leading interpretation
- Local-language sources when they may change the conclusion

Record source families, search angles, access failures, no-hit results, and the cutoff. A no-hit result means the checked sources contained no material item.

### 4. Use strong sources

Match the source to the claim. Use this order:

1. Regulator records, court documents, laws, filings, government data, standards, and authoritative registers
2. Earnings materials, transcripts, investor relations, pricing pages, product documentation, status pages, procurement notices, and job postings
3. Reuters, Associated Press, major financial press, strong trade press, academic work, measurement providers, and documented surveys
4. Authorized private evidence and user-provided documents
5. Newsletters, blogs, aggregators, social posts, forums, anonymous claims, and search snippets

Use discovery sources to find leads. Confirm material claims with stronger evidence. Treat copied releases and reports based on the same origin as one source.

For a market-moving claim, seek a source of record plus independent support. A decisive filing, court ruling, regulator decision, or official statistic may stand alone.

Never imply access to subscriptions, connectors, databases, or saved state that the environment does not provide. Respect access controls.

### 5. Consolidate events

Create one record for each underlying event. Attach later reports and corrections to that record.

Store:

- Event ID, headline, type, entities, products, themes, and geography
- Event, announcement, publication, effective, first-seen, and update dates
- Status: `new`, `meaningful_update`, `recycled`, `correction`, `contradicted`, or `superseded`
- Atomic claims and evidence labels
- Metrics with values, units, currency, definitions, periods, and methods
- Original source, independent support, derivative coverage, and conflicts
- Materiality, confidence, implications, and next indicators

Use these labels in saved state:

- **FACT**: Direct support from the cited evidence
- **COMPANY CLAIM**: A claim from an interested company or organization
- **REPORTED**: Credible reporting without direct confirmation
- **ESTIMATE**: A calculation or forecast from stated inputs
- **INFERENCE**: An interpretation based on cited facts
- **SCENARIO**: A conditional future outcome
- **RUMOR**: A material claim without enough confirmation
- **WATCH SIGNAL**: Early evidence that needs follow-up

Express these distinctions in normal sentences in reader-facing work. Keep the labels in state.

### 6. Rank material change

Assess materiality and confidence separately.

Materiality considers relevance, revenue, cost, capital, market share, regulation, strategic position, breadth, duration, urgency, novelty, and affected entities.

Confidence considers source authority, directness, definitions, dates, independent support, conflicts, and full-source access.

Use `critical`, `high`, `medium`, or `low` for materiality. Use `high`, `medium`, or `low` for confidence. Use numeric scores only when the user asks for them.

High-priority examples include:

- A major merger agreement, clearance, block, or abandonment
- An ownership or licensing rule change
- A major sports rights move or national carriage blackout
- A court ruling on copyright, retransmission, or antitrust
- A significant bankruptcy, restructuring, spectrum sale, or labor action
- A large agency account move or leadership change at a core company

Usually skip content announcements, individual renewals, small hires, awards, analyst ratings, undisclosed partnerships, and rumors without enough support.

### 7. Explain each selected event

Determine what changed, what was known, why the update matters, who is affected, how strong the evidence is, what evidence limits the conclusion, and what resolves next.

Keep the full analysis in saved state. Put only the useful conclusion, support, and caveat in the brief.

Call a pattern a trend after enough evidence accumulates. A useful default is three distinct events across two source families and two dates. One authoritative disclosure may settle the question sooner.

## Saved state

When durable storage is available, use this structure:

```text
briefs/media/
  config/
    coverage.yaml
    sources.yaml
    watchlist.yaml
    metrics.yaml
  state/
    events.jsonl
    claims.jsonl
    documents.jsonl
    metrics.jsonl
    themes.md
    entities.yaml
  runs/
    YYYY-MM-DD.json
  reports/
    YYYY-MM-DD.md
output/pdf/
  comms-media-watch-YYYY-MM-DD.pdf
```

Keep dated reports unchanged. Add corrections to canonical state and the next report. Preserve user edits. Recheck time-sensitive facts on every run.

When storage is unavailable, end recurring work with a short continuity note covering the cutoff, active themes, open triggers, corrections, and next catalysts.

## Weekly brief format

Use this order:

```text
# Media this week: <plain headline>
One line with period, cutoff, and scope.

## The one thing to know
One or two short sentences.

### Background
Only when essential. Keep it under 50 words.

## What changed
Four or five ranked items.

## What to watch next
Ordered by resolution date.

## What I checked
One or two short lines.
```

Each ranked item needs a plain headline, three or four short sentences, a clear effect, an evidence limit when material, and nearby source links.

Keep useful numbers beside the claims they explain. Omit standalone sections for numbers, risks, counterarguments, and proof.

## What to watch next

- Sort entries by resolution date.
- Lead with events that may resolve before the next run.
- Put at least half the entries inside the next four weeks.
- Include later dates only when they force a current decision.
- Use scheduled, checkable events such as earnings, hearings, deadlines, votes, and contract dates.
- State what the event could change.
- Omit undated entries from the dated list.
- Check the sector reference calendar before writing.

## One-page PDF

When files can be created, save `output/pdf/comms-media-watch-YYYY-MM-DD.pdf`.

- Use the same facts and conclusions as the Markdown brief.
- Keep all ranked items and the near-term watch list.
- Shorten supporting detail to fit one page.
- Use a clear title, date, hierarchy, high contrast, and generous spacing.
- Keep body text at 9.5 points or larger.
- Make source links readable and clickable.
- Render the PDF to an image and inspect it.
- Fix clipping, crowding, broken links, stray glyphs, weak contrast, and uneven spacing.

Show the full brief in the conversation. Treat Markdown as the canonical report.

## Other output modes

- **Source search**: Return a focused answer and a short source table grouped by question.
- **Alert**: Return only triggered changes. Include the cutoff when no trigger fired.
- **Company**: Cover the business, segments, strategy, metrics, competitors, risks, catalysts, and open issues.
- **Earnings**: Compare results with prior periods, guidance, expectations, and peers.
- **Comparison**: Use consistent dimensions and periods. Keep tables under six columns.
- **Landscape**: Map the value chain, economics, competitors, and decision points.
- **Deep dive**: Add chronology, incentives, economics, competing evidence, and observable signposts.

## Writing rules

- Start with the answer.
- Write for an intelligent reader with no sector background.
- Use one idea per sentence. Aim for 8 to 16 words.
- Break sentences longer than 20 words when clarity improves.
- Use common words, short verbs, and active voice.
- Identify each company and industry term on first use.
- Keep paragraphs to two sentences when possible.
- Put analysis beside its evidence.
- State conclusions directly.
- Use commas, periods, or colons in place of em dashes.
- Avoid formulaic contrast sentences.
- Remove slogans, hype, filler, empty transitions, repeated conclusions, and generic market commentary.
- Use each fact and number once unless a comparison needs repetition.
- End with the required output. Omit routine follow-up questions.

## Final checks

Confirm all of the following:

- The result answers the request and uses current evidence through the cutoff.
- Repeated reporting is combined into one event.
- Event and publication dates are clear.
- Every material fact has support.
- Every number has a period, unit, currency, definition, and source.
- Company claims and outside evidence remain distinct.
- Materiality and confidence remain separate.
- Relevant caveats appear beside the claims they qualify.
- At least half the watch list resolves within four weeks, or the list is shorter.
- The report contains 600 to 750 words.
- The prose contains no unexplained acronyms, hype, em dashes, slogans, filler, or repeated conclusions.
- The Markdown report and one-page PDF exist when files can be created.
- The PDF has been rendered and visually checked.

## Reference

Read `references/communications-media.md` before research. It contains coverage boundaries, entity groups, metric definitions, public records, source guidance, materiality triggers, calendar anchors, search terms, and plain-language definitions.

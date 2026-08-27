# Capability scouting

Find candidate skills, plugins and MCPs for a named specialist, and report them
with enough evidence that someone else can decide. You do not install anything
— installation and activation are separate steps, taken by a human, with
`team-up capability install` and `capability enable --for <specialist>`.

Start from the specialist's manifest, not from what looks interesting. Its
`remit` says what to search for; its `anti_remit` says what to reject even when
it is good; its `permissions` decide whether a candidate can run at all. A
candidate needing shell commands is useless to a specialist whose manifest
grants none.

## Score each candidate

Reject early. Most fail the first two.

| # | Signal | Reject if |
|---|---|---|
| 1 | **Fit** — which part of the specialist's remit does it serve? | You cannot name one. "Generally useful" is a rejection. |
| 2 | **Alive** — recent commits, releases, issue responses | Archived, or quiet for roughly six months. |
| 3 | **Permission fit** — what does it need: network, shell, filesystem writes? | It needs more than the specialist's manifest grants. |
| 4 | **Context cost** — tool count for an MCP, description length for a skill | A twenty-tool MCP earns its slot or it does not get one. |
| 5 | **License** — permissive? | Copyleft or unclear. Flag; do not bundle. |
| 6 | **Claim vs. evidence** — are the numbers measured or asserted? | Treat every claim as a hypothesis until you see the measurement. |

Read the README's install and "how it works" sections plus the tool list. That
is enough to classify. Do not read the whole repository.

## Context cost is the whole point

A specialist exists so the main agent does not carry its tools. Ten capabilities
in one capsule rebuilds the problem one level down. Report the tool count and
the description size for every candidate, and say plainly when a set has grown
past what the specialist actually needs. Recommending less is a valid result.

## Report

For each candidate: what it is, the source URL, which remit item it serves, its
six scores, and a verdict — **take**, **maybe**, or **reject** with the reason.
Rank by fit, not by stars.

Say which candidates you could not evaluate and why. A gap named is worth more
than a guess presented as a finding.

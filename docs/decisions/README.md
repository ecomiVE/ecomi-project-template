# Architecture decision records

One short record per significant technical decision: what the situation was,
what we chose, what else we considered, and what it costs us.

**Write one when** a choice is expensive to reverse, when two reasonable people
could disagree, or when you can imagine someone asking "why on earth is it like
this?" in six months. That someone is usually you.

**Do not write one** for routine choices with an obvious answer.

## How

1. Copy `0000-template.md` to `NNNN-short-title.md`, next number in sequence.
2. Fill it in — half a page is normal, a full page is long.
3. Include it in the pull request that implements the decision.

Records are immutable. If a decision is later reversed, write a new record that
supersedes the old one and add a line at the top of the old one pointing to it.
The history is the point: knowing what we rejected is as useful as knowing what
we chose.

## Index

| # | Decision | Status | Date |
| --- | --- | --- | --- |
| 0001 | [Record architecture decisions](0001-record-architecture-decisions.md) | Accepted | YYYY-MM-DD |

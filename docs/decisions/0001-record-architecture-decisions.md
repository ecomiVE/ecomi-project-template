# 0001. Record architecture decisions

- **Status:** Accepted
- **Date:** YYYY-MM-DD
- **Deciders:** <names>

## Context

Technical decisions on our projects have been made in calls, chat threads and
pull request comments. The reasoning is not recoverable afterwards. When
someone returns to a project — often the same developer months later — they can
see what the code does but not why it was built that way, so the choice gets
either blindly preserved or blindly reversed.

Both failures cost real time, and both happen for the same reason: the context
was never written down.

## Decision

We will record significant technical decisions as short markdown files in
`docs/decisions/`, in the repository they concern, added in the pull request
that implements the decision.

## Alternatives considered

| Option | Why not |
| --- | --- |
| A page in Drive | Drifts from the code. Nobody opens it while working. |
| ClickUp comments | Tied to a task that closes; not searchable from the code. |
| Nothing (status quo) | The problem described above. |

## Consequences

- **Positive:** the reasoning lives beside the code and travels with it; new
  people can orient themselves without interrupting anyone; reversing a
  decision becomes a deliberate act.
- **Negative:** a few minutes per decision, and the judgement call about what
  counts as significant.
- **We accept:** some records will turn out to be unnecessary. That is cheaper
  than the ones we fail to write.

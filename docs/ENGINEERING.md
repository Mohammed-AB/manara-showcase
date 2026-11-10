# Manara Learning: engineering notes

A learning assistant should help readers return to the material. Manara pairs an English/Arabic reading experience with questions whose answers point back to the selected source.

## System path

~~~mermaid
flowchart LR
  Reading --> Question
  Question --> SelectedPassages
  SelectedPassages --> GroundedAnswer
  GroundedAnswer --> Citation
  Citation --> Reading
~~~

This diagram describes the demonstrated system boundary, not a production deployment topology.

## Decisions and tradeoffs

### Sources are part of the interaction

Answers link to a specific passage, and opening the citation moves the reader to the supporting text.

### Unsupported questions stay unsupported

The recorded journey includes a question that the selected reading cannot answer. The assistant states that limit instead of supplying an invented detail.

### A refresh is not a new allowance

Question limits survive refresh and restart. Session, concurrency and persistent spending controls bound the public-content experience.

## Review questions

- What evidence demonstrates **sources are part of the interaction**, and what would fail without it?
- What evidence demonstrates **unsupported questions stay unsupported**, and what would fail without it?
- What evidence demonstrates **a refresh is not a new allowance**, and what would fail without it?

## Verification boundary

14 offline acceptance groups, including quotas, concurrency, restart persistence and Arabic decoding. Three recorded live questions: English answer, unsupported question and Arabic answer with a source jump. Eight EN/AR routes checked with automated accessibility tooling; no automated AA violations in that check.

The showcase contains a small authored selection, not the full book library. Automated accessibility checks do not replace human review.

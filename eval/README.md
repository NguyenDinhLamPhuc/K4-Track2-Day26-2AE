# Eval: prosecution

`eval/prosecute.py` implements the local prosecutor for all 17 rubric classes. It reads the opponent’s L1 trace, answer, and card; emits evidence-backed claims; and applies the arena budget of at most four claims and one per family.

## Detector coverage

The detectors cover infrastructure (enforcement failure, stale read, write violation, protocol misuse), truth (wrong answer, fabricated citation, hallucination, ungrounded answer, unsupported precision), safety (authority exceeded, guardrail breach, privacy leak), quality (unflagged conflict, overreach, incoherence, non-responsive answer), and economy (wasteful calls). They are deliberately conservative because the prosecutor receives only a single exchange trace and has no world-loader or network access. Some world-dependent conditions cannot be independently confirmed from that input.

## Evidence and budget

Claims cite `evt:NNNN`, `answer.span:N`, or `anchor:<A>` refs. `ProsecutionBudget` validates claim shape and enforces the four-claim/five-family limits. Family A has one slot, so a higher-weight `enforcement_failure` claim can displace `protocol_misuse` in a live exchange.

## Local evaluation

The committed labelled fixture set contains 40 traces, including positive, near-miss, and clean cases. Score the implementation with:

```bash
python -m eval.prosecute
python -m pytest tests/test_prosecute.py -v
```

Latest local fixture score: **precision 1.000, recall 1.000, F1 1.000**, with zero false, unproven, or rejected claims. This is the fixture score, not a promise of the live referee’s model-based adjudication.

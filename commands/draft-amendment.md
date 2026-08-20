---
description: Draft an amendment to a clause, check it against the constitution, and file it
argument-hint: "[clause id] [what you want to change]"
---

Draft an amendment for `$ARGUMENTS`.

1. `hrc_lookup` the target clause. Quote the current text back to the member.
2. Draft replacement text with them. Keep the constitution's register — plain,
   declarative, no hedging. A clause is a rule, not an essay.
3. Write a rationale: what problem this solves, and what changes in practice.
4. Run `hrc_check` on the draft **before** filing. Report the verdict in full,
   including any conflicts it creates with other clauses.
5. Run `hrc_impact` to show what else would be affected.
6. Show the member the complete submission. Ask explicitly whether to file it.
7. Only on a clear yes, call `draft_amendment`.

If `hrc_check` returns a conflict, do not file. Fix the draft or tell the member
why the conflict may be worth arguing for, and let them decide.

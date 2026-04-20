# Input: Bridge fix diff

Component: Button/Primary
Correction: Changed border-radius from hardcoded `4px` to semantic token `$radius/md`.
Scope: global — this applies to all Button variants, not just Primary.
Reason: hardcoded values were introduced during a quick fix and were flagged in the DS lint run.

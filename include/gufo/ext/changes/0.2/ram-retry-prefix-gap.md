# RAM retry prefix gap

Add `TextRunnerRamCacheOptions::retry_gap_tokens` and its default constant
`kDefaultRetryGapTokens` in `src/ext/text.hpp`. The default is 64 tokens.
A RAM-only retry snapshot can be skipped when a published RAM checkpoint
can restore a strictly shorter exact prefix within this distance. Zero
disables the check. Continuation, history, shared and disk-persisted captures
retain their existing policy.

Reserve `--cache-retry-gap-tokens` as a core serving option.

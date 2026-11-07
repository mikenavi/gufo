# Maintained Gufo source

`mikenavi/stable` is the maintained build branch. Its upstream base is
`211dba49fa736466d55feb66870aeeff05bef38a` from `gufo-org/gufo`.
`local/source.lock.json` records the integrated feature commits and hashes of
the maintained files. Build from an exact commit or immutable fleet tag.

`fix/history-cache-boundaries` carries the independent cache change on upstream
`main` for a possible contribution. It contains no deployment settings, weights,
credentials or fleet build files. Publishing the branch does not open a PR.

The cache change selects up to nine anchors before image/tool-result blocks and seven recent
message boundaries within the existing RAM budget. Compatible image anchors
are protected at their aligned legal prefill stops during later captures;
removed images lose that protection.
Unstructured prompts retain their grid policy. The byte limit remains strict.

Use `local/build-release.sh` for the ordinary pinned Nix release. Read upstream
`AGENTS.md` and `docs/TESTING.md` for focused CPU and model checks. Cache-plan,
serving, text-runner, chat-template and vision-cache CPU regressions cover the
feature, including split tool/image messages and aligned anchors under memory
pressure. These corrections passed CPU checks; GPU qualification and activation
remain separate steps. Model qualification and managed activation are recorded separately by
the deployment owner; source publication alone does not qualify either.

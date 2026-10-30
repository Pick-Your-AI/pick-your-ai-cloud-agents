# Contributing

Follow the [organization contribution policy](https://github.com/Pick-Your-AI/.github/blob/main/CONTRIBUTING.md), subject to the repository's live access settings and rulesets.

- Search existing issues, pull requests, and related research before proposing new work.
- Agree on scope and use GitHub assignees for accepted ownership. A team role alone does not assign work.
- Keep research evidence, implementation, and deployed behavior distinct. Label unknown or untested capabilities explicitly.
- Existing shared contracts remain owned by the research repository. Propose changes through its versioned review process rather than copying and editing generated schemas here.
- Do not commit credentials, account details, personal or customer data, or large evidence downloads.
- Submit changes through a pull request. The default branch requires independent approval, including approval after the latest push. Complete any applicable checks before merging.

There is no application, build process, or test suite in this initial repository. Define appropriate validation with the first implementation proposal; do not report tests as passed when none were run.

## Routing decisions

For an unresolved decision, first read the existing issue, its assignees, relevant
decision record and related pull requests. Preserve accepted ownership and local
review, evidence, security and release requirements. Routing identifies a contact;
it does not grant access, appoint an owner, authorize publication or waive a gate.

Use the canonical [escalation guide](https://github.com/Pick-Your-AI/.github/blob/main/docs/governance/ESCALATION.md) and
[versioned routing policy](https://github.com/Pick-Your-AI/.github/blob/main/governance/escalation-policy.json). These links depend on the organization
governance change merging; until then, use its reviewed checkout and describe the
route as provisional. Do not claim the central tooling is installed or active.

The order is repository team → repository maintainer → repository lead maintainer
→ applicable parent teams → CompleteDotTech. Record a disposition at each level,
including unresolved, vacant, pending-acceptance or inaccessible roles; membership,
team-management status and repository permissions do not establish accepted
operational ownership. Keep owner placeholders for the final fallback. Do not
silently skip an unresolved role or treat a proposed mapping as accepted.

An operator with read access must refresh the private snapshot before resolving:

```sh
python /path/to/org-checkout/governance/router.py refresh --policy /path/to/org-checkout/governance/escalation-policy.json --snapshot /private/path/routing-snapshot.json --status /private/path/routing-status.json
python /path/to/org-checkout/governance/router.py resolve --policy /path/to/org-checkout/governance/escalation-policy.json --snapshot /private/path/routing-snapshot.json --repo Pick-Your-AI/pick-your-ai-cloud-agents --max-age-seconds 86400 --status /private/path/routing-status.json
```

Here `86400` is an **operator-selected example**, not an approved default. Select
an appropriate explicit maximum age; a proposed policy value does not supply one.
Check that refresh succeeded. If refresh fails, stop recipient selection and
report the failure; the last successful snapshot is retained for diagnosis, not
as a current route. Report stale or incomplete coverage explicitly. Keep snapshots,
raw API responses, rosters and private
identities outside public Git and public issues. Share only the necessary public
team destination and a sanitized decision summary.

When escalation is needed, include the decision needed, current responsible role,
prior disposition and proposed next recipient. Reuse information already in the
issue or PR; routine contributions need no full escalation history. Send nothing
and change no assignment automatically. Sensitive reports follow the existing
private security/support process.

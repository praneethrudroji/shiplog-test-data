# shiplog-test-data

A small sandbox repo used to generate real GitHub activity for testing
[shiplog](https://github.com/praneethrudroji/shiplog-plugin), a Claude Code plugin that tracks a
developer's own work across Azure DevOps and GitHub and answers questions about it in plain
language.

## Why this repo exists

shiplog's GitHub source is tested with recorded fixtures, which proves the code handles the shapes
it was given correctly. It does not prove the code behaves correctly against a live account: real
pagination, a real token, real timing. This repo is the other half of that, a place to open real
pull requests, leave real comments, and run a real sync against them.

It also exercises shiplog's date attribution feature on purpose. A comment or PR description here
might say something like "yesterday I finished this" or "last Friday I noticed a bug", the same way
a real developer writes on a real PR. shiplog resolves that kind of phrase into an actual calendar
date rather than just recording when the comment was posted. Using real GitHub data to test this
caught a genuine bug: an attribution that resolved "last Friday" to a Saturday, accepted with high
confidence until a deterministic weekday check was added to catch exactly that. See
[shiplog's decision record](https://github.com/praneethrudroji/shiplog-plugin/blob/main/docs/DECISIONS.md)
for the full account.

## What is in here

Nothing meaningful on its own, just PRs, commits, and comments created to have something real for
shiplog to sync. Expect it to accumulate more of the same over time: more PRs, more comments,
sometimes deliberately awkward phrasing (typos, ambiguous dates, weekday mentions) aimed at testing
shiplog's date attribution rather than at building anything.

## Related

- [shiplog-plugin](https://github.com/praneethrudroji/shiplog-plugin), the actual plugin this repo
  exists to test.

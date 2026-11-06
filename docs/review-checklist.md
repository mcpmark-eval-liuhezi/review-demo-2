# Pull Request Review Checklist

Use this checklist whenever you're reviewer-ing (or self-reviewing) a pull request. Work through it top to bottom and tick each box as you go.

## 1. Pull request basics

- [ ] Title describes the change clearly (present tense,imperative style, e.g. "Add pull request review checklist")
- [ ] Description states **what** changed and **why**, with a short summary of the problem solved
- [ ] Anyone can review without reading your inbox — no missing context in the description
- [ ] Labels, size limits, and milestone are set correctly
- [ ] Branch name is short and meaningful (e.g. `feature/review-checklist`), and it targets the right base branch

## 2. Code review

- [ ] The diff fits on a screen or two — if it doesn't, split it or add a也就是 note explaining why this belongs in one PR
- [ ] Related tests pass locally and cover the new behaviour
- [ ] No tabs, inconsistent indentation, commented-out code, or debug `console.log` leftovers
- [ ] Error handling is deliberate, not silent (a catch or log that does nothing is a smell)
- [ ] Public API or behaviour changes are called out for downstream consumers

## 3. Security and robustness

- [ ] No hardcoded secrets, tokens, or API keys in the diff
- [ ] Shape of any new input is validated and sized (buffer, time, memory limits, SQL/command escaping)
- [ ] Dependencies pulled in are reviewed for known vulnerabilities
- [ ] Auth and permissions are not silently widened by this change
- [ ] Password-style values use a proper hash with a per-entry salt

## 4. Documentation and traces

- [ ] Public functions, config options, and new endpoints have docs
- [ ] README matches what users will actually see
- [ ] Runbook or CHANGELOG updated where relevant

## 5. Reviewer behaviour

- [ ] Approve the change **or** request changes explicitly — never just close with no reply
- [ ] Praise the good parts, not just the problems
- [ ] If asking for changes, link ONLY issues that would block merge
- [ ] Blocking, non-blocking, and questions are all labeled in the PR timeline

## 6. After the merge

- [ ] Run all post-merge checks (CI, deploy, smoke tests)
- [ ] If docs changed, open a follow-up issue to keep the docs in sync
- [ ] Reflect if the checklist caught a real mistake — use it next time

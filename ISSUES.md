# Writing an issue

People read an issue in a list first and open it second. These rules are for both readings, and they apply the same way to people, coding agents and NorBot.

Pick the form: **Bug** when something is broken, **Feature** when users or the team need something new, **Task** for engineering work nobody outside the team sees.

## Title

- 60 characters or less. 70 is the hard limit.
- A bug title states the symptom and where it happens.
- A feature or task title states the outcome, in the imperative.
- No `[Bug]:` or `[Feature]:` prefix. The form sets the issue type.
- One problem per issue. A title that needs "and" is two issues.

| Instead of | Write |
|---|---|
| `[Bug]: banner copy wrong` | `Inkorg says "bytt ägare" after a säljare removes the bostad` |
| `Chat improvements` | `Keep Visa lead on archived leads in Backoffice chats` |
| `[Chore]: Cut the lint noise, and clear the mechanical ones` | Two issues: `Print one line per lint warning` and `Fix the mechanical lint warnings` |

## Body

Two people read every issue. The product owner reads the top and stops. A developer reads all of it.

1. **In short comes first, for everyone.** 2 or 3 sentences, 60 words at most. Say what goes wrong or what is missing, who notices, and what happens if nothing changes. Use product words: no code names, file paths or internal terms. A reader who stops there can triage the issue.
2. **The Problem or Goal explains how it works, for developers.** Write the plain sentence first and the file path after it. Give one example with real numbers. Define an internal term the first time you use it.
3. **A decision or blocker goes directly after it**, never at the bottom.
4. **Done when is 3–7 checks anyone can run**, each naming where to check: the environment, the page, the command. More than 7 checks means the issue is two issues. A check nobody can tick objectively gets rewritten.
5. **Evidence goes under Context, with the commit or date it was measured.** Counts and file lines go stale, and the reader needs to know when to check them again.
6. **Long logs, queries and tables go in a `<details>` block.** Its summary line states the result: `<summary>Production, 2026-09-29: 2 794 inbox queries in 30 minutes (normal: 251)</summary>`. Nothing the reader must act on goes inside it.
7. **Short sentences.** 25 words at most. Outside `<details>`, an issue has 450 words at most.
8. Swedish product terms stay Swedish, with å, ä and ö.

Example of In short:

> When an agent with a very large inbox sends many messages quickly, the inbox never finishes loading. It starts over at each new message. On 29 September this kept the production database at full load for several minutes.

## Picking up an issue

- Check every number and file reference again before you start. Say on the issue what changed.
- If Done when is missing or cannot be checked, comment and ask. Do not guess.

## Linking from a PR

- `Related: #N` when the PR works on the issue. It moves the issue to In Progress.
- `Ref #N` when the PR only mentions the issue. It moves nothing.
- Never `Closes`, `Fixes` or `Resolves`. They close the issue before QA.

## Bots and agents

The same rules apply. A bot that files an issue from a chat message asks the requester for Done when if the message gives nothing to derive it from. It does not invent checks.

## Why these rules

- Missing information is the most common defect in bug reports, and steps to reproduce are what developers use most ([Bettenburg et al., FSE 2008](https://thomas-zimmermann.com/publications/files/bettenburg-fse-2008.pdf)).
- A title identifies the problem, not the fix, in under 60 characters ([Mozilla bug writing guidelines](https://bugzilla.mozilla.org/page.cgi?id=bug-writing.html)).
- Readers scan the first two words of a line, and only 16 % read word by word ([NN/g](https://www.nngroup.com/articles/first-2-words-a-signal-for-scanning/), [NN/g](https://www.nngroup.com/articles/how-users-read-on-the-web/)).
- Readable bug reports get fixed faster, and too-long text is a problem developers name ([Bettenburg et al., FSE 2008](https://thomas-zimmermann.com/publications/files/bettenburg-fse-2008.pdf)).
- 80 % of readers prefer plain language, and experts prefer it more ([Trudeau 2012](https://www.michbar.org/file/barjournal/article/documents/pdf4article2079.pdf)). Sentences of about 14 words give over 90 % comprehension ([GOV.UK](https://insidegovuk.blog.gov.uk/2014/08/04/sentence-length-why-25-words-is-our-limit/)).
- Two levels of detail work; more than two do not ([NN/g, progressive disclosure](https://www.nngroup.com/articles/progressive-disclosure/)).
- Contributors and maintainers both object to templates that ask for irrelevant information ([IEEE TSE 2022](https://ieeexplore.ieee.org/document/9961906/)), so each form requires only what the work cannot start without.

---
name: find-buyers
description: Use when the user wants to find companies or decision-makers that match an ideal customer profile, size a market, build a prospect list, look up who works at a named company, or export contacts. Triggers on "who should buy from us", "find me contacts at", "how many companies match", "build a prospect list", "size this market", "export these leads".
when-to-use: prospecting, market sizing, ideal customer profile, lead list, decision-makers, buyer research
---

# Finding buyers with Argorant

Argorant holds verified B2B contact data. This skill is about using it in the
right order, because the order is what keeps it cheap.

## The one rule

**Counting and previewing are free. Revealing and exporting spend the user's
credits.** Never reveal or export without saying what it will cost and getting
a yes. A user who is still shaping a segment does not want to pay for each
attempt, and they should not have to.

## The order that works

1. **Understand who they sell to.** If the user has not described a buyer, ask
   two questions and no more: what kind of company, and which roles. If they
   have a website, that is usually faster than a description.

2. **Count first.** `argorant_count_people` costs nothing. The number tells you
   immediately whether the segment is usable. Under a few hundred is usually too
   narrow to run a campaign on; hundreds of thousands usually means a filter is
   missing.

3. **Preview before committing.** `argorant_preview_people` returns masked rows.
   Read them back to the user. This is where a wrong segment gets caught: if the
   job titles look off, the filters are off.

4. **Narrow, then re-count.** Iterate here, not after paying. Adjust industry,
   size band, seniority or country and count again. Still free.

5. **Only then reveal or export.** `argorant_reveal_people` for a handful,
   `argorant_create_export` for a list. Say what it costs before you call it.

## Reading a count

A count is a population, not a promise. Say what it is: "there are 14,281
companies matching that profile" is right; "you will get 14,281 leads" is not.

## Looking up a single company

`argorant_company_people` takes a domain. Use it when the user names a company
rather than describing a type. It is free and it is the fastest way to show
someone that the data is real.

## Exports

An export runs asynchronously. Create it, then poll `argorant_export_status`.
Do not create a second export while the first is still running: it spends
credits twice for the same rows.

## When something is missing

If a segment comes back near zero, the filters are almost certainly too narrow
rather than the data being absent. Loosen the most specific constraint first,
usually the job title, and count again before telling the user there is nothing
there.

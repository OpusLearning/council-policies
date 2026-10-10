# Council policies by area: section 19, EOTAS and alternative provision

This is a reference dataset of what the 153 local authorities in England responsible for education
publish about education for children who cannot attend school. For each authority it records four
kinds of entry:

- its **section 19 / medical needs policy**: the council's published document on education for
  children who cannot attend school because of illness, exclusion or otherwise;
- its **EOTAS policy or guidance**, where it publishes one: education otherwise than at school;
- **alternative provision**: what the council publishes about education arranged away from school;
- the **free local SEND advice service** for the area (usually called SENDIASS).

It holds 612 entries: one entry for each of the four kinds for each of the 153 authorities.

The dataset is a reference list, not a summary of what the documents say. Every figure in it comes
from a council's own site, and the title and link are the council's own.

- **Canonical page:** <https://blog.jameswallace.tech/councils/>
- **Machine-readable change history:** <https://blog.jameswallace.tech/councils/changes.json>
  (JSON Feed 1.1, built from the same change list that the page shows as "What changed").

## Files

| File | What |
|---|---|
| `data/council-policies.csv` | The current list, one row per council and kind. UTF-8 with a BOM, RFC 4180, CRLF line endings. |
| `data/council-policies.json` | The same rows as a JSON array of objects, one object per row. |
| `data/council-policies-2026-10-09.csv` | The fixed copy as it stood when the 153 authorities were published on 9 October 2026. |
| `data/council-policies-2026-10-09.json` | The same fixed copy as JSON. |

Later corrections change the live files, not the dated copy.

## Columns

The rows come from the generator that builds the page, `sites/blog/scripts/council-list.mjs`
(its `DATA_COLUMNS` list), so the files and the page cannot disagree.

| Column | Meaning | Values |
|---|---|---|
| `council` | The local authority's name, as it names itself. | Text; 153 distinct names. |
| `ons_code` | The Office for National Statistics code for the area. | Text, e.g. `E06000015`. |
| `region` | The grouping used on the page. | One of: East Midlands and neighbours, West Midlands, Yorkshire and the Humber, East of England, London, North East, North West, South East, South West. |
| `kind` | Which of the four kinds of document the row records. | One of: `Section 19 / medical needs policy`, `EOTAS policy or guidance`, `Alternative provision`, `Local SEND advice service`. One row for each kind for each council. |
| `status` | Whether a document was found for this row. | One of: `found`, `none found`, `not checked yet`. |
| `title` | The document's own title, as the council published it. | Text; empty unless `status` is `found`. |
| `url` | The address of the document or page. | Text; empty unless `status` is `found`. |
| `document_date` | The date shown on the document itself, or the council's "last updated" date where the page carries one, copied as the council shows it. | Text; empty when the document carries no date or was not found. |
| `date_checked` | The date the row was last checked. | `YYYY-MM-DD`. |
| `how_checked` | How the entry was checked (see below). | One of: `checked by hand`, `two separate checks agreed`, `decided on a third check`, `one check, on the council's own site`, `not checked yet`. |
| `evidence` | A short quotation from the source that shows why the row was recorded, with any email address removed. | Text; usually empty. |
| `consultation_contacted_on` | The date the council or its advice service was asked about its entry. | `YYYY-MM-DD`; empty when no contact has been made. |
| `consultation_followed_up_on` | The date of a follow-up contact. | `YYYY-MM-DD`; empty when none. |
| `consultation_replied_on` | The date a reply was received. | `YYYY-MM-DD`; empty when none. |
| `consultation_outcome` | Plain words for what came back. | Text; empty when none. |

## How it was checked

This is a reference list, not a summary of what the documents say. It holds 612 entries across 153
councils in England: one entry for each of the four kinds of document for each council. An entry is
a slot, not always a link: it may be a document that was found, "none found" or "not checked yet".

Every link was opened and checked on the date shown for it (8 October 2026 or 9 October 2026).

How the 612 entries were checked: 156 checked by hand; 276 where two separate checks, made without
sight of each other, chose the same page or both found nothing; 169 decided on a third check that
looked at every candidate page; 11 found on a single check on the council's own site.

The 39 councils listed when the page was written were checked by hand. For the other 114, added on
9 October 2026, the searching and the separate checks were carried out with automated research
tools, under the direction of James Wallace Education, and every link chosen was then opened again
to confirm it loads. An independent review pass then tried to prove each published entry wrong, and
its corrections were applied.

136 entries are marked "none found". The advice-service links were checked on 9 October 2026.

## What "none found" means

"None found" means a document could not be found for that column on the council's own site on the
date checked. **It does not mean the council has no such policy.** A policy may be unpublished,
held only on request, or published under a different name.

## Known limits

- The dataset records what each council publishes, as found on the dates shown. It does not
  describe what any policy says, and nothing in it says whether any council meets its legal duties.
- "None found" is a statement about a search on a date, not about a council's practice.
- The 153 authorities are the upper-tier authorities responsible for education (county, unitary,
  metropolitan borough and London borough). District, parish and town councils do not hold this
  responsibility and are not listed.
- Councils reorganise their websites, merge teams and rename services, so a link that worked on the
  date checked may move later. If one stops working, search the council's own site for the title.
- Some councils publish a single document that covers more than one column, so the same link can
  appear more than once in a council's rows.
- The titles of the documents belong to the councils that published them. The links go to the
  councils' own sites.

## The councils will check their own entries

This is an initial release. The councils and their local advice services are being asked to check
their own entries from 12 October 2026, so entries may change considerably as they reply. The
Consultation columns record each contact and reply, and the change history records each change.

## Corrections

If something here is wrong, please say so. Email **hello@jameswallace.tech**, or use the contact
form at <https://jameswallace.tech/contact?topic=council-list-correction>. Corrections change the
live files; the dated copy keeps the 9 October 2026 version as it was.

## Licence

The dataset is published under the **Creative Commons Attribution 4.0 International licence**
(CC BY 4.0). See `LICENSE` for the full text. You are free to share and adapt it, for any purpose,
as long as you:

1. credit it to James Wallace Education;
2. link to <https://blog.jameswallace.tech/councils/> using that exact address;
3. say if you have changed the data or combined it with other data;
4. do not suggest that James Wallace Education endorses you or your use of it.

## How to cite

> James Wallace Education (2026). *Council policies by area: section 19, EOTAS and alternative
> provision.* https://blog.jameswallace.tech/councils/ (accessed on the date you used it).

Machine-readable citation metadata is in `CITATION.cff`; a Frictionless Data Package description is
in `datapackage.json`; Zenodo metadata is in `.zenodo.json`.

If you use the data, James would be glad to hear: **hello@jameswallace.tech**. That is a request,
not a condition.

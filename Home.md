---
title: Home
tags: [moc, home, index]
type: reference
---

> [!IMPORTANT]
> First time opening this vault? Read [[SETUP FIRST]]. The live tables below require the Dataview community plugin.

> [!SUMMARY]
> This vault is the analytical workspace for the [[Collection Overview|UAP file collection]]. Source PDFs live in the parent `Collection` folder. This vault stores structured notes, cross-references, and analytical layers built on top of those sources.

## Start here

- [[SETUP FIRST]] - install Dataview plugin so the live tables render
- [[Vault Conventions]] - controlled vocabulary, tag taxonomy, frontmatter standards, naming rules
- [[Collection Overview]] - one-page summary of what's in the source folder
- [[Acronyms and Glossary]] - resolve any unfamiliar military or intelligence term

## Maps of content

- [[MOC - Incidents by Year]]
- [[MOC - Incidents by Location]]
- [[MOC - Platforms and Units]]
- [[MOC - Sources]]
- [[MOC - Patterns and Theses]]

## Folder structure

| Folder | Purpose |
| ------ | ------- |
| `00 - Inbox` | Drop-in zone for unprocessed notes |
| `01 - Conventions and Templates` | Vault rules and note templates |
| `02 - Incidents` | One note per UAP observation event |
| `03 - Sources` | One note per source PDF |
| `04 - Locations` | Geographic entities (places, AORs, MGRS regions) |
| `05 - Platforms and Units` | Aircraft types and military units |
| `06 - Sensors and Equipment` | EO/IR pods, radars, weapons systems |
| `07 - Witnesses` | Named witnesses or witness categories |
| `08 - Phenomenology` | Observed behaviors, shapes, signatures |
| `09 - Patterns and Theses` | Cross-cutting analytical hypotheses |
| `10 - MOCs` | Navigation pages built from Dataview queries |
| `99 - Reference` | Acronyms, glossary, timeline, release authorities |

## Quick stats

```dataview
TABLE WITHOUT ID
  "Incidents" AS "Type",
  length(rows) AS "Count"
FROM "02 - Incidents"
GROUP BY true
```

```dataview
TABLE WITHOUT ID
  "Sources" AS "Type",
  length(rows) AS "Count"
FROM "03 - Sources"
GROUP BY true
```

```dataview
TABLE WITHOUT ID
  status AS "Status",
  length(rows) AS "Count"
FROM "02 - Incidents"
WHERE status
GROUP BY status
SORT length(rows) DESC
```

## Recent additions

```dataview
TABLE
  date_event AS "Date",
  aor AS "AOR",
  status AS "Status"
FROM "02 - Incidents"
SORT file.ctime DESC
LIMIT 10
```

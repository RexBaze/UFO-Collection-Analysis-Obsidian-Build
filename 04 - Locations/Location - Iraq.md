---
title: Location - Iraq
date: 2026-05-27
tags: [location, aor/centcom]
type: location
---

## Geography

country:: Republic of Iraq
region:: Middle East
aor:: centcom

## Significance

Operation Inherent Resolve AOR. Multiple U.S. and coalition airbases; active counter-ISIS operations 2014-present. Heavy ISR coverage, fighter overwatch.

## Incidents

```dataview
TABLE
  date_event AS "Date",
  platform AS "Platform",
  status AS "Status"
FROM "02 - Incidents"
WHERE contains(location, this.file.link)
SORT date_event ASC
```

## Related

- Adjacent: [[Location - Syria]] | [[Location - Iran]]
- Operation: [[Operation Inherent Resolve]]

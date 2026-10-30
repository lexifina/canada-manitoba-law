# How this repository was made (Manitoba)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Manitoba Laws (King's Printer): the "Legislative history" table on each C.C.S.M. Act page | <https://web2.gov.mb.ca/laws/statutes/index_ccsm.php> | 2026-10-29 | Facts only (chapter, title, enacting and amending Act citations, proclamation and in-force dates); no text of any Act is reproduced |
| Wikidata | <https://www.wikidata.org/wiki/Q1948> | 2026-10-30 | CC0 1.0 |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `catalogue` | Catalogue of the C.C.S.M. Acts of Manitoba: legislative history facts only (enacting and amending Acts, in-force dates) | 487 | 1985-09-30 to 2026-10-26 |
| `legal-system` | Manitoba: legal system facts (Wikidata) | 2 | 1870-07-15 to 2026-10-24 |

The build made 866 commits:

| Commits | Kind |
| ---: | --- |
| 2 | first version of an act |
| 864 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-30.
- 1 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 771 laws in the record.
- 1252 tags.

## Dates

Each commit is dated at noon (America/Winnipeg) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: A catalogue entry is dated by the in-force date the legislative history table gives; entries without one are dated by the day the tables were current. Entries describe Acts and are not law text. https://web2.gov.mb.ca/laws/statutes/index_ccsm.php

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `c171efcbc7abfab99e9e81032da57d73c4b387c78c49bd3c661915cdb64ddf6b` (2541632 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a97ff7ea62c3c7595c5668a297d533da0b74373c`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

Not yet run for this build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- No law text is published. Manitoba's copyright notice for its laws allows copies of an Act or regulation without permission only for study or research, for use in legal proceedings or for providing legal advice; any other copy needs the written consent of the King's Printer, and the Copyright Act (Canada) gives provincial statutes no exemption.
- The catalogue holds one file per C.C.S.M. Act with facts from its legislative history table: the Act's chapter and title, each enacting or amending Act citation, and the provisions, proclamation and in-force dates the table lists for it, one line each.
- Each line is dated by the in-force date it gives and credited to the Act it cites. Lines with no in-force date on or before the day the tables were current (2026-10-26) are dated that day and credited to the catalogue: the table records proclamations only, so Acts in force on assent or on a date they state carry no date here. Nothing is guessed.
- Titles and chapter numbers are those the tables give on 2026-10-26, even in earlier versions; Acts repealed before then are not listed.
- Wikidata facts (CC0) form the "legal-system" act, dated by the province's inception and otherwise by the latest revision of the Wikidata item before retrieval (2026-10-24).

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code with Claude Opus 5.5 wrote Lexifina's code and chose the sources; it did not write or alter any legal text. The code is deterministic and runs no model.

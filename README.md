# Manitoba: law history in git

The law of Manitoba as a git history: one file per provision, one commit per law on the day it took effect, and the law that made each change as the commit's author. `git blame` names the law behind every paragraph; `git log` lists every change; picking a date gives the text in force that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

## What this repository holds

**Metadata only, no law text, because Manitoba allows copies of its Acts only for study or research, for legal proceedings or for legal advice.** The Manitoba Laws copyright notice says any other copy needs the written consent of the King's Printer, and Canada's Copyright Act gives provincial statutes no exemption. This repository records, for each Act in the Continuing Consolidation of the Statutes of Manitoba (C.C.S.M.), which Acts enacted and amended it and when the changes came into force, and a handful of open facts about the province's legal system. To read an Act, go to [Manitoba Laws](https://web2.gov.mb.ca/laws/). Text will be added if the King's Printer gives consent.

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `catalogue/` | Catalogue of the C.C.S.M. Acts: legislative history facts only | 487 | 487 days from 30 September 1985 to 26 October 2026 (all 516 C.C.S.M. Acts; 5401 history lines, 1968 with an in-force date) |
| `legal-system/` | Legal system facts from Wikidata (CC0) | 2 | The province's inception, then the facts as Wikidata held them on 24 October 2026 |

## Source

The catalogue's facts come from the "Legislative history" table on each C.C.S.M. Act's page at [Manitoba Laws](https://web2.gov.mb.ca/laws/statutes/index_ccsm.php), published by the King's Printer for Manitoba, as current on 26 October 2026: the chapter and title, the enacting and amending Acts (as SM or RSM citations), and the provisions, proclamation status and in-force dates listed against each. No text of any Act or of those pages beyond these facts is reproduced. The Wikidata facts are from [Wikidata](https://www.wikidata.org/wiki/Q1948) (CC0).

## Dates

Each history line is dated by the in-force date the table gives for it and credited to the Act it cites (for example `sm-2014-c-25`). The table records proclamations, so an amendment that came into force on assent, or on a date written in the Act, has no date in it; such lines, and those not yet proclaimed, are dated 26 October 2026 (the day the tables were current) and credited to the catalogue. Nothing is guessed. Commits are at noon, Manitoba time (America/Winnipeg, with daylight saving time).

## How it is checked

Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`) and must match `corpus.json`; results are in `REPRODUCE.md`.

## What "author" means

The author of a commit is the law (or, for facts, the retrieval) that made the change, with an e-mail address that cannot exist (`<law key>@web2.gov.mb.ca.invalid`). The committer is always Lexifina.

## Limits

Only Acts in the C.C.S.M. as it stood on 26 October 2026 are listed; repealed Acts, private and municipal Acts and regulations are not. Titles and chapter numbers are the current ones, even in earlier versions. The in-force history is as complete as the tables are: many amendments carry no date. Nothing here is an official record of the statutes.

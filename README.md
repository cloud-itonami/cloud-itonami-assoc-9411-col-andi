# cloud-itonami-assoc-9411-col-andi

Industry rule/history catalog for **ANDI** (Asociación Nacional de
Empresarios de Colombia, historically Asociación Nacional de
Industriales) — the TWENTY-SECOND entry aligned to **ISIC 9411**
(activities of business, employers, and professional membership
organizations), alongside
[`-9411-sau-fsc`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-sau-fsc)
(Saudi Arabia),
[`-9411-aut-wko`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-aut-wko)
(Austria),
[`-9411-irl-ibec`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-irl-ibec)
(Ireland),
[`-9411-nzl-businessnz`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-nzl-businessnz)
(New Zealand),
[`-9411-cze-spcr`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-cze-spcr)
(Czech Republic),
[`-9411-ind-cii`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-ind-cii)
(India),
[`-9411-zaf-busa`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-zaf-busa)
(South Africa),
[`-9411-bra-cni`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-bra-cni)
(Brazil),
[`-9411-ken-kam`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-ken-kam)
(Kenya),
[`-9411-can-chamber`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-can-chamber)
(Canada),
[`-9411-mex-coparmex`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-mex-coparmex)
(Mexico),
[`-9411-ita-confindustria`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-ita-confindustria)
(Italy),
[`-9411-nld-vnoncw`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-nld-vnoncw)
(Netherlands),
[`-9411-kor-kcci`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-kor-kcci)
(South Korea),
[`-9411-arg-uia`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-arg-uia)
(Argentina),
[`-9411-bel-feb`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-bel-feb)
(Belgium),
[`-9411-dnk-di`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-dnk-di)
(Denmark),
[`-9411-swe-sn`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-swe-sn)
(Sweden),
[`-9411-fin-ek`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-fin-ek)
(Finland),
[`-9411-tha-fti`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-tha-fti)
(Thailand), and
[`-9411-chl-sofofa`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-chl-sofofa)
(Chile), and
[`-9411-cri-uccaep`](https://github.com/cloud-itonami/cloud-itonami-assoc-9411-cri-uccaep)
(Costa Rica). Part of the
[`cloud-itonami`](https://github.com/cloud-itonami) compliance-fact
family (ADR-2607141700, `cloud-itonami-compliance-fact-federation`,
in `com-junkawasaki/root`).

## Sourcing note

This repo fills Colombia's previously-open association-axis gap (one
of the 6-country gap list recorded at tick 156). Colombia now has
real, individually verified facts across all three axes: country
([`cloud-itonami-iso3166-col`](https://github.com/cloud-itonami/cloud-itonami-iso3166-col)),
municipality
([`cloud-itonami-municipality-col-bogota`](https://github.com/cloud-itonami/cloud-itonami-municipality-col-bogota)),
and association (this repo).

Twenty-seven entries, each carrying the page it came from
(`:source-article`) and the verbatim span the claim rests on
(`:source-quote`). Twenty-four are ANDI's own pages and documents:
the statutes (PDF, signed Cartagena, 10-11 August 2017), the
Declaración de Principios Éticos del Empresario Colombiano, the 2003
declarations on social responsibility and on the UN Global Compact,
the 2003 resolution on decent work, the 2012 declaration on
Colombia's OECD accession, and the about, English, legal-affairs,
economics, industry, innovation and CESLA pages. Three rest on
`es.wikipedia.org`.

### The first party is reachable only through the Internet Archive

`andi.com.co` refuses non-browser clients. Measured 2026-09-11: `/`
answers HTTP 403 with a WAF page; every other path — `Quiénes
Somos`, the statutes PDF, anything — drops the connection ("Empty
reply from server", "Connection timed out"). July's note recorded
"socket hang up" on every page tried. The site is, however, captured
at `web.archive.org` — the about page as recently as 2026-08-27 — and
that is what this catalog cites, as
`https://web.archive.org/web/<timestamp>/<original>`. The
provenance keyword `:official-andi-archived` declares both the host
that serves the URL and the host it must wrap, and the checker
refuses an archived provenance whose wrapped original is not on
`andi.com.co`. The capture timestamp is in the URL; `:retrieved-at`
is when this catalog read it.

Two consequences are recorded rather than hidden. The July catalog
said the founding city was disputed (Wikipedia then wrote Usaquén in
one place and Antioquia in another); ANDI's own page says Medellín,
its statutes fix Medellín as the domicile (Art. 2), and Wikipedia's
body text now also says Medellín. And ANDI's English page says
"headquarters in Bogotá" while its Spanish page and statutes say
Medellín; the catalog asserts the statutory domicile and notes the
discrepancy in the entry's title.

Two first-party documents were fetched and **not** used: the
anniversary booklet (`ANDI-ANIVERSARIO-1.pdf`) is image-only and
yields no text to quote, and the 2025 strategy deck is a consultant's
document marked confidential on every page, hosted publicly but not
ANDI's own words. The Mega 2025 is cited from the about page instead.

### Reachability is not support

A URL that returns HTTP 200 without the claim reads exactly like one
that carries it, so every entry pins a verbatim span and `--live`
requires that span to still be in the fetched page. Where a document
dates itself away from the claim — the statutes in their signature
block, the 2003 resolutions in their closing line — the entry carries
that second span as `:date-quote`, and the date is checked against
it; `--live` requires both spans.

The soft-404 control is kept from the siblings and made
archive-aware: for an archived source it fetches the capture of a
path that was never archived on the original host. `web.archive.org`
answers that with 404 (measured on all three origins cited), so a
rotted archived path is a refusal — the source could not be read —
rather than a pass. Shown to bite: one character changed in the
statutes PDF's filename produced exactly that.

Two things about these sources that the checker had to learn: the
site's CMS leaves zero-width spaces inside words (`gremi<U+200B>o`,
`p<U+200B>roblemas`), and the ethics declaration's PDF renders its
bullets as a private-use Symbol-font glyph glued to the first word of
each item. Both are stripped before comparison on both sides; the
ethics entry was the one finding of the first `--live` run until the
second was.

## Scope

A **read-only reference/archive** catalog — not an Advisor⊣Governor
actuation actor. It proposes or executes nothing on ANDI's behalf.

Coverage is reported honestly (see `association.facts/coverage`): an
association not in `catalog` has **no spec-basis**, full stop — never
fabricate one.

## Data

`data/datascript-tx.edn` is **the only place the facts are
authored**. Both readings are generated from it:

- `data/datascript-tx.edn` — the catalog, source of truth.
- `src/association/facts.kotoba` — the Clojure reading
  (`association.facts`). Generated.
- `src/association_facts.kotoba` — the Kotoba port, which reaches
  the Kotoba oracle, wasm and both native ISAs. Generated.
- `schema/association-rule.edn` — DataScript schema.

Query it alongside other `cloud-itonami`/`etzhayyim` compliance-fact
sources via `com-junkawasaki/root`'s
`scripts/compliance-fact-query.cljs`.

Dates are ISO with `:date-precision` saying how precisely the *source*
dates the fact; the checker builds the Spanish forms for the specific
date being checked (`11 de septiembre de 1944`, `Agosto de 2003`). An
entry with no date says why (`:date-unknown-because`); the ethics
declaration's PDF, for instance, carries no date in its text, and the
2003 decent-work resolution is what records that the LI General
Assembly adopted it.

No personal name of any office-holder is persisted. The presidency
page, the statutes' signature block and Wikipedia's list of presidents
carry names; they are cited only for what they say about the
institution.

## Checking it

```
nbb scripts/verify-catalog.cljs          # structural, offline
nbb scripts/verify-catalog.cljs --live   # fetch every :url (needs curl +
                                         # pdftotext), require every
                                         # :source-quote and :date-quote to
                                         # still be in it, and run the
                                         # soft-404 control
nbb scripts/gen-kotoba-port.cljs --check # both readings match the data
clojure -M:parity                        # compile the Kotoba port and
                                         # compare every field of every
                                         # entry with the Clojure reading
```

Exit codes: `0` clean, `1` findings, `2` REFUSED (could not check —
not a pass). `clojure -M:test` collects nothing since the 2026-09-10
rename of `.clj`/`.cljc` to `.kotoba` and exits 0; `-M:parity` loads
both `.kotoba` files by path and is the run that counts.

## License

AGPL-3.0-or-later (matches the `cloud-itonami-iso3166-*` /
`-municipality-*` / `-assoc-*` / `-lei-*` convention). Policy text
itself remains ANDI's; this repo stores only citation metadata
(id/title/url/dates/verbatim spans), not full text.

(ns association.facts
  "Industry rule/history catalog for ANDI (Asociación Nacional de
  Empresarios de Colombia, historically Asociación Nacional de
  Industriales) -- a 64th industry-association-level source (see
  cloud-itonami-assoc-9411-sau-fsc, -9411-aut-wko, -9411-irl-ibec,
  -9411-nzl-businessnz, -9411-cze-spcr, -9411-ind-cii, -9411-zaf-busa,
  -9411-bra-cni, -9411-ken-kam, -9411-can-chamber, -9411-mex-coparmex,
  -9411-ita-confindustria, -9411-nld-vnoncw, -9411-kor-kcci,
  -9411-arg-uia, -9411-bel-feb, -9411-dnk-di, -9411-swe-sn, -9411-fin-ek,
  -9411-tha-fti, -9411-chl-sofofa for the first twenty-one) per
  ADR-2607141700 (cloud-itonami-compliance-fact-federation). The
  TWENTY-SECOND entry aligned to ISIC 9411 (activities of business,
  employers, and professional membership organizations). Fills
  Colombia's previously-open association-axis gap (one of the
  6-country gap list recorded at tick 156) -- Colombia now has real,
  individually verified facts across ALL THREE axes (country:
  cloud-itonami-iso3166-col statute.facts; municipality:
  cloud-itonami-municipality-col-bogota; association: this entry).

  andi.com.co's own domain returned a 'socket hang up' connection
  failure on every page tried this tick (both the 'Quiénes Somos'
  page and a news article). Both entries here were instead directly
  WebFetch-verified against es.wikipedia.org's own article, which
  quotes verbatim: 'Fue fundada el 11 de septiembre de 1944 en
  Usaquén' and 'varios gerentes de empresas de Antioquia se dieron
  cita el 11 de septiembre de 1944' (the 11 September 1944 date is
  unanimous across every source checked, though the article itself
  is internally inconsistent about the founding CITY -- Usaquén, a
  Bogotá locality, versus Antioquia/Medellín-region company managers
  -- so this catalog states only the date, not a disputed founding
  city). REJECTED SOURCE ERROR: Wikidata Q5641268's own 'inception'
  statement lists '11 September 1994' (not 1944) with ZERO
  references -- a 50-year discrepancy from every other source
  checked and unsupported by any citation, almost certainly a
  Wikidata data-entry typo; this claim was checked, found
  unsupported and contradicted by the directly-read Wikipedia body
  text plus independent WebSearch corroboration, and was NOT used
  (matching this session's established discipline of scrutinizing
  even structured-data sources rather than trusting them by
  default). The founder's name (Cipriano Restrepo), incidentally
  encountered, is NOT persisted here.

  An association not in `catalog` has NO spec-basis, full stop; never
  fabricate one.")

(def catalog
  "association-slug -> vector of association-rule entries."
  {"andi"
   [{:association-rule/id "andi.founding-1944-09-11"
     :association-rule/title "ANDI (Asociación Nacional de Industriales, now Asociación Nacional de Empresarios de Colombia) founded 11 September 1944 (es.wikipedia.org, corroborated by independent WebSearch results; NOTE: Wikidata Q5641268's own inception statement erroneously lists '11 September 1994' with zero references -- rejected as an apparent data-entry error, not used)"
     :association-rule/association "andi"
     :association-rule/isic "9411"
     :association-rule/country "COL"
     :association-rule/kind :governance-program
     :association-rule/url "https://es.wikipedia.org/wiki/Asociaci%C3%B3n_Nacional_de_Industriales"
     :association-rule/url-provenance :wikipedia-corroborated
     :association-rule/established-date "1944-09-11"
     :association-rule/retrieved-at "2026-07-18"
     :association-rule/topic #{:governance}}
    {:association-rule/id "andi.dinero-ranking-2017"
     :association-rule/title "In 2017, ANDI partnered with revista Dinero to create the first version of its business ranking ('escalafón') (es.wikipedia.org)"
     :association-rule/association "andi"
     :association-rule/isic "9411"
     :association-rule/country "COL"
     :association-rule/kind :governance-program
     :association-rule/url "https://es.wikipedia.org/wiki/Asociaci%C3%B3n_Nacional_de_Industriales"
     :association-rule/url-provenance :wikipedia-corroborated
     :association-rule/established-date "2017"
     :association-rule/retrieved-at "2026-07-18"
     :association-rule/topic #{:governance}}]})

(defn spec-basis [association] (get catalog association))

(defn coverage
  ([] (coverage (keys catalog)))
  ([associations]
   (let [have (filter catalog associations)
         missing (remove catalog associations)]
     {:requested (count associations)
      :covered (count have)
      :covered-associations (vec (sort have))
      :missing-associations (vec (sort missing))
      :note (str "cloud-itonami-assoc-9411-col-andi Wave 0 (ADR-2607141700): "
                 (count (get catalog "andi")) " ANDI entries seeded "
                 "with Wikipedia corroboration (andi.com.co returned a socket hang up on every "
                 "page tried this tick; Wikidata's own '1994' inception claim was checked, found "
                 "unsupported/contradicted, and rejected). "
                 "Extend `association.facts/catalog`, never fabricate an id/url.")})))

(defn by-topic [association topic]
  (filterv #(contains? (:association-rule/topic %) topic) (spec-basis association)))

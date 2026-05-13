# Legalize HR

### Hrvatski propisi u Markdown formatu, verzionirani putem Gita.

Svaki propis je datoteka. Svaka izmjena je commit.

Konsolidirani propisi iz [Narodnih novina](https://narodne-novine.nn.hr) — Službeni dio.

Dio projekta [Legalize](https://github.com/legalize-dev/legalize) · [legalize.dev](https://legalize.dev)

> **Rana faza** — Ovaj se repozitorij aktivno razvija. Struktura datoteka, povijest commitova i sadržaj mogu biti bitno promijenjeni, uključujući potpunu regeneraciju.

## Brzi početak

```bash
# Kloniraj hrvatske propise
git clone https://github.com/norislav/legalize-hr.git

# Povijest izmjena određenog propisa
git log --oneline -- hr/HR-NN-2022-151-2343.md
```

## Struktura

```
hr/
  HR-NN-YYYY-{broj}-{redni_broj}.md    — svaki propis kao zasebna datoteka
```

Vrsta propisa (zakon, uredba, pravilnik, odluka, …) navedena je u YAML zaglavlju svake datoteke, a ne u strukturi direktorija.

## Format

Svaka datoteka sadrži:

- **YAML frontmatter** — metapodatke: naslov, identifikator, datum objave, status, vrsta, donositelj, izvor
- **Markdown tekst** — konsolidirani tekst propisa sa strukturom dijelova, glava, poglavlja i članaka
- **Tablice** — očuvane kao Markdown *pipe* tablice kada je to moguće

Commitovi koriste povijesni datum objave svake izmjene. Svaki commit sadrži trailere s identifikatorima propisa i izmjene, što omogućuje rekonstrukciju potpune povijesti propisa putem `git log`.

### Opseg

Obrađuju se propisi iz **Službenog dijela** Narodnih novina od 1990. nadalje. Međunarodni i Oglasni dio zasad nisu uključeni.

### Pokrivenost

Pokrivenost punog kataloga: **96 938 / 97 116 = 99,82%**.

Preostalih 178 propisa nemaju Markdown datoteku jer Narodne novine same ne objavljuju njihov tekst u obliku iz kojeg ga je moguće izdvojiti:

- **~140 odluka o uvođenju kurikula** (Ministarstvo znanosti i obrazovanja, 2024.–2025.) — NN ih prikazuje kao tanak HTML omotač s ugrađenim PDF-om; obvezujući tekst kurikula (program, satnica, ishodi učenja) nalazi se u rasterskim slikama unutar PDF-a i zahtijevao bi OCR za izdvajanje.
- **5 zakona** koje NN nikada nije digitalizirao u tekstualnom obliku — uključujući Ustavni zakon o ljudskim pravima i slobodama i o pravima etničkih i nacionalnih zajednica (NN 65/1991) i Zakon o izmjenama Zakona o izvršavanju Državnog proračuna za 2020. (NN izričito prikazuje "Sadržaj je nedostupan").
- **~33 razno** — rješenja o imenovanjima, ne-kurikulske odluke, te sadržaji brojeva NN — metapodatkovni unosi bez tijela.

Nedostaci su NN-ovi, ne pipelineovi. Cjeloviti metapodaci za svih 178 propisa dostupni su preko ELI URI-ja (`metadata.source`).

## Izvor

Svi podaci dolaze iz [Narodnih novina](https://narodne-novine.nn.hr) — službenog glasila Republike Hrvatske.

Ažuriranja obrađuje [Legalize Pipeline](https://github.com/legalize-dev/legalize-pipeline) — Python alat koji pretvara službene propise u Markdown s Git poviješću.

## Licenca

Obrađeni propisi u ovom repozitoriju objavljeni su pod [MIT licencom](LICENSE).

Izvorni propisi javno su dostupni putem Narodnih novina u skladu s hrvatskim pravom.

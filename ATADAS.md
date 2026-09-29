# Weboldal átadási dokumentum

**Projekt:** K.T BYGG HUNGARY KFT · egyoldalas bemutatkozó weboldal
**Kapcsolattartó:** Varga Gyula
**Fájl:** `index.html` (egyfájlos oldal, külső függőség csak a Google Fonts)
**Képek:** `img/` mappa (webp, optimalizálva) + `img/eredeti/` (eredeti JPG-ek, változatlan)
**Utolsó frissítés:** 2026. szeptember

---

## 1. Hogyan nyitható meg

- **Kettős kattintás az `index.html`-re** — böngészőben azonnal működik, telepítés nélkül.
- Éles üzemhez: a teljes mappa (index.html + img/) feltölthető bármilyen tárhelyre (pl. tárhelyszolgáltató FTP-je, Netlify, Vercel). Nincs szerver-igény, nincs adatbázis.
- **Jelenleg élő publikus elérhetőség:** a projekt GitHub Pages-en van (repo: `varga-gyula-generalkivitelezes`). Minden push után néhány percen belül automatikusan frissül.

## 2. A könnyen cserélhető dolgok

| Mit | Hol az `index.html`-ben |
|---|---|
| Cégnév (most: **K.T BYGG HUNGARY KFT**) | `<title>`, header `.brand-name`, footer, `og:title` |
| Telefonszám (+36 70 251 2561) | keresés: `702512561` — header, callbar, kapcsolat szekció, footer |
| E-mail (ktbygg.hungary@gmail.com) | keresés: `ktbygg.hungary` — kapcsolat szekció + footer |
| Régió (Budapest és Pest megye) | keresés: `Budapest` — title, meta, topbar, hero, rólunk, GYIK, footer |
| Logó | a `.brand-mark` SVG-k (header, footer) + a `<link rel="icon">` favicon |

## 3. Hogyan bővíthető új csúszkás párral

Az előtte–utána párok a script tetején a **`BA_CONFIG`** listában vannak. Egy sor = egy pár, **kizárólag csúszkás** megjelenítéssel:

```
{
  before: 'img/ba-....webp',  after: 'img/ba-....webp',
  w: 1150, h: 863,            // a képek valós mérete (px) — a layout-ugrás ellen
  altB: '...', altA: '...',   // a két állapot valódi leírása
  title: '...', cat: 'Medence',
  ratio: '4/3',               // a keret képaránya
  desc: '...'
}
```

**Szabály:** csak olyan fotópár kerülhet a listába, amely **azonos vagy közel azonos nézőpontból** készült (ugyanabból a szögből fotózva, csak más munkafázisban). Amelyik képhez nincs valódi pár, az nem kerül fel — nem találunk ki párt.

**Új pár hozzáadása:** a két webp az `img/` mappába (kb. 1150–1200 px oldalhossz), egy új blokk a `BA_CONFIG`-ba, a `w`/`h` értékek a valós méret — kész.

## 4. Amit az oldalon NEM találsz (és nem is írtunk bele)

- alapítási év, évtizedes tapasztalat, projektszám, dolgozói létszám
- garanciaidő, minősítés, díj, ügyfélvélemény
- ilyen számok megjelenítése csak akkor kerül az oldalra, ha valós adat érkezik.

## 5. Ismert javítanivalók éles üzem előtt

1. **Domain után**: canonical link + éles OpenGraph-kép (1200×630) beállítása.
2. A hero-fotó cserélhető bármikor: az `img/ba-p2-utana.webp` fájl helyére másik, hasonló arányú (4:3) kép.

## 6. Kép-karbantartás

- Az eredeti fotók **változatlanul** megmaradnak az `img/eredeti/` mappában — a webp-ek ebből készültek, kb. 1150–1200 px oldalhosszra méretezve.
- Újrafeldolgozáshoz (ugyanaz a minőség, mint a mostani): bármilyen eszközzel 1200 px-re méretezett, q~72-es WebP a megfelelő formátum.

## 7. Státusz

- ✅ Csak hiteles, azonos nézőpontú előtte–utána csúszkás párok vannak fent (5 pár: emelt medence, medencetest, fóliázás→kész medence, terasz-lépcső szerkezet→burkolat, külső kőlépcső burkolás alatt→kész).
- ✅ Elsődleges konverzió a telefonhívás (`tel:` linkek: header, mobil hívósáv, kapcsolat szekció, footer).
- ✅ Reszponzív: 320–1440 px szélességen tesztelve, nulla kicsúszás.
- ⬜ Domain bekötése után: canonical + OG-kép.

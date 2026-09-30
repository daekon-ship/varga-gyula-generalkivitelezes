# Weboldal átadási dokumentum

**Projekt:** K.T BYGG HUNGARY KFT · egyoldalas bemutatkozó weboldal
**Kapcsolattartó:** Varga Gyula (ügyvezető)
**Fájl:** `index.html` (egyfájlos oldal, külső függőség csak a Google Fonts)
**Képek:** `img/` mappa (webp, optimalizálva), `img/g/` (galéria-deriváltak), `img/eredeti/` (eredeti JPG-ek, változatlan)
**Utolsó frissítés:** 2026. szeptember — v4 redesign + production release QA

**ÉLES DOMAIN:** https://epuletesmedence.hu/ (canonical, og:url, og:image ide mutat)
**Publikus GitHub mirror:** daekon-ship/varga-gyula-generalkivitelezes (Pages másodlagos)

**Végleges tartalmi állapot:**
- Galéria: **17 kép**, munkafolyamat-kronológia (5 fázis-fejléc), minden felirat a valós képtartalmat írja le
- Előtte–utána csúszkák: **6 hiteles pár** (p2 medence szerkezet, p6 medencetest, p13 fóliázás→kész, p14 terasz-lépcső, p15 kőlépcső, p17 medence-lépcsősor) — csak azonos nézőpontú, valós párok
- Kontakt: +36 70 251 2561 · ktbygg.hungary@gmail.com · Kapcsolattartó: Varga Gyula ügyvezető
- Működési terület: Budapest és Pest megye

**v4.1 változások:**
- Galéria átrendezve **munkafolyamat-kronológiába** (fázis-fejlécekkel): Földmunka és szerkezet → Medence építés → Lépcsők és burkolás → Kész medence → Kész ház és kert (23 kép).
- Production QA: ba-p16 pár kivéve (nem azonos nézőpont), lépcső/medence képfeliratok teljes auditja, canonical/og → epuletesmedence.hu
- Új kész- és fázisképek a galériában (villa homlokzat kész, lépcső kész, támfal, fóliázás, burkolás fázisok).
- Logó hozzáadva: `logo/logo.svg` + `logo-{1024,512,256,128}.png` (küldhető az ügyfélnek).
- Mobiljavítás: hero alsó sáv (`.hero-strip`) mobilon nem zsugorodik össze, wrapper törik.

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

## 3. Galéria bővítése

Az összes munkafotó a scriptben lévő **GALLERY** listában van. Új kép hozzáadása:
1. Az eredeti JPG az `img/eredeti/` mappába (változatlanul megmarad)
2. Két webp derivált: `img/g/[név]-1200.webp` (galéria) és `img/g/[név]-1800.webp` (lightbox), kb. q70–72 minőség
3. Egy új sor a `GALLERY` listában: `{ id:'[név]', o:'álló'|'fekvő', cap:'rövid leírás', w2:true|false, h2:true|false }`
   - `w2`: dupla szélességű csempe · `h2`: dupla magasságú csempe (nagy kiemeléshez)

A lightbox automatikusan működik: nyilakkal lépkedhet, Escape/zár-gomb bezár, fókuszcsapdás, keyboard-elérhető.

## 3b. Hogyan bővíthető új csúszkás párral

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

## 7. Státusz (v4 redesign után)

- ✅ 40 valós munkafotó van fent: hero + 3 kiemelt projekt + 5 hiteles csúszkás pár + 25 képes galéria lightboxszal
- ✅ Csak hiteles, azonos nézőpontú előtte–utána csúszkás párok (5 pár)
- ✅ Elsődleges konverzió a telefonhívás (`tel:` linkek: header, mobil hívósáv, kapcsolat szekció, footer)
- ✅ Reszponzív: 320–1440 px szélességen tesztelve, nulla kicsúszás, külön mobil kompozíció
- ✅ SEO: canonical, Open Graph, JSON-LD (csak hiteles adatokkal), 1 db H1, szemantikus struktúra
- ✅ Akadálymentesítés: fókuszcsapdás lightbox, Escape kezelés, aria-labelek, reduced-motion támogatás
- ⬜ Domain bekötése után: a canonical URL-t frissíteni az éles domainre + éles OG-kép (1200×630)

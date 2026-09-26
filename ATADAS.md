# Weboldal átadási dokumentum

**Projekt:** Varga Gyula — Generálkivitelezés · egyoldalas bemutatkozó weboldal
**Fájl:** `index.html` (egyfájlos oldal, külső függőség csak a Google Fonts)
**Képek:** `img/` mappa (webp, optimalizálva) + `img/eredeti/` (eredeti JPG-ek, változatlan)
**Utolsó frissítés:** 2026. szeptember

---

## 1. Hogyan nyitható meg

- **Kettős kattintás az `index.html`-re** — böngészőben azonnal működik, telepítés nélkül.
- Éles üzemhez: a teljes mappa (index.html + img/) feltölthető bármilyen tárhelyre (pl. tárhelyszolgáltató FTP-je, Netlify, Vercel). Nincs szerver-igény, nincs adatbázis.

## 2. A könnyen cserélhető dolgok

| Mit | Hol az `index.html`-ben |
|---|---|
| Cégnév (most: „Varga Gyula – Generálkivitelezés") | `<title>`, header `.brand-name`, footer, `og:title` |
| Telefonszám (+36 70 251 2561) | keresés: `702512561` — a script tetején a `CONTACT` blokkban és a linkekben |
| E-mail (gyulavarga68@gmail.com) | keresés: `gyulavarga68` — a `CONTACT` blokk és a mailto linkek |
| Logó | a `.brand-mark` SVG-k (header, footer) + a `<link rel="icon">` favicon |
| Szolgáltatás-szövegek | a „SZOLGÁLTATÁSOK" szekció kártyái |

A `CONTACT` blokk a script tetején egyetlen helyen tartja az elérhetőséget — az űrlap mindenhonnan onnan olvas.

## 3. Hogyan bővíthető képekkel

A képek két listában vannak a script tetején:

1. **`BA_CONFIG`** — előtte–utána párok. Egy sor = egy pár:
   - `before` / `after` a két képfájl,
   - `title` (kártya címe), `cat` (kategória-címke),
   - `pair: true` → húzható csúszka (csak azonos nézőpontú fotóknál!), `pair: false` → egymás melletti nézet.
2. **`GALLERY_CONFIG`** — a galéria. Egy sor = egy kép:
   - `src`, `alt` (a valódi képtartalom!), `width`, `height`,
   - `title`, `place`, `cat` (medence / burkolas / kulter),
   - opcionális `pos: '50% 80%'` — a kártya-nézet fókuszát állítja, ha a középvágás nem jó.

Új kép: a webp a `img/` mappába, egy új sor a listába — kész.

## 4. Amit az oldalon NEM találsz (és nem is írtunk bele)

- alapítási év, évtizedes tapasztalat, projektszám, dolgozói létszám
- garanciaidő, minősítés, díj, ügyfélvélemény
- ilyen számok megjelenítése csak akkor kerül az oldalra, ha valós adat érkezik.

## 5. Ismert javítanivalók éles üzem előtt

1. **Űrlap-küldés**: a form most e-mail-kliensben (mailto) nyitja meg az üzenetet. Éles üzemhez ajánlott egy űrlap-végpont (pl. Formspree) bekötése.
2. **Domain után**: canonical link + éles OpenGraph-kép (1200×630) beállítása.
3. **Adatkezelés**: a footer most e-mail hivatkozást ad meg — hivatalos adatkezelési tájékoztató tölthető a helyére.
4. A hero-fotó cserélhető bármikor: az `img/ba-p2-utana.webp` fájl helyére másik, hasonló arányú (4:3) kép.

## 6. Kép-karbantartás

- Az eredeti fotók **változatlanul** megmaradnak az `img/eredeti/` mappában — a webp-ek ebből készültek, 1200 px oldalhosszra méretezve.
- Ha egy kártya-kivágás mégsem jó: a `GALLERY_CONFIG` adott sorában a `pos` értékkel finomítható (`'50% 30%'` = feljebb néz, `'50% 85%'` = lejjebb).
- Újrafeldolgozáshoz (ugyanaz a minőség, mint a mostani): bármilyen eszközzel 1200 px-re méretezett, q~72-es WebP a megfelelő formátum.

## 7. Státusz

- ✅ Minden fotó ellenőrizve (integritás + vágás), a galériából a nem egyértelmű/ismétlődő képek eltávolítva.
- ✅ Reszponzív: 320–1440 px szélességen tesztelve, nulla kicsúszás.
- ✅ Előtte–utána szekció, galéria szűrőkkel, lightbox, űrlap, mobil hívósáv működik.
- ⬜ Éles tartalom-feltöltés (képek száma bővíthető bármikor), formbackend, domain.

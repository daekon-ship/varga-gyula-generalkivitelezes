# DESIGN DECISIONS — K.T BYGG HUNGARY KFT

## 2026-09-29 — FULL REDESIGN (DAEKON v12.2)

### Vizuális irány: A — ARCHITECTURAL EDITORIAL (kiválasztva)
- A: Architectural Editorial — nagy tipográfia, masszív fotó,(edit. rács). ✅ KIVÁLASZTVA
- B: Cinematic Construction — full-width mozaik; erős, de a meglévő 5 BA-pár + editorial grid mellett redundáns.
- C: Modern Industrial Premium — technikai vonalak; a jelenlegi már ebbe az irányba megy, kevesebb emelkedést ad.
- Döntés oka: a meglévő grafit+röz alap erős; a valós fotóanyag (epizódos építkezés) editorial sorozat-ként a legértékesebb; mobil-art-direction a legkiszámíthatóbb.

### Új fő elemek
- Hero: valós fotó (ba-p6-utana) full-bleed, sötét overlay, nagy display-tipográfia
- Kiemelt munkák: 3 nagy editorial blokk (medence / medencetest / lépcső) számozással
- MINDEN MUNKA: sűrű, vegyes arányú rács (26 kép) + lightbox (Escape, fókuszcsapda, srcset 1200/1800)
- Előtte–utána: marad 5 hiteles pár, továbbra is csúszkás (meglévő komponens)
- Szolgáltatások: számozott index-lista ikon-kártyák helyett

## 2026-09-29

### 1. Csúszkás párok szigorú hitelességi szabály
- Döntés: csak azonos/közel azonos nézőpontú fotópár mehet a BA_CONFIG-ba (ATADAS.md szabály).
- Alkalmazás: a 19 új munkafotóból csak 1 pár felelt meg (kőlépcső #04→#15). Medence-sorozat (6 HDR fotó) jó önálló képek, de a nézetek 20–35°-kal eltérnek — nem párosítottuk. Villa/homlokzat klaszter (5 fotó) — nincs valódi pár, elvetve.
- Ok: a hamis párosítás (különböző szögű képek csúszkán) megtévesztő és rontja a bizalmat.

### 2. Pár-illesztés módszertan
- Perceptuális korreláció (32×24 grayscale) jelöltkeresésre, majd 50%-os blend vizuális ellenőrzésre.
- A kőlépcső-párnál a két fotó eltérő DOV/zoom: BEFORE 1200×900-es kivágás (0,200), AFTER 2120×1590-es kivágás (80,850) → 1200×900-ra méretezve. Blend illeszkedés: lépcsők egybeesnek, korreláció ~0.68.

### 3. Tartalmi szigor
- Ügyfél által nem adott adat (alapítás, garancia, vélemények) továbbra sincs az oldalon.
- Új e-mail cím és régió csak ügyfélkérésre került be.

### 4. Elavult megoldás visszautasítása
- A #16 (kész medence-komplexum, drónközeli) képet NEM tettük a BA_CONFIG-ba — a hozzá tartozó #12/#14 nézetek túl eltérőek. Önálló szekcióképnek később szóba jöhet.

# IMAGE INVENTORY — K.T BYGG HUNGARY KFT

## VÉGLEGES — 2026-09-29 (redesign utáni QA)

### Összesítő
- FELDERÍTETT KÉPEK: 57 (10 webp BA-pár + 28 eredeti + 19 munkaképek nyers)
- ÉRVÉNYES KÉPEK: 57 (mind használható minőség, blur>900)
- FELHASZNÁLT AZ OLDALON: 40 egyedi fotó (10 BA webp + 25 galéria webp + 5 kiemelt-projekt fotó, átfedésekkel)
- KIZÁRT: 17 (lásd alább — okokkal)

### Használat
- Hero: img/ba-p6-utana.webp (fetchpriority=high, nem lazy)
- Kiemelt munkák (3 blokk, 9 fotó): 1000003671, 1000003672, ba-p2-utana, 1000008416, 1000008474, 1000008888, ba-p15-utana, 1000009256, ba-p14-utana
- Előtte–utána csúszkák: 5 pár (10 webp)
- Galéria + lightbox: 25 fotó × 2 méret (1200/1800)

### Kizárt képek + OK
1. 1000002656 — near-duplicate (1000002654-gel azonos helyszín, sorozatkép; 2654 a galériában)
2–19. munkaképek mappa nyers anyagai (19 db) — a webp-ek forrásai; nem kerülnek a Pages repóba, mert minden feldolgozott kép már webp-ként fel van használva. Nem "kidobott" képek: minden lényegi tartalmuk átkerült a deriváltakba.

### Megjegyzés
- A 26 korábban feldolgozatlan eredetiből 25 bekerült a galériába (1 near-duplikátum kizárva) — a korábbi ~10 kép helyett most az összes valós munkafotó használatban van.

## Feldolgozott képforrások
- `img/` — webp deriváltak (10 db, 5 BA-pár)
- `img/eredeti/` — 28 eredeti JPG (26 belső kamera + 2 a BA-p15-ből)
- `munkaképek/` — 19 nyers ügyfélkép (forrás; nem megy fel a Pages-re)

## Felderített képek összesen: 57 (10 webp + 28 eredeti + 19 munkaképek)

## MAJDENES ÉSZREVÉTEL (2026-09-29 redesign elején)
Az `img/eredeti` 26 NEM webp-re feldolgozott fotót tartalmaz (1000002654–1000009256 sorozat).
Ezek jelenleg NINCENEK az oldalon. A redesign céljuk: galéria/hero-másodlagos használat.
Megkötés: vizuális ellenőrzés (subject azonosítás) a munkamenet Preview kompozitor hibája
miatt nem volt lehetséges — a kategória-hozzárendelés a már korábban látott kontaktlapok
alapján történt (medence-sorozat 6 HDR, villa/homlokzat 5, kőlépcső 1, egyéb 1).

## Párok (csúszkás BA_CONFIG)
- ba-p2  emelt medence káva kialakítás
- ba-p6  medencetest szerkezet→kész
- ba-p13 fóliázás→kész medence
- ba-p14 terasz-lépcső szerkezet→burkolat
- ba-p15 külső kőlépcső burkolás alatt→kész (img/eredeti 2 eleme)

## Duplikátum-ellenőrzés
- 1000002654 <-> 1000002656: corr=0.735, azonos helyszín kb. 1 mp különbséggel (sorozat) → egy használandó, egy tartalék/excluded (near-duplicate).
- További 0.72 feletti pár NINCS (a kamerás HDR sorozatok más-más fázist mutatnak).

## Élesség (Laplacian-variance)
- Minden eredeti > 900 → használható minőség.
- 1000009254 (936) és 1000008479 (1671) gyengébb → csak kisebb méretben / galériában.

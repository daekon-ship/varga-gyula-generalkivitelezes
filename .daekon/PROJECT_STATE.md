# PROJECT STATE — K.T BYGG HUNGARY KFT (varga-gyula-generalkivitelezes)

## Current goal (2026-09-29, v4 redesign)
Kész a teljes "Architectural Editorial" redesign: hero valós fotóval, 3 kiemelt projekt-blokk, 5 BA csúszka, 25 fotós galéria lightboxszal, számozott szolgáltatás-index, JSON-LD. Az összes valós munkafotó használatban (40/40 egyedi kép).

## QA eredmények (DOM-alapú, a szekció screenshot-kompozitorja hibás)
- Funkcionális: lightbox nyit/zár/Escape/nyilak/fókusz OK; BA csúszkák mind OK; mobilmenü OK
- Reszponzív: 390/768/1440 px — nincs overflow, burger váltás OK
- Képek: 0 törött, mind width/height-tal (CLS-védett), LCP eager+high
- Brand: K.T BYGG HUNGARY KFT konzisztens (5 előfordulás), VARGA GYULA mint cégnév: nincs

## Completed work (2026-09-29)
- munkaképek mappa (19 fotó) átnézve; perceptuális hasonlóság + blend-igazítás alapján párkeresés
- 1 új valós, azonos nézőpontú pár: külső kőlépcső (burkolás alatt → kész) = ba-p15
- Elavult kísérleti párok (P3, P5, P6, P7, villa-klaszter, #16 nézet) ELVEVE — nem azonos nézőpont
- Tartalmi frissítés (ügyfélkérés): Varga Gyula = ügyvezető + kapcsolattartó; e-mail: ktbygg.hungary@gmail.com; régió: Budapest és Pest megye (title, meta, topbar, hero, chip, rólunk, GYIK, footer)
- ATADAS.md szinkronizálva
- Mobil (390px) és desktop (1440px) vizuális ellenőrzés: hero, chip, Rólunk kártya, kapcsolat, footer, 5. csúszka — rendben, nincs overflow
- Csúszka funkcióteszt OK (range → --pos → moved)

## Open tasks
- Domain bekötése után: canonical + og:url + OG-kép frissítése az éles domainre (1200×630)
- Ha új fotópár érkezik: csak azonos nézőpontú mehet a BA_CONFIG-ba; új galériakép: lásd ATADAS.md 3. szakasz

## Technical constraints
- Egyfájlos statikus oldal (index.html), külső függőség csak Google Fonts
- Képek: img/ webp ~1200px q72; eredetiek változatlanul img/eredeti/
- BA_CONFIG a script tetején; w/h a valós méret
- Deployment: GitHub Pages, push → auto (repo: daekon-ship/varga-gyula-generalkivitelezes)

## Next best action
Domain + OG-kép, amikor az ügyfél megadja; új referenciapárok érzékeny szűrése.


## v4.1 — 2026-09-30
- 5 új munkakép feldolgozva (munkaképek/): rózsaszín villa kész (3 nézet — megegyezik a villa-haz-kesz-1/2/3-mal, hash-ellenőrizve), kert kész nagy, lépcső zsaluzás/burkolás pár.
- Galéria 23 elemre bővülve, munkafolyamat-kronológia + .g-fazis fázis-fejlécek (5 fázis).
- 2 új BA-pár: ba-p16 (tereprendezés→kész kert), ba-p17 (lépcső burkolás→kész). 7 pár összesen.
- Projekt-02 mini kicserélve: 8286 (más helyszín, 2024-08-09) → lepcso-kesz-terasz.
- Mobiljavítás: .hero-strip flex:0 0 100% (flex-itemként összehúzódott → villámgyors fix, tanulság: flex konténerbe tett stripnek explicit flex-basis kell).
- QA: 390/360/768/1280px, nincs overflow, 0 törött kép, lightbox + burger + BA-range működik.
- Takarítás: kontakt/montázs segédfájlok törölve.
## Next best action
FTP élesítés (we052.tarhely.com), utána domain/OG-kép az ügyféllel egyeztetve.

## FTP ÉLESÍTÉS — 2026-09-30 KÉSZ
- Éles cím: https://epuletesmedence.hu/ (we052.tarhely.com, FTP-gyökér = webroot)
- Feltöltve: index.html + img/ (eredeti archív KIVÉVE) + logo/ — 110/110 fájl, 0 hiba
- Ellenőrizve: index 200, webp-k 200, logo 200, title OK, v4.1 tartalom (fázis-fejlécek, ba-p16) él
- Tanulság: FTP feltöltésnél a nem létező almappába STOR elakad → MKD előbb (curl -Q "MKD dir")

## VIZUÁLIS JAVÍTÁSI KÖR — 2026-09-30 (user 4 észrevétele alapján) KÉSZ
1. Hero badge: white-space:nowrap — nem törik a pill-kereten belül
2. Hero-strip mobil GYÖKERE megtalálva: a .hero flex-konténer, a strip flex-itemként a hero-inner MELÉ csúszott. Fix: flex-wrap:wrap a .hero-n + flex:0 0 100% a stripen. Mobilon 2×2 grid.
3. Galéria 23→18 elem: 5 villa-duplikátum kivéve (villa-homlokzat-kesz/-2, villa-haz-kesz-1/-3, +1), csak villa-haz-kesz-2 + fazis-villa-homlokzat maradt. FELIRATOK JAVÍTVA a valós tartalomhoz: homlokzat-reszlet→medence alapozás, kert-kesz→medence EPS, terasz-reszlet kikerült (régi ház bejárat), 1000008286→kocsifeljáró, fazis-tamfal→garázskapu, fazis-alapozas→medence földmunka.
4. Kontakt e-mail: kártyás formára (ikon+címke), a telefon-kártyával egységes.
- QA: 360/390/768/1280px, 0 overflow, 0 törött kép, lightbox OK, élő oldalon is ellenőrizve.
- Push: 2aafeb2, FTP: index.html frissítve, éles ellenőrizve.

## PRODUCTION RELEASE — 2026-09-30 VÉGLEGES
- KRITIKUS javítás: lepcso-kesz-terasz (medencés kép lépcsőként) KIVÉVE a galériából és Projekt-02 miniből; fazis-lepcso-zsaluzas → "Medencetest és lépcső — burkolás alatt" (Medence fázis)
- BA audit: p16 KIVÉVE (nem azonos nézőpont), p17 → medence-lépcsősor cím, p2 cím pontosítva. VÉGSŐ: 6 hiteles pár (p2,p6,p13,p14,p15,p17)
- SEO: canonical + og:url + og:image → https://epuletesmedence.hu/ (abszolút); github.io NINCS production metában; JSON-LD jobTitle
- Tartalom: "Székhely" → "Működési terület — Budapest és Pest megye"
- Tipográfia: hero h1 84→66, sub 17.5→16, h2 46→40, intro big 30→26 (user visszajelzés: szöveg túl nagy)
- Galéria: 17 elem (minőség > mennyiség), feliratok teljesen valósak
- QA: 360/390/430/768/1024/1280/1440px — 0 overflow, 0 törött kép, lightbox wrap-around + Escape OK, burger OK, 1 H1, heading sorrend OK, 0 console error, 0 404
- Éles ellenőrzés: HTTP 200, minden SEO meta helyesen él, og:image 200
- Push: ef4e11d · FTP: index.html frissítve
## ÁLLAPOT: ÜGYFÉLNEK ÁTADHATÓ

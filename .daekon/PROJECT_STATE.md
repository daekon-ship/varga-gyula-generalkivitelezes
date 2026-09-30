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

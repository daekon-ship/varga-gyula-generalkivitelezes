# PROJECT STATE — K.T BYGG HUNGARY KFT (varga-gyula-generalkivitelezes)

## Current goal
Egyoldalas bemutatkozó oldal karbantartása, hiteles referenciapárok bővítése, mobil vizuális minőség.

## Completed work (2026-09-29)
- munkaképek mappa (19 fotó) átnézve; perceptuális hasonlóság + blend-igazítás alapján párkeresés
- 1 új valós, azonos nézőpontú pár: külső kőlépcső (burkolás alatt → kész) = ba-p15
- Elavult kísérleti párok (P3, P5, P6, P7, villa-klaszter, #16 nézet) ELVEVE — nem azonos nézőpont
- Tartalmi frissítés (ügyfélkérés): Varga Gyula = ügyvezető + kapcsolattartó; e-mail: ktbygg.hungary@gmail.com; régió: Budapest és Pest megye (title, meta, topbar, hero, chip, rólunk, GYIK, footer)
- ATADAS.md szinkronizálva
- Mobil (390px) és desktop (1440px) vizuális ellenőrzés: hero, chip, Rólunk kártya, kapcsolat, footer, 5. csúszka — rendben, nincs overflow
- Csúszka funkcióteszt OK (range → --pos → moved)

## Open tasks
- Domain bekötése után: canonical + éles OG-kép (1200×630)
- Ha új fotópár érkezik: csak azonos nézőpontú mehet a BA_CONFIG-ba

## Technical constraints
- Egyfájlos statikus oldal (index.html), külső függőség csak Google Fonts
- Képek: img/ webp ~1200px q72; eredetiek változatlanul img/eredeti/
- BA_CONFIG a script tetején; w/h a valós méret
- Deployment: GitHub Pages, push → auto (repo: daekon-ship/varga-gyula-generalkivitelezes)

## Next best action
Domain + OG-kép, amikor az ügyfél megadja; új referenciapárok érzékeny szűrése.

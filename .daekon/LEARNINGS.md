# LEARNINGS — K.T BYGG HUNGARY KFT

## Bugs & fixes
- Preview szerver csak a regisztrált .html fájlt szolgálja ki → elemző kontaktlapokat a regisztrált fájlba írjuk (cp/felülírás), nem új fájlba.
- PNG-t a preview nem szolgálja ki közvetlenül → base64-be ágyazott .html nézetet használunk.
- Preview screenshot néha "no frames" hibát ad → új tab (preview_open) vagy register_preview url+pid megoldja; a resize után néha kell egy reload.
- scrollTo sima hívása smooth-scroll (html{scroll-behavior}) miatt versenyt fut a screenshot-tal → mindig {behavior:'instant'}.
- Pillow getdata() DeprecationWarning — only warning, működik.

## Patterns
- Párkeresés: korreláció + blend harmadik panelen (before | after | blend) → a blend mutatja meg azonnal, ha a nézőpont eltér.
- Különböző DOV/zoom fotók párba állításánál: AFTER-en nagyobb FOV kivágás (felbontásbőség kihasználása), BEFORE-en teli szélesség.
- W-Végződésű fájlnév (IMG-...-V.jpg) = Messenger-kompresszió, EXIF dátum nélkül — kamerás HDR fájlok az elsődleges források.

## Deployment
- Push → GitHub Pages auto-deploy pár percen belül.

# Rendrakás a Szükség Szobájában — így kerül fel a GitHub Pages-re

Ez a mappa (`pages`) egy kész, feltölthető weboldal: maga a játék. Ugyanúgy megy, mint a
Varázsviccnél: egy nyilvános GitHub-tárolóba töltöd fel, és a GitHub Pages egy saját webcímen
kiszolgálja. **Számítógépre készült** (Edge vagy Chrome, Xbox kontrollerrel), konzolra nem.

A játék az Abszol úton kezdődik; a boltok ajtaja mögött 10 helyszín vár, és bennük tízezer
gyűjtői figura (500 féle × 20), amit a helyére kell tenni.

A mappában ezek vannak:

- `index.html` – maga a játék
- `sw.js` – az offline működéshez kell
- `manifest.webmanifest` és az `icons` mappa – az ikon és a telepíthető alkalmazás adatai
- `assets` mappa – a figurák adatai (`figs`, `figures-baked`, `figures`) és a zene helye (`music`);
  **nélkülözhetetlen**, a teljes mappát töltsd fel
- `figures-preview.html` – a figurák előnézete (nem kötelező)
- ez az `OLVASSEL.md` (nem kötelező)

Összesen kb. 550 fájl, kb. 235 MB. A legnagyobb fájl kb. 13 MB, így mind belefér a GitHub
25 MB-os feltöltési korlátjába.

---

## 1. Feltöltés (egyszer)

1. **github.com** → jobb felül **+** → **New repository**. Név: `szukseg-szobaja`.
   Legyen **Public**, majd **Create repository**.
2. Az üres tároló oldalán: **uploading an existing file**.
3. A böngésző egyszerre kb. 100 fájlt tölt fel megbízhatóan, ezért **több körben** töltsd fel:
   - **1. kör:** `index.html`, `sw.js`, `manifest.webmanifest`, `figures-preview.html`, az `icons`
     mappa, valamint az `assets` mappán belül a `figs`, a `figures` és a `music` mappa
     (húzd be az `assets` mappát úgy, hogy előtte a gépeden ideiglenesen kiveszed belőle a
     `figures-baked` mappát, vagy egyenként húzd be ezt a három almappát az `assets` mappába).
     → **Commit changes**.
   - **2–7. kör:** az `assets/figures-baked` mappa 521 fájlja, kb. 90-esével. A tárolóban lépj be
     az `assets` mappába, hozd létre a `figures-baked` mappát az első adaggal (húzd be a mappát az
     első 90 fájllal), utána a további adagokat az `assets/figures-baked` mappán belül
     **Add file → Upload files**-szal töltsd fel. Minden kör végén **Commit changes**.
4. **Settings → Pages**: Source `Deploy from a branch`, branch `main`, mappa `/ (root)`, **Save**.
5. Pár perc múlva a cím: `https://puxi63.github.io/szukseg-szobaja/`

A tároló nyilvános; ez egy saját, magáncélú rajongói játék, a linket ne oszd meg szélesebb körben.
A Varázsviccet ez nem érinti: külön tároló, külön mentés.

---

## 2. Irányítás (Xbox kontroller)

- **Bal kar** – járás, **jobb kar** – nézelődés
- **X** – használat (felvesz, polcra tesz, ajtót nyit)
- **A** – ugrás (ha már megvetted a képességet)
- **Y** – térkép
- **Menü gomb** – szünet és beállítások
- **Második kontroller: Start** – belép a házimanó (Dobby) segítőként; hosszú Start – kilép.

Billentyűzettel és egérrel is játszható (kattints a képre, hogy az egér a nézelődést irányítsa).

**Telepítés alkalmazásként:** a címsor jobb szélén megjelenő telepítés ikonnal. Ezután saját
ikonnal, böngészősáv nélkül indul, és egy kis játék után internet nélkül is.

---

## 3. Frissítés

Új változatnál töltsd fel újra a megváltozott fájlokat ugyanebbe a tárolóba
(**Add file → Upload files**, felülírja a régit), majd **Commit changes**. Szinte mindig elég az
`index.html` és a `sw.js`; ha a figurák változtak, az `assets` érintett fájljai is.
Ha mégis a régi változat jön be, töltsd újra az oldalt még egyszer.

---

## 4. A mentés

A játék a böngésző saját tárolójában ment, automatikusan, két váltakozó mentéshellyel. A Szünet
menüben látszik az utolsó mentés ideje, és ott van a **Mentés törlése** is. Ha törlöd a
böngészőadatokat, a mentés is elvész.

---

## 5. Saját zene

1. Nevezd el a fájlokat így: `zene-1.mp3`, `zene-2.mp3` … legfeljebb `zene-100` (kisbetűvel,
   szóköz nélkül, 1-től, kihagyás nélkül). `.ogg` és `.m4a` is jó. Egy fájl legfeljebb 25 MB.
2. A tárolóban nyisd meg az `assets/music` mappát → **Add file → Upload files** → **Commit changes**.
3. Újratöltés után a saját zene szól; a Beállítások → Hang pontban keverhető és halkítható.

Csak saját vagy szabad licencű zenét tölts fel, mert a tároló nyilvános. Részletek:
`assets/music/OLVASSEL-ZENE.txt`.

---

## 6. Teljesítmény és hibaelhárítás

**Beállítások → Kép → Teljesítmény:** *Automatikus* (ajánlott, Közepesről indul), *Könnyű*,
*Közepes*, *Magas*. Automatikus módban akadozáskor a játék előbb a felbontást, aztán az effekteket
csökkenti.

Fokozat menü nélkül: írd a cím végére, hogy `#konnyu`, `#kozepes` vagy `#magas`.

**Ha lassú:**

1. Edge-ben: `edge://settings/system` → **Grafikus gyorsítás használata, ha elérhető** legyen bekapcsolva.
2. Két videokártyás laptopon: Windows **Gépház → Rendszer → Kijelző → Grafika** → Microsoft Edge →
   **Nagy teljesítmény**.
3. Hogy melyik videokártyát használja az Edge, az `edge://gpu` oldalon látszik (*GL_RENDERER*).

A **Teljesítménypanel** (Beállítások → Kép) mutatja a képkocka/másodpercet és a memóriát; ha valami
nem működik, érdemes képernyőképet készíteni róla.

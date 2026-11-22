# FunkeeB Cygnus 3x5 — ZMK

Firmware ZMK dla bezprzewodowego Dactyl Cygnus 3x5 (36 klawiszy), z obsługą
[ZMK Studio](https://zmk.studio/).

## Sprzęt

- Cygnus 3x5, matryca okablowana jak Corne zgodnie z oryginalną instrukcją.
- Dwa kontrolery SuperMini nRF52840 albo nice!nano v2.
- Lewa połówka jest centralna i łączy się z komputerem.

Konfiguracja używa oficjalnego shielda `corne_left` / `corne_right` oraz jego
fizycznego układu 5-column. Dzięki temu numery pinów i kolejność klawiszy są
zgodne z instrukcją Cygnusa, bez utrzymywania kopii definicji sprzętowej.

## Gałęzie

- `main` — prosty układ QWERTY.
- `personal` — osobisty układ przeniesiony z gałęzi `private` repozytorium
  `temper-zmkstudio`.

Każda gałąź buduje własny komplet firmware. Przed pobraniem plików sprawdź,
czy w GitHub Actions wybrana jest właściwa gałąź.

## Pobranie firmware

1. Otwórz kartę **Actions** w repozytorium.
2. Wybierz najnowszy udany przebieg **Build ZMK firmware** dla właściwej gałęzi.
3. Pobierz artefakt `firmware`.
4. Rozpakuj archiwum. Znajdziesz w nim:
   - `cygnus-3x5-left-studio.uf2`,
   - `cygnus-3x5-right.uf2`,
   - `settings-reset.uf2`.

## Pierwsze flashowanie

1. Wyłącz obie połówki.
2. Podłącz prawą połówkę przewodem USB i dwukrotnie naciśnij reset.
3. Skopiuj `cygnus-3x5-right.uf2` na dysk `NICENANO`.
4. Powtórz operację dla lewej połówki, używając
   `cygnus-3x5-left-studio.uf2`.
5. Włącz obie połówki i połącz komputer przez Bluetooth z urządzeniem
   **Cygnus 3x5**.

Jeżeli połówki były wcześniej sparowane z innym firmware, wgraj najpierw
`settings-reset.uf2` do obu kontrolerów (najpierw prawego), a następnie ponownie
wgraj odpowiedni firmware lewej i prawej strony.

## ZMK Studio

1. Podłącz lewą połówkę do komputera przez USB.
2. Przełącz wyjście na USB: na warstwie **Symbols & Settings** użyj klawisza
   `OUT_USB`.
3. Na tej samej warstwie użyj klawisza **Studio Unlock**.
4. Otwórz [zmk.studio](https://zmk.studio/) w Chrome albo Edge i wybierz
   urządzenie.

Zmiany zapisane przez Studio są przechowywane w pamięci klawiatury. Późniejsze
zmiany w pliku `config/corne.keymap` nie zastąpią ich automatycznie — w Studio
należy wybrać **Restore Stock Settings**, aby wrócić do układu z firmware.

## Źródła

- [Oryginalna instrukcja Cygnusa](https://github.com/juhakaup/keyboards/tree/main/Cygnus%20v1.0)
- [Dokumentacja ZMK Studio](https://zmk.dev/docs/features/studio)
- [Oficjalna definicja Corne w ZMK](https://github.com/zmkfirmware/zmk/tree/main/app/boards/shields/corne)


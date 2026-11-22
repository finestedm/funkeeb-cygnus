# FunkeeB Cygnus 3x5 — ZMK

ZMK firmware for the wireless 36-key Dactyl Cygnus 3x5, with
[ZMK Studio](https://zmk.studio/) support.

## Hardware

- Cygnus 3x5 with the matrix wired like a Corne, as described in the original
  build guide.
- Two SuperMini nRF52840 or nice!nano v2 controllers.
- The left half acts as the central side and connects to the computer.

This configuration uses the official `corne_left` and `corne_right` shields
with their 5-column physical layout. This keeps the pin assignments and key
order compatible with the Cygnus build guide without maintaining a separate
copy of the hardware definition.

## Branches

- `main` — a straightforward QWERTY layout.
- `personal` — the personal layout ported from the `private` branch of the
  `temper-zmkstudio` repository.

Each branch builds its own firmware package. Before downloading the files,
make sure you select a GitHub Actions run from the correct branch.

## Downloading the firmware

1. Open the **Actions** tab in this repository.
2. Select the latest successful **Build ZMK firmware** run for the desired
   branch.
3. Download the `firmware` artifact.
4. Extract the archive. It contains:
   - `cygnus-3x5-left-studio.uf2`,
   - `cygnus-3x5-right.uf2`,
   - `settings-reset.uf2`.

## First-time flashing

1. Turn off both keyboard halves.
2. Connect the right half over USB and press its reset button twice.
3. Copy `cygnus-3x5-right.uf2` to the `NICENANO` drive.
4. Repeat the process for the left half using
   `cygnus-3x5-left-studio.uf2`.
5. Turn on both halves and pair your computer with **Cygnus 3x5** over
   Bluetooth.

If the halves were previously paired while running different firmware, flash
`settings-reset.uf2` to both controllers first, starting with the right half.
Then flash the correct left and right firmware again.

## ZMK Studio

1. Connect the left half to your computer over USB.
2. Switch the output to USB using the `OUT_USB` key on the
   **Symbols & Settings** layer.
3. Use **Studio Unlock** on the same layer.
4. Open [zmk.studio](https://zmk.studio/) in Chrome or Edge and select the
   keyboard.

Changes made in Studio are stored in the keyboard's memory. Later changes to
`config/corne.keymap` will not replace them automatically. Select
**Restore Stock Settings** in Studio to return to the layout bundled with the
firmware.

## References

- [Original Cygnus build guide](https://github.com/juhakaup/keyboards/tree/main/Cygnus%20v1.0)
- [ZMK Studio documentation](https://zmk.dev/docs/features/studio)
- [Official Corne definition in ZMK](https://github.com/zmkfirmware/zmk/tree/main/app/boards/shields/corne)
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


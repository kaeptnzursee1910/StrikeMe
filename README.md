# StrikeMe

Counter-Strike 1.6 **im Browser auf dem iPad – mit Tastatur und Maus**.
StrikeMe ist ein Launcher für die freie Engine [Xash3D FWGS](https://github.com/FWGS/xash3d-fwgs)
(WebAssembly-Port *webxash3d-fwgs* + Open-Source-Client *cs16-client*). Die Spieldateien kommen aus **deiner eigenen** Installation.
Dieses Repository enthält keine Dateien von Valve.

## Einrichten

1. **GitHub Pages:** Settings → Pages → Deploy from a branch → `main` / `(root)`.
2. **ZIP bauen (am PC, einmalig):** Im Ordner `Half-Life` deiner CS-1.6-Installation (Steam: `steamapps/common/Half-Life`)
   die Ordner `valve` und `cstrike` zusammen als `cs16.zip` packen und in iCloud Drive legen.
3. **iPad:** Maus/Trackpad und Tastatur koppeln, `https://kaeptnzursee1910.github.io/StrikeMe/` in Safari öffnen,
   ZIP wählen → **Spiel starten** → einmal ins Bild klicken (Maus wird eingefangen, **Esc** gibt sie frei).

## Benötigte Dateien

| Ordner | Was gebraucht wird |
|---|---|
| `cstrike/` | `liblist.gam`, `*.wad` (Texturen, z. B. `cstrike.wad`), `maps/*.bsp` (mind. eine Karte), `models/`, `sound/`, `sprites/`, `gfx/`, `resource/`, die `*.txt`/`*.lst`-Dateien im Hauptordner |
| `valve/` | `*.wad` (u. a. `halflife.wad`, `decals.wad`), `models/`, `sound/`, `sprites/`, `gfx/`, `resource/` |
| **nicht nötig** | `valve/maps`, `valve/media`, `*_hd`-, `*_downloads`- und andere Mod-Ordner, alle `.exe`/`.dll`/`.so` |

Der Launcher prüft die Pflichtdateien (`cstrike/liblist.gam`, eine Karte, Texturen, Modelle, Sounds, `valve/halflife.wad`,
`valve/decals.wad`) und meldet, was fehlt. Unnötiges wird beim Entpacken übersprungen.
Je kleiner die ZIP, desto stabiler läuft Safari, das den Speicher pro Tab begrenzt.

## Hinweise

- Alles bleibt lokal: die ZIP wird nur im Browser entpackt, nichts wird hochgeladen.
- Engine und Client werden zur Laufzeit von jsDelivr geladen (`xash3d-fwgs@latest`, `cs16-client@latest`).
  Wenn der Start scheitert, steht die Ursache unter „Technisches Protokoll“.
- Ohne Tastatur/Maus kann die Touch-Steuerung der Engine eingeblendet werden (Option im Launcher).

# Unterwegs in Düsterburg with EasyRPG

Play **Unterwegs in Düsterburg (UiD)** on modern **Windows, macOS, and Linux** with [EasyRPG Player](https://easyrpg.org/player/).

**TL;DR:** download the game and RPG Maker 2000 RTP, extract both, copy the RTP files into the UiD folder, then start the game with EasyRPG Player.

The original game is available from the [official UiD website](https://www.duesterburg.rpg-atelier.net/downloads.php). For convenience, this guide uses the archived ZIP from RMArchiv. For copyright reasons, this repository does **not** include UiD, RPG Maker 2000, the RTP, or their assets.

## 1. Download what you need

1. **Unterwegs in Düsterburg 1.21-lite** — download the ZIP from RMArchiv.  
   [RMArchiv page](https://rmarchiv.de/games/68) · [Direct ZIP download](https://rmarchiv.de/games/download/2271/1790585175)

2. **RPG Maker 2000 RTP** — UiD uses some standard RTP assets, so you need the original runtime files.  
   [RPG Maker RTP page](https://www.rpgmakerweb.com/run-time-package) · [Direct installer](https://assets.rpgmakerweb.com/rpg2000_rtp_installer.exe)

3. **EasyRPG Player** — this is what runs UiD on modern systems.  
   [EasyRPG downloads](https://easyrpg.org/player/downloads/)

   <details>
   <summary><strong>Windows</strong></summary>

   Download EasyRPG Player from the [EasyRPG website](https://easyrpg.org/player/downloads/).

   Direct download for 64-bit Windows:

   https://easyrpg.org/downloads/player/latest/easyrpg-player-latest-windows-x64.zip

   Extract the downloaded ZIP. You will use `easyrpg-player.exe` when starting the game.

   </details>

   <details>
   <summary><strong>macOS</strong></summary>

   Install with Homebrew:

   ```bash
   brew install easyrpg-player
   ```

   If Homebrew is unavailable, download EasyRPG Player directly from the [EasyRPG website](https://easyrpg.org/player/downloads/).

   </details>

   <details>
   <summary><strong>Linux</strong></summary>

   Use your distribution package manager. On Debian/Ubuntu:

   ```bash
   sudo apt install easyrpg-player
   ```

   If the package is unavailable or outdated, download EasyRPG Player directly from the [EasyRPG website](https://easyrpg.org/player/downloads/).

   </details>

4. **7-Zip** — used to extract the RPG Maker 2000 RTP installer.  
   [7-Zip downloads](https://www.7-zip.org/download.html)

   <details>
   <summary><strong>Windows</strong></summary>

   Download and install 7-Zip from the [official download page](https://www.7-zip.org/download.html). The 64-bit x64 `.exe` installer is the usual choice for modern Windows PCs.

   </details>

   <details>
   <summary><strong>macOS</strong></summary>

   Install with Homebrew:

   ```bash
   brew install sevenzip
   ```

   If Homebrew is unavailable, use the macOS console build from the [7-Zip download page](https://www.7-zip.org/download.html).

   </details>

   <details>
   <summary><strong>Linux</strong></summary>

   Use your distribution package manager. On Debian/Ubuntu:

   ```bash
   sudo apt install 7zip
   ```

   If your distribution does not provide the package, use the Linux console build from the [7-Zip download page](https://www.7-zip.org/download.html).

   </details>

## 2. What you should have after downloading

After downloading, you should have something similar to:

```text
Downloads/
├── Unterwegs in Düsterburg 1.21-lite.zip
└── rpg2000_rtp_installer.exe
```

## 3. Extract UiD and the RTP

Extract the UiD ZIP first. The correct game folder directly contains files such as:

```text
Unterwegs in Düsterburg/
├── RPG_RT.ldb
├── RPG_RT.lmt
├── RPG_RT.ini
├── CharSet/
├── ChipSet/
├── Music/
├── Picture/
└── Sound/
```

Then extract `rpg2000_rtp_installer.exe` with 7-Zip.

**You do not need to install the RPG Maker 2000 RTP. This guide only extracts the files from the installer so they can be copied into UiD.**

<details>
<summary><strong>Windows</strong></summary>

Right-click `rpg2000_rtp_installer.exe`, open it with 7-Zip, and extract it to a temporary folder such as `rpg2000-rtp`.

</details>

<details>
<summary><strong>macOS</strong></summary>

```bash
7zz x "$HOME/Downloads/rpg2000_rtp_installer.exe" -o"$HOME/Downloads/rpg2000-rtp"
```

</details>

<details>
<summary><strong>Linux</strong></summary>

```bash
7zz x "$HOME/Downloads/rpg2000_rtp_installer.exe" -o"$HOME/Downloads/rpg2000-rtp"
```

Some distributions provide the command as `7z` instead of `7zz`.

</details>

After extraction, you should have two separate directories:

```text
Downloads/
├── Unterwegs in Düsterburg/
│   ├── RPG_RT.ldb
│   ├── RPG_RT.lmt
│   ├── CharSet/
│   ├── Sound/
│   └── ...
└── rpg2000-rtp/
    └── ...
```

Inside the extracted RTP files, find the directory that directly contains folders such as:

```text
Backdrop/
Battle/
CharSet/
ChipSet/
FaceSet/
GameOver/
Monster/
Music/
Panorama/
Picture/
Sound/
System/
Title/
```

## 4. Copy the RTP into UiD

Copy the contents of that directory into the existing `Unterwegs in Düsterburg` folder.

<details>
<summary><strong>Windows</strong></summary>

Drag the RTP folders into the UiD folder, or use **Ctrl+C / Ctrl+V**.

When Windows asks about existing folders, merge them. If it asks whether to overwrite existing files, choose **Skip these files**.

</details>

<details>
<summary><strong>macOS</strong></summary>

Drag the RTP folders into the UiD folder, or use **Cmd+C / Cmd+V**.

If prompted about existing items, keep the UiD versions. The goal is only to add missing RTP assets.

</details>

<details>
<summary><strong>Linux</strong></summary>

Drag the RTP folders into the UiD folder, or use **Ctrl+C / Ctrl+V**.

If prompted about existing files, keep the UiD versions. The goal is only to add missing RTP assets.

</details>

<details>
<summary><strong>rsync alternative for macOS/Linux</strong></summary>

Run this with the RTP directory as the source and the UiD directory as the destination:

```bash
rsync -av --ignore-existing \
  "$HOME/Downloads/rpg2000-rtp/" \
  "$HOME/Downloads/Unterwegs in Düsterburg/"
```

If the extracted assets are inside an additional `RTP/` directory, use that directory as the source instead.

</details>

## 5. Check the final folder

The UiD folder should now contain both the original game files and the missing RTP assets:

```text
Unterwegs in Düsterburg/
├── RPG_RT.ldb
├── RPG_RT.lmt
├── RPG_RT.ini
├── Backdrop/
├── Battle/
├── CharSet/
├── ChipSet/
├── FaceSet/
├── GameOver/
├── Monster/
├── Music/
├── Panorama/
├── Picture/
├── Sound/
├── System/
└── Title/
```

To check if the RTP has been merged correctly, check that these paths exist:

```text
Unterwegs in Düsterburg/Sound/Bite.*
Unterwegs in Düsterburg/Sound/Damage1.*
Unterwegs in Düsterburg/Sound/Sword1.*
```

## 6. Start UiD with EasyRPG

<details>
<summary><strong>Windows</strong></summary>

Place `easyrpg-player.exe` in the UiD folder and double-click it.

Optionally, you can start it from PowerShell:

```powershell
& "C:\Games\EasyRPG\easyrpg-player.exe" `
  --project-path "C:\Games\UiD\Unterwegs in Düsterburg"
```

</details>

<details>
<summary><strong>macOS</strong></summary>

Open a terminal in the UiD folder and run:

```bash
cd "$HOME/Downloads/Unterwegs in Düsterburg"
easyrpg-player
```

</details>

<details>
<summary><strong>Linux</strong></summary>

Open a terminal in the UiD folder and run:

```bash
cd "$HOME/Downloads/Unterwegs in Düsterburg"
easyrpg-player
```

</details>

## Troubleshooting

### EasyRPG says `Sound not found: Bite` or `Cannot find: Sound/Damage1`

The RTP was probably not merged into the correct directory. Check that files such as these exist directly below the UiD folder:

```text
Unterwegs in Düsterburg/Sound/Bite.*
Unterwegs in Düsterburg/Sound/Damage1.*
```

### My files are under `Unterwegs in Düsterburg/RTP/Sound/`

They are one level too deep. Move the contents of `RTP/` into `Unterwegs in Düsterburg/` so that `Sound/`, `CharSet/`, `Music/`, and the other RTP folders sit directly beside `RPG_RT.ldb`.

### EasyRPG reports missing `CharSet` or other game files

Make sure EasyRPG is pointed at the directory that directly contains:

```text
RPG_RT.ldb
RPG_RT.lmt
```

---

## Thank you

Thank you to [Grandy](https://rmarchiv.de/developer/39), the creator of *Unterwegs in Düsterburg*, for making such a fun and memorable game, and for giving so many people a reason to revisit Düsterburg years later.

## Support this guide

<p align="center">
  <strong>Did this guide save you some setup time?</strong><br>
  Support continued testing, updates, and documentation for this guide.
</p>

<p align="center">
  <a href="https://www.buymeacoffee.com/dominikfalkner">
    <img
      src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png"
      alt="Buy me a coffee"
      width="217"
      height="60"
    >
  </a>
</p>

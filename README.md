# Unterwegs in Düsterburg with EasyRPG

Play **Unterwegs in Düsterburg (UiD)** on modern **Windows, macOS, and Linux** with [EasyRPG Player](https://easyrpg.org/player/).

**TL;DR:** download the German or English version of UiD, extract it, and run it with EasyRPG Player. The **German version** also needs the RPG Maker 2000 RTP files copied into the game folder.

The original game is available from the [official UiD website](https://www.duesterburg.rpg-atelier.net/downloads.php). For convenience, this guide uses archived downloads from RMArchiv. For copyright reasons, this repository does **not** include UiD, RPG Maker 2000, the RTP, or their assets.

## 1. Download what you need

1. **Unterwegs in Düsterburg**

   **German 1.21-lite**  
   [RMArchiv page](https://rmarchiv.de/games/68) | [Direct ZIP download](https://rmarchiv.de/games/download/2271/1790585175)

   **English 1.3**  
   [RMArchiv page](https://rmarchiv.de/games/68) | [Direct RAR download](https://rmarchiv.de/games/download/3823/1790627991)

2. **RPG Maker 2000 RTP** - needed for the **German version only**.  
   [RPG Maker RTP page](https://www.rpgmakerweb.com/run-time-package) | [Direct installer](https://assets.rpgmakerweb.com/rpg2000_rtp_installer.exe)

3. **EasyRPG Player** - runs UiD on modern systems.  
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

4. **Archive tools** - used to extract the German RTP installer and the English `.rar` archive.  
   [7-Zip downloads](https://www.7-zip.org/download.html)

   <details>
   <summary><strong>Windows</strong></summary>

   Download and install 7-Zip from the [official download page](https://www.7-zip.org/download.html). The 64-bit x64 `.exe` installer is the usual choice for modern Windows PCs.

   </details>

   <details>
   <summary><strong>macOS</strong></summary>

   Install the archive tools with Homebrew:

   ```bash
   brew install sevenzip unar
   ```

   Use 7-Zip for the German RTP installer. Use `unar` for the English `.rar` file:

   ```bash
   unar "UiD eng 1_3.rar"
   ```

   If you do not use Homebrew, download 7-Zip from the [7-Zip website](https://www.7-zip.org/download.html) and `unar` from the [The Unarchiver command-line tools page](https://theunarchiver.com/command-line).

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

For the **German version**:

```text
Downloads/
|- Unterwegs in Düsterburg 1.21-lite.zip
`- rpg2000_rtp_installer.exe
```

For the **English version**:

```text
Downloads/
`- UiD eng 1_3.rar
```

## 3. Extract UiD

Extract the UiD archive first. Your extracted game folder should contain files such as:

```text
game-folder/
|- RPG_RT.ldb
|- RPG_RT.lmt
|- RPG_RT.ini
|- CharSet/
|- ChipSet/
|- Music/
|- Picture/
`- Sound/
```

**If you downloaded the English version, skip Steps 4 and 5 and continue with Step 6.**

### German version: extract the RTP

These RTP steps are only needed for the **German version**.

Extract `rpg2000_rtp_installer.exe` with 7-Zip.

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
|- Unterwegs in Düsterburg/
|  |- RPG_RT.ldb
|  |- RPG_RT.lmt
|  |- CharSet/
|  |- Sound/
|  `- ...
`- rpg2000-rtp/
    `- ...
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

## 4. German version only: copy the RTP into UiD

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

## 5. German version: check the final folder

The UiD folder should now contain the game files and the missing RTP assets:

```text
Unterwegs in Düsterburg/
|- RPG_RT.ldb
|- RPG_RT.lmt
|- RPG_RT.ini
|- Backdrop/
|- Battle/
|- CharSet/
|- ChipSet/
|- FaceSet/
|- GameOver/
|- Monster/
|- Music/
|- Panorama/
|- Picture/
|- Sound/
|- System/
`- Title/
```

To check the RTP merge, make sure these paths exist:

```text
Unterwegs in Düsterburg/Sound/Bite.*
Unterwegs in Düsterburg/Sound/Damage1.*
Unterwegs in Düsterburg/Sound/Sword1.*
```

## 6. Start UiD with EasyRPG

### German version

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

### English version

The English version needs EasyRPG's English RPG Maker 2000 engine mode and Windows-1252 encoding:

```bash
easyrpg-player --engine rpg2ke --encoding 1252
```

Run this command from inside the extracted English UiD folder.

<details>
<summary><strong>Windows</strong></summary>

Place `easyrpg-player.exe` in the extracted English UiD folder.

Then open PowerShell in that folder and run:

```powershell
.\easyrpg-player.exe --engine rpg2ke --encoding 1252
```

If EasyRPG Player is stored elsewhere, pass the game folder with `--project-path`.

</details>

<details>
<summary><strong>macOS</strong></summary>

Open a terminal in the extracted English UiD folder and run:

```bash
easyrpg-player --engine rpg2ke --encoding 1252
```

</details>

<details>
<summary><strong>Linux</strong></summary>

Open a terminal in the extracted English UiD folder and run:

```bash
easyrpg-player --engine rpg2ke --encoding 1252
```

</details>

## Troubleshooting

### English version does not start

If EasyRPG shows `This is not a valid RPG2000 database`, start the English version with:

```bash
easyrpg-player --engine rpg2ke --encoding 1252
```

Without these options, EasyRPG may fail to detect the correct engine or encoding.

### EasyRPG says `Sound not found: Bite` or `Cannot find: Sound/Damage1`

This applies to the **German version**.

The RTP was probably not merged into the correct directory. Check that files such as these exist directly below the UiD folder:

```text
Unterwegs in Düsterburg/Sound/Bite.*
Unterwegs in Düsterburg/Sound/Damage1.*
```

### My files are under `Unterwegs in Düsterburg/RTP/Sound/`

This applies to the **German version**.

They are one level too deep. Move the contents of `RTP/` into `Unterwegs in Düsterburg/` so that `Sound/`, `CharSet/`, `Music/`, and the other RTP folders sit directly beside `RPG_RT.ldb`.

### EasyRPG reports missing `CharSet` or other game files

Make sure EasyRPG is pointed at the directory that directly contains:

```text
RPG_RT.ldb
RPG_RT.lmt
```

### Help, I'm stuck!

Check out this [guide](https://lparchive.org/Unterwegs-in-Duesterburg/).

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
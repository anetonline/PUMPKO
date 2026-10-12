<div align="center">

# 🎃 PUMPKO
### SEASONS OF ADVENTURE

**Twelve months. Ninety-six stages. One very haunted beginning.**

![Version](https://img.shields.io/badge/version-2.0.0-ff8a32?style=for-the-badge)
![ANSI](https://img.shields.io/badge/graphics-CP437%20%2F%20ANSI-58d9ca?style=for-the-badge)
![Platforms](https://img.shields.io/badge/platforms-Linux%20%7C%20Pi%20%7C%20Windows-879dff?style=for-the-badge)
![BBS](https://img.shields.io/badge/built%20for-the%20BBS-b896ff?style=for-the-badge)

*A pumpkin came home with you. Something else came with it.*

[The adventure](#-a-new-month-a-new-adventure) · [Daily challenges](#-one-day-one-challenge) · [InterBBS](#-your-bbs-on-the-world-stage) · [Shared chat](#-different-games-same-lobby) · [Installation](#-put-pumpko-on-your-bbs)

</div>

---

PUMPKO started in the haunted pumpkin patch. **Version 2.0 turns it into an all-year-round BBS adventure**: winter mysteries, spring heists, summer trouble, an October nightmare, and holiday quests.

The calendar changes the campaign, characters, locations, guardians, and ANSI artwork. The next day brings another Daily challenge. Your callers can chase scores, represent their BBS, and meet players from other games in the shared lobby.

**Created by StingRay · Jerry Reed · A-Net Online**

## 🗓 A new month. A new adventure.

All twelve campaigns ship with the game. Each has **eight story stages**, for **96 stages across the year**. There is no monthly content download or network requirement for the seasonal adventure.

| Month | Campaign |
| :--- | :--- |
| ❄️ January | **The Frozen Midnight** |
| 💔 February | **The Heartbreak Engine** |
| ☘️ March | **The Stolen Spring** |
| 🐇 April | **The Storm-Egg Heist** |
| 🌸 May | **The Thorn Queen** |
| ☀️ June | **The Sun That Would Not Set** |
| 🎆 July | **The Firework Rebellion** |
| 🦈 August | **The Undertow Arcade** |
| 📚 September | **The Bell After Dark** |
| 🎃 October | **A Halloween Nightmare** |
| 🦃 November | **The Feast of Shadows** |
| 🎅 December | **The Midnight Sleigh** |

Explore, solve puzzles, gather supplies, and face each stage’s guardian. Choose from five character classes and make your way through the month’s story.

October retains the original **Revenge of the Pumpkins** atmosphere. The other eleven months bring their own trouble.

> **One calendar for every BBS:** campaigns and Daily challenges use UTC. A run already in progress keeps its original date and season when the clock crosses midnight. The twelve seasonal campaigns repeat each year.

<details>
<summary><strong>Preview the seasonal CP437 artwork</strong></summary>

![PUMPKO seasonal ANSI artwork](seasons/art-contact-sheet.png)

The preview is a rendered contact sheet. The game itself draws terminal artwork using CP437 bytes and ANSI colors.

</details>

## ⚔️ One day. One challenge.

Daily mode gives callers a dated challenge with changing encounters and choices. Its deterministic date-based generation keeps the challenge consistent across supported platforms.

- A fresh challenge every UTC day.
- One **completed** Daily run per caller per day.
- Choices, class, supplies, and combat determine the result.
- Persistent player profiles and local Story/Daily score records.

Story mode follows the monthly campaign; Daily mode gives callers a reason to return tomorrow.

## 🏆 Your BBS on the world stage.

Enable optional **InterBBS score sharing** to send results to the A-Net score hub and view shared Story and Daily rankings.

**Score hub:** https://scores.a-net.online

Local scores remain available. The seasonal game works offline, and score sharing can be disabled independently of live chat.

Already registered your BBS? **Keep its existing credentials.** Updating the game does not require a new BBS identity. If credentials are lost, contact the hub operator for recovery or a verified registration reset.

## 💬 Different games. Same lobby.

A caller in PUMPKO on one BBS can meet a caller in **ANetARCADE** on another.

Enable shared live chat during installation, then press **C** from the lobby. The status display shows connected players, BBSes, and how many callers are in chat.

**Shared lobby:** https://chat.a-net.online

Say **no** during setup and chat stays out of the menu. Score sharing and chat are separate options—you choose which services your board uses.

## 🖥 Terminal soul. Native builds.

PUMPKO uses **OpenDoors**, native terminal input, and CP437 ANSI artwork. It is built for callers entering through a BBS, with local play available for testing.

| Platform | Release package |
| :--- | :--- |
| Linux x86-64 | `PUMPKO-2.0.0-linux-x64.zip` |
| Raspberry Pi / Linux ARM64 | `PUMPKO-2.0.0-pi-arm64.zip` |
| Windows 32-bit | `PUMPKO-2.0.0-windows-x86.zip` |
| Windows 64-bit | `PUMPKO-2.0.0-windows-x64.zip` |
| Source | `PUMPKO-2.0.0-source.zip` |

Use a **64-bit operating system** for the ARM64 package. Windows online features require Windows 7 SP1 or later with working TLS 1.2 and certificate trust. Linux online features require HTTPS-capable `curl` and CA certificates.

No Python or PowerShell is required on the installed game client. Python is used for source/build tooling and the separate hub servers.

## 🚀 Put PUMPKO on your BBS.

1. Download and extract the package for your operating system and architecture.
2. Run its installer:
   - **Linux / Pi:** `bash INSTALL-LINUX.sh`
   - **Windows:** launch `PUMPKO-SETUP.exe`
3. Choose the installation directory and review the BBS, score-sharing, and optional chat settings.
4. Add PUMPKO to your BBS door menu. Set its working directory to the installed game folder and pass the caller’s OpenDoors-compatible dropfile.

### Local test

```bash
# Linux / Raspberry Pi
./PUMPKO -L
```

```bat
REM Windows
PUMPKO.exe -L
```

### Door command examples

```bash
./PUMPKO -D /path/to/BBSDEV.DRP
```

```bat
PUMPKO.exe -D C:\path\to\DOOR32.SYS
```

Use your BBS software’s actual dropfile path or substitution. On ANetBBS, `-D %f` passes its generated dropfile to the door. Keep the correct caller identity across upgrades so existing profiles continue to belong to the same players.

**Linux permissions matter:** the BBS service account needs access to the game’s configuration and write access to player data and synchronization state. Credential files should remain private; use appropriate ownership and group access rather than making secrets world-readable.

See the [installation guide](docs/INSTALL.txt), [multiuser setup](docs/INSTALL-MULTIUSER.txt), and [shared chat guide](docs/SHARED-CHAT.txt).

## 🔄 Upgrade the game. Keep the adventure.

The installers support both fresh installations and upgrades from an existing PUMPKO setup. Back up the door, close active game sessions and synchronization workers, and install into the **existing directory**.

Existing settings, BBS credentials, player profiles, and scores are retained. **Do not delete the game directory to perform an upgrade.**

PUMPKO 2.0 also includes a sysop updater:

```bash
# Linux / Raspberry Pi: check, then choose whether to install
./PUMPKO-UPDATE --check
./PUMPKO-UPDATE
```

```bat
REM Windows: check, or launch the updater for its installation prompt
PUMPKO-UPDATE.exe --check
PUMPKO-UPDATE.exe
```

The updater verifies a signed release manifest, download size, and SHA-256 hash. It refuses installation while PUMPKO callers are active, preserves configuration and data, and uses backups and rollback during installation. A game update does not require a BBS or VM reboot.

The update service must be published by the hub operator before online checks can succeed. Install 2.0 manually first when upgrading from a version without the updater. See [online updates](docs/ONLINE-UPDATES.txt) and [upgrade notes](docs/UPDATING.txt).

## 🛠 Build from source.

The source tree includes OpenDoors and SQLite sources. Build tools include CMake, make, Python 3, zip, file, and the compilers for the desired targets.

```bash
# Build all four platforms
bash build-all.sh

# Or build one target
bash build-all.sh --target linux-x64
bash build-all.sh --target pi-arm64
bash build-all.sh --target win32
bash build-all.sh --target win64
```

Linux x64 builds use `musl-gcc`; ARM64 builds use the GNU cross compiler; Windows builds use MinGW x86/x64 compilers. These are **developer dependencies**, not game-client requirements.

The separate score and chat servers live under `hub/`. Production hub code, configuration, and databases should be deployed outside a client game directory so game upgrades do not affect the running services.

## 📖 Sysop reference.

| Topic | Guide |
| :--- | :--- |
| Seasonal campaigns and UTC calendar | [SEASONS.txt](docs/SEASONS.txt) |
| Playing the game | [PLAYING.txt](docs/PLAYING.txt) |
| Installation | [INSTALL.txt](docs/INSTALL.txt) |
| InterBBS score hub | [SCORE-HUB.txt](docs/SCORE-HUB.txt) |
| Shared live chat | [SHARED-CHAT.txt](docs/SHARED-CHAT.txt) |
| Signed updates | [ONLINE-UPDATES.txt](docs/ONLINE-UPDATES.txt) |
| Existing-install upgrades | [UPDATING.txt](docs/UPDATING.txt) |
| Build and test status | [RELEASE-VALIDATION.txt](docs/RELEASE-VALIDATION.txt) |

For bug reports, include your PUMPKO version, OS/architecture, BBS software, dropfile type, terminal client, and reproduction steps. **Never include credential JSON files, shared secrets, or private signing keys in an issue or commit.**

## ❤️ Built for the BBS.

Created by **StingRay (Jerry Reed)** at **[A-Net Online](https://a-net.online)**, with **[OpenDoors](https://github.com/RealDeuce/OpenDoors)** providing the door interface. Refer to the bundled OpenDoors license and notices for its licensing terms.

<div align="center">

**The calendar turns. The adventure changes. The BBS stays alive.**

🎃 ❄️ 💔 ☘️ 🐇 🌸 ☀️ 🎆 🦈 📚 🦃 🎅

</div>

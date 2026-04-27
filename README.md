# Outbreak Mod Registry

The centralized mod registry for **Resident Evil Outbreak** and **Resident Evil Outbreak File #2**, powering the [Outbreak Mod Manager & Launcher](https://github.com/dievour).

---

## Overview

This repository serves as the backbone of the Outbreak Mod Manager. The launcher reads from this registry on startup to discover available mods, fetch version information, display author credits, and provide players with one-click installation of mod files directly from their respective repositories.

---

## Currently Listed Mods

| Mod | Author | Game | Version |
|-----|--------|------|---------|
| **Terror Mod** | Terror Mod Team | FILE #1 & FILE #2 | F1: v4.3.6 / F2: v4.6.8 |
| **Apocalypse** | Despair | FILE #1 | v1.1.0 |
| **Madness** | darllanbr | FILE #2 | v1.0.0 |

---

## Structure

```
outbreak-mod-registry/
├── registry.json   ← Master mod list read by the launcher
├── LICENSE
└── README.md
```

Each mod listed in `registry.json` points to its own repository via a `manifest_url`. The launcher fetches the individual `mod.json` from each mod's repo to retrieve release data, download URLs, SHA-256 hashes, and patch notes.

---

## Registry Schema

Each mod entry in `registry.json` follows this structure:

```json
{
  "id": "mod-id",
  "aliases": ["mod", "mod-id", "modid"],
  "name": "Mod Display Name",
  "author": "Author Name",
  "contributors": ["Contributor A", "Contributor B"],
  "description": "Brief description of the mod.",
  "tags": ["stage"],
  "games": ["re_outbreak_f1", "re_outbreak_f2"],
  "featured": false,
  "version_f1": "1.0.0",
  "version_f2": "1.0.0",
  "min_manager_version": "1.0.0",
  "manifest_url": "https://raw.githubusercontent.com/author/mod-repo/main/mod.json",
  "thumbnail": "https://raw.githubusercontent.com/author/mod-repo/main/thumbnail.png",
  "updated_at": "2026-04-26T00:00:00Z"
}
```

### Tags

| Tag | Description |
|-----|-------------|
| `stage` | Stage and scenario file modifications — requires an ELF to boot |
| `skin` | Character skins, costumes, and 3D model replacements |
| `audio` | Music, sound effects, and voice modifications |
| `misc` | Quality of life, UI, and other miscellaneous modifications |

---

## Supported Games

| ID | Title | Supported Regions |
|----|-------|-------------------|
| `re_outbreak_f1` | Resident Evil Outbreak | NTSC-U, NTSC-J, PAL |
| `re_outbreak_f2` | Resident Evil Outbreak File #2 | NTSC-U, NTSC-J, PAL |

---

## For Mod Authors

If you would like your mod listed in the registry, your mod must have:

1. A public GitHub repository
2. A `mod.json` manifest in the root of your repository following the schema documented in the launcher
3. At least one published GitHub Release with mod files as assets
4. SHA-256 hashes for all release assets

Contact **Despair** to submit your mod for listing.

---

## License

This registry is licensed under the [MIT License](LICENSE).

Resident Evil Outbreak and Resident Evil Outbreak File #2 are properties of **Capcom Co., Ltd.** This project is a fan-made tool and is not affiliated with or endorsed by Capcom.


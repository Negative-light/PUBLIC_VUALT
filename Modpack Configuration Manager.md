---
tags:
  - programing
  - projects
---
This project should allow the user to create modpacks using version control. It should automatically
- Export to Cruseforge
    - Preferentially pulling mods from that platform
- Export to Modrinth
    - Preferentially Pulling mods form that platform
- Export to Zip
    - Preferentially pulling mods from Modrinth
- Automate version control
    - Minecraft version
    - Mod Set versions
    - Mod Updates Version
    - `<mc version>-<platform>-<mod set version>.<mods update verions>.<documentation updates version>`
- Provide packing to modpack docs
- automated changeloging
- All files should be stored in a OS format
- It should also automatically output a version with each platform and provide information on each including
    - The % of mods that exist inside each pack
    - The "Equated Categories" based on the categories of each of the mods (this is of course platform based information)

# Development

After having a conversation with Chat GPT and some other users I think i will make it in rust with the ultimate plan to use Tauri for. I also came up with a few command line ideas and a file format to store the information in.

## Commands
```sh
mccm init <moadpack-name>
mccm mod add <mod name>
mccm mod remove <mod name>
mccm mods
# Update all mods
mccm update
# Only Check for updates
mccm update -c 
mccm export
# Export Only Curseforge Version
mccm export cf
# Export only Modrinth version
mccm export mr
# Export only zip file
mccm export zip
mccm changelog
mccm doc
mccm analyize
mccm help
```

## File Format
```yaml
name: 'Example'
curseforge: true
modrinth: true
loaders:
    fabric: true
    forge: true
    neforge: true
mods:
    - name: "mod a"
    - versions:
        - "mc version": "max mod version"
    - loaders:
        - fabric
        - forge
        - neoforge
    - platforms:
        - curseforge: "project #"
        - modrinth: "project #"
```

### Todays notes
- I should work on [GitHub - packwiz/packwiz: A command line tool for editing and distributing Minecraft modpacks, using a git-friendly TOML format. Supports CurseForge and Modrinth mods with automated updates!](https://github.com/packwiz/packwiz), conversion as it probably has a lot of what I need to do.


# Naming
| Rank | Modpack Management Tool Names |
| ----:|:----------------------------- |
|    1 | Negative Pack Architect       |
|    2 | Negative Mod Matrix           |
|    3 | MatrixMod Manager             |
|    4 | Negative Craft Nexus           |
|    5 | Negative Mod Merger            |
|    6 | Negative Pack Pathfinder       |
|    7 | Negative Forge Fabricator      |
|    8 | Negative Wave Weaver           |
|    9 | Mod Meld Mastermind            |
|   10 | Craft Core Conductor           |

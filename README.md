# S.T.A.L.K.E.R. *.spawn Compiler/Decompiler

This tool is designed for unpacking and packing all.spawn/level.spawn files from any builds starting from 1265.

## Main Modes of Operation

- **Unpacking** original spawns from SoC, CS, CoP, and builds of SoC starting from xrCore build 1265.
- **Unpacking mod spawns** (requires the config folder from the mod).
- **Converting spawns** to any other version.
- **Mass replacing game vertices** in the unpacked spawn.
- **Splitting all.spawn** into level.spawn and level.game.
- **Comparing unpacked spawns**.
- **Updating vertices** according to object coordinates.

## Requirements

- The spawn itself (all.spawn or level.spawn).
- game.graph (only if unpacking all.spawn).
- config/configs folder (if unpacking a mod and universal acdc complains about an unknown section).

## Usage

Place **all.spawn** (or **level.spawn**) and **game.graph** into the folder with the program, create a batch file with the necessary commands, and run it.

## Commands

### Unpacking Spawn

Command: `universal_acdc -d <spawn_file> [common_options]`

- `-d <spawn_file>` — path to the spawn file.
- `common_options` — common options (described below).

If an "unknown section" error occurs when unpacking mod spawns, use the `-scan` key with the path to the config/configs folder.

### Packing Spawn

Command: `universal_acdc -compile <dir> [-idx <index_file>] [-f <flag1,flag2,...>] [common_options]`

- `-compile <dir>` — folder with the unpacked spawn.
- `-idx <index_file>` — creates a config with object sections.
- `common_options` — common options.

### Converting Spawn

Command: `universal_acdc -convert <file> -version <new_version> [-ini <file>] [common_options]`

- `-convert <file>` — file for conversion (packed or unpacked).
- `-version <new_version>` — new spawn version.
- `-ini <file>` — file for fine-tuning the conversion.
- `common_options` — common options.

### Mass Replacing Vertices

Command: `universal_acdc -parse <file> -old <old_gvid0> -new <new_gvid0> [-way] [common_options]`

- `-parse <file>` — name of the ltx file with the spawn.
- `-old <old_gvid0>` — old starting game_vertex_id of the location.
- `-new <new_gvid0>` — new starting game_vertex_id of the location.
- `-way` — process the way_***.ltx file for the same location.
- `common_options` — common options.

### Splitting all.spawn into level.spawn

Command: `universal_acdc -split <file> [-use_graph] [-way] [common_options]`

- `-split <file>` — file for splitting.
- `-use_graph` — use game.graph to restore graph points.
- `-way` — generate level.game from the spawn.
- `common_options` — common options.

### Comparing Unpacked Spawn Files

Command: `universal_acdc -compare <file1,file2> [common_options]`

- `-compare <file1,file2>` — files for comparison.
- `common_options` — common options.

### Updating Vertices by Coordinates

Command: `universal_acdc -update <spawn_name> [common_options]`

- `-update <spawn_name>` — all.spawn file for vertex updating.
- `common_options` — common options.

## Common Options

- `-out <file>` — path to the result file/folder.
- `-scan <scan_dir>` — path to the config folder.
- `-g <graph_dir>` — path to the game.graph folder.
- `-level` — process spawn as level.spawn.
- `-af` — unpack/pack artifact spawn locations (section2.bin).
- `-nofatal` — disable crash on fatal error.
- `-sort <type>` — sorting of alife objects (simple or complex).

## Spawn Versions

| Version | Script Version | Build                                      |
|---------|----------------|--------------------------------------------|
| 128     | 12             | Call Of Pripyat (any patch)                |
| 124     | 8              | Clear Sky (1.5.04 - 1.5.10)                |
| 123     | 8              | Clear Sky (1.5.03)                         |
| 122     | 8              | Clear Sky (1.5.00 - 1.5.02)                |
| 118     | 6              | Shadow Of Chernobyl (1.0001 or higher)     |
| 118     | 5              | xrCore build 2559-2947                     |
| 117     | 4              | xrCore build 2571                          |
| 115     | 3              | xrCore build 2365                          |
| 109     | 2              | xrCore build 2307                          |
| 104     | 2              | xrCore build 2217, 2232                    |
| 103     | 2              | xrCore build 2198, 2191                    |
| 102     | 2              | xrCore build 2221                          |
| 101     | 2              | xrCore build 2205, 2215                    |
| 95      | 1              | xrCore build 2218-2201                     |
| 94      | 1              | xrCore build 2212-2217                     |
| 93      | 0              | xrCore build 2202                          |
| 92      | 0              | xrCore build 1994                          |
| 90      | 0              | xrCore build 1964-1971                     |
| 89      | 0              | xrCore build 1957                          |
| 85      | 0              | xrCore build 1936                          |
| 79      | 0              | xrCore build 1935                          |
| 77      | 0              | xrCore build 1925                          |
| 76      | 0              | xrCore build 1902-1917                     |
| 75      | 0              | xrCore build 1893                          |
| 73      | 0              | xrCore build 1875                          |
| 72      | 0              | xrCore build 1865                          |
| 65      | 0              | xrCore build 1850                          |
| 63      | 0              | xrCore build 1842                          |
| 60      | 0              | xrCore build 1844 (19 May 2005)            |
| 59      | 0              | xrCore build 1833-1835                     |
| 56      | 0              | xrCore build 1834 (09 April 2005)          |
| 51      | 0              | xrCore build 1844-1849                     |
| 49      | 0              | xrCore build 1835                          |
| 47      | 0              | xrCore build 1834 (09 Feb 2005)            |
| 46      | 0              | xrCore build 1829                          |
| 45      | 0              | xrCore build 1828                          |
| 44      | 0              | xrCore build 1851                          |
| 41      | 0              | xrCore build 1837                          |
| 40      | 0              | xrCore build 1610-1638                     |
| 39      | 0              | xrCore build 1511-1580                     |
| 38      | 0              | xrCore build 1510                          |
| 35      | 0              | xrCore build 1475                          |
| 34      | 0              | xrCore build 1475                          |
| 16      | 0              | xrCore build 1472                          |
| 14      | 0              | xrCore build 1472                          |
| 13      | 0              | xrCore build 1472                          |
| 8       | 0              | xrCore build 1469                          |
| 7       | 0              | xrCore build 1465                          |
| 3       | 0              | xrCore build 1233-1265                     |
| 2       | 0              | xrCore build 1230-1254                     |

## Usage of AI Locations

### Always spawn by coordinates

- CSE_ALifePHSkeletonObject
- CSE_ALifeSpaceRestrictor
- CSE_ALifeObjectPhysic
- CSE_ALifeObjectHangingLamp
- CSE_ALifeObjectProjector
- CSE_ALifeHelicopter
- CSE_ALifeCar
- CSE_ALifeObjectBreakable
- CSE_ALifeObjectClimable
- CSE_ALifeItemBolt
- CSE_ALifeCreatureCrow
- CSE_ALifeCreaturePhantom

### Always spawn by nodes

- CSE_ALifeSmartZone
- CSE_ALifeCreatureAbstract

## Notes

- To work correctly with builds 25xx spawns, delete `sections.ini` and rescan the configs before each new unpacking.
- If an error 'unknown clsid ... for section...' occurs, add new sets to `clsids.ini`.

## Authors

- ACDC for SoC: bardak
- ACDC for CoP: bardak, Kolmogor
- Everything else: K.D.

Use and share, crediting the authors.

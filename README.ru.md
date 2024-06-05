# S.T.A.L.K.E.R. *.spawn Compiler/Decompiler

Этот инструмент предназначен для распаковки и запаковки файлов all.spawn/level.spawn любых билдов, начиная с 1265.

## Основные Режимы Работы

- **Распаковка** оригинальных спавнов ТЧ, ЧН, ЗП и билдов ТЧ, начиная с xrCore build 1265.
- **Распаковка спавнов модов** (требуется папка конфигов от мода).
- **Конвертация спавнов** в любую другую версию.
- **Массовая замена гейм-вертексов** в распакованном спавне.
- **Разбивка all.spawn** на level.spawn и level.game.
- **Сравнение распакованных спавнов**.
- **Обновление вертексов** согласно координатам объектов.

## Требования

- Сам спавн (all.spawn или level.spawn).
- game.graph (только если распаковывается all.spawn).
- Папка config/configs (если распаковываете мод и универсальный acdc жалуется на unknown section).

## Использование

Поместите **all.spawn** (или **level.spawn**) и **game.graph** в папку с программой, создайте батник с нужными командами и запустите его.

## Команды

### Распаковка Спавна

Команда: `universal_acdc -d <spawn_file> [common_options]`

- `-d <spawn_file>` — путь до спавна.
- `common_options` — общие опции (описаны ниже).

Если при распаковке спавнов модов возникает ошибка "unknown section", используйте ключ `-scan` с указанием пути до папки config/configs.

### Запаковка Спавна

Команда: `universal_acdc -compile <dir> [-idx <index_file>] [-f <flag1,flag2,...>] [common_options]`

- `-compile <dir>` — папка с распакованным спавном.
- `-idx <index_file>` — создает конфиг с секциями объектов.
- `common_options` — общие опции.

### Конвертирование Спавна

Команда: `universal_acdc -convert <file> -version <new_version> [-ini <file>] [common_options]`

- `-convert <file>` — файл для конвертации (запакованный или распакованный).
- `-version <new_version>` — новая версия спавна.
- `-ini <file>` — файл тонкой настройки конвертации.
- `common_options` — общие опции.

### Массовая Замена Вертексов

Команда: `universal_acdc -parse <file> -old <old_gvid0> -new <new_gvid0> [-way] [common_options]`

- `-parse <file>` — имя ltx-файла с спавном.
- `-old <old_gvid0>` — старый начальный game_vertex_id локации.
- `-new <new_gvid0>` — новый начальный game_vertex_id локации.
- `-way` — обработка файла way_***.ltx для этой же локации.
- `common_options` — общие опции.

### Разбивка all.spawn на level.spawn

Команда: `universal_acdc -split <file> [-use_graph] [-way] [common_options]`

- `-split <file>` — файл для разбивки.
- `-use_graph` — использование game.graph для восстановления граф-поинтов.
- `-way` — генерация level.game из спавна.
- `common_options` — общие опции.

### Сравнение Файлов Распакованного Спавна

Команда: `universal_acdc -compare <file1,file2> [common_options]`

- `-compare <file1,file2>` — файлы для сравнения.
- `common_options` — общие опции.

### Обновление Вертексов по Координатам

Команда: `universal_acdc -update <spawn_name> [common_options]`

- `-update <spawn_name>` — файл all.spawn для обновления вертексов.
- `common_options` — общие опции.

## Общие Опции

- `-out <file>` — путь до файла/папки с результатом.
- `-scan <scan_dir>` — путь до папки с конфигами.
- `-g <graph_dir>` — путь до папки с game.graph.
- `-level` — обрабатывать спавн как level.spawn.
- `-af` — распаковка/запаковка мест спавна артефактов (section2.bin).
- `-nofatal` — отключение вылета при фатальной ошибке.
- `-sort <type>` — сортировка alife-объектов (simple или complex).

## Версии спавнов

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

## Использование Ai локаций

### Всегда спавнятся по координатам

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

### Всегда спавнятся по нодам

- CSE_ALifeSmartZone
- CSE_ALifeCreatureAbstract

## Примечания

- Для корректной работы со спавнами билдов 25xx удаляйте `sections.ini` и сканируйте конфиги заново перед каждой новой распаковкой.
- Если возникнет ошибка 'unknown clsid ... for section...', добавьте новые сеты в `clsids.ini`.

## Авторы

- ACDC для ТЧ: bardak
- ACDC для ЗП: bardak, Kolmogor
- Все остальное: K.D.
- Бинарный файл и обновление под новую версию Perl: (PSI)[https://github.com/PSIget]

Используйте и выкладывайте, указывая авторов.

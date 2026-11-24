# Moving Castle Pack: beta QA

Checklists for beta testers of the moving castle pack's own mods: Thaumic Concilium, Forbidden Magic (Thaumaturge),
Thaumic Horizons and Aspect Interpreter. Every build here is a **beta**: it passes the automated pack test, but most of
it has never been played. You are the first people to play it.

32 chapters, 336 checks, generated 2026-11-24 from the pack's QA specs.

## 1. Set up

1. Install the pack in Prism Launcher (NeoForge 21.1.265, Minecraft 1.21.1) with the mods in [SETUP.md](SETUP.md).
   Our mods are on their GitHub release pages (linked there).
2. Download `qa-quests-<date>.zip` from this repo's [latest release](../../releases/latest) and unzip it into the
   instance's `minecraft` folder (it adds `config/ftbquests/quests/chapters/qa_*.snbt` and
   `config/thaumicconcilium/qa_stages.json`).
3. Make a **new singleplayer world with cheats on** (or Open to LAN with Allow Cheats). Staging resets your research
   and empties your inventory, so never use a world you care about.

## 2. Test

Open the quest book. Each **QA:** chapter is one feature. In a check, click the green **Set up this check** line: you
are moved to a fresh pad far away, given the kit and only the research that check needs, and the test build appears in
front of you. Follow the steps in chat, then click **[Pass, next]**, **[Fail, next]**, **[Again]** or **[Skip]**.
Every verdict is written to `qa_verdicts.log` in the instance's `minecraft` folder.

The checklists below hold the same steps, so you can read ahead or test without the quest book.

## 3. Report

- One [QA report](../../issues/new?template=qa-report.yml) per failed check (passes can go in one report per chapter).
  Attach `qa_verdicts.log` and, for a crash, the crash report from `crash-reports/`.
- Anything that is not a check (a crash on start, a bug you found while playing): [bug report](../../issues/new?template=bug.yml).
- Say how it felt as well as whether it worked: balance, clarity and fun count.

## Chapters

| Chapter | Id | Checks |
|---|---|---|
| [Aspect Interpreter 1.9.0: no runaway amounts](checklists/aspect_interpreter_1_9.md) | `aspect_interpreter_1_9` | 5 |
| [Botania wand parts](checklists/botania.md) | `botania` | 4 |
| [Casting Bracelets](checklists/bracelets.md) | `bracelets` | 8 |
| [Crimson outfits (0.16.0)](checklists/crimson_outfits.md) | `crimson_outfits` | 4 |
| [Foci ported 1:1](checklists/foci_restored.md) | `foci_restored` | 8 |
| [Forbidden Magic (Thaumaturge)](checklists/forbidden_magic.md) | `forbidden_magic` | 19 |
| [Horizons H1: the Vat](checklists/horizons_h1.md) | `horizons_h1` | 9 |
| [Horizons H2: souls and golems](checklists/horizons_h2.md) | `horizons_h2` | 9 |
| [Horizons H3: species mobs](checklists/horizons_h3.md) | `horizons_h3` | 9 |
| [Horizons H4: self-infusion](checklists/horizons_h4.md) | `horizons_h4` | 5 |
| [Horizons H5: tools, foci, lenses and boats](checklists/horizons_h5.md) | `horizons_h5` | 10 |
| [Horizons H6: Balanced Shard and vis machines](checklists/horizons_h6.md) | `horizons_h6` | 6 |
| [Horizons H7-1: the planar rift core](checklists/horizons_h7_1.md) | `horizons_h7_1` | 8 |
| [Horizons H7-2: the pocket plane](checklists/horizons_h7_2.md) | `horizons_h7_2` | 5 |
| [Horizons H7-3a: the plane's features](checklists/horizons_h7_3a.md) | `horizons_h7_3a` | 5 |
| [Horizons H7-3b: the planar clouds](checklists/horizons_h7_3b.md) | `horizons_h7_3b` | 7 |
| [Horizons H7-4: keystones and gateways](checklists/horizons_h7_4.md) | `horizons_h7_4` | 9 |
| [Horizons H7-5: void-craft products](checklists/horizons_h7_5.md) | `horizons_h7_5` | 6 |
| [Horizons H7-6: the Teleological Recombinator](checklists/horizons_h7_6.md) | `horizons_h7_6` | 4 |
| [Powders and the Burdening Amulet](checklists/phase3_restorations.md) | `phase3_restorations` | 10 |
| [Crimson Forces (5a)](checklists/phase_5a.md) | `phase_5a` | 19 |
| [Flesh, Peeler and the Crimson Dagger (5b)](checklists/phase_5b.md) | `phase_5b` | 16 |
| [The Vessel (5c)](checklists/phase_5c.md) | `phase_5c` | 24 |
| [The Vessel (5d): capital, endings, grove, pond](checklists/phase_5d.md) | `phase_5d` | 28 |
| [Monitors and machines (6b)](checklists/phase_6b.md) | `phase_6b` | 17 |
| [The Brightest One and subspace (6c)](checklists/phase_6c.md) | `phase_6c` | 13 |
| [Phase 7: Valet Seal and Vengeful Golem](checklists/phase_7.md) | `phase_7` | 14 |
| [Phase 8: Assistant Seal, Golem Bydlo and the Balanced Shard](checklists/phase_8.md) | `phase_8` | 11 |
| [Phase 8-4: Protobody, Protolimbs, Solid Void](checklists/phase_8_4.md) | `phase_8_4` | 5 |
| [The rift workshop](checklists/rift_workshop.md) | `rift_workshop` | 8 |
| [Shield Foci](checklists/shield_foci.md) | `shield_foci` | 20 |
| [Thaumaturges and the fallen](checklists/thaumaturges.md) | `thaumaturges` | 11 |

## Licences

The checklists and quest files are MIT. The mods keep their own licences (see each repo). No third-party mod files are
distributed here.

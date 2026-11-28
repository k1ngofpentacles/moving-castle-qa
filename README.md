# Moving Castle Pack: beta QA

Checklists for beta testers of the moving castle pack's own mods: Thaumic Concilium, Forbidden Magic (Thaumaturge), Thaumic Horizons, Gadomancy and Aspect Interpreter. Every build here is a **beta**: it passes the automated pack test, but most of
it has never been played. You are the first people to play it.

5 chapters, 221 checks, generated 2026-11-28 from the pack's QA specs.

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
| [Aspect Interpreter](checklists/aspect_interpreter.md) | `aspect_interpreter` | 1 |
| [Thaumic Concilium](checklists/concilium.md) | `concilium` | 98 |
| [Forbidden Magic](checklists/forbidden_magic.md) | `forbidden_magic` | 16 |
| [Gadomancy](checklists/gadomancy.md) | `gadomancy` | 50 |
| [Thaumic Horizons](checklists/horizons.md) | `horizons` | 56 |

## Licences

The checklists and quest files are MIT. The mods keep their own licences (see each repo). No third-party mod files are
distributed here.

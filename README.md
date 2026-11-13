# The Ashen Gate

*A document-inspection game about papers and plague.*

**▶ Play it:** https://eddyarriaga00.github.io/ashen-gate/

It is the autumn of 1631. A demonic sickness called **the Hollowing** is spreading through the parishes
around the walled city of Halvermarch. You are the Warden of the Ashen Gate. Every traveller hands papers
through your window. Check the papers, check the person, then stamp one of three judgements:

| Stamp | When it's right |
|---|---|
| **ADMIT** | Papers in order, no Signs of the Hollowing |
| **TURN AWAY** | Papers wrong, but the traveller is clean |
| **CONDEMN** | Hollowed, or from a sealed parish |

Papers can be perfect while the person is Hollowed. Papers can be forged while the person is innocent.

## Features
- **12-day campaign** with recurring characters, a daily newspaper, new ordinances each morning and seven endings.
- **Inspection tools:** compare documents in inspect mode, the tallow candle (the Hollowed cast a false shadow), holy water (cursed ink boils), magnifying zoom.
- **Wartime economy:** bread, coal, incense and medicine prices rise as the war drags on, alongside lodging, levies, arrears and bribes. Keep your family alive.
- **Hand-made pixel art,** rendered procedurally in canvas. No image assets.
- **Plays on desktop and mobile.** Landscape, plus a dedicated portrait layout for phones. Touch drag and stamping.
- **Saves** to the browser's local storage, so you can resume any day you've reached.

## Controls
| Action | Desktop | Mobile |
|---|---|---|
| Call next traveller | Bell / `N` | Tap bell |
| Move papers | Drag | Drag |
| Inspect mode | `Space` | Inspect button |
| Stamp (with the lever upgrade) | `1` `2` `3` | Stamp bar |
| Zoom a document | Double-click | Double-tap |

## Running locally
It's a single HTML file with no build step:

```bash
open ashen-gate.html
```

Or serve the folder with any static server, for example `python3 -m http.server`.

## Project layout
- `ashen-gate.html`: the whole game (HTML, CSS and JS).
- `index.html`: redirects to the game (GitHub Pages entry point).
- `DESIGN.md`: design plan, the campaign table and notes from each pass.

## License
MIT. See [LICENSE](LICENSE).

# THE ASHEN GATE — Design Plan

*A document-inspection game about papers and plague.*

## Pitch
It is the autumn of 1631. A demonic sickness called **the Hollowing** is spreading through the
parishes around the walled city of **Halvermarch**. You are the Warden of the Ashen Gate. Every
traveller hands you papers through a barred window. You check the papers, you check the person,
and you give one of three judgements:

| Stamp | Meaning | When it's right |
|---|---|---|
| **ADMIT** (green wax) | Enters the city | Papers are in order and no Signs of the Hollowing |
| **TURN AWAY** (black ink) | Sent back down the road | Papers are wrong, but the person is not Hollowed |
| **CONDEMN** (red wax) | Dragged to the Lazaret | Hollowed, or from a parish that has been sealed |

The third stamp is the main change from the immigration-booth formula. Papers can be perfect and the
person can still be Hollowed. Papers can be forged and the person can be innocent. Condemning someone
is lethal, so the guilt hits harder than a simple deny.

## Core loop (one day)
1. **Morning: The Halvermarch Crier.** A newspaper with the day's headline and a **new ordinance**
   (a new rule or a new tool).
2. **The shift (06:00 to 18:00, about 3 real minutes).** Ring the bell, and the next traveller walks
   from the queue to your window.
   - **Drag** papers around the desk.
   - **Inspect mode** (Space): click two things to compare them, such as a name and a name, a seal
     and the rulebook seal, an expiry date and today's date, or the person and a Sign. A red thread
     links the two and the Warden questions the traveller about any discrepancy.
   - **Tallow candle** (limited each day): lights the antechamber. *A Hollowed soul's shadow does not
     match its owner.* This is the only way to catch an early infection.
   - Open the **stamp bar**, slide the Writ under a stamp, and press it.
   - **Hand the papers back** by dragging them to the window. The traveller leaves and the vista
     shows where they went: through the gate, back down the road, or to the pyre.
3. **Night: The Ledger.** Wages (5 silver for each correct judgement) minus citations. Pay for lodging,
   bread, coal and **incense**. Each Hollowed soul you let in raises the **City Taint**. With no
   incense burning, the taint can reach your family.

## Documents and rules (how difficulty ramps)
| Day | New ordinance | New ways to fail |
|---|---|---|
| 1 | Writ of Passage required. Condemn anyone showing Signs. | Expired writ, forged parish seal, unknown parish, likeness doesn't match |
| 2 | Bill of Health from a **Registered Physician** required. Tallow candles issued. | Missing bill, name mismatch, unregistered physician, *shadow-only* infections |
| 3 | **Greyhallow is sealed**: condemn all who come from it. Bills older than 2 days are void. | Stale examination date, sealed parish |
| 4+ (planned) | Confessions, relics, bribes, a cult smuggling the Hollowed, the Inquisition auditing *you* | Interrogation, forged ink (tested with holy water), the Warden's own infection |

### Signs of the Hollowing (the rulebook's medical page)
- Black veins climbing the throat
- Eyes gone milk-white or ember-red
- Black tears
- A shadow that does not match its owner (visible only by candlelight)

Decoys such as pox, scars and eye-patches look sinister but are **not** Signs. Condemning for them earns a citation.

## Art direction
- **Pixel art at a 3× scale**, rendered in code on a 320×200 virtual canvas, with a chunky, muted
  palette of soot, ash, bone and parchment, plus one hot colour: ember.
- **Three-panel screen**: a gate vista across the top (city wall, portcullis, plague-doctor
  guards, the queue, a smoking pyre, falling ash), the booth window bottom-left with the traveller,
  and the desk bottom-right.
- **Type**: pixel blackletter for headings and seals, a pixel grotesque for fields.
- Each traveller is a **procedural portrait**: skin, cloak, headwear (hood, hat, coif, cap or bare),
  beard, age, ruff, decoys and Signs. The likeness engraved on the Writ uses the same generator and
  is shown in sepia.
- Art pass 2: portraits with 4-tone skin, irises, rim light, satchels, brooches and pilgrim badges; Hollowed veins pulse and their eyes glow. The vista now has layered sky, ash clouds, a cathedral, torches, waving flags, fog, puddle reflections and crow flocks. The booth has a swinging lantern and dust motes; the desk has a candlestick, an hourglass that drains with the shift, and film grain with a vignette.
- Art pass 3: portraits are rendered by a small lighting engine. Each face is a sculpted height field (brow ridge, eye sockets, cheekbones, nose, lips, chin) lit by a warm lantern key and a cool night fill, quantized to 8 to 9 tone hue-shifted ramps with ordered dithering. Hair, beards, hats, hoods, coifs, cloaks, straps and brass are lit the same way.
- Mobile: on a tall phone the whole stage rotates to landscape at full size. Touch dragging is supported, and double-tapping any paper opens it large to read.
- Synthesized sound: stamp thud, paper rustle, bell, candle, an ambient drone with wind.

## Prototype scope (this build)
- [x] Title screen, 3 days with newspapers, ledger and an end card
- [x] Procedural travellers, documents, faults and the correct verdict
- [x] Dragging, stamp bar, handing papers back, inspect-pair system, candle shadows
- [x] Citations, wages, family needs, City Taint
- [ ] Save/load, more days, story characters, interrogation, more tools


## The 12-day campaign (built)
| Day | Date | New pressure | Story beat |
|---|---|---|---|
| 1 | 14.XI | Writ of Passage | Sister Maude, a nurse of Saint Wendel, passes through |
| 2 | 15.XI | Bill of Health, Registry, candles | Ilse Brandt pleads for her son Tobi, who comes next with black tears |
| 3 | 16.XI | Greyhallow sealed; Bills void after 2 days | Inquisitor Valeska Morn arrives |
| 4 | 17.XI | Holy water: cursed ink boils | The Ember Brotherhood leaves a note: let the red cord through |
| 5 | 18.XI | Low Corvane sealed | Sister Maude returns, Hollowed |
| 6 | 19.XI | Dr. Roe struck off; Deep Hollowed (no Signs, true shadow) | Pim falls ill at home (medicine) |
| 7 | 20.XI | Rent rises to 20 | Travellers carry Roe's void Bills |
| 8 | 21.XI | Inquisition audit: errors cost 10 | Ilse returns; her words depend on what you did to Tobi |
| 9 | 22.XI | Thistlewick sealed, Low Corvane reopened; Bills void after 1 day | A family member may bear the Signs: Lazaret or hide them |
| 10 | 23.XI | Only three parishes may enter | The Brotherhood offers your family passage out |
| 11 | 24.XI | Red cords are now to be Condemned (20 silver bounty) | Brother Ansel brings pitch for the fires |
| 12 | 25.XI | Trust only the Book | The Lord Protector's herald orders the Gate opened. He is Deep Hollowed |

**Endings:** The Gate Holds · The Herald's Dusk · Halvermarch Hollows (Taint 8) · The Inquisition's Guest (14 citations or 3 audit errors) · Turned Out (can't pay rent) · Over the Hills (flee with the Brotherhood).

**Art direction, pass 4:** portraits are posterized into hard tone bands with muted colour, a dark outline and contour seams. The UI is pixel-pure, with no film grain, and includes a transcript tape of every exchange.

## Research-driven additions (pass 5)
These draw on the genre's proven pillars, built as our own mechanics:
- **Interview as evidence:** the Warden asks each traveller's business, and their answer prints on the transcript. From Day 3, the stated business must match the Writ's Purpose. In inspect mode you compare the transcript line with the field.
- **Distinguishing Marks** on the Writ (pox, scars, eye-patch). From Day 5 they must match the face, so the decoy features now matter.
- **Bribes:** from Day 3, some improperly papered travellers slide a purse under the shutter. Hand it back, or keep it for silver. A purse kept on audit day is a citation, and five purses trigger the *A Heavy Purse* ending.
- **Booth improvements** (bought in the ledger): Oil lantern (+2 candles), Blessed font (+2 holy water), Brass stamp lever (stamp with keys 1, 2 and 3). The bell is on N, and inspect on Space.
- **The gate rush:** on Days 5, 9, 11 and 12, a Hollowed sprints at the Gate. Tap it on the road to bring in the crossbows (+5 silver), or it breaks the line (Taint, citation).
- **Day-to-dusk light:** the vista shifts from cold dawn to red dusk to dark as the shift runs.
- **Return to any morning:** each day is saved in the browser. The title screen lists reached days, labelled with that day's headline.

## Wartime economy (pass 6)
Wages stay fixed at 5 silver per correct judgement while the war drives prices up:
| | Days 1–5 | Days 6–7 | Days 8–12 |
|---|---|---|---|
| Lodging (required) | 12 | 12 → 16 from Day 7 | 16 |
| Bread | 6 → 7 | 7 → 8 | 8 → 9 |
| Coal | 4 | 6 (winter) | 6 |
| Incense | 5 | 5 | 7 (shortage) |
- War levies: 8 silver on Day 5 and 10 silver on Day 10 (required).
- The first two citations each day are warnings; after that, 5 silver each (10 on audit day).
- **Arrears:** if you can't make the required payments, the landlord waits one night (nothing else can be bought). A second short night is the *Turned Out* ending.
- Target pace: about 6 correct a day breaks even early and loses 5–10 a day late; 8+ a day stays solvent, which leaves bribes and bounties as real temptations.

## Portrait mode (pass 6)
On a tall screen the stage becomes a 540-wide portrait layout instead of rotating. The vista sits on top (2× scale, cropped to the gate and queue), the booth with a column of large tool buttons beside it, and a tall desk below. The stage height stretches to the phone's own aspect (960–1260), and the extra height goes to the desk. Every document position, drop zone, stamp footprint, zoom centre and slip is driven by a layout table, so turning the phone rearranges a day in progress. The newspaper, ledger, title and endings reflow to one column.

## Next steps after the prototype
1. Playtest the inspect loop. It's the heart of the game and needs to feel snappy.
2. Add recurring story characters (a mother pleading for her son, a cultist with a coded note, the
   Inquisitor who audits you).
3. Hand-paint key art over the procedural base, or replace the generator with sprite layers.
4. Choose an engine for the full game (Godot works well for 2D pixel games) and port the systems.

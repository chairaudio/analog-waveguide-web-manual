# Analog Waveguide Manual — Content Comparison

**Source A (web):** *Analog Waveguide — Manual of Operation*, https://chairaudio.github.io/analog-waveguide-web-manual/ — compared against the complete page source (`index.html`, ~105 KB), so coverage extends through the last section.
**Source B (TeX):** [manual.tex](doclib://01a0f6a8-a6cd-76db-b296-38a6e8527272/7ab58ca3-db6a-4eb0-bf0f-2291ebc87427) — firmware version 1.3.0, hardware revision 3.2, document revision C

Both documents claim **firmware 1.3.0 / hardware rev. 3.2**, and the overall chapter structure is identical (Preface → Module Overview → Individual Functions → Display → Patch Examples → Menu System → Calibration → Firmware Update → Cleaning → Firmware Version History → Manufacturer → Bibliography). Layout-only differences (explicit "Fig. 2.1" numbers vs. LaTeX-generated ones, QR code vs. link, sentence/paragraph splitting, table markup, the web-only sidebar/TOC) are ignored below, as requested. Note: the TeX title page lives in a separate `\include{Titlepage}` file that was not part of the attachment.

> **Note on the six "missing" patch examples:** manual.tex contains *commented-out placeholder headings* (`%\section{Gong}`, `Singing Saw`, `Frame Drum`, `Wood Organ`, `Vintage Reverb`, `Tanpura Drone`) with no content. Neither document actually contains these sections, so the identical patch-example list (4.1–4.6) is **not** a discrepancy.

---

## 1. Substantive content differences

### 1.1 Footnotes: present on the web, but 8 of 12 are reworded — several shortened with information dropped ⚠️

The web page **does** contain all 12 footnote texts (in the "Notes" section at the bottom of the page, linked from the superscript markers 1–12). However, only 4 are verbatim identical; the rest were rewritten for the web version, in several cases losing content:

| # | Topic | Status |
|---|---|---|
| 1 | Stereo phase analyzer (§1.2) | **Rewritten.** TeX explains the 45°-rotated view in those analyzers ("left and right channels are the diagonals… They are also called **audio goniometers**"). Web instead justifies the design choice: "We chose to not rotate our display, so that the quadrants… directly correspond to the sign of the X and Y signals." The goniometer mention is dropped. |
| 2 | Mono mix of anti-phase signal (§1.2) | **Shortened.** TeX: "…silence; very inconvenient for listeners on the kitchen radio. **Hence the importance of the stereo phase analyzer in broadcasting.**" Web keeps only the cancellation explanation and drops the broadcasting rationale. |
| 3 | "Normalled" connections (§1.2) | **Completely rewritten.** TeX *defines the term*: "An in-built connection behind the front panel is sometimes referred to as a 'normalled' connection, we will continue to use this term later in document." Web instead: "An in-built connection that is broken as soon as a cable is inserted into the corresponding input." |
| 4 | Theta notation (§1.2) | Shortened: "commonly used in geometry as a symbol for an angle" → "commonly used to denote an angle". |
| 5 | Pseudo-physical models (§1.4) | **Rewritten.** TeX: "…recreate a specific real-world object with mathematical accuracy, but are algorithms or circuits which exhibit a behavior with characteristics satisfying our expectations towards interaction with the world." Web: "…model an existing acoustic instrument or physical object with complete accuracy, but rather explore the sonic possibilities that physical modeling techniques open up, without a real-world equivalent necessarily existing." |
| 6 | Bucket Brigade Delay (§2.1) | **Strongly shortened.** TeX explains the BBD principle ("a chip with a series of capacitors (stages), where a signal can be moved through driven by the speed of a clock. The faster the clock, the higher is the pitch. The two BBDs in the Analog Waveguide have **1024 stages each**."). Web reduces this to: "a chip technology used for the analog delay lines at the heart of the Analog Waveguide." The 1024-stages detail exists nowhere else on the page. |
| 7 | Endless potentiometer (§2.5) | **Replaced.** TeX compares endless pots to digital encoders ("more robust and tend to have a longer lifespan while providing continuous analog values compared to digital encoders which have a limited lifespan and can only offer discrete steps"). Web instead notes the rotation-direction fix ("Corrects endless potentiometer rotation direction—see the firmware version history…") and adds a shorter definition ("no minimum or maximum position and can be turned indefinitely"). |
| 8 | VCV Rack dummy module (§4.x) | **Shortened.** TeX: "…a dummy Analog Waveguide module for VCV Rack without any DSP in it. **There is currently no functional Analog Waveguide module for VCV Rack.**" Web drops the no-functional-module statement and adds a gloss: "…for VCV Rack, a modular synthesizer simulator, for illustrative purposes only." |
| 9 | "In VCV Rack: 'Twin Peaks'" (§4.x) | Identical. |
| 10 | Firefox/Safari not Chromium-based (§7.2) | Identical. |
| 11 / 12 | STM32 Cube Programmer / dfu-util URLs | Same targets; web drops the `https://` scheme (link text only). |

### 1.2 Two sentences dropped from the Patch Examples intro ⚠️

manual.tex (chapter *Patch Examples*) contains:

> "Personally, we don't believe that exactly reproducing the sounds of acoustic instruments is necessarily the main goal of sound designers or electronic musicians. Despite that however, we still came up with some patches that mimic acoustic instruments."

Neither sentence appears on the web page; the web intro jumps straight from the building-blocks motivation to "We think these patches are a great way to learn…".

### 1.3 Intro sentence dropped in "Input and Output Section" (2.4)

TeX opens the section with: "Each channel, X and Y has its own in- and output section, see Figure …" — absent from the web version (the accompanying figure was removed as well).

### 1.4 Link-switch sentence dropped in 2 of 3 entries (2.6) ⚠️

TeX ends the **Lowpass**, **Feedback** and **Pitch** link-switch descriptions with:

> "Flipping the switch to the right enables the link, flipping it left disables it."

The web version keeps this sentence only in the **Lowpass Link Switch** entry and drops it from **Feedback** and **Pitch** (reasonable de-duplication, but a content difference).

### 1.5 Quadrant diagram caption missing in "The maths…" (1.2)

The TeX includes an equation-figure (II|I / III|IV quadrant array) captioned **"The four quadrants of a Cartesian plane."** The web version has no equivalent figure/caption (the `.quadrant-table` CSS class exists but is unused in the page body).

### 1.6 One sentence dropped in "Unfolded String Model" (4.6)

TeX: "In Figure … you can see the necessary parameter settings." — the web version contains no counterpart ("necessary parameter" does not appear anywhere on the page). Related web rewordings in this section are listed under §2.

---

## 2. Word-level differences (TeX → web)

The web version contains numerous small wording fixes. Typos present in the TeX are corrected on the web:

| TeX (manual.tex) | Web |
|---|---|
| "dis**encouraged**" (Preface) | "discouraged" |
| "**an** hand pan" (Module Overview) | "a hand pan" |
| "**Strings** instruments" (1.1) | "String instruments" |
| "non-linear **non-linear** FM like sounds" (2.5 — duplicated word) | "non-linear FM-like sounds" |
| "**acoustical** instruments" (Patch Examples) | "acoustic instruments" |
| "Analog **Wavaguide**" (4.3) | "Analog Waveguide" |
| "play the **trumped**" (4.4) | "play the trumpet" |
| "we **will** an ADSR" (4.4) | "we use an ADSR" |
| "changing **pick** position" (4.6) | "changing **pluck** position" (consistent with the rest of the section) |
| "You should **here** a sine wave" (6.2, Trim CV feed-through) | "You should hear a sine wave" |
| "Cleaning and **Maintainance**" (chapter 8 heading) | "Cleaning and Maintenance" |
| "For **F**irmware update. DFU **M**ode **D**evice ID" (spec table) | "For firmware update. DFU mode device ID" (casing) |
| "81.92kHz", "1 %", double spaces after periods | "81.92 kHz", "1%", single spaces |
| "clock wise / counter clock wise", "keytracking", "self oscillating", "in-harmonic", "two dimensional", "frequency dependent", "structure borne", "amplitude modulate", "frequency modulated", "heavier modulated" | hyphenated/grammatical forms ("clockwise", "counter-clockwise", "key tracking", "self-oscillating", "inharmonic", "two-dimensional", "frequency-dependent", "structure-borne", "amplitude-modulate", "frequency-modulated", "more heavily modulated") |

Further meaning-preserving rewordings/precisions in the web version:

- "Inverting one of the two channels however will transform…" → "Inverting **only** one of the two channels, however, will transform…" (2.5)
- Tense/agreement fixes throughout: "will modulate" → "modulates", "will introduce" → "introduces", "will step" → "steps", "will interfere" → "interferes", "will take care" → "takes care", "This switch controls" → "Controls" (all three link-switch entries), "work well" → "works well", "Both of these combined **will form**" → "**form**" (4.6), "In this case our modified rotation scattering junction behaves…" → "Our modified rotation scattering junction behaves…, as illustrated above" (4.6)
- "The Send/Return jacks **allow to patch-in** other modules, such as filters, phasers, flangers, or a second Analog Waveguide, into the feedback loop" → "…**allow you to patch in** other modules**—**such as filters, phasers, flangers, or a second Analog Waveguide**—**into the feedback loop" (2.4)
- "With these building blocks we can realize a series of physical models, **that we describe** in the patch examples (Section …)" → "…physical models, **described** in the patch examples (Chapter 4)" (1.4)
- "Note that the Analog Waveguide **can be also** understood" → "can also be understood" (1.4)
- Bandpass explanation in 4.1 restructured into one sentence with an em dash
- Web adds **approximation markers**: "(200 Hz)" → "(**≈**200 Hz)", "an LFO running at 7 Hz" → "at **≈**7 Hz" (4.4/4.5)
- Figure references rephrased positionally: "Figure … shows" → "The diagram above shows…" (1.4); "In Figure … we use the 'RANDOM' module" → "In the patch above…" (4.4); "See figure …" → "See figure below" (6.2–6.4); "References … are shown in Figure …" → "shown below" (6.5); "Repeat steps 4. and 5." → "Repeat the previous two steps" (6.2); "Follow the steps from subsection …" → "Follow the steps from Auto-calibration" (7.3); "Proceed further from step … in subsection … above with your preferred update software.." → "Proceed further from the dfu-util step above with your preferred update software" (7.3; double period also fixed)
- Menu entries made explicit on the web: "scroll to the menu entry" → "scroll to the **'Go back'** menu entry" (ch. 5), "navigate to the entry" → "the **'Settings'** entry" (ch. 5), "the menu entry" → "the **'Firmware update mode'** menu entry" (7.2/7.3), "navigate to the entry" → "the **'Re-initialize'** entry" (6.5); similarly button names in 7.2 are set in quotes ("USB", "reload", "Connect", "Open file", "Download", "Download as a guest") — the names themselves are present in both documents
- Several sentence pairs merged with em dashes (e.g. "Note that the Y input is normalled to the X input. — That means…" → one sentence, 2.4; "…online forum discourse.chair.audio" + "or contact us at support@chair.audio." → one sentence, 7.3; "…to our liking. Detuning it will make the sound richer." → one sentence, 4.5; "…was reversed, these two bugs almost canceled…" → "…was reversed—these two bugs…", version history 1.0.4)
- 3.1 *Display*: Lissajous explanations regrouped under new labels ("Circles and ellipses:", "Axis-symmetric patterns:", "Rotation-symmetric patterns:") with sentences tightened/merged; "with a 45 degree angle, that means" → "at a 45 degree angle,"; "So having a signal only in the X channel will result in a horizontal line whereas…" → "A signal only in the X channel results in a horizontal line, whereas…"; "that turns into a 45 degrees tilted ellipse when the phase shift is between 0 and 90 degrees" → "turning into a tilted ellipse between 0 and 90 degrees, and a perfect circle at 90 degrees"
- 4.6: "two waves of vibration **running** through the string" → "**run** through the string…—call them the left- and right-moving waves" (merged); "We can model this process **by utilizing**" → "**using**"; "The outputs of the two delay lines must be mixed together into one mono signal **in order for** the moving wave modeling to be effective." → "…**for** the moving-**wave** modeling to be effective—listened to independently, the two channels would model the right and left vibrations moving separately, which is physically impossible." (merged); "simulate a changing pluck position: this is directly analogous to the physical string—if you change the plucking position…" (restructured from two sentences); caption "Diagram of string." → "Diagram of an 'unfolded' string."
- 1.2: "projected back **on** the two **axis**" → "projected back **onto** the two **axes**"; "a bit **closer**" → "a bit **more closely**" (4.6); "reality" phrasing as noted above

---

## 3. Web-only content

- **PDF link (not in manual.tex):** "The original PDF version of this document can be found here: discourse.chair.audio/t/analog-waveguide-manual"
- **Hero subtitle:** "A versatile stereo resonator for physical modeling synthesis." — cannot be checked against manual.tex because the TeX title page lives in a separate `\include{Titlepage}` file that was not part of the attachment.
- **"Colophon" heading** above the three manufacturer lines ("Made on planet Earth…", "Printed circuit boards made in Europe, assembled in Germany.", "Conceived and designed in Weimar and Marseille.") — the lines themselves exist verbatim in both documents; only the heading label is web-only.
- **Bibliography and Notes as explicit page sections** — LaTeX generates these (footnotes at page bottom, bibliography via `\printbibliography`); the web page renders both as sections. The bibliography *entry texts* cannot be compared because the TeX relies on external `.bib` files (CHAIR.bib, own_pubs.bib) that were not part of the attachment; the in-text citations match (see §4).
- Explicit numbering ("Fig. 1.1 —", "Chapter 4", "5.1 Settings") replaces LaTeX-generated numbers — layout only.

---

## 4. Verified as matching (no content difference)

The comparison covered **both documents in full**, including all tail sections that earlier live-page fetches could not reach:

- All narrative text Preface → §4.6 (modulo the wording fixes above), including the full *Unfolded String Model* derivation (invert equations, θ = 90° parameterization, ± equations, source credit to Smith, *Physical Audio Signal Processing*)
- Technical specification tables: Dimensions (Width 24 HP, Depth 34 mm, PCB height 112 mm — **the web table is correct**; an earlier draft of this report claimed otherwise due to a fetch artifact), Current draw (+12 V 200 mA, −12 V 131 mA, +5 V not connected), Input/Output ranges incl. USB-C "DFU mode device ID 0483:df11"
- Signal-flow block list; pitch/lowpass/feedback/rotation/link-switch parameter descriptions (ranges, C0–C4, 1.4 kHz, 48 kHz, ±5/±8/±12 V, 6 dB/octave, ~50 Hz–20 kHz)
- All six patch examples (4.1–4.6) step-by-step content
- Menu System: navigation instructions, factory-settings button; Display Settings (brightness steps of 1%, screen saver 5 s–2 h/"off") and Limiter Settings (threshold, soft knee, release, reset) — all values match
- All calibration procedures: BBD Calibration (Vbias X/Y to 6 V), Adjust Clock Trimmer, Trim CV feed-through (220 Hz sine), Trim XY decay boost (−3 dB to −9 dB, ideal −6 dB), Trim XY channel balance (< 2 dB), Auto-calibration, Editing/Re-initializing calibration data
- Firmware Update: Web Updater (chairaudio.github.io/CHAIR-browser-dfu), STM32 Cube Programmer steps (incl. "Download as a guest", PID 0xDF11 / VID 0x0483), dfu-util incl. the "Error during download get_status" note; Troubleshooting (calibration-data loss incl. "full erase" warning, DFU update mode entry) incl. the forum and support@chair.audio contacts
- **Firmware Version History: all six entries (1.3.0, 1.2.3, 1.0.5, 1.0.4, 1.0.2, 1.0.0) are present and match verbatim** (typography-only deviations: "81.92 kHz" spacing, one em-dash merge in the 1.0.4 entry)
- Manufacturer colophon lines and address (Neupert & Wegener GbR, chair.audio)
- In-text citations (biblatex author–year "Wegener & Neupert, 2024", "Gerzon, 1971/1972", "Stautner & Puckette, 1982", "Puckette, 2011", "Smith, *Physical Audio Signal Processing*")

---

## 5. Summary

The two documents are near-identical in content: the web version is a faithful, lightly copy-edited conversion of manual.tex, with roughly 50 small wording/typo fixes, sentence merges, and more explicit menu-entry/button names. Genuine content differences are:

1. **Footnotes** — all 12 texts exist on the web, but 8 of 12 are reworded and several shortened, losing detail: the "audio goniometer" term and broadcasting rationale (fn 1–2), the definition of "normalled" (fn 3), the BBD working principle incl. the 1024-stages figure (fn 6), the endless-potentiometer vs. encoder comparison (fn 7), and the "no functional VCV Rack module" note (fn 8).
2. **Two sentences** missing from the Patch Examples introduction.
3. **One intro sentence** missing in the Input and Output section (2.4).
4. **"Flipping the switch to the right enables the link…"** dropped from the Feedback and Pitch link-switch descriptions (kept for Lowpass).
5. **One figure caption** ("The four quadrants of a Cartesian plane.") missing (1.2), and **one sentence** ("In Figure … you can see the necessary parameter settings.") missing (4.6).
6. Web adds a PDF-version link, the hero subtitle, a "Colophon" heading, and ≈-qualifiers on two numeric values; heading typo "Maintainance" is fixed on the web.

No factual contradictions (values, specs, procedures, firmware history) were found — every number, range and step checked out identical in both documents.
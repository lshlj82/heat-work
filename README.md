# Heat and Work, Interactively

An interactive, single-page web demo of thermodynamic processes involving heat and work: the first law of thermodynamics, compression work and PV diagrams, isothermal and adiabatic processes, heat capacities, latent heat, enthalpy, and the curious negative heat capacity of gravitating systems.

Created by **Claude Opus 5.5**, based on the lecture notes by **Sang Hoon Lee** (Statistical Physics 1, Chapter 1, Sections 1.4 to 1.6). It follows the demo for Sections 1.1 to 1.3 (temperature and energy).

## What's inside

**Heat, work, and the first law.** Conservation of energy, heat as spontaneous energy flow driven by a temperature difference (conduction, convection, radiation), the calorie, work as any other energy transfer, and ΔU = Q + W.

**Compression work.** W = −∫P dV for quasistatic processes, with an interactive process explorer for one mole of ideal gas. Choose isothermal, adiabatic, constant-pressure, or constant-volume steps (or a straight line back to the start), preview each on a PV diagram with the work shaded, and apply it to watch the piston, the gas temperature, and any heat flow. A table keeps the running W, Q, ΔU, and ΔT, and closing a cycle reports whether it acted as an engine (heat in, work out) or the reverse. Presets reproduce the triangle and rectangle cycles of Problems 1.33 and 1.34, with the same signs as in the lecture. The gas can be monatomic (f = 3) or diatomic (f = 5).

**Adiabats and the lapse rate.** The derivation of VT<sup>f/2</sup> = constant and PV<sup>γ</sup> = constant with γ = (f + 2)/f, and dT/dP = (2/(f + 2)) T/P (Problem 1.40). Combined with the barometric equation, this gives the dry adiabatic lapse rate, about −10 °C/km (9.4 °C/km for nitrogen). A chart compares a rising air parcel with the surrounding air, and shows when convection sets in.

**Heat capacities.** C = Q/ΔT and the specific heat c = C/m, C<sub>V</sub> and C<sub>P</sub>, and for an ideal gas C<sub>V</sub> = (f/2)Nk<sub>B</sub> and C<sub>P</sub> = C<sub>V</sub> + nR, with the rule of Dulong and Petit for solids. A comparison shows why constant-pressure heating needs more heat for the same temperature rise.

**Latent heat.** A heating curve for one gram of water from ice at −20 °C to steam at 120 °C, with the plateaus for melting (333 J ≈ 80 cal) and boiling (2257 J ≈ 540 cal) compared with the 418 J (100 cal) needed to warm the water from 0 °C to 100 °C, and the proportions of ice, water, and steam at each stage.

**Enthalpy.** H = U + PV, ΔH = Q + W<sub>other</sub> at constant pressure, and C<sub>P</sub> = (∂H/∂T)<sub>P</sub>. For the formation of water, H₂ + ½O₂ → H₂O with ΔH = −286 kJ, the demo splits the energy released into the part from the molecules (about 282 kJ) and the work done by the atmosphere as it collapses into the space left by the consumed gas (about 3.7 kJ).

**Negative heat capacity (Problem 1.55).** For a gravitationally bound system, U<sub>potential</sub> = −2U<sub>kinetic</sub> (the virial theorem), so U<sub>total</sub> = −(3/2)k<sub>B</sub>T per particle and C < 0. Two equal masses orbit their center of mass; adding energy widens the orbit and lowers the kinetic energy, so the system gets colder.

## Running it

There is nothing to build or install. The whole demo is one self-contained file, `index.html`, with all CSS and JavaScript inline.

Open it locally by double-clicking `index.html`, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

### Publishing with GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select your main branch and the `/ (root)` folder, then save.
4. After a minute or so, the demo will be live at `https://<your-username>.github.io/<repository-name>/`.

## Technical notes

- Plain HTML, CSS, and vanilla JavaScript drawn on `<canvas>`. No frameworks, no build step.
- The process explorer works in liters and kilopascals, so P × V is in joules, for one mole of ideal gas. Work, heat, and energy changes use the exact formulas for each process (for example W = nRT ln(V<sub>i</sub>/V<sub>f</sub>) for an isothermal step), and every closed cycle returns ΔU = 0.
- The animations pause when scrolled off screen and are reduced when the system asks for reduced motion.
- Long equations wrap on narrow screens.
- Equations are typeset with [MathJax 3](https://www.mathjax.org/) (SVG output, loaded from cdnjs), so they need no extra web fonts.
- The only other external resources are the Newsreader and Instrument Sans fonts from Google Fonts, with system font fallbacks if they fail to load.
- Opening the page requires an internet connection for MathJax; offline, the equations appear as raw TeX.
- Supports light and dark mode: it follows `prefers-color-scheme`, and a sun/moon button in the top-right corner switches by hand, and the choice is remembered across pages; and is responsive down to phone widths.
- Constants used: k<sub>B</sub> = 1.381 × 10<sup>−23</sup> J/K, R = 8.314 J/(mol K), 1 cal = 4.184 J.

## Caveats

- All processes in the explorer are quasistatic and the gas is ideal, with f independent of temperature.
- The lapse-rate chart is for dry air; moist air cools more slowly as it rises, since condensing water releases heat.
- The orbiting pair in the last section changes energy gradually so the orbit stays circular; it illustrates the virial-theorem result rather than simulating an actual star.

## Credits

- Demo: Claude Opus 5.5
- Physics content and examples: lecture notes by Sang Hoon Lee
- The lecture follows Daniel V. Schroeder, *An Introduction to Thermal Physics* (Sections 1.4 to 1.6 and Problems 1.33, 1.34, 1.40, and 1.55).

## License

No license has been chosen yet. Add a `LICENSE` file (for example, MIT or CC BY 4.0) before sharing or reusing this project publicly, and confirm that any use of the lecture material is permitted by its author.

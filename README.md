# MLT Colour Perception Simulator — Professional Edition

An educational **Red-Green-Yellow (RGY) signal-light colour perception trainer** inspired by the Martin Lantern Test, built as a self-contained, zero-dependency HTML/CSS/JS application.

Live Link- https://mevaibhavpandey.github.io/MLT-Test/

> ⚠️ **Disclaimer:** This application is for **educational and training purposes only**. It is NOT an official Martin Lantern Test and does NOT constitute a medical assessment or diagnosis. For professional vision testing, consult a qualified optometrist or aviation medical examiner.

---

## Features

### 🎯 Test Engine
- **Practice Mode** — lights remain visible until you answer; user controls pace
- **Exam Mode** — lights visible for 800–2000 ms (random), then hidden; cannot be replayed
- **10 / 20 / 30 set** configurations
- Keyboard shortcuts: `1/2/3` → Top colour · `4/5/6` → Bottom colour · `Space` → Next set

### 💡 Realistic Signal Lamps
- 6 px illuminated aperture + multi-layer bloom + outer halo
- Layered radial gradients simulating incandescent optical filters
- Subtle filament flicker animation via `requestAnimationFrame`
- Per-render procedural hue/luminance/bloom variation — no two tests look identical

### 🎨 Colour Engine (150 curated shades)
- **50 Red** · **50 Green** · **50 Yellow** shades — all realistic signal-light hex values
- Full augmentation: HSL · HSV · CIE L\*a\*b\* · relative luminance · bloom radius · ~wavelength
- Difficulty-weighted shade selection (1–5 scale)
- Delta-E CIE76 perceptual distance computation

### 📊 Analytics Dashboard (Results Screen)
- Overall Accuracy · Combined Score · CP-1 to CP-5 estimate
- Median / Mean / Min / Max reaction time
- Consistency Score · Confusion Index · Difficulty-Weighted Score
- 4 hand-drawn Canvas charts: accuracy timeline · reaction histogram · confusion matrix heatmap · difficulty scatter

### 📋 Question Review
- Every question expandable — shows both lamp hex values, correct vs user answer, reaction time, difficulty
- **"View Colour Analysis"** modal — full hex/RGB/HSV/HSL/L\*a\*b\*/luminance/wavelength/bloom data + Delta-E between the pair

### 🗂️ Session History
- All sessions persisted to `localStorage`
- Sortable by date / accuracy / score · Filterable by mode / CP rating
- Delete individual sessions or clear all · Export to JSON

### ⚙️ Calibration Wizard (7 steps)
1. Screen Brightness check
2. Contrast check
3. Gamma check
4. Ambient Light advisory
5. Viewing Distance guide
6. Display Settings checklist
7. Dark Adaptation 60 s countdown

### 🎨 Colour Library
- Browse all 150 shades in a grid
- Click any shade → full detail modal with colour data + 4 most similar shades by ΔE

### 🌈 Wavelength Simulator
- Interactive 380–780 nm spectrum slider
- Live lamp preview · wavelength · RGB · HSL · LAB · luminance · frequency (THz)
- Spectral sensitivity reference chart (L/M/S cone curves)

### ↔️ Colour Distance Tool
- Compare any two shades from the library
- Delta-E · ΔHue · ΔLightness · ΔSaturation · ΔLuminance · Confusion Risk rating

---

## Usage

1. Open `index.html` in any modern browser (Chrome / Edge / Firefox recommended)
2. Run through the **Calibration Wizard** for best results
3. Select **Practice** or **Exam** mode and number of sets
4. Click **LAUNCH TEST**
5. View detailed results and save session history automatically

No installation, no build tools, no internet required (after initial Google Fonts load).

---

## Technical Details

| Item | Detail |
|---|---|
| File | Single `index.html` (~3850 lines) |
| Dependencies | None (Google Fonts optional) |
| Storage | Browser `localStorage` |
| Charts | Hand-drawn Canvas / SVG (no external libraries) |
| Compatibility | Chrome 90+, Firefox 88+, Edge 90+ |

### Module Architecture

```
MLT.ColorEngine        — 150-shade colour database + CIE LAB/Delta-E
MLT.LightRenderer      — Incandescent lamp rendering + flicker animation
MLT.TestEngine         — State machine: idle → flash → answer → done
MLT.StatisticsEngine   — Accuracy, RT, confusion index, CP estimate
MLT.HistoryManager     — localStorage CRUD + JSON export
MLT.ChartEngine        — Canvas chart rendering (5 chart types)
MLT.UIEngine           — 9-screen router + all component renderers
```

---

## Screens

| Screen | Description |
|---|---|
| Boot | Animated startup sequence |
| Dashboard | Home, mode/sets selector, session stat cards |
| Test | Distraction-free lamp view (fullscreen overlay) |
| Results | Full analytics dashboard |
| History | Sortable/filterable session table |
| Colour Library | 150-shade browser |
| Wavelength Simulator | 380–780 nm interactive spectrum |
| Colour Distance | Two-shade comparison tool |
| Calibration Wizard | 7-step display calibration |

---

## License

Educational use only. Not for medical or certification purposes.

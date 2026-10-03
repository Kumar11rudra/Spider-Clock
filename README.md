# 🕷️ Spider Clock

An atmospheric, animated analog real-time clock featuring an intricate spider-web dial and a hanging white spider suspended by its silk thread, perfectly synchronized with your local system time.

Built purely with vanilla **HTML5**, **CSS3**, and **JavaScript** — 100% offline, lightweight, and zero external dependencies.

🌐 **Live Demo**: [https://kumar11rudra.github.io/Spider-Clock/](https://kumar11rudra.github.io/Spider-Clock/)

---

## 🌟 Features

- **Atmospheric Dark Aesthetic**: Rich dark header with glowing amber accents and a warm brown/orange radial gradient clock face.
- **Accurate Real-Time Analog Clock**: Computes hour, minute, and second positions continuously from the user's local system time.
- **Smooth Sweep & Classic Tick Modes**: Easily toggle between high-precision smooth 60fps/120fps sweep motion and traditional 1-second mechanical step motion.
- **Geometric Spider Web Dial**: Procedurally generated SVG web featuring 12 radial spokes aligned with clock hours, catenary sagging silk curves, and subtle dewdrop nodes.
- **Interactive White Spider**:
  - Detailed SVG arachnid anatomy with cephalothorax, abdomen chevron markings, 8 jointed legs, and ruby obsidian eyes.
  - Suspended gracefully near the center by a shimmering silk thread.
  - Organic idle swaying/bobbing physics animation.
  - Interactive reaction: click or hover to make the spider scurry along its silk thread.
- **Digital Time & Date Readout**: Displays formatted 12-hour digital time (`HH:MM:SS AM/PM`) and the full local calendar date.
- **Fully Responsive**: Adapts seamlessly to all screen sizes, from mobile phones to high-resolution desktop monitors.
- **Zero Dependencies & 100% Offline**: No external CDN scripts, frameworks, fonts, or images required. Open it anywhere, anytime.

---

## ⚙️ How It Works

1. **Time Calculation Engine**:
   - Reads the local system clock via JavaScript's `Date` object on each frame using `requestAnimationFrame`.
   - Calculates the exact angular rotation for each hand:
     - **Second hand**: `(seconds + milliseconds / 1000) * 6°`
     - **Minute hand**: `(minutes + (seconds + milliseconds / 1000) / 60) * 6°`
     - **Hour hand**: `((hours % 12) + (minutes + seconds / 60) / 60) * 30°`
   - Applies CSS `transform: rotate(...)` around the central pivot point (`50% 100%`).
2. **Procedural Web Generation**:
   - Generates 12 radial silk spokes connected by concentric catenary arcs using quadratic Bézier curves (`Q cx cy x2 y2`).
3. **Organic Animation Loop**:
   - Utilizes CSS keyframe animations for gentle pendulum sway on the spider body, paired with hardware-accelerated transforms for smooth rendering without layout thrashing.

---

## 🛠️ Technologies Used

- **HTML5**: Semantic document structure and accessible metadata.
- **CSS3**: Modern layouts with Flexbox, CSS Custom Properties (variables), radial gradients, glassmorphism, and keyframe animations.
- **SVG (Scalable Vector Graphics)**: Razor-sharp procedural spider web and white spider illustration that scale losslessly to any resolution.
- **JavaScript (ES6+)**: Real-time clock calculations, smooth `requestAnimationFrame` loop, and event handling with zero external libraries.

---

## 🚀 How to Run Locally

You can run this project locally using either of the following methods:

### Option 1: Direct File Open
Simply double-click or open `index.html` directly in any modern web browser:
```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

### Option 2: Local HTTP Server
Run a lightweight local HTTP server using Python:

```bash
python3 -m http.server 5500
```

Then open your browser and navigate to:
```
http://localhost:5500
```

---

## 📶 Offline Usage

Spider Clock is engineered to function completely offline without internet connectivity:
- No CDN links or external fonts (uses native system font stacks).
- No external image assets (all graphics are inline vector SVG and CSS).
- Works straight from disk (`file://` protocol) or over a local network.

---

## 🌐 Browser Compatibility

Tested and compatible with all modern browsers:
- Google Chrome (Desktop & Mobile)
- Mozilla Firefox (Desktop & Mobile)
- Apple Safari (macOS & iOS)
- Microsoft Edge
- Opera / Brave

---

## 📁 Project Structure

```
Spider-Clock/
├── index.html       # Complete application (HTML, CSS styling, SVG graphics, and JavaScript)
├── README.md        # Comprehensive documentation and run instructions
├── LICENSE          # MIT open-source license
└── .gitignore       # Git ignore rules for system artifacts
```

---

## 🎨 Customization Instructions

Spider Clock is designed for easy customization:

- **Dial Colors**: Modify the `--bg-dark`, `--accent-orange`, and `--accent-gold` variables at the top of the `<style>` block in `index.html`.
- **Clock Size**: Adjust `min(84vw, 420px)` in the `.clock-bezel` CSS selector.
- **Web Rings**: Adjust the `ringRadii` array in `buildSpiderWeb()` (`[28, 55, 84, 115, 146, 178]`) inside `<script>` to change the density or spread of the spider web.
- **Spider Size & Appearance**: Customize the SVG paths and dimensions in `.spider-body-wrapper` and the `#spiderBodyGrad` gradient in `index.html`.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

Created with 🕸️ by Anil ❤️

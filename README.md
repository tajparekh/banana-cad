# 🍌 Banana CAD

> **A free, zero-install 3D modeling and physics studio that runs directly in your web browser.**

Banana CAD is a complete 3D Computer-Aided Design (CAD) application self-contained in a single file ([`index.html`](file:///Users/tajparekh/documents/hackathon/banana-cad/index.html)). You do not need to install Node.js, run servers, or download dependencies.

---

## 🚀 How to Run It (Takes 3 Seconds)

1. Find the file named **[`index.html`](file:///Users/tajparekh/documents/hackathon/banana-cad/index.html)** in this folder.
2. **Double-click it** to open it in any web browser (Chrome, Safari, Edge, Firefox, Brave).
3. That’s it! The app runs completely offline on your computer.

*Prefer the terminal?*
```bash
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

---

## 🧭 Quick-Start Guide (Your First 60 Seconds)

### Step 1: Start or Open a Project
- When the app opens, click **"Continue as Guest"** (or create a local account if you prefer).
- You will see your project library. Click **"Mechanical Gearbox Demo"** to explore an example, or click **"＋ New Project"** to start with a clean slate.

### Step 2: Look Around the 3D Space
| Action | How to do it |
| :--- | :--- |
| **Rotate Camera (Orbit)** | Click and drag with the **Left Mouse Button** on empty space. |
| **Move Camera (Pan)** | Hold **Right Mouse Button** (or hold **Shift + Left Click**) and drag. |
| **Zoom In / Out** | Scroll your **Mouse Wheel** up or down. |
| **Preset Angles** | Click the **top**, **front**, **iso**, or **reset** buttons on the top right. |

### Step 3: Add & Select Shapes
- **Add a quick primitive**: Click any shape in the left sidebar (**Cube**, **Sphere**, **Cylinder**, **Cone**, **Gear**, **Humanoid**).
- **Browse the full catalog**: Click **"📦 Catalog"** in the top bar to choose from over 20 shapes (Stars, Torus rings, Pyramids, Capsules).
- **Select a shape**: Simply click on any part on screen. A yellow outline and transform ring will appear around it.

---

## 🎯 How to Use the Key Features

### 📐 1. Precision Measurements & Live Calipers
Want to know exact sizes or build to millimeter precision?
1. Click on any shape to select it.
2. Click **"📐 Dimensions"** in the top toolbar.
3. Three measurement brackets appear in 3D:
   - **X (Red)** = Width
   - **Y (Green)** = Height
   - **Z (Blue)** = Depth
4. In the dimensions box, you can **type any exact number** (e.g. change X to `2.50`) and press Enter. Only that dimension will stretch!

### 🧲 2. Magnetic Grid Snapping
Need parts to line up without eyeballing?
1. Click **"🧲 Snap"** in the top toolbar to open the snap controls on the bottom-right.
2. Check or uncheck snapping for:
   - **Move**: Snaps position in increments (default: `0.5m`).
   - **Rotate**: Snaps angle in clean steps (default: `15°`).
   - **Scale**: Snaps sizing in steps (default: `0.1x`).
3. Now whenever you move, rotate, or resize parts, they will lock cleanly to the grid.

### ⬤ 3. Subtractive Modeling (Cutting Holes)
Need to cut a hole through an object?
1. Select the shape you want to turn into a hole (e.g., a cylinder).
2. Click **"⬤ Negative"** in the top toolbar.
3. The shape turns into a purple translucent stencil.
4. When you fuse it with a solid object, it cuts out that space!

### 🔗 4. Fusing Shapes & Saving Custom Assemblies
Combine multiple shapes into one solid object:
1. Select multiple shapes (hold **Ctrl** or **Cmd** and click each shape, or select one).
2. Right-click and choose **"Fuse into One"** (or use the group dialog).
3. The parts fuse into a single compound model.
4. **Custom Builds Library**: Click **"💾 Save Build"** to save your creation. You can now open **"📦 Catalog"** ➔ **"🏗️ Custom Builds"** anytime to spawn copies of your fused assembly into any scene!

### ⚙️ 5. Meshing Gear Physics Simulation
Create realistic mechanical mechanisms:
1. Add two or more **Gears** from the catalog and place them next to each other so their teeth touch.
2. Switch to **"⚡ Test Mode"** at the top.
3. The gears will automatically detect their neighbors and counter-rotate with accurate gear ratios!
4. Use the **⚙️ Gear slider** in the top bar to speed them up, slow them down, or click **"⏸ Pause"**.

### ✏️ 6. 2D Smart Sketching to 3D Extrusion
Draw your own shapes from scratch:
1. Click **"✏️ Smart Sketch"** in the top toolbar.
2. Draw any closed outline directly on the ground with your mouse.
3. Set your desired thickness with the **Height** slider.
4. Click **"Extrude 3D"** to instantly convert your 2D sketch into a solid 3D prism!

### ⚡ 7. Physics Drop & Bounce Test
See how your design reacts to gravity:
1. Click **"⚡ Test"** at the top of the screen.
2. Gravity turns on! Shapes fall to the ground and interact with each other.
3. Adjust the **Bounce slider** to control how springy materials are.
4. Click **"🔨 Build"** when you want to return to editing.

### 🖨️ 8. Export for 3D Printing (STL)
Ready to 3D print your creation?
1. Click **"⬇ Export STL"** on the top right.
2. Banana CAD will immediately download a standard `.stl` file to your computer.
3. Open the file in your 3D printer slicer (Bambu Studio, Cura, PrusaSlicer, OrcaSlicer) and print!

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| **Delete** or **Backspace** | Delete the selected shape |
| **Page Up** / **Page Down** | Elevate shape up / down (Y axis) |
| **Arrow Keys** | Rotate selected shape |
| **Ctrl + Click** / **Cmd + Click** | Select multiple shapes |
| **Right-Click** | Open context menu (Group, Fuse, Color, Gizmo) |

---

## ❓ Frequently Asked Questions

**Does my work get saved?**  
Yes. All your projects, custom builds, and settings are automatically saved in your browser's local storage. They will be there when you come back.

**Can I use this without the internet?**  
Yes. Banana CAD is 100% offline. You can run it on an airplane, in the woods, or with Wi-Fi turned off.

**Can I move `index.html` to my Desktop?**  
Yes. `index.html` contains the entire studio in one file. You can move it anywhere, rename it, or email it to a friend.

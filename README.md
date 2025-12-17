# 🦆 Duck Blaster - AR Gesture Shooting Game

<div align="center">

![Duck Blaster](https://img.shields.io/badge/Game-Duck%20Blaster-FFD93D?style=for-the-badge&logo=gamepad&logoColor=white)
![AR](https://img.shields.io/badge/AR-Gesture%20Control-87CEEB?style=for-the-badge&logo=hand&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-3D%20Rendering-000000?style=for-the-badge&logo=three.js&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Hand%20Tracking-4285F4?style=for-the-badge&logo=google&logoColor=white)

**An immersive AR shooting game where you blast flying ducks using hand gestures!**

[🎮 Play Now](#-how-to-play) • [📖 Features](#-features) • [🚀 Quick Start](#-quick-start) • [🎯 Controls](#-controls)

</div>

---

## 🎮 Overview

Duck Blaster is a single-file HTML5 AR shooting game that combines hand gesture recognition with 3D graphics. Make a pistol gesture with your hand, aim at flying duck targets, and flick upward to shoot! Features magnetic aim assist, laser targeting, particle explosions, and satisfying sound effects.

### ✨ Key Highlights

- 🎯 **Hand Gesture Control** - Natural pistol gesture recognition
- 🦆 **3D Duck Targets** - Cute animated ducks flying toward you
- 🎨 **Beautiful Graphics** - Three.js powered 3D rendering at 60 FPS
- 🔊 **Sound Effects** - Procedurally generated audio feedback
- 🎪 **Visual Effects** - Particle explosions, laser aiming, floating text
- 🖱️ **Mouse/Keyboard Fallback** - Play even without camera access

---

## 🎯 Features

### Hand Gesture Recognition
- **Pistol Gesture Detection** - Index finger extended, other fingers curled
- **Flick-Up Shooting** - Rapid upward motion triggers shots (like gun recoil!)
- **Smooth Tracking** - Landmark smoothing for stable aim
- **Confidence Indicators** - Visual feedback on gesture recognition quality

### Gameplay
- **Flying Targets** - 4 ducks always on screen, respawn instantly when hit
- **Magnetic Aim Assist** - Crosshair automatically attracts to nearby targets
- **Laser Aiming Line** - Red beam from wrist to fingertip
- **Hit Detection** - Accurate collision detection with visual feedback
- **Score & Accuracy** - Track your performance in real-time

### Visual & Audio
- **3D Particle Explosions** - Colorful feather particles on hit
- **Muzzle Flash** - Visual feedback on each shot
- **Floating Text VFX** - "🦆 QUACK!" on hits, "MISS" on misses
- **Procedural Sound Effects** - Gunshot, hit, and miss sounds via Web Audio API
- **Animated Background** - Starfield with grid overlay

### Technical Excellence
- **Crash-Safe Loading** - Full-screen loading overlay with progress
- **Version-Locked Dependencies** - MediaPipe pinned to prevent WASM crashes
- **Performance Optimized** - AI detection at ~25 FPS, rendering at 60 FPS
- **Error Handling** - Try-catch protection throughout detection loop
- **Responsive Design** - Works on various screen sizes

---

## 🚀 Quick Start

### Option 1: Direct Play (Recommended)
1. Open `ar-gesture-shooter.html` in a modern browser (Chrome, Edge, Firefox)
2. Allow camera access when prompted
3. Wait for the AI model to load (~10-15 seconds)
4. Make a pistol gesture and flick up to shoot!

### Option 2: Local Server
```bash
# Python 3
python3 -m http.server 8080

# Node.js (http-server)
npx http-server -p 8080

# Then open: http://localhost:8080/ar-gesture-shooter.html
```

### Option 3: GitHub Pages
1. Fork this repository
2. Enable GitHub Pages in repository settings
3. Set source to `main` branch
4. Access via: `https://YOUR_USERNAME.github.io/AR-duckGame/ar-gesture-shooter.html`

---

## 🎮 Controls

### Hand Gesture (Primary)
1. **Make Pistol Shape** - Extend index finger, curl other fingers
2. **Aim** - Point your index finger at targets
3. **Shoot** - Quickly flick your hand upward (recoil motion)

### Mouse (Fallback)
- **Aim** - Move mouse cursor
- **Shoot** - Left click

### Keyboard (Fallback)
- **Aim** - Move mouse cursor
- **Shoot** - Press `Spacebar`

---

## 📋 Requirements

- **Modern Browser** with WebGL support (Chrome 90+, Firefox 88+, Edge 90+, Safari 14+)
- **Webcam** (for hand gesture control)
- **HTTPS** (required for camera access on most browsers)
  - Local files work with `file://` protocol
  - For remote hosting, HTTPS is mandatory

### Browser Compatibility
| Browser | Version | Status |
|---------|---------|--------|
| Chrome  | 90+     | ✅ Full Support |
| Edge    | 90+     | ✅ Full Support |
| Firefox | 88+     | ✅ Full Support |
| Safari  | 14+     | ✅ Full Support |

---

## 🛠️ Technical Stack

- **Three.js r128** - 3D graphics rendering
- **MediaPipe Hands v0.4.1646424915** - Hand gesture recognition (pinned version)
- **Web Audio API** - Procedural sound generation
- **HTML5 Canvas** - 2D overlay graphics (laser, crosshair)
- **Vanilla JavaScript** - No frameworks, pure performance

### Architecture
- **Single File** - Everything in one HTML file for easy deployment
- **Modular Code** - Well-organized sections for maintainability
- **60 FPS Rendering** - Smooth gameplay experience
- **Throttled Detection** - AI runs at ~25 FPS to balance performance

---

## 🎨 Game Mechanics

### Gesture Recognition
- **Pistol Detection**: Analyzes finger angles and positions
- **Confidence Scoring**: Multi-factor scoring system (0-1 scale)
- **Temporal Stability**: Requires consistent gesture over multiple frames
- **Smoothing**: Exponential smoothing reduces jitter

### Target System
- **Spawn Points**: Random edges of screen
- **Movement**: Fly toward center with slight variation
- **Rotation**: Continuous rotation with wobble animation
- **Respawn**: Instant replacement when destroyed

### Aim Assist
- **Magnetic Pull**: 35% attraction strength toward nearest target
- **Detection Radius**: 150px screen space
- **Visual Feedback**: Crosshair turns green when locked on

### Scoring
- **Hit**: +100 points
- **Accuracy**: Calculated as hits/shots percentage
- **Real-time Updates**: HUD updates instantly

---

## 🐛 Troubleshooting

### Camera Not Working
- **Check Permissions**: Ensure browser has camera access
- **HTTPS Required**: Remote sites need HTTPS for camera
- **Try Mouse Mode**: Game works without camera (click to shoot)

### Gesture Not Detected
- **Lighting**: Ensure good lighting on your hand
- **Distance**: Keep hand 1-3 feet from camera
- **Background**: Plain background works best
- **Check Indicators**: Bottom indicator shows detection status

### Performance Issues
- **Close Other Tabs**: Free up browser resources
- **Lower Resolution**: Some browsers allow camera resolution adjustment
- **Update Browser**: Use latest browser version

### Model Loading Fails
- **Check Internet**: Model downloads from unpkg CDN
- **Firewall**: Ensure unpkg.com is accessible
- **Retry**: Refresh page and try again

---

## 📝 Development

### File Structure
```
AR-duckGame/
├── ar-gesture-shooter.html  # Main game file (all-in-one)
└── README.md                 # This file
```

### Key Functions
- `processHandLandmarks()` - Gesture recognition logic
- `shoot()` - Firing mechanism
- `magneticAimAssist()` - Aim assist calculation
- `createDuckTexture()` - Procedural duck texture generation
- `playSound()` - Web Audio API sound generation

### Customization
- **Target Count**: Change `state.targets.length < 4` in `spawnTargets()`
- **Aim Assist Strength**: Modify `attraction` value in `magneticAimAssist()`
- **Flick Sensitivity**: Adjust `flickThreshold` in state object
- **Colors**: Edit color values in CSS and Three.js materials

---

## 🤝 Contributing

Contributions are welcome! Feel free to:
- 🐛 Report bugs
- 💡 Suggest features
- 🎨 Improve graphics
- 📖 Enhance documentation
- ⚡ Optimize performance

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

- **MediaPipe** - Google's hand tracking solution
- **Three.js** - 3D graphics library
- **Web Audio API** - Browser audio capabilities

---

## 📧 Contact

Created with ❤️ by [@andreaturchet](https://github.com/andreaturchet)

---

<div align="center">

**🎮 Happy Duck Blasting! 🦆**

[⬆ Back to Top](#-duck-blaster---ar-gesture-shooting-game)

</div>

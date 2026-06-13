# Memory Universe V2

A premium cinematic web application that transforms personal photographs into an emotionally resonant 3D film experience. Built to celebrate significant life moments with reverence and beauty.

## Features

### Viewer Mode
- **3D Cinematic Experience**: Full-screen WebGL rendering with Three.js
- **8-Phase Animation Sequence**: Each photo follows a choreographed journey
  1. Emergence – photo spawns from depth
  2. Approach – travels toward viewer
  3. Rotation Reveal – cinematic 3D turn
  4. Center Moment – optimal viewing position
  5. Caption Entrance – text reveals
  6. Contemplation – gentle upward drift
  7. Exit Dissolve – organic pixel scatter
  8. Seamless Loop – next photo enters early
  
- **Atmospheric Visuals**:
  - Animated nebula skybox with dual-color clouds
  - 2000+ ambient particles with alpha breathing
  - Glass-framed photos with neon glow edges
  - Cinematic post-processing (bloom, film grain, vignette)
  - Dynamic lighting with breathing intensity

- **Celebration Finale**: After the last photo
  - Gold particle storm
  - Three-line configurable text reveal
  - Seamless return to Photo 1

### Studio Mode
- **Drag-and-Drop Upload**: Add photos via drop zone or file browser
- **Photo Editing**:
  - Custom titles and captions
  - Per-photo duration (8–30 seconds)
  - Real-time timeline preview
- **Global Settings**:
  - Bloom intensity adjustment
  - Celebration message customization
  - Particle density and effect toggles

### Persistence
- All photos and settings stored in IndexedDB
- Survives page refresh and browser restart
- No server required

## Keyboard Shortcuts

- `V` – Enter Viewer (watch the experience)
- `S` or `Esc` – Enter Studio (edit)

## Technology Stack

- **Three.js** – 3D graphics and WebGL rendering
- **GSAP** – Timeline and animation engine
- **IndexedDB** – Local data persistence
- **Web Audio API** – Audio playback (foundation for future)
- **CSS3** – Glassmorphism UI and responsive design

All dependencies loaded from CDN—no build tools required.

## Browser Compatibility

- Chrome 100+
- Firefox 100+
- Edge 100+
- Safari 16+ (with WebGL2 support)

## Deployment

### Vercel (Recommended)

```bash
git push origin main
```

Visit `https://your-project.vercel.app` (auto-deployed on push)

### Local Development

Since IndexedDB requires HTTPS or localhost, use a local server:

```bash
# Using Python
python -m http.server 8000

# Or Node.js
npx http-server
```

Then open `http://localhost:8000`

**Note:** Opening `index.html` directly (`file://`) will not work due to browser security policies on IndexedDB.

## File Structure

```
Memory-Universe-V2/
├── index.html          # Single-file application
├── vercel.json         # Vercel deployment config
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## Architecture

The application is built as a modular system within the single HTML file:

- **StorageEngine** – IndexedDB wrapper for persistence
- **SceneEngine** – Three.js scene, camera, renderer, post-processing
- **ParticleSystem** – Ambient particle rendering and animation
- **PhotoEngine** – Photo mesh factory with glass frame effects
- **NarrativeEngine** – 8-phase animation sequencer
- **CelebrationEngine** – Finale sequence controller
- **ControlStudio** – Admin UI for photo management
- **AppController** – Mode switching and initialization

All modules communicate via a lightweight EventBus to minimize coupling.

## Performance Targets

- Desktop: 60fps (1920x1080)
- Tablet: 30fps+ (iPad Air or better)
- Mobile: Reduced effects, 30fps+

Optimizations include texture streaming, geometry pooling, and delta-time frame independence.

## Future Enhancements

- Audio integration with music reactivity
- Multi-family album support
- Share/export as video
- Mobile touch gestures
- Custom theme editor

## License

Personal use. Contact for commercial licensing.

## Support

For issues or feedback, contact studio@pixelbloomcreations.com

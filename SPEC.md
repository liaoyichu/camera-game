# Finger Knock - Camera Game Specification

## 1. Project Overview

- **Name**: Finger Knock
- **Type**: Interactive webcam-controlled physics game
- **Core Functionality**: Use finger/hand tracked via webcam to knock objects off the screen
- **Target Users**: Casual players looking for a fun physical interaction game

## 2. UI/UX Specification

### Layout Structure
- Full viewport canvas game
- Webcam video preview in corner (small, semi-transparent)
- Floating score display (top-right)
- Start/restart button overlay

### Visual Design
- **Background**: Dark gradient (#0a0a1a to #1a1a2e) with subtle grid pattern
- **Primary Color**: #00ffaa (cyan-green neon)
- **Secondary Color**: #ff6b35 (warm orange)
- **Accent Color**: #a855f7 (purple glow)
- **Objects**: Colorful circles with glow effects and trails
- **Typography**: 
  - Title: "Orbitron" bold, 48px
  - Score: "Orbitron", 24px
- **Effects**: 
  - Glowing objects with shadowBlur
  - Particle trails on hit
  - Screen shake on impact

### Components
- **Target Objects**: Floating colored circles that drift slowly
- **Finger Pointer**: Glowing cyan cursor follow the tracked finger
- **Score Display**: Large neon text
- **Combo Counter**: Shows hit streak

## 3. Functionality Specification

### Core Features
1. **Webcam Access**: Request camera permission, display mirrored preview
2. **Hand Tracking**: Simple skin-color based detection or use MediaPipe Hands lite
3. **Physics Objects**: 
   - 5-8 floating spheres with random colors
   - Each has position, velocity, radius
   - Drift slowly, bounce off edges
   - Knock away when touched by finger
4. **Collision Detection**: Circle-circle collision between finger and objects
5. **Knockback Physics**: 
   - On collision, apply force based on finger velocity
   - Objects fly off with momentum
6. **Scoring**:
   - +10 points per object knocked off screen
   - Combo multiplier for consecutive knocks
7. **Game Loop**:
   - Objects respawn after being knocked off
   - Score accumulates

### User Interactions
- **Start**: Click "Start Game" button
- **Play**: Move finger in front of camera to knock objects
- **Restart**: Button appears when all objects cleared or on click

### Edge Cases
- Camera permission denied: Show error message
- No hand detected: Show finger tracking guide
- Objects cluster: Add slight repulsion

## 4. Acceptance Criteria

- [ ] Webcam activates and shows mirrored preview
- [ ] Finger tracking works reasonably well
- [ ] Objects float and drift on screen
- [ ] Collision with finger knocks objects away
- [ ] Objects leaving screen adds to score
- [ ] Score displays correctly
- [ ] Game is playable and fun
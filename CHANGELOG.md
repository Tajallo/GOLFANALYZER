# Changelog - Golf Swing Analyzer

All notable changes to this project will be documented in this file.

## [2.2.0] - 2026-04-22
### Added
- **Pro Analysis Dashboard (v4)**: High-performance fullscreen modal for synchronized video analysis.
- **Advanced Playback Engine**: Added Master Play/Pause, Scrubber (frame-by-frame seeking), and variable speed control (0.25x, 0.5x, 1x).
- **Deep Biomechanical Audit**: 
  - **Comparative Metric Table**: Real-time comparison of Spine Tilt, Shoulder Turn, and Knee Flexion between User and Pro.
  - **Stage-by-Stage Diagnostics**: Dedicated analysis for Address (Posture) and Transition phases.
- **HUD Toggles (Golf Boy Style)**: Dynamic layer selector for Skeleton (Guía), Joints (Cruces), Angles, and Movement Trail.
- **Hand Path Trail**: New visualization that draws the arc of the swing in real-time, allowing for path-plane analysis.
- **Optimized Viewport**: XL display mode with automated aspect-ratio scaling to prevent cropping on high-resolution portrait videos.

### Fixed
- **UI Stability**: Resolved syntax errors that caused the club list and general initialization to fail.
- **Landmark Visibility**: Upgraded User skeleton to Bright Cyan (#00D1FF) with 4px lines for superior visibility on outdoor backgrounds.
- **Data Capture**: Implemented pose history buffer to ensure audit metrics are captured even with delayed AI results.

## [2.1.0] - 2026-04-21
### Added
- **v2.1 UI Update**: Added version badge in the header to confirm successful reload and bypass cache issues.
- **Dynamic Tracking**: Fixed MediaPipe frame-by-frame processing over the video element.
- **Visual Feedback**: Added blue (User) and neon green (Pro Ghost) skeleton overlays that update in real-time during analysis.

### Changed
- **MediaPipe Optimization**: Optimized the `startAnalysis` loop to process frames more reliably across different browsers.
- **Drawing Utils**: Integrated with MediaPipe's drawing utilities for more professional-looking skeletal visualizations.

## [2.0.0] - 2026-04-20
### Added
- **Premium Design System**: Complete visual overhaul using **Glassmorphism**, vibrant emerald and electric blue palette, and **Google Fonts** (Outfit & Inter).
- **IA Rory Master**: Advanced biomechanical analysis module including:
  - **Kinematic Sequence Graph**: Dynamic SVG representation of deceleration curves (Pelvis, Torso, Hands).
  - **Biomechanical Diagnostics**: Detailed clinical feedback on Lag, X-Factor, and club path.
- **Golf Boy Integration**: Added logic to simulate/parse rich metadata from Golf Boy video files (Ball Speed, Smash Factor, Club Path, Total Distance).
- **Session History**: Persistent local storage registry to track progress over time without a database.
- **Re-upload Logic**: Added "New Video" functionality to allow multiple consecutive analyses without refreshing.
- **Pro Frame Overlay**: Dedicated modal for static frame comparison vs pro ideal for impact zone analysis.

## [1.0.0] - 2026-04-19
### Added
- Initial functional version of the Golf Swing Analyzer.
- Basic tab navigation (Upload, Analysis, Compare, History).
- Simple MediaPipe Pose integration.
- Responsive layout for mobile and desktop.
- Automatic Dark Mode.

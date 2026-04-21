# Changelog - Golf Swing Analyzer

All notable changes to this project will be documented in this file.

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

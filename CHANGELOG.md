# Changelog - Golf Swing Analyzer

All notable changes to this project will be documented in this file.

## [4.6.0] - 2026-10-23
### Added
- **3D World Landmark Tracking (`poseWorldLandmarks`)**: Full 3D rotational vector extraction (`turn3D`) using MediaPipe metric world coordinates $(x, y, z)$ for shoulder line (11-12) and hip line (23-24). Completely fixes the 2D foreshortening artifact where shoulder turn and X-Factor collapsed to 0° at top position.
- **Diestro (Right-Handed) Default & Dynamic Update**: Changed default handedness to Right-Handed ("Diestro"), with reactive dynamic recalculation (`onHandChange`) for lead/trail side overlays, ghost reference, and biomechanical metrics without requiring re-analysis.
- **Interactive Camera Framing Guide Modal**: Built-in visual guide with exact tripod heights (waist/hands), distance (3.5m), and alignment instructions for Down-the-Line (DTL) and Face-On to avoid perspective distortions.
- **Monetization & Credit Store System**:
  - Top header balance display with remaining AI credits.
  - Credit Pack Store modal (1 Swing = 1€, 5 Swings = 3.99€, 10 Swings = 6.99€) ready for Apple StoreKit / Google Play Billing integration via Capacitor.
- **PGA Professional Review Workflow (50€)**:
  - Pro Review request modal allowing players to send video + telemetry summary to a certified PGA Coach.
  - Interactive fault checklist (Slice, Hook, Shank, Fat, Thin, Distance Loss), student notes, and guaranteed <24h turnaround.

### Fixed
- **iPhone Slow-Motion Seek Resilience**: Implemented safety timeout fallback in `seek()` (250ms) to prevent video stalling during analysis of 120fps/240fps iPhone slow-mo recordings.
- **MediaPipe Model Complexity Optimization**: Maintained `opt(1)` to eliminate dynamic ~100MB CDN heavy model download stalls, ensuring instant client-side execution in under 3 seconds.

## [4.5.0] - 2026-10-23
### Added
- **Full Video MP4 Export Engine (`v4.5`)**: Export the analyzed golf swing frame-by-frame with all overlays (skeletons, postural guides, ideal ghost avatar, hand trajectory, and HUD telemetry) into a crystal-clear H.264 MP4 file.
- **Hardware-Accelerated Encoding**: Integrated `mp4-muxer` and WebCodecs (`VideoEncoder`) for deterministic, fast offline frame rendering without stutter or dropped frames.
- **MediaRecorder Fallback**: Added real-time stream recording fallback for browsers without WebCodecs support.
- **Configurable Playback Speeds for Export**: Options for 0.25x (Recommended slow-motion for biomechanical swing analysis), 0.5x, and 1.0x (real-time).
- **Resolution Selector**: Choose between Full HD 1080p (optimized, fast and compatible for social media/coaches) and Original video resolution (up to 4K).
- **Interactive Visual Layer Toggles**: Checkboxes to customize which layers to include in the exported video (Skeleton & Joints, Hands Trajectory with A/T/I/F markers, Spine & Pelvis Guides, Ideal Ghost Swing + Face Angle, and HUD).
- **Broadcast-Grade HUD Overlay**: Sleek semi-transparent pills displaying current swing phase (`ADDRESS`, `BACKSWING`, `IMPACTO`, `FINISH`), impact-relative timer, club name, tempo ratio, and frame counter.
- **Batch Swing Export**: Ability to export the currently selected swing or all detected swings in the video session in sequence.
- **Progress Modal & Safety Cancel**: Real-time progress bar with percentage and frame count, plus responsive cancel handling.

### Fixed
- **Camera Auto-Detection Bug**: Fixed `const VIEW = 'dtl'` reassignment error in `autoView` by converting `VIEW` to `let`.
- **Seek Timeout Reliability**: Added `safeSeek` with timeout protection to prevent seeking freezes during video scrubbing and export.

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

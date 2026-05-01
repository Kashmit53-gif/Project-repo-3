# G-INTELLIGENCE v2.0

Advanced Gesture Recognition & Neural HUD
G-INTELLIGENCE is a high-performance, browser-based gesture recognition interface. It leverages MediaPipe's Skeleton Tracking and the Web Audio API to create an interactive, "Iron Man" style HUD (Heads-Up Display) that responds to your hand movements with real-time visual effects and procedural soundscapes.


# Key Features

•	Real-Time Skeleton Tracking: High-fidelity hand landmark detection using MediaPipe.
•	Procedural SFX Engine: Dynamic audio generation (hover drones, electrical crackles, and "electroblasts") that reacts to hand proximity and gestures.
•	Vortex Particle System: Pixelated energy orbs that follow your index fingers, featuring spiral physics and "plasma" tendrils.
•	Gesture Recognition Engine: Specialized logic for detecting complex hand shapes:
•	Orbs: Point index fingers to spawn Blue (Left) and Red (Right) energy.
•	Purple Formation: Join index and middle fingers (or touch index tips together) to create a massive purple vortex.
•	Electroblast: Form a "Purple Formation" then quickly flick to an "Open Palm" to trigger a cinematic energy blast.
•	Electrified Mode: Perform a "Fist Up" with one hand and "Fist Down" with the other to trigger screen-wide electrical interference.
•	Immersive HUD: A futuristic UI displaying real-time FPS, hand counts, and system logs.


# Technology Stack

Component	Technology
Tracking	MediaPipe Hands
Audio	Web Audio API (Oscillators, LFOs, Gain Nodes)
Rendering	HTML5 Canvas (2D Context)
Styling	CSS3 Grid & Backdrop Filters
Fonts	Google Fonts (Inter & Space Mono)


# How to Use

  1.	Open the file in any modern web browser (Chrome or Edge recommended for best performance).
	2.	Grant Camera Permission when prompted.
	3.	Position your hands within the camera view.
	4.	Try the following gestures:
•	☝️ Point: Spawn Red/Blue orbs at your fingertips.
•	✌️ Victory/Joined: Join your index and middle fingers to charge a Purple Core.
•	🖐️ Flick to Palm: Rapidly open your hand from a joined position to Blast.
•	✊ Fists: Hold one fist up and one down to Electrify the screen.


# Technical Requirements

•	Camera: Integrated webcam or external USB camera.
•	Browser: Chromium-based browsers (Chrome, Edge, Brave) provide the best Web Audio and MediaPipe compatibility.
•	Environment: Best used in a well-lit room with a plain background for optimal skeleton tracking.


# Engine Specifications

Gesture Logic
The GestureEngine class calculates the Euclidean distance between landmarks.
$$d = \sqrt{(x_2-x_1)^2 + (y_2-y_1)^2}$$

It compares fingertip positions relative to the "knuckle" (PIP) joints to determine if a finger is extended or folded.
Audio Synthesis
The SFXEngine does not use MP3 files. It synthesizes sound in real-time:
•	Hover: Low-frequency Sine waves (72Hz) modulated by a 3.5Hz LFO.
•	Blast: Exponential frequency ramps (4000Hz down to 80Hz) combined with white noise bursts.
Note: This application runs entirely client-side. No video data is ever sent to a server; all processing happens locally in your browser.

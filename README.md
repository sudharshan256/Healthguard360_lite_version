🛡️ HealthGuard360 Lite
> **Real-Time Health Monitoring, Stress Analysis, & Drug Safety During Computer Use.**
Developed under Laddle Tech, HealthGuard360 Lite is an immersive, client-side single-page utility designed to combat desk fatigue, prevent ergonomic strain, and provide instant medication safety clearance. It blends computer vision tracking with public healthcare telemetry and large language model intelligence.
---

🧭 System Architecture & Core Modules
The application is structured into three unified panels accessible via the top glassmorphism navigation header:

1. 🧘 Wellness Scan (Computer Vision & Ergonomics)
Biomechanical Posture Assessment: Integrates `@mediapipe/pose` to construct a real-time skeletal hierarchy. Evaluates shoulder level variations (left vs. right drops in pixels), forward head projection thresholds, head tilt offsets, spine vertical compression ratios, and hip distribution.
Facial Tension Telemetry: Leverages `@mediapipe/face\_mesh` landmarks to mathematically track sub-surface strain indicators:
Brow Furrowing: Monitored via absolute pixel distance dynamics between landmarks `55` and `285`.
Jaw Clenching: Tracks distance variances between the chin (`152`) and upper lip (`13`).
Lip Compression & Squint Ratios: Computes standard Eye Aspect Ratio (EAR) profiles to detect stress-induced squinting outside typical blinking windows.
Comprehensive Stress Analytics Engine: Merges real-time facial indicators (30% weight), posture breakdown loads (25% weight), eye fatigue/session duration factors (20% weight), sound ambient decibels (15% weight), and optical lighting quality parameters (10% weight) into an aggregated Stress Score (0–100) mapping into discrete wellness zones (Relaxed, Focused, Tense, Stressed, Burnout Risk).
Ergonomic Enforcement ("Caught You Slouching"): Captures automated canvas image snapshots when posture ratings plunge beneath a critical threshold (<40%), raising explicit alert popups to enforce corrective behaviors.
Environmental Monitoring: Uses Web Audio API analysers to gauge environmental noise and monitors real-time frame buffer data to compute room contrast, backlight errors, and illumination frequency flickers.
Contextual AI Coaching: Intermittently feeds live metric summaries into Google's `gemini-2.5-flash` endpoint to spit out concise, ultra-personalized physical instructions.

2. 💊 MedSafe QuickCheck (Drug Interaction & FDA Compliance)
Multi-API Health Registry Resolution: Cross-references search terms through the National Library of Medicine's RxNorm API to resolve exact generic string bindings (`IN` semantic concepts), brand translations (`BN`), and chemical delivery forms (`SCDG`).
Safety Databank Retrieval: Simultaneously queries the openFDA API and parses deep XML files using DailyMed Services to pull warnings, food/drug-drug interactions, maximum overdosage rules, storage criteria, and contraindications.
Enforcement & Recalls: Aggregates official FDA enforcement logs to flag global recall distributions and isolate active manufacturer alerts.
Teratogenic Classification: Classifies maternal and fetal risk profiles based on FDA Pregnancy Categories (A, B, C, D, X).
Dual Comparative Analysis: Renders synchronous side-by-side matrices contrasting warnings, storage profiles, and contraindications between two different drugs.
Portable Safety Cards: Generates responsive, standalone client-side HTML documents wrapped within dynamically rendered QRCode.js objects for mobile scanning, offline review, or structured printing.

3. 👩‍⚕️ Virtual Doc (Educational Guidance & Triage)
Symptom Mapping Pipeline: Evaluates key symptoms (Fever, Headaches, Allergies, Cold/Cough, Tooth Pain, Stomach Discomfort) or parses unformatted natural language text fields.
Natural Language Heuristics Engine: Scans symptom text using advanced regex maps to cross-verify structural safety constraints (e.g., severe pain terms, pediatric contexts, geriatric conditions, pregnancy markers, or acute blood signals).
AI-Driven Triage Architecture: Calls the Gemini API to format clean, bulleted advice outlining probable causes, actionable behaviors, and mandatory warning flags.
Automated OTC Bridging: Identifies fitting safe Over-The-Counter active ingredients (such as acetaminophen, ibuprofen, cetirizine) and programmatically runs them through the MedSafe engine to populate the user's view with active FDA recall logs and manufacturer alerts.


🎨 Visual Identity & UI Design
HealthGuard360 Lite uses a modern, highly polished aesthetic designed for professional desk environments:
Color Palette: Muted, desaturated earth-and-water tones including soft calm teal-blue accents (`#5b8fa8`), muted lavender details (`#7e6bbf`), and sage greens (`#4a9b74`).
Typography: Strict geometric hierarchies pairing clean running body font families (Inter) with high-legibility terminal font spaces (JetBrains Mono) for displaying live numbers and millisecond timestamps.
Adaptive Layout: Optimized utilizing clean CSS Media Queries across varying form-factor screens (Desktop monitors down to compact tablets/mobile devices).
Data Visualization: Renders interactive inline CSS performance meters, SVG circle indicators, and high-frequency real-time `<polyline>` sparkline vectors tracking 5-minute stress variations.


🛠️ Installation & Execution
Since HealthGuard360 Lite is a completely decoupled, front-end application with zero local node compilation dependencies, launching it requires no terminal environment setups:
Clone or download the target file: `HealthGuard360\_v2\_fixed (1).html`.
Open the file in any modern web browser (Google Chrome, Microsoft Edge, or Mozilla Firefox recommended for full MediaPipe camera framework support).
Grant permissions for Camera and Microphone inputs when prompted by the security layer of your browser.

🔒 Security & Privacy Posture
Zero-Server Footprint: All computer vision computations, frame modifications, mathematical processing, and database parsing are conducted completely locally inside the sandboxed running environment of your client browser.
No Image Transmission: No physical webcam footage, media frames, audio signals, or canvas layers are sent to external networks or developer databases.
Secure API Requests: Outbound calls to public healthcare platforms (openFDA, DailyMed, RxNorm) use clean URL strings containing non-identifiable, public drug terms. Large language model text prompts strictly encapsulate raw, scalar numeric strings (e.g., `Stress score: 34/100`) rather than human images or visual assets.


📜 Medical Disclaimer
HealthGuard360 Lite and its internal modules (MedSafe & Virtual Doc) are designed for informational and fitness tracking purposes only. This application does not constitute professional medical advice, clinical diagnosis, or prescriptive therapeutic recommendations. Always consult a licensed healthcare professional or emergency medical provider prior to altering chemical doses, initiating health courses, or interpreting severe acute symptoms.



⚠️ DISCLAIMER: THIS IS JUST A WORKING PROTOTYPE. DO NOT HOST THIS IN A OPEN WEB SERVER. SUITABLE FOR DEMO OR MINI PROJECTS ONLY.

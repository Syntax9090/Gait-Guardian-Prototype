GaitGuardian (Exploratory Prototype)
An experimental platform to democratize instrumented gait analysis for pediatric rehabilitation.

⚠️ CRITICAL DISCLAIMER: This software is a Research Prototype. It is NOT a medical device, has not been cleared by the FDA/EMA, and is not intended for clinical diagnosis. It is a technical demonstration of how modern web standards (Web Bluetooth) and Agentic AI can reduce the cost of prototyping rehabilitation tools. Use strictly for development and educational purposes.

The Mission
Pediatric therapists need quantitative tools to track gait patterns in children with Cerebral Palsy (CP). Current solutions are either:

Too Expensive: Clinical motion capture labs ($50k+).

Too Slow to Build: Custom software typically takes 18-24 months.

GaitGuardian explores a new path: "Fast Prototyping, Slow Validation." By leveraging Agentic AI (Google Antigravity workflows) and commodity hardware (Bluetooth IMUs), we built this functional telemetry stack in days, not years.

Architecture
This project uses a Local-First architecture to ensure data privacy by design. Raw sensor data is processed in the browser and never touches a server.

Frontend: Next.js 14 (App Router) + Tailwind CSS.

Hardware Bridge: Web Bluetooth API (No native app required; runs in Chrome).

Visualization: React Three Fiber (3D Limb Representation) + Recharts (Live Data Streams).

Math Kernel: Deterministic Trigonometry (Quaternion/Euler conversion) running client-side. No LLMs are used for gait calculation.

Data Sync: Supabase (PostgreSQL) for aggregated session reports only (e.g., "Session Score: 80/100").

graph TD
    A[Bluetooth IMU Sensor] -->|BLE Stream| B(Browser / Chrome)
    B -->|Decode Bytes| C{Math Engine}
    C -->|Quaternions| D[3D Visualizer]
    C -->|Threshold Logic| E[Game Engine]
    E -->|Session Summary| F[Supabase DB]
    B -.->|Raw Data| G[Local Storage]

Getting Started
Prerequisites

A Bluetooth Low Energy (BLE) IMU Sensor (Movesense, Arduino Nano 33 BLE, or generic ESP32).

Google Chrome or MS Edge (Firefox/Safari do not support Web Bluetooth yet).

Installation:

# 1. Clone the repo
git clone https://github.com/yourusername/gait-guardian-prototype.git

# 2. Install dependencies
npm install

# 3. Run the development server
npm run dev

📂 GitHub Repository: gait-guardian-prototype
Here is the README.md content for your repository. I have structured it to be technically impressive to engineers while remaining medically responsible to clinicians.

It explicitly flags the project as "Exploratory" using standard open-source badges and a dedicated "Clinical Safety" section.

Repository Metadata
Name: gait-guardian-prototype

Short Description: A local-first, agentic-built gait analysis tool for pediatric CP rehabilitation using Web Bluetooth and real-time visualization. [Exploratory Prototype - Not a Medical Device]

Topics: health-tech, cerebral-palsy, web-bluetooth, nextjs, agentic-ai, physiotherapy

README.md
🏃 GaitGuardian (Exploratory Prototype)
An experimental platform to democratize instrumented gait analysis for pediatric rehabilitation.

⚠️ CRITICAL DISCLAIMER: This software is a Research Prototype. It is NOT a medical device, has not been cleared by the FDA/EMA, and is not intended for clinical diagnosis. It is a technical demonstration of how modern web standards (Web Bluetooth) and Agentic AI can reduce the cost of prototyping rehabilitation tools. Use strictly for development and educational purposes.

🔭 The Mission
Pediatric therapists need quantitative tools to track gait patterns in children with Cerebral Palsy (CP). Current solutions are either:

Too Expensive: Clinical motion capture labs ($50k+).

Too Slow to Build: Custom software typically takes 18-24 months.

GaitGuardian explores a new path: "Fast Prototyping, Slow Validation." By leveraging Agentic AI (Google Antigravity workflows) and commodity hardware (Bluetooth IMUs), we built this functional telemetry stack in days, not years.

🏗 Architecture
This project uses a Local-First architecture to ensure data privacy by design. Raw sensor data is processed in the browser and never touches a server.

Frontend: Next.js 14 (App Router) + Tailwind CSS.

Hardware Bridge: Web Bluetooth API (No native app required; runs in Chrome).

Visualization: React Three Fiber (3D Limb Representation) + Recharts (Live Data Streams).

Math Kernel: Deterministic Trigonometry (Quaternion/Euler conversion) running client-side. No LLMs are used for gait calculation.

Data Sync: Supabase (PostgreSQL) for aggregated session reports only (e.g., "Session Score: 80/100").

Code snippet

graph TD
    A[Bluetooth IMU Sensor] -->|BLE Stream| B(Browser / Chrome)
    B -->|Decode Bytes| C{Math Engine}
    C -->|Quaternions| D[3D Visualizer]
    C -->|Threshold Logic| E[Game Engine]
    E -->|Session Summary| F[Supabase DB]
    B -.->|Raw Data| G[Local Storage]
🛠 Getting Started
Prerequisites
A Bluetooth Low Energy (BLE) IMU Sensor (Movesense, Arduino Nano 33 BLE, or generic ESP32).

Google Chrome or MS Edge (Firefox/Safari do not support Web Bluetooth yet).

Installation
Bash

# 1. Clone the repo
git clone https://github.com/yourusername/gait-guardian-prototype.git

# 2. Install dependencies
npm install

# 3. Run the development server
npm run dev
Connecting Your Sensor
Open http://localhost:3000.

Click "Connect Device".

Select your sensor from the browser pairing menu.

Note: You may need to update src/config/ble-uuids.ts if your sensor uses a non-standard UART Service UUID.

🤖 The "Agentic" Workflow
This codebase was largely scaffolded using Agentic AI workflows.

Role of AI: Boilerplate generation, UI component structure, Three.js scene setup.

Role of Human Engineer: Web Bluetooth stability, signal processing logic, privacy architecture.

This repository serves as a case study for how Clinician-Builders can use AI to manifest their ideas into testable software.

🛣 Roadmap (Exploratory)
[x] Phase 1: Stable Web Bluetooth connection & Raw Data Stream.

[x] Phase 2: 3D Real-time Visualization of Limb Orientation.

[ ] Phase 3: "Zeroing" Calibration feature for sensor drift.

[ ] Phase 4: Gamification Logic (Rocket ship rises on successful dorsiflexion).

🤝 Contributing
We welcome contributions from Biomedical Engineers and Frontend Developers.

Clinicians: Please open an Issue to suggest "Game Logic" or "Feedback Metrics."

Devs: Please help us optimize the Bluetooth event loop in useIMUSensor.ts.

Built with ❤️ for the CP Community.

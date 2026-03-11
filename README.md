# OptiLMS — Optical Lab Management System Demo

An interactive demo simulating the complete job lifecycle of an optical laboratory management system (LMS). This demo walks through all **10 production stages** — from a doctor submitting a prescription to finished glasses shipping out the door — showing the real equipment communication protocols used in the optical industry.

### [▶ Launch Live Demo](https://opticalowners.github.io/OptiLMS/)

![OptiLMS Demo](https://img.shields.io/badge/Status-Interactive_Demo-00e5c3?style=for-the-badge) ![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge) ![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge)

## Quick Start

**Option 1 — Live demo (no install):**

👉 **https://opticalowners.github.io/OptiLMS/**

**Option 2 — Run locally:**

```bash
git clone https://github.com/opticalowners/OptiLMS.git
cd OptiLMS
open index.html        # macOS
# or
start index.html       # Windows
# or
xdg-open index.html    # Linux
```

No build step, no dependencies to install, no server required.

## What This Demonstrates

### The 10 Production Stages

| Stage | Equipment | Protocol | What Happens |
|-------|-----------|----------|-------------|
| 📥 **Order Intake** | Web Portal | HTTP/REST | Doctor submits Rx, system validates, allocates lens blanks, creates production job |
| 📐 **Frame Trace** | National Optronics 7E | RS-232 Serial (OMA/DCS) | Tracer captures 400 radial points defining the frame shape |
| 🧮 **Lens Design** | IOT Freeform Server | TCP/IP | LDS calculates 12,000-point progressive surface geometry |
| ⚙️ **Surfacing** | Satisloh VFT-orbit 2 | TCP/IP (OMA/DCS) | Diamond tool generator cuts the freeform back surface |
| ✨ **Polish** | Satisloh SP-3000 | RS-232 Serial (OMA/DCS) | Polishing pad smooths tool marks to optical clarity |
| 🎨 **Coating** | Satisloh MC-380 | TCP/IP (OMA/DCS) | Vacuum chamber applies hard coat, UV, AR, and smudge resist |
| 💎 **Edging** | Briot Alta SX | RS-232 Serial (OMA/DCS) | Diamond wheel cuts lens to match the frame trace shape |
| 🔍 **Quality Check** | Auto-Lensometer | RS-232 Serial | Measures finished Rx and validates ANSI Z80.1 tolerances |
| 🔧 **Assembly** | Manual Station | — | Technician mounts lenses in frame, verifies PD and OC height |
| 📦 **Ship** | Shipping Integration | API | Generates shipping label, notifies provider, tracks delivery |

### OMA/VCA/DCS Protocol

The demo shows the actual data packets exchanged between the LMS and lab equipment using the **OMA/VCA/DCS** (Data Communication Standard), which is maintained by The Vision Council. This is the real industry-standard protocol used by optical labs worldwide.

Key protocol features demonstrated:

- **REQ=INI** — Auto-initialization handshake between host and device
- **REQ=FIL** — Job file transfer containing Rx, lens, and frame data
- **REQ=TRC** — Frame trace data request/response with radial point arrays
- **Label=Value format** — `SPH=-2.50;-3.00` (semicolons separate OD/OS values)
- **TRCFMT** — Trace format descriptor (type, points, unit, record label, side)
- **R=** records — Hundreds of radial distance values defining frame shape

## How to Use the Demo

1. **Open `index.html`** in your browser
2. **Click ▶ Play** at each stage to watch events unfold in real-time, or **Show All** to see everything at once
3. **Click Next Stage →** to advance through the pipeline
4. **Click any stage** in the top pipeline bar to jump directly to it
5. **Click SHOW** in the right panel to view the raw OMA/DCS data packets
6. The **left panel** shows order details and an animated SVG illustration of the current stage's equipment

## Tech Stack

- **React 18** — loaded via CDN (no build step)
- **Babel Standalone** — JSX compilation in-browser
- **SVG Animations** — lightweight equipment illustrations
- **Zero dependencies** — single HTML file, works offline after first load

## About OptiLMS

OptiLMS is a commercial SaaS Optical Lab Management System designed for optical laboratories of all sizes. This demo represents the core production workflow module.

### Core Modules

- **Order Management & Tracking** — Full production pipeline from intake to shipping
- **Lens Selection & Optimization** — Rx-based lens matching with thickness/cost optimization
- **Inventory Management** — Lens blanks, coatings, consumables, and equipment tracking
- **Billing & Invoicing** — Provider account management with payment tracking
- **Equipment Integration** — OMA/VCA/DCS protocol for RS-232 and TCP/IP device communication

## License

Copyright (c) 2025 OptiLMS. All rights reserved. This software is proprietary. See [LICENSE](LICENSE) for details.

# 🌍 AI Disaster Damage Assessment Using Satellite Images

> **"60-second AI-powered damage maps that tell rescue teams not just where the damage is — but where to go first."**

![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat-square&logo=python)
![React](https://img.shields.io/badge/React-18-61DAFB?style=flat-square&logo=react)
![FastAPI](https://img.shields.io/badge/FastAPI-0.100-009688?style=flat-square&logo=fastapi)
![Node.js](https://img.shields.io/badge/Node.js-18-339933?style=flat-square&logo=nodedotjs)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0-EE4C2C?style=flat-square&logo=pytorch)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

---

## 📌 Table of Contents..

- [Project Overview](#-project-overview)
- [Problem Statement](#-problem-statement)
- [Solution](#-solution)
- [Key Features](#-key-features)
- [USPs](#-unique-selling-points)
- [Tech Stack](#-tech-stack)
- [System Architecture](#-system-architecture)
- [Dataset](#-dataset)
- [Project Structure](#-project-structure)
- [Installation & Setup](#-installation--setup)
- [How It Works](#-how-it-works)
- [API Reference](#-api-reference)
- [Screenshots](#-screenshots)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Project Overview

**AI Disaster Damage Assessment** is a full-stack AI-powered web application that analyzes satellite imagery before and after natural disasters to automatically detect, classify, and visualize building damage — enabling faster, smarter disaster response.

Powered by a **pretrained U-Net model trained on the xBD dataset** (850,000+ building annotations), the system processes satellite image pairs and outputs a damage classification map with rescue priority zones in under 60 seconds.

Built for:
- 🏛️ Government disaster management agencies
- 🚒 Rescue and relief teams
- 🌐 NGOs and humanitarian organizations
- 🔬 Researchers and urban planners

- 

---

## 🚨 Problem Statement

After a major disaster — earthquake, flood, wildfire, cyclone — the biggest bottleneck is **not resources. It's information.**

| Challenge | Current Reality |
|---|---|
| Damage survey time | 3–7 days manually |
| Coverage | Limited to accessible areas |
| Accuracy | Dependent on field personnel |
| Resource allocation | Guesswork-based |
| Language barrier | Reports only in English |

> Every hour of delay in damage assessment = more lives at risk.

---

## ✅ Solution

A web platform where authorities upload **before and after satellite images** of a disaster-hit region. Within 60 seconds, the AI returns:

- 🗺️ A **damage heatmap** overlaid on the region
- 🔴 **Priority rescue zones** ranked by severity
- 🚧 **Road accessibility status** — which routes are blocked
- 📊 **Building damage statistics** — destroyed, major, minor, safe
- 📋 **Auto-generated PDF report** (available in Hindi/English)
- 👥 **Resource allocation estimate** — rescue teams, medical units, relief material needed

---

## ⭐ Key Features

### Core Features
- [x] Before/After satellite image upload
- [x] AI-powered damage detection (U-Net CNN)
- [x] Damage classification — No Damage / Minor / Major / Destroyed
- [x] Interactive damage heatmap (Leaflet.js)
- [x] Before/After image slider comparison UI
- [x] Damage statistics dashboard (Chart.js)

### Advanced Features
- [x] Rescue priority zone ranking (Zone A / B / C)
- [x] Confidence score per prediction zone
- [x] Road accessibility layer
- [x] Resource allocation calculator
- [x] PDF report export (English + Hindi)
- [x] NASA EONET live disaster feed integration
- [ ] Drone image support *(coming soon)*
- [ ] Disaster progression timeline *(coming soon)*
- [ ] WhatsApp volunteer coordination *(coming soon)*

---

## 🏆 Unique Selling Points

### 1. ⚡ Speed — 60 Seconds vs 3–7 Days
Traditional damage surveys take days. Our system delivers a complete damage map before rescue teams land.

### 2. 🔴 Rescue Priority Zones
Not just damage detection — the system ranks zones automatically:
```
Zone A 🔴 Critical  — Deploy immediately
Zone B 🟠 Severe    — Deploy within 2 hours  
Zone C 🟡 Moderate  — Ground verification recommended
```

### 3. 📊 Confidence Scores
Every prediction includes a confidence score — distinguishing high-certainty zones from areas needing ground verification. Production-grade transparency.

### 4. 🚧 Road Accessibility Layer
Damage maps are useless if rescue teams can't reach the area. Our system flags blocked and flooded roads alongside building damage.

### 5. 🇮🇳 Vernacular PDF Reports
Auto-generated assessment reports downloadable in **Hindi and English** — because local authorities need reports they can actually read and act on.

### 6. 🧮 Resource Allocation Calculator
```
320 destroyed buildings detected
→ Estimated displaced: ~1,280 people
→ Rescue teams needed: 8
→ Relief material: ~43 tons
→ Medical units: 3
```

---

## 💻 Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| React.js 18 | UI framework |
| Tailwind CSS | Styling |
| Leaflet.js | Interactive damage maps |
| Chart.js | Statistics dashboard |
| React-Leaflet | Map integration |

### Backend
| Technology | Purpose |
|---|---|
| Node.js + Express.js | REST API server |
| Multer | Image upload handling |
| Axios | AI model communication |

### AI / ML
| Technology | Purpose |
|---|---|
| Python 3.10 | AI backend language |
| PyTorch | Deep learning framework |
| OpenCV | Image preprocessing |
| FastAPI | AI model API server |
| U-Net CNN | Damage segmentation model |
| xView2 Pretrained Weights | Model backbone |

### Infrastructure
| Technology | Purpose |
|---|---|
| Cloudinary | Satellite image storage |
| NASA EONET API | Live disaster feed |
| Render / Railway | Deployment |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                     USER / BROWSER                      │
└─────────────────────┬───────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────┐
│              React Frontend Dashboard                    │
│   Image Upload │ Map View │ Charts │ PDF Export          │
└─────────────────────┬───────────────────────────────────┘
                      │  REST API
                      ▼
┌─────────────────────────────────────────────────────────┐
│           Node.js + Express Backend API                  │
│        Image handling │ Route management                 │
└─────────────────────┬───────────────────────────────────┘
                      │  HTTP
                      ▼
┌─────────────────────────────────────────────────────────┐
│           Python FastAPI — AI Model Server               │
│      Preprocessing │ Inference │ Postprocessing          │
└─────────────────────┬───────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────┐
│         U-Net CNN (xView2 Pretrained Weights)            │
│    Damage Segmentation │ Classification │ Confidence     │
└─────────────────────────────────────────────────────────┘
```

**Data Flow:**
```
User uploads Before + After images
        ↓
React sends to Node.js API
        ↓
Node.js forwards to Python FastAPI
        ↓
U-Net model processes image pair
        ↓
Damage mask + confidence scores returned
        ↓
Node.js enriches with zone ranking + resource calc
        ↓
React renders heatmap + dashboard + PDF option
```

---

## 📊 Dataset

### Primary — xBD Disaster Dataset ⭐ Best
The largest publicly available building damage dataset for satellite imagery.

| Property | Details |
|---|---|
| Size | 850,000+ building annotations |
| Images | 45,000 satellite images |
| Disasters covered | Earthquake, Flood, Wildfire, Hurricane, Tsunami, Volcano |
| Image pairs | Before + After per disaster event |

**Damage Classes:**
```
0 → No Damage
1 → Minor Damage  
2 → Major Damage
3 → Destroyed
```

**Download:** [xview2.org](https://xview2.org) | [AWS Open Data](https://registry.opendata.aws/xview2/) | [GitHub](https://github.com/DIUx-xView/xView2_baseline)

---

### Secondary Datasets

| Dataset | Best For | Link |
|---|---|---|
| FloodNet | Flood segmentation | [floodnet.cs.uh.edu](https://floodnet.cs.uh.edu) |
| SpaceNet | Building detection | [spacenet.ai](https://spacenet.ai) |
| FireNet | Wildfire damage | [GitHub](https://github.com/fire-dataset/FireNet) |

---

## 📂 Project Structure

```
disaster-ai-project/
│
├── frontend/                          # React Dashboard
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Upload.jsx             # Image upload component
│   │   │   ├── DamageMap.jsx          # Leaflet heatmap
│   │   │   ├── StatsChart.jsx         # Chart.js dashboard
│   │   │   ├── PriorityZones.jsx      # Zone ranking display
│   │   │   ├── ResourceCalc.jsx       # Resource allocation
│   │   │   ├── BeforeAfterSlider.jsx  # Image comparison slider
│   │   │   └── PDFExport.jsx          # Report generator
│   │   ├── App.jsx
│   │   └── index.js
│   └── package.json
│
├── backend/                           # Node.js API
│   ├── routes/
│   │   └── analyze.js                 # Damage analysis route
│   ├── uploads/                       # Temp image storage
│   ├── server.js
│   └── package.json
│
├── ai-model/                          # Python AI Server
│   ├── model/
│   │   ├── model.py                   # U-Net architecture
│   │   └── damage_model.pth           # Pretrained weights
│   ├── dataset/
│   │   ├── pre_disaster/
│   │   ├── post_disaster/
│   │   └── labels/
│   ├── preprocess.py                  # Image preprocessing
│   ├── predict.py                     # Inference script
│   ├── train.py                       # Training script
│   ├── api.py                         # FastAPI server
│   └── requirements.txt
│
├── .env.example
├── .gitignore
├── docker-compose.yml
└── README.md
```

---

## ⚙️ Installation & Setup

### Prerequisites
- Python 3.10+
- Node.js 18+
- Git

---

### 1. Clone the Repository
```bash
git clone https://github.com/shwetankrai12/disaster-ai-assessment.git
cd disaster-ai-assessment
```

### 2. Setup AI Model Server
```bash
cd ai-model

# Install dependencies
pip install torch torchvision
pip install fastapi uvicorn
pip install opencv-python numpy pillow

# Download pretrained weights
# Get from: https://github.com/DIUx-xView/xView2_baseline

# Start AI server
uvicorn api:app --reload --port 8000
```

### 3. Setup Node.js Backend
```bash
cd backend

npm install

# Create .env file
cp ../.env.example .env
# Add your configs

node server.js
# Runs on port 5000
```

### 4. Setup React Frontend
```bash
cd frontend

npm install

npm start
# Runs on port 3000
```

### 5. Open in Browser
```
http://localhost:3000
```

---

## 🔄 How It Works

### Step 1 — Upload Images
User uploads two satellite images:
- Pre-disaster image (before the event)
- Post-disaster image (after the event)

### Step 2 — AI Processing
The U-Net model:
1. Preprocesses both images (resize to 256×256, normalize)
2. Detects changes between the image pair
3. Classifies each building: No Damage → Minor → Major → Destroyed
4. Generates confidence score per prediction

### Step 3 — Results Dashboard
The system outputs:
- Interactive damage heatmap
- Priority zone ranking (A/B/C)
- Road accessibility status
- Damage statistics breakdown
- Resource allocation estimate

### Step 4 — Export
Download auto-generated PDF report in English or Hindi.

---

## 📡 API Reference

### AI Model API (FastAPI — Port 8000)

#### POST `/predict`
Analyze satellite image pair for damage.

**Request:**
```
Content-Type: multipart/form-data

pre_image:  [image file]
post_image: [image file]
```

**Response:**
```json
{
  "damage_map": [[0, 1, 3, 2, ...]],
  "confidence_scores": [[0.94, 0.87, 0.62, ...]],
  "statistics": {
    "no_damage": 550,
    "minor_damage": 220,
    "major_damage": 410,
    "destroyed": 320,
    "total_buildings": 1500
  },
  "priority_zones": {
    "zone_a": { "severity": "critical", "buildings": 320 },
    "zone_b": { "severity": "severe",   "buildings": 410 },
    "zone_c": { "severity": "moderate", "buildings": 220 }
  }
}
```

---

### Backend API (Node.js — Port 5000)

#### POST `/analyze`
Upload images and get full damage assessment.

#### GET `/disasters/live`
Fetch live disaster events from NASA EONET API.

#### POST `/report/generate`
Generate downloadable PDF assessment report.

---

## 📸 Screenshots

> *(Add screenshots of your dashboard here after building)*

| Feature | Preview |
|---|---|
| Upload Interface | `screenshots/upload.png` |
| Damage Heatmap | `screenshots/heatmap.png` |
| Priority Zones | `screenshots/zones.png` |
| Statistics Dashboard | `screenshots/stats.png` |
| PDF Report | `screenshots/report.png` |

---

## 🗺️ Roadmap

### Phase 1 — MVP (Current)
- [x] Core damage detection pipeline
- [x] Basic dashboard UI
- [x] Priority zone ranking
- [x] PDF report export

### Phase 2 — Enhanced
- [ ] Disaster progression timeline (Day 0 → Day 7 → Day 14)
- [ ] Drone image support
- [ ] WhatsApp volunteer coordination

### Phase 3 — Production
- [ ] Real-time satellite data (Sentinel Hub integration)
- [ ] "What If" flood scenario simulator
- [ ] Mobile app (React Native)
- [ ] Multi-language support (Tamil, Telugu, Bengali)

---

## 🤝 Contributing

Contributions are welcome!

```bash
# Fork the repo
# Create your feature branch
git checkout -b feature/your-feature-name

# Commit your changes
git commit -m "feat: add your feature"

# Push to the branch
git push origin feature/your-feature-name

# Open a Pull Request
```

---

## 📜 License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.

---

## 🙏 Acknowledgements

- [xView2 / xBD Dataset](https://xview2.org) — DIUx xView2 Challenge
- [FloodNet Dataset](https://floodnet.cs.uh.edu) — University of Houston
- [SpaceNet Dataset](https://spacenet.ai) — SpaceNet LLC
- [NASA EONET API](https://eonet.gsfc.nasa.gov) — NASA Earth Observatory
- [U-Net Architecture](https://arxiv.org/abs/1505.04597) — Ronneberger et al.

---

<div align="center">

**Built with ❤️ for faster disaster response**

⭐ Star this repo if you find it useful

[Report Bug](https://github.com/shwetankrai12/disaster-ai-assessment/issues) · [Request Feature](https://github.com/shwetankrai12/disaster-ai-assessment/issues)

</div>

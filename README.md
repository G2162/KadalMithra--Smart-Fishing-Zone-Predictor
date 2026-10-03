# 🌊 KadalMithra – Smart Fishing Zone Predictor

> **Friend of the Sea** 🎣

KadalMithra is a browser-based decision-support system designed to help fishermen identify promising fishing zones while considering ocean conditions and safety.

The project combines **Fishing Zone Prediction, Safety Classification, Boat Queue Management, Route Planning, and Data Structures** into a single interactive web application.

---

## 📌 Overview

Fishermen often depend on experience and trial-and-error to decide where to fish. This can increase fuel consumption and expose boats to unsafe sea conditions.

KadalMithra provides a simple interface where users can:

- 🐟 View predicted fishing potential across coastal zones
- 🌊 Monitor wind, wave and ocean conditions
- ⚠️ Classify zones as **SAFE, CAUTION, or DANGER**
- 🚤 Register and manage fishing boats
- 📋 Maintain a launch queue for each fishing zone
- ↩️ Undo recent boat-management operations
- 🔙 Recall the latest boat launched
- 🗺️ Plan routes that avoid dangerous zones
- 📍 Track boats and their planned routes
- 🔔 Generate and manage safety warnings

The application is implemented entirely on the client side using **HTML, CSS and JavaScript**, with no backend, database or external framework. :chatgpt-content-reference{index="1"}

---

## ✨ Features

### 🐟 Fishing Zone Prediction

The application displays fishing information for six coastal zones:

- Kannur
- Beypore
- Kochi
- Alappuzha
- Kollam
- Vizhinjam

Predictions are available for four time windows:

- 🌅 Dawn
- ☀️ Day
- 🌇 Dusk
- 🌙 Night

The prediction module provides:

- Fish probability
- Wind speed
- Wave height
- Sea surface temperature
- Chlorophyll
- Current speed
- Wind direction
- Top predicted fish species

The project uses a **deterministic demonstration model**, meaning the same zone and time selection produces repeatable values. It does **not** use live satellite or weather data. :chatgpt-content-reference{index="2"}

---

### ⚠️ Safety Classification

Each fishing zone is classified according to wind and wave conditions.

| Status | Condition |
|---|---|
| 🟢 SAFE | Waves ≤ 1.7 m and wind ≤ 15 kn |
| 🟡 CAUTION | Waves > 1.7 m or wind > 15 kn |
| 🔴 DANGER | Waves > 2.5 m or wind > 20 kn |

Boats detected inside danger zones generate safety warnings that are displayed on the warning board. :chatgpt-content-reference{index="3"}

---

### 🚤 Boat Management

KadalMithra maintains a separate queue for each fishing zone.

Users can:

- Add a boat
- Insert a boat at a selected queue position
- Launch the next boat
- Remove a boat
- Undo the previous operation
- Recall the most recently launched boat
- View recent activity

Example:

```text
Kollam Queue

Front
 ↓
[Anugraha] → [Matha] → [SeaQueen]
                              ↓
                            Back

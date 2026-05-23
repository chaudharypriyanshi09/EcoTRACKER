<!-- BADGES - Professional, data-driven glance metrics -->
<div align="center">

![GitHub last commit](https://img.shields.io/github/last-commit/chaudharypriyanshi09/EcoTRACKER?style=for-the-badge&color=2e7d32)
![GitHub Repo stars](https://img.shields.io/github/stars/chaudharypriyanshi09/EcoTRACKER?style=for-the-badge&color=4caf50)
![GitHub License](https://img.shields.io/github/license/chaudharypriyanshi09/EcoTRACKER?style=for-the-badge&color=81c784)
<br>
![Made with Love for Earth](https://img.shields.io/badge/Made%20with-%E2%9D%A4%EF%B8%8F%20for%20Earth-2e7d32?style=for-the-badge)
![Built with Framer Motion](https://img.shields.io/badge/Built%20with-Framer%20Motion-ff69b4?style=for-the-badge)

</div>

<br />
<div align="center">
<img src="assets/logo.png" alt="EcoTracker Logo" width="120" height="120">

<h1>🌱 EcoTracker</h1>

<p align="center">
<strong>Promoting active urban transportation through real-time GIS spatial tracking and behavioral stimulation.</strong>
<br />
A sleek, high-fidelity sustainability mobile application built to encourage low-emission lifestyles by tracking, understanding, and shifting daily commuting choices.
<br />
<br />
    <a href="https://4182cc4a-cdb6-4b0f-88a7-1fdc54125fe8.dev6.app-preview.com"><strong>✨ View Live Application Preview »</strong></a>
·
<a href="https://github.com/chaudharypriyanshi09/EcoTRACKER/issues">🐞 Report Bug</a>
·
<a href="https://github.com/chaudharypriyanshi09/EcoTRACKER/issues">💡 Request Feature</a>
</p>
</div>

---

## 🎯 **Core Concept**

Individual commute choices often feel completely detached from personal environmental impact. **EcoTracker** bridges this gap using advanced mobile ICT architecture to make users consciously aware of their ecological footprint. 

By converting real-time movement data into transparent, actionable milestones, the application functions on the principle of behavioral stimulation. EcoTracker empowers you to take charge of your carbon emissions, rewards you for sustainable mobility choices, and gamifies your journey toward a healthier lifestyle.

---

## ✨ **Key Features**

<table>
<tr>
<td width="50%">
 <h3>🚴 Automated Trip Recognition</h3>
 <p>Tracks location, speed, and routes using a combined <strong>Geohash-GIS spatial approach</strong> along with GPS to automatically identify transport modes (walking, cycling, or motorized) in real time[cite: 1].</p>
</td>
<td width="50%">
 <h3>☁️ Real-Time Carbon Tracking</h3>
 <p>Calculates precise carbon emissions for each individual trip made, displaying your cumulative CO₂ savings and benchmarking metrics at personal and community levels[cite: 1].</p>
</td>
</tr>
<tr>
<td width="50%">
 <h3>🪙 Gamified "Eco Points"</h3>
 <p>Earn points based on the carbon you save by avoiding motorized vehicles[cite: 1]. Eco Points can be accumulated to unlock special profile badges, custom certificates, and even redeemed for real monetary benefits[cite: 1].</p>
</td>
<td width="50%">
 <h3>💡 Sustainability Prompts</h3>
 <p>Contextual <strong>Environmental Education Prompts</strong> pop up on screen to provide instant sustainability tips, health modules, and fitness challenges[cite: 1].</p>
</td>
</tr>
<tr>
<td width="50%">
 <h3>🔥 Health & Biometric Insights</h3>
 <p>Monitors physical wellness side-by-side with environmental metrics by logging your total calories burned and delivering context-aware health insights[cite: 1].</p>
</td>
<td width="50%">
 <h3>📈 Framer Motion Dashboard</h3>
 <p>Highlights your achievements—like total carbon saved and calories burned—using ultra-smooth, visually appealing micro-interactions and animations built with <strong>Framer Motion</strong>[cite: 1].</p>
</td>
</tr>
</table>

---

## 📐 **The Carbon Calculation Regression Model**

The app’s intelligent carbon calculation is driven by a multiple linear regression model that estimates exact baseline $CO_2$ emissions based on specific vehicle characteristics[cite: 1]:

$$\text{CO}_2\text{Emissions} = 70.49 \cdot \text{Mass\_Kg} - 38.67 \cdot \text{vehicle\_type\_M1} - 28.90 \cdot \text{vehicle\_type\_M1G} - 15.25 \cdot \text{vehicle\_type\_MASTER} - 16.26 \cdot \text{vehicle\_type\_N1} + 42.98 \cdot \text{fuel\_type\_e85} - 43.76 \cdot \text{fuel\_type\_electric} + 23.66 \cdot \text{fuel\_type\_lpg} - 11.24 \cdot \text{fuel\_type\_ng\_biomethane} + 43.99 \cdot \text{fuel\_type\_petrol} + 183.55$$

### Variable Parameter Breakdown[cite: 1]:
*   **`Mass_Kg`:** Vehicle mass in kilograms[cite: 1]. The coefficient ($+70.49$) indicates that heavier vehicles are directly associated with higher $CO_2$ emissions[cite: 1].
*   **Vehicle Classification Dummy Variables (`M1`, `M1G`, `MASTER`, `N1`):** These are binary ($0$ or $1$) dummy variables representing passenger cars (`M1`), off-road capable vehicles (`M1G`), Renault Master vans (`MASTER`), and light commercial vehicles (`N1`)[cite: 1]. Negative coefficients mean these vehicle types emit less $CO_2$ compared to the baseline reference category[cite: 1].
*   **Fuel Type Dummy Variables:** Binary inputs representing fuel chemistry[cite: 1]. Petrol ($+43.99$) and Ethanol E85 ($+42.98$) heavily increase emissions, Liquefied Petroleum Gas (`lpg`) scales it moderately ($+23.66$), while Natural Gas/Biomethane ($-11.24$) and Electric choices ($-43.76$) drop the footprint calculation[cite: 1].
*   **Intercept ($183.55$):** The fixed baseline constant representing estimated $CO_2$ emissions when all other variable metrics are zero (the baseline reference vehicle)[cite: 1].

---

## ⚙️ **How It Works: Operational Lifecycle**

```text
 [User Taps "Start"] ──► 1. TRIP INITIALIZATION: GPS Tracking Starts & Origin Points Saved[cite: 1]
                                    │
                                    ▼
 [Active Commute]     ──► 2. LIVE UPDATES: Coordinates Stream & Map Interface Refreshes[cite: 1]
                                    │
                                    ▼
 [User Taps "End"]    ──► 3. TRIP COMPLETION: Compute Distance, MLR Carbon, & Disburse Points[cite: 1]

# Greg — Full-Stack Developer & Applied AI Engineer

> End-to-end design and implementation of complex simulation software — from rules engine to RL agent to production deployment.

---

## 🔭 Featured Project — [Warhammer 40K Tactical Simulator](https://github.com/GregSQT/40k)

A complete turn-based tactics engine with a self-training AI opponent, built solo from scratch.

| Layer | Stack |
|---|---|
| **Backend** | Python 3.11 · Flask REST API |
| **Frontend** | React 19 · TypeScript · Vite · PIXI.js (WebGL) |
| **AI / RL** | PyTorch · Stable-Baselines3 · MaskablePPO · Custom Gym environment |
| **Infra** | Docker Compose · Nginx · Self-hosted Synology NAS · TLS |
| **Quality** | pytest · vitest · pyright strict · Biome |

### By the numbers

| Metric | |
|---|---|
| 🏆 Win rate | **+90%** against 6 diverse-strategy bots — benchmark saturated |
| ⚙️ Action space | **1,389** boolean-masked actions per step |
| 📋 Rules engine | **7** game phases · **100+** special rules · multi-level 3D line-of-sight |
| 🧪 Test coverage | **7,100+** automated tests · **952** rule-compliance checks on real game logs |
| 🤖 Training curriculum | **15** progressive self-play stages + exploiters (OpenAI League approach) |
| 🎮 Frontend | PvP / PvE · step-by-step replay · **6** playable factions |

### Architecture highlights

- **Rules engine** — 7 game phases, multi-level 3D LoS, 100+ special rules faithfully implemented from official PDFs; custom engine-invariant linters enforce rule compliance at every commit
- **RL architecture** — MaskablePPO with shared-weight entity encoders, pointer head over a 32×32 CNN (AlphaStar-inspired); invalid actions are masked at source, not penalised
- **Progressive self-play** — 15 learner stages + exploiters (OpenAI League approach), curriculum from isolated mechanics to full-game strategy
- **Zero-divergence dual mode** — PvP hot-seat and PvE share a single engine; no separate codepath, no divergence risk
- **Quality pipeline** — strict `pyright` + `tsc --noEmit`, 7,100+ automated tests, 952-check rule compliance analyser running on real game logs

---

## 🛠 Tech Stack

**Backend & AI**

![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-REST%20API-000000?style=flat-square&logo=flask)
![PyTorch](https://img.shields.io/badge/PyTorch-GPU-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Stable-Baselines3](https://img.shields.io/badge/Stable--Baselines3-MaskablePPO-4B8BBE?style=flat-square)
![Gymnasium](https://img.shields.io/badge/Gymnasium-custom%20env-0072B2?style=flat-square)

**Frontend**

![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-build-646CFF?style=flat-square&logo=vite&logoColor=white)
![PIXI.js](https://img.shields.io/badge/PIXI.js-WebGL-e72264?style=flat-square)

**Infra & Quality**

![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=flat-square&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-reverse%20proxy-009639?style=flat-square&logo=nginx&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-7100%2B%20tests-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Pyright](https://img.shields.io/badge/Pyright-strict-FFBC00?style=flat-square)
![Biome](https://img.shields.io/badge/Biome-lint%20%2B%20format-60A5FA?style=flat-square)

---

## 📊 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=GregSQT&show_icons=true&theme=dark&hide_border=true&count_private=true&include_all_commits=true" height="160"/>
  &nbsp;
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=GregSQT&layout=compact&theme=dark&hide_border=true&langs_count=6" height="160"/>
</p>

<p align="center">
  <img src="https://streak-stats.demolab.com?user=GregSQT&theme=dark&hide_border=true"/>
</p>

---

## 📫 Contact

Open to full-stack or AI/ML engineering roles.  
Reach me on [LinkedIn](https://www.linkedin.com/in/) · or open an issue on the [40k repo](https://github.com/GregSQT/40k) if you want to discuss the architecture.

# Greg — Full-Stack Developer & Applied AI Engineer

> Building production-grade simulation software where game engines meet reinforcement learning.

---

## 🔭 Featured Project — [Warhammer 40K Tactical Simulator](https://github.com/GregSQT/40k)

A complete turn-based tactics engine with a self-training AI opponent, built from scratch over a multi-month solo effort.

| Layer | Stack |
|---|---|
| **Backend** | Python 3.11 · Flask REST API |
| **Frontend** | React 19 · TypeScript · Vite · PIXI.js (WebGL) |
| **AI / RL** | Stable-Baselines3 · MaskablePPO · Custom Gym environment |
| **Infra** | Docker Compose · Nginx · Self-hosted Synology NAS · TLS |
| **Quality** | pytest · vitest · pyright · Biome |

**What makes it non-trivial:**

- **Custom hex-grid game engine** — full Warhammer 40K rule set implemented from spec PDFs: movement, shooting, melee, stratagems, missions, terrain, transports, reserves
- **Masked action space** — the agent only ever sees legal moves; no invalid-action penalty hacks, no post-hoc filtering
- **End-to-end RL pipeline** — curriculum training → holdout evaluation → replay analysis → model versioning
- **Zero-divergence dual mode** — human vs. human (hot-seat) and human vs. AI share a single engine; no separate codepath
- **Typed throughout** — pyright strict on Python, `tsc --noEmit` on TypeScript, no `any` escape hatches

---

## 🛠 Tech Stack

**Backend & AI**

![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-REST%20API-000000?style=flat-square&logo=flask)
![PyTorch](https://img.shields.io/badge/PyTorch-GPU-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Stable-Baselines3](https://img.shields.io/badge/Stable--Baselines3-MaskablePPO-4B8BBE?style=flat-square)

**Frontend**

![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-build-646CFF?style=flat-square&logo=vite&logoColor=white)
![PIXI.js](https://img.shields.io/badge/PIXI.js-WebGL-e72264?style=flat-square)

**Infra & Quality**

![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=flat-square&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-reverse%20proxy-009639?style=flat-square&logo=nginx&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-unit%20%2B%20integration-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Pyright](https://img.shields.io/badge/Pyright-strict-FFBC00?style=flat-square)

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

<h1 align="center">Hi, I'm Gregory Souquet 👋</h1>

<p align="center">
  <b>ML / RL Engineer</b> — I design and ship complex simulation software end to end:<br/>
  rules engine → reinforcement-learning agent → production deployment.
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/YOUR-HANDLE"><img src="https://img.shields.io/badge/LinkedIn-connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
  &nbsp;
  <a href="https://github.com/GregSQT/40k"><img src="https://img.shields.io/badge/Featured-Warhammer%2040K%20Simulator-1f6feb?style=for-the-badge&logo=github&logoColor=white"/></a>
</p>

---

## 🎮 Warhammer 40K Tactical Simulator

<p align="center">
  <a href="https://github.com/GregSQT/40k">
    <img src="https://raw.githubusercontent.com/GregSQT/40k/main/frontend/public/Game%20sample.jpg" alt="Warhammer 40K simulator — WebGL board, unit datasheets and game log" width="100%"/>
  </a>
  <br/>
  <sub><i>Movement phase, Orks vs Space Marines — WebGL board with terrain & line-of-sight overlays, live unit datasheets, event log.</i></sub>
</p>

A complete turn-based tactics engine with a **self-training AI opponent**, built solo from scratch: the full tabletop ruleset, a React/WebGL client to play it, and an RL pipeline that learns to play it better than scripted bots.

<p align="center">
  <img src="https://img.shields.io/badge/win%20rate-90%25%2B%20vs%206%20bots-2ea043?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/action%20space-1%2C389%20masked-8957e5?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/tests-8%2C600%2B-0A9EDC?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/rule%20checks-952%20on%20real%20logs-f0883e?style=for-the-badge"/>
</p>

### How it fits together

```mermaid
flowchart LR
  UI["🖥️ React 19 + PIXI.js<br/>PvP · PvE · step replay"] <-->|REST| API["Flask API"]
  API --> ENGINE["⚙️ Rules engine<br/>7 phases · 100+ special rules · 3D line of sight"]
  GYM["🎲 Gymnasium env<br/>invalid actions masked at source"] --> ENGINE
  PPO["🧠 MaskablePPO · PyTorch<br/>entity encoders + pointer head over 32×32 CNN"] <--> GYM
  ENGINE --> LOGS["📜 Game logs"]
  LOGS --> ANALYZER["🔍 Rule-compliance analyzer<br/>952 checks"]
```

### 🧠 The AI
- **MaskablePPO** with shared-weight entity encoders and a pointer head over a 32×32 CNN (AlphaStar-inspired) — 1,389 boolean-masked actions per step
- **Progressive self-play**: 15 curriculum stages from isolated mechanics to full-game strategy, plus exploiters (OpenAI League approach)
- **Benchmark saturated**: 90%+ win rate against 6 bots with different strategies

### ⚙️ The engine
- 7 game phases, multi-level 3D line of sight, 100+ special rules implemented **from the official PDFs**, not from memory
- **One engine, zero divergence**: PvP hot-seat, PvE and the training environment run the exact same code path
- Engine-invariant linters and a 952-check compliance analyzer replay real game logs against the rules at every commit

### 🖥️ The product
- React 19 / TypeScript / PIXI.js (WebGL) client — PvP, PvE against the trained agent, step-by-step replay, 6 playable factions
- Flask REST API, Docker Compose + Nginx + TLS, self-hosted on a Synology NAS
- `pyright` strict · `tsc --noEmit` · Biome · 8,600+ pytest + vitest tests

<details>
<summary><b>More on the training pipeline</b></summary>
<br/>

- Custom Gymnasium environment wrapping the engine; observations = entity lists + 32×32 spatial grid; actions = decision types × unit slots × targets
- Curriculum: each stage adds mechanics (move → shoot → charge → fight → objectives), evaluation on a held-out opponent pool before promotion
- Exploiters trained against the current champion to close its blind spots, then folded back into the pool
- TensorBoard telemetry per action family, action-usage audit tools, replayable decision logs
</details>

---

## 🛠 Tech stack

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/PyTorch-GPU-EE4C2C?style=flat-square&logo=pytorch&logoColor=white"/>
  <img src="https://img.shields.io/badge/Stable--Baselines3-MaskablePPO-4B8BBE?style=flat-square"/>
  <img src="https://img.shields.io/badge/Gymnasium-custom%20env-0072B2?style=flat-square"/>
  <img src="https://img.shields.io/badge/Flask-REST%20API-000000?style=flat-square&logo=flask"/>
  <br/>
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript&logoColor=white"/>
  <img src="https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black"/>
  <img src="https://img.shields.io/badge/Vite-build-646CFF?style=flat-square&logo=vite&logoColor=white"/>
  <img src="https://img.shields.io/badge/PIXI.js-WebGL-e72264?style=flat-square"/>
  <br/>
  <img src="https://img.shields.io/badge/Docker-Compose-2496ED?style=flat-square&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Nginx-reverse%20proxy-009639?style=flat-square&logo=nginx&logoColor=white"/>
  <img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white"/>
  <img src="https://img.shields.io/badge/vitest-6E9F18?style=flat-square&logo=vitest&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pyright-strict-FFBC00?style=flat-square"/>
  <img src="https://img.shields.io/badge/Biome-lint%20%2B%20format-60A5FA?style=flat-square"/>
</p>

---

## 📊 GitHub stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=GregSQT&show_icons=true&theme=dark&hide_border=true&count_private=true&include_all_commits=true" height="160"/>
  &nbsp;
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=GregSQT&layout=compact&theme=dark&hide_border=true&langs_count=6" height="160"/>
</p>

<p align="center">
  <img src="https://streak-stats.demolab.com?user=GregSQT&theme=dark&hide_border=true"/>
</p>

---

## 📫 Let's talk

Open to **full-stack** or **AI/ML engineering** roles.
[LinkedIn](https://www.linkedin.com/in/YOUR-HANDLE) · [Open an issue on the 40k repo](https://github.com/GregSQT/40k/issues) if you want to discuss the architecture.

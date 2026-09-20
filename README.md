<h1 align="center">Hi, I'm Gregory Souquet 👋</h1>

<p align="center">
  <b>ML / RL Engineer</b> · Python · Reinforcement Learning · Software Engineering
</p>

<p align="center">
  I design and ship complex AI systems end to end — from deterministic simulation engines<br/>
  and rule validation to reinforcement-learning agents, evaluation pipelines and production deployment.
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/YOUR-HANDLE"><img src="https://img.shields.io/badge/LinkedIn-connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
  &nbsp;
  <a href="https://github.com/GregSQT/40k"><img src="https://img.shields.io/badge/Featured-Tactical%20RL%20Simulator-1f6feb?style=for-the-badge&logo=github&logoColor=white"/></a>
</p>

---

## 🧠 Featured Project — Tactical Simulation & Reinforcement Learning

<p align="center">
  <a href="https://github.com/GregSQT/40k">
    <img src="https://raw.githubusercontent.com/GregSQT/40k/main/frontend/public/Game%20sample.jpg" alt="Tactical simulator — WebGL board, unit datasheets and game log" width="100%"/>
  </a>
  <br/>
  <sub><i>Full-stack tactical simulation: WebGL client, deterministic rules engine, 3D line of sight, live game state and replay.</i></sub>
</p>

**A full-stack simulation and reinforcement-learning platform built from scratch.**

The project combines a deterministic, rule-driven simulation engine with a custom RL environment, a self-training agent, automated evaluation and a playable web client.

The game is the application domain; the engineering challenges are **simulation, decision-making, validation, machine learning and reliable software delivery**.

<br/>

<table align="center">
  <tr>
    <td align="center" width="250">
      <h1>🏆 90%+</h1>
      <b>win rate</b><br/>
      <sub>against 6 diverse scripted<br/>opponent policies</sub>
    </td>
    <td align="center" width="250">
      <h1>🎯 1,389</h1>
      <b>masked actions</b><br/>
      <sub>invalid actions removed<br/>before policy selection</sub>
    </td>
    <td align="center" width="250">
      <h1>🧠 15</h1>
      <b>self-play stages</b><br/>
      <sub>progressive curriculum<br/>+ exploiters</sub>
    </td>
  </tr>
  <tr>
    <td align="center" width="250">
      <h1>📜 100+</h1>
      <b>special rules</b><br/>
      <sub>7 game phases · multi-level<br/>3D line of sight</sub>
    </td>
    <td align="center" width="250">
      <h1>🧪 8,600+</h1>
      <b>automated tests</b><br/>
      <sub>pytest + vitest · strict<br/>static type checking</sub>
    </td>
    <td align="center" width="250">
      <h1>🔍 952</h1>
      <b>compliance checks</b><br/>
      <sub>automatically replayed against<br/>real game logs</sub>
    </td>
  </tr>
</table>

<br/>

### Architecture

```mermaid
flowchart TB
  subgraph PLAY[" Play / Evaluate "]
    direction LR
    UI["🖥️ React 19 + PIXI.js<br/>PvP · PvE · Replay"] <-->|REST| API["Flask API"]
  end

  subgraph TRAIN[" Train "]
    direction LR
    PPO["🧠 MaskablePPO · PyTorch<br/>Entity encoders + pointer head"] <--> GYM["🎲 Custom Gymnasium env<br/>Dynamic action masking"]
  end

  API --> ENGINE["⚙️ Deterministic rules engine<br/>7 phases · 100+ special rules · 3D line of sight"]
  GYM --> ENGINE
  ENGINE --> LOGS["📜 Game logs"]
  LOGS --> ANALYZER["🔍 Compliance analyzer<br/>952 automated checks"]
```

### 🤖 Reinforcement Learning

* **MaskablePPO** with shared-weight entity encoders and a pointer head over a 32×32 spatial representation
* **1,389 dynamically masked actions** per decision step, removing invalid actions before policy selection
* Custom **Gymnasium environment** wrapping the same engine used for gameplay
* Observations combine entity-level state with spatial information
* Progressive curriculum from isolated mechanics to full-game strategy
* **15 training stages**, with held-out evaluation before promotion
* Exploiters trained against the current champion to expose weaknesses and expand the evaluation pool
* TensorBoard telemetry, action-usage analysis and replayable decision logs

### ⚙️ Simulation & Rules Engine

* Deterministic turn-based engine with **7 game phases**
* **100+ special rules** implemented from the official rules documentation
* Multi-level **3D line-of-sight** and spatial interactions
* PvP, PvE and RL training all execute through the **same engine code path**
* Engine-invariant linters designed to detect illegal or inconsistent state transitions
* **952 automated rule-compliance checks** replay real game logs against expected behaviour

### 🧪 Evaluation & Reliability

The agent is evaluated against a fixed pool of scripted opponents representing different strategic behaviours.

Current evaluation:

**90%+ aggregate win rate** against the six-opponent benchmark.

The project also includes:

* **8,600+ automated tests** across Python and TypeScript
* `pyright` strict type checking
* `tsc --noEmit`
* Biome linting and formatting
* Automated game-log validation
* Deterministic replay and step-by-step debugging
* Training/evaluation separation to reduce overfitting to the training opponents

### 🖥️ Full-Stack Product

* **React 19 / TypeScript / PIXI.js** WebGL client
* PvP, PvE against trained agents and step-by-step replay
* Flask REST API
* Docker Compose
* Nginx reverse proxy + TLS
* Self-hosted deployment
* 6 playable factions

<details>
<summary><b>More on the training pipeline</b></summary>
<br/>

The RL environment converts the game state into entity-level observations combined with a 32×32 spatial representation.

The action space is factorised into decision types, unit slots and targets. Invalid combinations are dynamically masked rather than presented to the policy and penalised during training.

The curriculum progressively introduces game mechanics:

`movement → shooting → charge → combat → objectives → full-game strategy`

Each stage is evaluated against a held-out opponent pool before promotion. Exploiters are then trained against the current champion to target weaknesses and improve robustness.

The training infrastructure includes:

* reproducible training configurations
* model/version management
* TensorBoard telemetry
* action-family statistics
* decision-level replay logs
* automated evaluation
* game-log analysis

</details>

---

## 🛠 Technical Stack

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

## 📊 GitHub Activity

<p align="center">
  <img src="https://streak-stats.demolab.com?user=GregSQT&theme=dark&hide_border=true"/>
</p>

---

## 📫 Let's talk

Open to **ML / AI Engineering, Reinforcement Learning and Software Engineering** roles.

[LinkedIn](https://www.linkedin.com/in/YOUR-HANDLE) · [40k project](https://github.com/GregSQT/40k)

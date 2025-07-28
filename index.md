---
layout: default
---
<h1 align="center"><img src="/assets/Icon.png" alt="Paper Icon" style="height:2em; vertical-align:middle; margin-right:0.5em;"> POINT: Passenger Open-Ended Instruction Realization with LLM-Enabled Multi-Planner Scheduling in Autonomous Vehicles</h1>
<p align="center"> Anonymous for Now. *Source code and dataset will be released after formal publication*.</p>

# Abstract
Most Human-Machine Interaction (HMI) research overlooks the maneuvering needs of passengers in autonomous driving (AD). Natural language offers an intuitive interface, yet translating passenger open-ended instructions into control signals—without sacrificing interpretability and traceability—remains a challenge. This study proposes an innovative framework that leverages a large language model (LLM) to interpret instructions, generates executable scripts that schedule multiple motion planners based on real-time feedback, and converts planned trajectories into control signals. The scheduling-centric design decouples semantic reasoning from vehicle control at different timescales, establishing a transparent, auditable reasoning pathway from high-level instructions to low-level actions. Due to the absence of high-fidelity evaluation tools, this study also introduces the first benchmark for open-ended instruction realization in a closed-loop setting. Comprehensive experiments reveal that the framework significantly improves task-completion rates over LLM-agent and data-driven baselines, reduces LLM query costs, and achieves safety and compliance on par with specialized AD approaches.

# Framework
<h1 align="center"><img src="/assets/Overview.png" alt="Framwork Overview" style="height:15em; vertical-align:middle; margin-right:0.5em;"></h1>

This work proposes an instruction-realization framework powered by LLM. The framework leverages a LLM to interpret instructions (Stage 1) and generate executable scheduling scripts (Stage 2). These scripts schedule multiple motion planners using real-time environmental feedback and translate planned trajectories into control signals in a closed-loop setting (Stage 3).







# Animated Visualization Results of the Proposed Framework


<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Left_Lane_Change_1.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Watch out for pedestrians!"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Left_Lane_Change_2.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"So, when do we get to join the fast lane club?"</figcaption>
    </td>
  </tr>
</table>


<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Pull_Over_2.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"There’s a convenience store up ahead, mind if I grab something?"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Compositional_1.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Change to the fast lane after the turn."</figcaption>
    </td>
  </tr>
</table>



<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Right_Lane_Change_1.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"You are totally blocking the poor guy behind us!"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Right_Lane_Change_2.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Exit is just around the corner — get ready for the escape."</figcaption>
    </td>
  </tr>
</table>




<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Pull_Over_3.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"I am not feeling great, can we stop for a second?"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Compositional_2.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Overtake in three seconds."</figcaption>
    </td>
  </tr>
</table>





<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Left_Lane_Change_4.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"I feel unsafe behind that truck."</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Acceleration_1.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"Hit the gas, grandma!"</figcaption>
    </td>
  </tr>
</table>


<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Left_Lane_Change_5.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"We’re kinda hogging the fast lane — maybe time to scoot over?"</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/Deceleration.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">"This isn’t a highway, it’s a neighborhood street!"</figcaption>
    </td>
  </tr>
</table>



# Instruction Realization with Various LLMs

We contrasts the planner scheduling of Qwen‑3‑8B and DeepSeek‑V3 under identical simulation conditions for the left lane‑change command. Qwen‑3‑8B initiates the maneuver immediately at low speed, reducing traffic efficiency and leaving the lane change incomplete. DeepSeek‑V3 delays initiation until the ego vehicle speed exceeds 3 m/s, enlarging the target‑lane gap and shortening maneuver time, resulting in a smoother, earlier execution. This indicates that LLMs with different intelligence levels can exhibit substantial differences in behavior scheduling in dynamic traffic.

<table style="width:100%; border:none; margin:2em 0;">
  <tr>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/SLM_1.gif" alt="gif1" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">LLM Scheduling: Directly change to the left Lane.</figcaption>
    </td>
    <td style="text-align:center; vertical-align:top; width:50%;">
      <img src="/assets/LLM_1.gif" alt="gif2" style="max-width:100%; height:auto;">
      <figcaption style="margin-top:0.5em;">LLM Scheduling: Change to the left Lane when ego vehicle speed exceeds 3 m/s.</figcaption>
    </td>
  </tr>
</table>


### 🔥 Project A
- **简介**：一个基于 Vue3 + Vite 的后台管理系统模板  
- **地址**：[github.com/username/project-a](https://github.com/username/project-a)  
- **演示**：[在线预览](https://username.github.io/project-a)

### 🎨 Project B
- **简介**：使用 D3.js 可视化数据仪表盘  
- **地址**：[github.com/username/project-b](https://github.com/username/project-b)  
- **演示**：[在线预览](https://username.github.io/project-b)

---

## 联系方式

- 📧 邮箱：your.email@example.com  
- 🐦 Twitter：[@yourhandle](https://twitter.com/yourhandle)  
- 🖇️ 个人主页：[https://username.github.io](https://username.github.io)

---

> “代码改变世界，分享让世界更美好。”  

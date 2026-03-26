## Project Title
SPEAK-AI MULTILINGUAL SUPPORT

---

**Working On:**
Improving Robustness and Flexibility of the Text-to-Speech Pipeline in Speak Activity

---

## Basic Details

**Full Name:** Kavya Kumari
**Email:** Kavyalohani24@gmail.com
**GitHub Username:** Kavyalohani  

**First Language:** Hindi (comfortable with English for communication)  
**Location & Timezone:** India (IST, UTC +5:30)  

**Previous Open Source Work:**
- Contributions to Speak Activity in Sugar Labs

**Sugar Labs Contributions:**
- PR #1: https://github.com/sugarlabs/speak-ai/pull/70
- PR #2: https://github.com/sugarlabs/speak-ai/pull/77
- PR #3: https://github.com/sugarlabs/speak-ai/pull/80

---

## Introduction

Hello, I am a second-year undergraduate student at IILM University in Greater Noida,Uttar Pradesh, India with a strong interest in open-source, programming and systems development..

I have been actively contributing to the Speak Activity in Sugar Labs, focusing on improving the text-to-speech pipeline. My recent contributions include adding Hindi TTS support using gTTS and improving fallback handling between Kokoro, gTTS, and espeak  

Through these contributions, I have gained familiarity with the codebase, especially the speech pipeline, and identified areas where reliability and flexibility can be improved further.

This proposal is directly inspired by my hands-on contributions and observations while working on the project.

I aim to improve reliability for real users (students using Speak Activity), especially in low-connectivity environments.

---

## What are you making?

The current TTS pipeline lacks structured fallback handling and relies mainly on failure-based switching, which can reduce reliability.

This project focuses on redesigning and improving the Text-to-Speech (TTS) pipeline in the Speak Activity to make it more robust, modular, and extensible.

Currently, the system relies on a simple priority-based fallback mechanism between Kokoro and espeak, with limited handling of backend failures and no structured decision-making.

I propose to implement a structured TTS management system that:

- Introduces backend readiness checks before usage  
- Implements a prioritized and condition-aware fallback system  
- Supports multiple TTS backends (Kokoro, gTTS, espeak)  
- Enables language-aware backend selection  
- Improves error handling to prevent pipeline failures  

The goal is to transform the existing fallback logic into a more reliable and scalable system.

---

## Proposed Design

The improved system will introduce a structured decision flow for selecting TTS backends:

1. Check backend availability (e.g., Kokoro initialized)  
2. Check language compatibility  
3. Attempt synthesis using preferred backend  
4. On failure, fallback to next available backend  
5. Log errors and fallback transitions  

**Fallback Order:** Kokoro → gTTS → espeak

Each backend will be handled independently with proper exception handling to avoid breaking the overall pipeline.

This design ensures that failures in one backend do not disrupt the overall speech pipeline.

### Extensibility Consideration

The proposed design keeps backend handling modular, allowing new TTS engines to be integrated with minimal changes to the core pipeline logic.

This ensures long-term maintainability and scalability of the system.

### Pipeline Overview

Text → Kokoro → gTTS → espeak → Output

---

## How will it impact Sugar Labs?

- Ensures uninterrupted speech output through robust fallback handling  
- Improves accessibility for multilingual users  
- Reduces crashes due to TTS failures  
- Makes the system easier to extend with future TTS backends  
- Enhances overall user experience for students  
- Improves efficiency by avoiding unnecessary backend failures and retries

---

## Technologies

- Python  
- GStreamer (Gst, GLib)  
- Kokoro TTS  
- Google Text-to-Speech (gTTS)
- espeak  
- Git & GitHub  

---

## Timeline

### Community Bonding Period
- Study existing architecture  
- Discuss design with mentors  

### Week 1–2
- Refactor existing fallback logic  
- Add backend readiness checks  

### Week 3–4
- Implement structured fallback system  
- Improve error handling  

### Week 5 (Evaluation 1)
- Stable fallback system  
- Testing and bug fixing  

### Week 6–7
- Implement language-aware routing  

### Week 8–9
- Add configuration support  
- Improve logging  

### Week 10 (Evaluation 2)
- Stability improvements  
- Documentation  

### Week 11–12
- Testing  
- Final improvements  

### Buffer Time
- Reserved for unexpected issues  

---

## Time Commitment

I will dedicate approximately 30–35 hours per week to this project.

---

## Progress Reporting

- Regular GitHub updates (commits and PRs)  
- Weekly updates on Matrix / mailing list  
- Continuous mentor interaction  
- Will actively participate in community discussions and incorporate mentor feedback continuously

---

## Understanding of Mentorship

Based on my interactions on my pull requests, I understand that mentors are focused on improving stability and fallback handling in the TTS pipeline.

Their feedback emphasizes:
- Reliable backend transitions  
- Proper error handling  
- Maintaining compatibility  

This aligns with my proposal, and I look forward to working closely with mentors and improving the system iteratively.

---

## Why Me

I have already contributed to the Speak Activity with multiple pull requests focused on improving the TTS pipeline.

My contributions include:
- Adding Hindi TTS support using gTTS  
- Integrating fallback between multiple TTS systems  
- Improving error handling and system stability  

Through this work, I have gained a solid understanding of the codebase and the challenges involved in managing multiple TTS backends.

I am comfortable working with Python and debugging system-level issues. I actively engage with the community, respond to feedback, and iterate on my work.

I am committed to continuing my contributions even after GSoC, which makes me a strong fit for this project.
---

## Risk Management

- If Kokoro is unstable, fallback ensures continuity  
- Buffer time included in timeline  
- Regular mentor feedback will guide progress
- Fallback system design ensures graceful degradation instead of complete failure  

---

## Future Scope

- Support for additional TTS engines  
- GUI-based backend selection  
- Voice customization  

---

## Post GSoC Plans

I plan to continue contributing to Sugar Labs after GSoC by improving the speech system and helping new contributors.

I am interested in long-term involvement with the community.

I aim to become a long-term contributor to Sugar Labs and continue improving the Speak Activity beyond the scope of this project.


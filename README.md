# Secure AI Chat Assistant (Android & RAG)

![Android](https://img.shields.io/badge/Platform-Android-3DDC84?logo=android)
![Kotlin](https://img.shields.io/badge/Language-Kotlin-7F52FF?logo=kotlin)
![Security](https://img.shields.io/badge/Focus-Cybersecurity-red)

An advanced mobile AI implementation featuring Retrieval-Augmented Generation (RAG) and high-level binary protection. This project serves as a proof-of-concept for secure, context-aware Generative AI in mobile environments.

---

##  Overview

This assistant goes beyond simple LLM integration. It implements a local memory system (RAG) to provide long-term context while maintaining a hostile defense posture against reverse engineering.

### Key Pillars:
- **Intelligent Retrieval:** Local database-driven context for personalized AI interactions.
- **Hardened Security:** Multi-layered defense (The "Defense Protocol") to protect sensitive API assets.
- **Native Performance:** Optimized C++ core for cryptographic and logic-heavy operations.

---

## Architecture

The system is divided into two main specialized modules:

### 1. RAG Workflow
Detailed technical flow of how the assistant retrieves and processes local data to augment LLM prompts.
> [**View RAG Documentation ↗**](./app/docs/RAG_WORKFLOW.md)

### 2. Security Architecture
A comprehensive "Defense in Depth" strategy protecting the application from static and dynamic analysis.
> [**View Security Documentation ↗**](./app/docs/SECURITY_ARCHITECTURE.md)

---

## Tech Stack

- **Frontend:** Kotlin / Jetpack Compose
- **Local Storage:** Room Database (SQLite)
- **Native Core:** C++ / Android NDK / JNI
- **AI Engine:** Google Gemini Pro API / RAG Implementation
- **Security:** R8 Obfuscation, Anti-Debugging Heuristics, XOR Key Derivation

---

### Note
This repository is a technical showcase of secure mobile architecture. For security reasons and to protect the integrity of the integrated AI services, a full production build environment is not provided.

---
## ⚖️ License
Distributed under the MIT License. See `LICENSE` for more information.

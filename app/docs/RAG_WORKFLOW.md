# Secure AI Chat Assistant (Android & RAG Implementation)

A practical implementation of Generative AI in mobile environments, focusing on long-term memory and secure data handling. This project was developed to explore the intersection of Android Development and Cybersecurity.

##  Technical Implementation

### Architecture & RAG Workflow

![Diagrama de flujo del sistema](../assets/images/architecture_v1.png)

###  AI & Data Context
* **RAG Workflow:** Integrated a custom memory engine to provide the LLM with relevant historical context.
* **Vector Similarity:** Used **Cosine Similarity** logic to compare FloatArrays (Embeddings), ensuring the most relevant memories are retrieved.
* **API Integration:** Connected with Google’s `text-embedding-004` and `Gemini 1.5 Flash` using REST and SDKs, managing custom safety and generation settings.

###  Security & Performance (Cybersecurity Focus)
* **Native Layer (NDK/JNI):** Moved sensitive processing to C++ to practice basic obfuscation and protect app logic from easy reverse engineering.
* **Data Persistence:** Managed local storage with **Room Database**, using DAOs and Entities to handle complex message history.
* **Concurrency:** Used **Kotlin Coroutines** (Dispatchers.IO) to keep the UI responsive while performing background calculations.

###  Android Fundamentals
* **Modern Kotlin:** Built using Lambdas, Data Classes, and Extension Functions.
* **Dynamic UI:** Implemented a RecyclerView with multiple ViewTypes and used **ObjectAnimator** for smooth menu transitions.
* **Formatting:** Used `SpannableStringBuilder` for real-time text styling without relying on heavy HTML rendering.

###  MMD

```mermaid
graph TD
    %% Node styles
    classDef user fill:#4CAF50,stroke:#2E7D32,stroke-width:2px,color:white;
    classDef frontend fill:#2196F3,stroke:#1565C0,stroke-width:2px,color:white;
    classDef database fill:#FF9800,stroke:#EF6C00,stroke-width:2px,color:white;
    classDef background fill:#607D8B,stroke:#37474F,stroke-width:2px,color:white;
    classDef cloud fill:#9C27B0,stroke:#6A1B9A,stroke-width:2px,color:white;

    %% Nodes
    U((👤 User)):::user
    UI[📱 ChatActivity / UI]:::frontend
    DB[(🗄️ Room Database)]:::database
    LLM[☁️ Gemini Chat API]:::cloud
    WORKER[⚙️ Vector Synchronizer]:::background
    EMBED[🧠 Gemini Embeddings API]:::cloud

    %% PHASE 1: REAL-TIME CHAT
    U -->|1. Sends message| UI
    UI -->|2. Saves message immediately| DB
    DB -->|3. Returns chat history| UI
    UI -->|4. Sends History + Prompt| LLM
    LLM -->|5. Returns AI response| UI
    UI -->|6. Displays response on screen| U
    UI -->|7. Saves AI response| DB

    %% PHASE 2: LONG-TERM MEMORY
    DB -.->|8. Detects messages without vector| WORKER
    WORKER -.->|9. Sends clean UI text| EMBED
    EMBED -.->|10. Returns RAG Vector FloatArray| WORKER
    WORKER -.->|11. Updates message with its Vector| DB
```


---
*Note: Source code is private to protect API implementation details. Walkthroughs are available for technical interviews.*

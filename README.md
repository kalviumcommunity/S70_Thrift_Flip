# 👔 Thrift Flip 🌦️

Your personal AI-powered morning assistant that makes dressing decisions effortless and intelligent. By combining **real-time weather**, **calendar events**, and your **virtual closet**, it suggests stylish, context-appropriate outfits every day.

---

## 🚀 Project Goal

The goal of this project is to simplify the daily decision of **"What should I wear today?"** using **AI reasoning, embeddings, and external APIs**.  
The assistant:

- Analyzes **weather data** to determine comfort requirements.  
- Reads **calendar events** to understand dress codes.  
- Filters the **virtual closet** to find the best options.  
- Suggests **three complete outfits** (top, bottom, shoes, accessories).  
- Explains why the outfit was chosen in a clear and stylish way.  

---

## 🧠 Key AI/ML & Prompting Features

1. **Chain of Thought Prompting (CoT):** Step-by-step reasoning ensures logical outfit suggestions.  
2. **Dynamic Prompting:** Prompts are built on real-time data (`weather_json`, `calendar_json`, `closet_json`).  
3. **Zero-shot, One-shot, and Multi-shot Prompting:** Used for outfit suggestions, style tips, and explanation generation.  
4. **System + User Prompts:**  
   - **System:** `"You are 'Aura,' a smart fashion assistant..."`  
   - **User:** Dynamic weather + calendar + closet data.  
5. **Stop Sequences:** Ensures clean structured output (`\n---`).  
6. **Structured Output:** JSON objects with outfit details (top, bottom, shoes, accessories).  
7. **Temperature, Top-K, Top-P:** Balanced creativity and coherence.  

---

## 📊 Similarity Search Features

- **Cosine Similarity:** Finds semantically closest clothing items.  
- **Dot Product Similarity:** Alternative similarity metric.  
- **L2 Distance (Euclidean):** Third metric option.  
- **Embeddings:** Each clothing item has a text description (e.g., `"black wool formal trousers"`) stored as embeddings.  
- **Vector Database:** Fast and efficient search for similar items when replacements are needed.  

---

## 🔧 Technology Stack

- **Frontend:** React / React Native (dashboard, closet UI, outfit rendering)  
- **Backend:** Node.js + Express  
- **Database:** MongoDB (user data), Vector Database (closet embeddings)  
- **APIs:**  
  - Weather API (via `get_local_weather(location)`)  
  - Calendar API (via `get_calendar_events(date, user_id)`)  
- **LLM Integration:** OpenAI GPT with function calling + structured output  

---

## 🧩 Core Implementations

### Function Calling
```ts
get_local_weather(location: string) → weather_json
get_calendar_events(date: string, user_id: string) → calendar_json

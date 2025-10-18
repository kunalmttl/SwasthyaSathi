
---

<div align="center">
  <img src="public/swasthyasathi_logo.svg" alt="SwasthyaSathi Logo" width="100"/>
  <br/>
  <h1>SwasthyaSathi - AI-Driven Public Health Chatbot</h1>
  <p>A multilingual, AI-powered WhatsApp chatbot designed to democratize healthcare access and awareness across rural India.</p>

  <p>
    <a href="#-key-features">Key Features</a> •
    <a href="#-tech-stack--architecture">Tech Stack</a> •
    <a href="#-project-showcase">Showcase</a> •
    <a href="#-getting-started">Setup</a>
  </p>
</div>

<!-- Optional: replace the YouTube link with your final demo video -->
[![DEMO VIDEO](https://img.youtube.com/vi/Y_kK3CRe0d4/maxresdefault.jpg)](https://youtube.com/shorts/Y_kK3CRe0d4?si=_LNzr25sGj0UVhyt)

---

## 🩺 About The Project

**SwasthyaSathi** is an **AI-driven public health chatbot** built for the **Smart India Hackathon 2025** by **Team Null & Void Inc.**

Our mission is simple yet powerful:
> To bridge India's rural healthcare gap by making verified medical information instantly accessible — in every language, through the simplest platform: WhatsApp.

This chatbot allows users to:
- Ask health-related questions in their local language.
- Receive AI-generated insights for symptoms or images (like rashes or prescriptions).
- Get real-time **vaccination and outbreak alerts**.
- Directly contact verified doctors for emergencies.

The result: a **proactive, multilingual, AI-powered health assistant** that transforms healthcare from **reactive to preventive**.

---

## ✨ Key Features

- **🗣️ Multilingual Onboarding:** Interactive registration in multiple Indian languages using IndicTrans2.
- **🧠 Hybrid Intent Recognition (Rasa + Node.js):** Classifies user messages into simple FAQs or escalates complex medical ones to the AI.
- **🩺 Medical & Vision AI:** Accepts images (like prescriptions or skin issues) and text to provide context-aware health analysis.
- **🔔 Proactive Health Alerts:** Daily automation scripts send localized outbreak and vaccination notifications using official health APIs.
- **☁️ Scalable User Database:** Stores user data, preferences, and consent in Supabase (PostgreSQL).
- **💬 WhatsApp Integration:** Real-time conversation using the official WhatsApp Cloud API.
- **📍 Smart Location Detection:** Automatically fetches location from WhatsApp’s “Share Location” feature and maps it to the nearest pincode.
- **🔐 Safety-First Design:** Emergency or critical symptoms are identified early and routed directly to healthcare professionals.

---

## 🛠️ Tech Stack & Architecture

This project is built as a **modular Node.js application**, designed for scalability, automation, and multilingual support.

### Backend:
| Category | Technology |
| :--- | :--- |
| **Framework** | **Node.js** with **Express.js** |
| **Database** | **Supabase (PostgreSQL)** |
| **AI & NLP** | **Rasa NLU**, **Perplexity API**, **IndicTrans2** |
| **Image Handling** | WhatsApp Media API + AI Vision Model |
| **Automation** | Node.js Cron Jobs for proactive alerts |
| **Integration** | **WhatsApp Cloud API** for real-time messaging |
| **Environment Management** | `.env` variables (ignored via `.gitignore`) |

### Core Architectural Concepts:
- **Hybrid AI Flow:** Rasa handles intents → routes complex cases to an advanced LLM.
- **Stateless Backend:** Every request verified via API key or token; no session persistence.
- **Multimodal Analysis:** Accepts text + image + location inputs for context-rich interaction.
- **Proactive Automation:** Outbreak and vaccination alerts run as standalone cron jobs.
- **Language Intelligence:** IndicTrans2 enables support for major Indian languages.

---

## 📸 Project Showcase

Below are key screens and scenarios you can capture for your README or presentation:

- [ ] **Multilingual Onboarding Flow:** Demonstrating the welcome message and registration in Hindi.
- [ ] **Chat Interaction:** Example of user asking a medical question and receiving AI-assisted reply.
- [ ] **Image Query Flow:** User uploads image of prescription or rash for analysis.
- [ ] **Outbreak Alert Notification:** Automatic alert message with district-level data.
- [ ] **Vaccination Drive Alert:** Scheduled message about a nearby vaccination event.
- [ ] **Emergency Routing:** Example of chatbot detecting a critical case and connecting to doctor.

---

## 🧠 System Architecture Overview

**1️⃣ User Interaction Layer**
- Users communicate via WhatsApp.
- Messages (text, image, or location) are received through **WhatsApp Cloud API**.

**2️⃣ NLP Router**
- Message passed to **Rasa NLU** → determines intent.
- Simple FAQs answered instantly.
- Complex queries routed to **AI Analyzer**.

**3️⃣ AI Analyzer**
- Uses **Perplexity API** for advanced reasoning.
- Handles both text and images (multimodal analysis).

**4️⃣ Database Layer**
- **Supabase** stores:
  - User profile
  - Language preference
  - Consent info
  - Location
  - Health interaction history (optional)

**5️⃣ Automation Layer**
- Independent Node.js scripts:
  - `vaccination.js` → Fetches and notifies users about drives.
  - `outbreak.js` → Fetches disease alerts from official sources.
- Can be run daily using **Cron Jobs** or serverless triggers.

---

## 🧩 Directory Structure (Simplified)

```

SwasthyaSathi/
│
├── index.js               # Main server entry point
├── chat.js                # WhatsApp message handling logic
├── onboarding.js          # Multilingual user registration flow
├── outbreak.js            # Outbreak data fetch & alert script
├── vaccination.js         # Vaccination drive alert script
├── services.js            # Helper functions / external API calls
├── supabaseClient.js      # Database connection & queries
├── db.js                  # (Optional) Database utilities
├── .env                   # Local environment variables (ignored)
├── .gitignore             # Ignore sensitive files like .env
└── package.json           # Project metadata & dependencies

````

---

## 🚀 Getting Started

Follow these steps to set up the project locally:

### 1. Clone the repository:
```bash
git clone https://github.com/kunalmttl/SwasthyaSathi.git
cd SwasthyaSathi
````

### 2. Configure Environment Variables:

Create a `.env` file in the root directory:

```env
SUPABASE_URL=your_supabase_project_url
SUPABASE_KEY=your_supabase_api_key
WHATSAPP_ACCESS_TOKEN=your_meta_whatsapp_token
RASA_API_URL=your_rasa_endpoint
PERPLEXITY_API_KEY=your_perplexity_key
PORT=3000
```

### 3. Install Dependencies:

```bash
npm install
```

### 4. Run the Development Server:

```bash
npm run dev
```

### 5. Run Automated Alert Scripts (optional):

```bash
node vaccination.js
node outbreak.js
```

Your WhatsApp-based chatbot will now be live on your configured webhook URL.

---

## 💡 Future Roadmap

| Phase       | Feature                                 | Description                                                 |
| :---------- | :-------------------------------------- | :---------------------------------------------------------- |
| **Phase 2** | 🎙️ Voice Queries                       | Add Speech-to-Text for voice-based inputs.                  |
| **Phase 3** | 💊 Prescription-based Reminders         | Analyze prescription images and schedule medication alerts. |
|             | 🤰 Pregnancy Journey Tracker            | Personalized guidance for expectant mothers.                |
| **Phase 4** | 🏥 Government Health Record Integration | Connect ABHA & CoWIN APIs for verified data access.         |
| **Phase 5** | 👩‍⚕️ Doctor Directory                  | Fetch nearby verified clinics and doctors.                  |

---

## 🌍 Impact & Vision

| Impact Area                | Description                                                          |
| :------------------------- | :------------------------------------------------------------------- |
| **Rural Empowerment**      | Brings healthcare to users with basic phones.                        |
| **Multilingual Inclusion** | Communicates fluently in local Indian languages.                     |
| **Healthcare Efficiency**  | Frees doctors from repetitive queries.                               |
| **Proactive Ecosystem**    | Moves healthcare from reactive to preventive.                        |
| **Health Equity**          | Ensures everyone, regardless of literacy, gets reliable information. |

---

## 🧠 Key Differentiators

* **WhatsApp-first platform** — no apps or websites required.
* **Deep multilingual AI** — powered by IndicTrans2 and Rasa.
* **Safety-first AI pipeline** — intercepts emergencies.
* **Proactive automation** — daily health alerts & reminders.
* **Scalable & modular backend** — easy to expand with new health modules.

---


## 🏁 Conclusion

**SwasthyaSathi** reimagines healthcare accessibility for rural India using **AI, automation, and language technology** — right inside the most familiar app: **WhatsApp**.

> “Trusted health information, in every language, for everyone.”

---

### 🧩 License

This project is open-source under the **MIT License**.

---

### 🙏 Acknowledgements

Special thanks to:

* **Smart India Hackathon 2025** organizers
* **Supabase**, **Meta Cloud API**, and **Rasa** teams
* The open-source AI community for building the foundation for accessible health tech

---

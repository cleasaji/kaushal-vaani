<div align="center">

# 🎙️ Kaushal Vaani
### Voice-First AI for Livelihood Mapping & NSQF-Aligned Skilling

*From **"What skill do I need?"** to **"What can I do next?"***

![SIH 2026](https://img.shields.io/badge/Smart%20India%20Hackathon-2026-E85A9B?style=for-the-badge)
![PS](https://img.shields.io/badge/Problem%20Statement-SIH26097-B98BE8?style=for-the-badge)
![Theme](https://img.shields.io/badge/Theme-Smart%20Education-F27FBC?style=for-the-badge)
![Category](https://img.shields.io/badge/Category-Software-FCAFDB?style=for-the-badge)

**Team Sirius** · Team ID 123894

</div>

---

## 📌 Problem statement
**SIH26097: AI-Driven Voice Assistant for Livelihood Mapping & NSQF-Aligned Skilling Recommendations for SC Communities under the GIA component of PM-AJAY.**

A beneficiary may know what work they do, what they are good at, or what they want to learn, but may not know which skill course suits them, which opportunity matches their existing skills, or how to communicate their needs through a digital system. For many people, language and digital access become an extra barrier.

## 💡 Our idea
Instead of asking the beneficiary to navigate a complicated form, **Kaushal Vaani lets them simply speak** in their preferred language. The system uses that conversation to:

1. **Listen**: understand what the beneficiary says
2. **Build a profile**: livelihood, skills, interests, training needs
3. **Find a skill match**: NSQF-aligned Qualification Packs and courses
4. **Create actionable insights**: a structured view for GIA officers

> *"The beneficiary speaks. The system understands. The programme gets better information."*

| 👤 For the beneficiary | 🏛️ For the GIA officer |
|---|---|
| Voice-first interaction | Structured beneficiary information |
| Preferred-language support | Sector-wise livelihood data |
| Skill and livelihood profiling | Skill-gap visibility |
| Relevant NSQF-aligned course suggestions | Better inputs for intervention planning |

## 🧭 How it works (production architecture)

```
 Reach the beneficiary      Understand the voice        Build the profile
 IVR · WhatsApp · Web  ───▶ Bhashini · ASR · TTS  ───▶ Livelihood · Skills ───┐
                                                       Interests · Needs      │
                                                                              ▼
 GIA Officer Dashboard  ◀───  Find the right match  ◀───────────────────────────
 sector-wise insights         NSQF Qualification Packs & courses
```

**Production plan:** BHASHINI → verified NSQF/NQR data → RAG → backend → IVR / WhatsApp → training-option integration. Deployment is planned as containerised, version-controlled and monitored.

> ⚠️ **Prototype vs. production.** This repository is the **working prototype**: a single-file HTML demo that runs **rule-based matching on illustrative sample data**. Bhashini speech, RAG, IVR/WhatsApp and live NSQF/NQR integration are part of the proposed production design and are **not** implemented in this prototype. All figures in the demo's dashboard are labelled *Illustrative Demo Data*.

## 🖥️ The prototype (`index.html`)

Two views, switchable from the top bar:

**Citizen Assistant**: a guided flow
1. Choose your language
2. Voice interview (mic button with consent prompt: *Not now* / *Allow & speak*, plus text input)
3. Your livelihood profile
4. Recommended pathway

**Officer Dashboard**: a block-level livelihood and skilling snapshot
- A. Overview
- B. Sector-wise demand
- C. Skill gaps
- D. Possible planning insight
- E. Beneficiary records

A **▶ Try Sample Beneficiary** button runs the whole flow instantly, and **⟲ Reset Demo** starts over.

**Run it:** no build step. Open `index.html` in a browser (or serve the folder with `python -m http.server`).

## ✅ Feasibility and how we handle the hard parts

| Challenge | Approach |
|---|---|
| Dialects and accents | Multilingual ASR with short, guided questions |
| Low connectivity | IVR works on any basic phone; WhatsApp / Web optional |
| Voice-data privacy | Consent-first, aggregated officer view, aligned to the **DPDP Act 2023** |
| Wrong matches | Suggestions only from verified NSQF / NQR data |
| Scaling | Add languages and state-wise course data on open / government stacks |

## 📚 References
- PM-AJAY Guidelines, GIA component: Ministry of Social Justice & Empowerment ([socialjustice.gov.in](https://socialjustice.gov.in/schemes))
- NSQF & Qualification Packs: NCVET ([ncvet.gov.in](https://ncvet.gov.in/hi/)), National Qualifications Register ([nqr.gov.in](https://nqr.gov.in))
- BHASHINI: National Language Translation Mission, Digital India Corporation ([bhashini.gov.in](https://bhashini.gov.in/about-bhashini))
- AI4Bharat IndicASR / IndicTTS: IIT Madras ([ai4bharat.iitm.ac.in](https://ai4bharat.iitm.ac.in))
- PMKVY 4.0: Ministry of Skill Development & Entrepreneurship · Skill India Digital ([skillindia.gov.in](https://www.skillindia.gov.in))
- PLFS: Ministry of Statistics & Programme Implementation ([mospi.gov.in](https://mospi.gov.in))
- Digital Personal Data Protection Act, 2023: MeitY

---

<div align="center">

**Team Sirius** · Smart India Hackathon 2026

</div>

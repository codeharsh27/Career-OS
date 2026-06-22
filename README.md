<div align="center">

# CareerOS

**A career management platform built because job searching 
was broken and nobody had fixed the fragmentation problem.**

[![Flutter](https://img.shields.io/badge/Flutter-Mobile-blue?logo=flutter)](https://flutter.dev)
[![FastAPI](https://img.shields.io/badge/FastAPI-Python-green?logo=fastapi)](https://fastapi.tiangolo.com)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL-green?logo=supabase)](https://supabase.com)
[![Play Store](https://img.shields.io/badge/Play%20Store-Live-brightgreen?logo=google-play)](your-play-store-link)

**20+ active users · Live on Play Store**

[Play Store](your-play-store-link) ·
[Portfolio](https://harshmule.vercel.app) ·
[LinkedIn](https://linkedin.com/in/harshmule27)

</div>

---

## The Problem

Job searching is fragmented.

During college I watched friends juggle LinkedIn, Naukri, 
Indeed, company career pages, and WhatsApp job groups 
in the same session. They spent more time managing 
the process than actually applying.

Some forgot where they'd already applied.
Some missed roles because they only checked one platform.
Others didn't know what to prepare for after finding a posting.

The problem wasn't finding jobs. It was managing the search.

---

## What CareerOS Does

One platform for the entire career journey.

**Discover** — job listings aggregated from multiple 
sources into one unified feed.

**Match** — AI matching engine surfaces relevant 
opportunities against your profile. Built to work 
even before you have enough profile data to train on.

**Track** — every application through every stage:
```
Applied → Assessment → Interview → Offer → Selected / Rejected
```

**Prepare** — role-specific learning resources and 
interview prep surfaced based on the actual job description.

---

## The Hard Technical Problem

The matching engine had a cold-start problem.

You can't meaningfully match jobs to a profile 
that doesn't have enough signal yet. Most systems 
wait for data before building logic. 

I had to define what "match" actually means structurally 
— before a single user had completed their profile — 
then build the engine backward from that definition.

That forced a product decision disguised as a technical one: 
what signals matter most in the first 60 seconds 
of a user's experience?

---

## Architecture

CareerOS is built as a full-stack cross-platform system
handling real-world job data, user workflows,
and intelligent recommendations simultaneously.

```
carrer-os/
├── lib/                    # Flutter app
│   ├── core/               # Global utilities, themes, constants
│   ├── data/               # Data layer — APIs, local storage, models
│   │   ├── repositories/   # Repository implementations
│   │   └── services/       # External services (Supabase, HTTP)
│   ├── domain/             # Business logic — entities, use cases
│   └── presentation/       # UI — screens, widgets, state management
├── backend/                # FastAPI backend
├── assets/                 # App assets
└── android/ ios/ web/      # Platform configs
```

**Mobile:** Flutter + Dart + Riverpod + Provider
Clean Architecture with strict Presentation / Domain / Data separation.

**Backend:** FastAPI (Python)
REST API with structured data handling and
an AI inference layer for matching and recommendations.

**Database:** PostgreSQL + Supabase
Structured data for jobs, users, applications, 
and the tracking pipeline. Auth built-in via Supabase.

**Local Storage:** Hive
Offline-first capabilities — the app works
even without a network connection.

**AI Layer:** LLM integration for career guidance,
skill gap analysis, resume suggestions,
and intelligent job matching.

---

## Key Features

| Feature | Description |
|---|---|
| Job Aggregation | Multi-source job feed — one place, all opportunities |
| Smart Matching | AI matches jobs to profile even with limited initial data |
| Application Tracking | Full pipeline: Applied → Assessment → Interview → Offer |
| Skill Gap Analysis | Identifies what to learn based on target job descriptions |
| AI Career Guidance | LLM-powered mentor for career questions and interview prep |
| Resume Builder | AI-generated ATS-optimized resume from your profile |
| Offline Support | Hive local storage — works without internet |

---

## Getting Started

### Prerequisites
```bash
Flutter SDK 3.x
Python 3.10+
Supabase account
```

### Clone and install
```bash
git clone https://github.com/codeharsh27/Carrer-OS.git
cd Carrer-OS

# Install Flutter dependencies
flutter pub get

# Install backend dependencies
cd backend && pip install -r requirements.txt
```

### Environment setup
```bash
# Add to your environment or .env file:
SUPABASE_URL=your_supabase_url
SUPABASE_ANON_KEY=your_supabase_anon_key
OPENROUTER_API_KEY=your_openrouter_key
```

### Firebase setup
```bash
# Add google-services.json to android/app/
# Add GoogleService-Info.plist to ios/Runner/
```

### Run
```bash
# Start backend
cd backend && uvicorn main:app --reload

# Run Flutter app
flutter run
```

---

## What I Learned

Building the product was the easy part.

CareerOS has 20+ active users who chose it over 
every other option available to them. Getting there 
taught me three things no course covers:

→ Distribution is a completely different skill from building.
  A great product with no users is just a project.

→ Observing real users before writing code is not optional.
  It is the actual work.

→ A "figure-it-out" mindset compounds fast.
  Most problems are solvable if you start before 
  you feel ready.

---

## Built By

**Harsh Mule** — Product Engineer

[harshmule.vercel.app](https://harshmule.vercel.app) ·
[code.harsh26@gmail.com](mailto:code.harsh26@gmail.com)

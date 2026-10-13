<div align="center">

# Sutr

### Everything connected. Nothing complicated.

An AI-powered platform that connects people with opportunities, simplifies complicated processes, and makes existing services easier to access.

**Discover opportunities. Understand eligibility. Follow a clear path forward.**

</div>

---

## About

Accessing scholarships, government schemes, and public services can be unnecessarily complicated. Information is scattered across different websites, eligibility requirements are difficult to interpret, documentation processes are disconnected, and users are often left to figure out the next steps themselves.

**Sutr aims to change that.**

Sutr is an AI-powered access and assistance platform designed to connect existing information sources and services through a unified experience. Rather than simply listing opportunities, it helps users understand their options, evaluate relevant eligibility criteria, identify missing requirements, and follow a personalized action plan.

The platform initially focuses on educational scholarships and student assistance, with a long-term vision of helping citizens access government benefits and other public services.

Our approach is simple: **the infrastructure already exists in many cases. The experience connecting it doesn't.**

## The Problem

People frequently struggle with:

* Discovering scholarships and benefits relevant to their circumstances.
* Understanding complicated eligibility criteria.
* Identifying the documents required for an application.
* Finding the appropriate services for obtaining missing documents.
* Navigating multiple websites and disconnected application processes.
* Tracking deadlines, pending tasks, and application requirements.
* Understanding what to do next when information is incomplete or confusing.

These challenges can prevent people from accessing opportunities and services that could benefit them.

## Our Approach

Sutr acts as an intelligent assistance layer around existing services.

Instead of replacing established systems, Sutr aims to make them easier to navigate by connecting information, requirements, and actionable steps.

The platform combines AI-assisted guidance, verified information retrieval, eligibility evaluation, and workflow management to simplify the user's journey.

## Key Features

### 1. Intelligent Opportunity Discovery

Help users discover scholarships and other opportunities relevant to their educational background and circumstances.

### 2. Eligibility Analysis

Evaluate known eligibility requirements against user-provided information and explain which conditions appear satisfied, unsatisfied, or still require verification.

### 3. AI-Generated Application Roadmaps

Generate personalized checklists that organize application requirements into clear, actionable steps.

### 4. Connected Services

Connect opportunity information, documentation requirements, relevant services, and official application portals wherever reliable information and authorized integrations are available.

### 5. Application Progress Tracking

Help users manage pending tasks, completed steps, and verified deadlines in one place.

### 6. AI-Powered Assistance

Allow users to ask questions about eligibility, documentation, application requirements, and their next steps.

### 7. Source-Aware Information

Prioritize official sources, retain source references, and clearly identify information that is incomplete or has not been verified.

> Features are being developed incrementally. Capabilities requiring external integrations will only be considered available when those integrations have been implemented and tested.

## How It Works

1. **Tell Sutr about yourself.** Provide the information needed to identify relevant opportunities.
2. **Discover opportunities.** Search available records and supported information sources.
3. **Understand eligibility.** Review relevant criteria and identify missing information.
4. **Generate your roadmap.** Receive a personalized checklist based on the available requirements.
5. **Connect to services.** Access relevant official websites and supported integrations.
6. **Track your progress.** Manage outstanding tasks and continue your application journey.

## Technology Stack

The implementation is designed around a lightweight web architecture suitable for rapid development and future expansion.

| Layer                  | Technology                                          | Purpose                                        |
| ---------------------- | --------------------------------------------------- | ---------------------------------------------- |
| Frontend               | React + Vite                                        | User interface                                 |
| Language               | TypeScript                                          | Type safety and maintainability                |
| Styling                | Tailwind CSS                                        | Responsive interface development               |
| Icons                  | Lucide React                                        | Consistent interface icons                     |
| Backend                | Node.js + Express                                   | API and application logic                      |
| AI                     | Hosted LLM API                                      | Contextual explanations and roadmap generation |
| Information retrieval  | Curated records and supported search sources        | Retrieve relevant information                  |
| Eligibility evaluation | Deterministic application logic                     | Evaluate explicit eligibility criteria         |
| Initial data storage   | Structured JSON and local storage where appropriate | Store opportunity records and MVP progress     |

The exact implementation may evolve as the project develops.

## Architecture

```text
                    ┌──────────────────────┐
                    │        User          │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   React Frontend     │
                    │                      │
                    │  Discovery           │
                    │  Eligibility         │
                    │  Application Roadmap │
                    │  AI Assistant        │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │    Express API       │
                    └──────────┬───────────┘
                               │
             ┌─────────────────┼─────────────────┐
             │                 │                 │
             ▼                 ▼                 ▼
      ┌────────────┐    ┌────────────┐    ┌────────────┐
      │ Opportunity│    │ Eligibility│    │    LLM     │
      │ Retrieval  │    │   Engine   │    │ Integration│
      └────────────┘    └────────────┘    └─────┬──────┘
                                                │
                                                ▼
                                      ┌──────────────────┐
                                      │ Roadmap Generator│
                                      └────────┬─────────┘
                                               │
                                               ▼
                                      ┌──────────────────┐
                                      │ Workflow Tracking│
                                      └──────────────────┘
```

External services are accessed through supported information sources and authorized integrations. Their availability and capabilities depend on the specific service.

## Project Structure

The following is a proposed structure for a combined frontend and backend repository.

```text
sutr/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── hooks/
│   │   ├── types/
│   │   └── App.tsx
│   ├── public/
│   └── package.json
│
├── backend/
│   ├── src/
│   │   ├── routes/
│   │   ├── controllers/
│   │   ├── services/
│   │   ├── data/
│   │   ├── types/
│   │   ├── middleware/
│   │   └── server.ts
│   └── package.json
│
├── .env.example
├── .gitignore
├── AGENTS.md
└── README.md
```

This structure is a starting point, not a requirement to reorganize an existing implementation unnecessarily.

## Getting Started

### Prerequisites

* Node.js and npm.
* Git.
* An API key for the selected LLM provider if live AI functionality is enabled.

### 1. Clone the repository

```bash
git clone <repository-url>
cd sutr
```

Replace `<repository-url>` with the actual repository URL.

### 2. Install frontend dependencies

```bash
cd frontend
npm install
```

### 3. Install backend dependencies

```bash
cd ../backend
npm install
```

### 4. Configure environment variables

Create a `.env` file in the backend directory based on `.env.example`.

Example:

```env
PORT=3000
FRONTEND_URL=http://localhost:5173

LLM_API_KEY=
LLM_MODEL=
```

Configure the variable names and model according to the provider selected by the project.

**Never commit real API keys or secrets to the repository.**

### 5. Start the backend

From the backend directory, run the development command configured in its `package.json`.

For example:

```bash
npm run dev
```

### 6. Start the frontend

Open a second terminal:

```bash
cd frontend
npm run dev
```

Open the local URL displayed by Vite.

> These instructions assume the proposed directory structure and corresponding npm scripts have been implemented.

## API Overview

The following endpoints describe the intended API surface. Their availability depends on the current implementation.

| Method | Endpoint                          | Purpose                             |
| ------ | --------------------------------- | ----------------------------------- |
| POST   | `/api/opportunities/search`       | Search relevant opportunities       |
| GET    | `/api/opportunities/:id`          | Retrieve opportunity details        |
| POST   | `/api/eligibility/check`          | Evaluate known eligibility criteria |
| POST   | `/api/roadmaps`                   | Generate a personalized roadmap     |
| GET    | `/api/roadmaps/:id`               | Retrieve a roadmap                  |
| PATCH  | `/api/roadmaps/:id/tasks/:taskId` | Update task completion              |
| POST   | `/api/assistant/chat`             | Request contextual AI assistance    |

The frontend and backend should share consistent request and response schemas.

## Responsible AI and Data Reliability

Sutr is intended to help users navigate important opportunities and services. Reliability matters more than producing a confident-sounding answer.

The project follows these principles:

* Prefer authoritative, traceable information sources.
* Distinguish verified facts from estimates and unknown information.
* Use deterministic logic for explicit eligibility conditions wherever possible.
* Do not allow an LLM to invent scholarships, deadlines, documents, or official URLs.
* Clearly communicate when information is incomplete or requires verification.
* Require appropriate user consent for personal information and external actions.
* Keep users in control of official submissions and consequential decisions.
* Protect API keys and avoid unnecessary collection of sensitive personal information.

An eligibility assessment is guidance based on available information, not a guarantee of acceptance or entitlement.

## Roadmap

### MVP

* [ ] Student profile setup.
* [ ] Scholarship discovery.
* [ ] Eligibility analysis.
* [ ] AI-generated application roadmap.
* [ ] Interactive task tracking.
* [ ] Official source references.
* [ ] Contextual AI assistance.

### Future Development

* [ ] Broader government-benefit discovery.
* [ ] Additional citizen profiles, including farmers.
* [ ] Multilingual and voice-assisted interactions.
* [ ] Authorized integrations with relevant public services.
* [ ] Improved application-status tracking where supported.
* [ ] Notifications and deadline monitoring.
* [ ] Persistent user accounts and cross-device synchronization.

## Contributing

Contributions are welcome.

Before submitting changes:

1. Review `AGENTS.md` for project-specific development instructions.
2. Follow the existing architecture and coding conventions.
3. Keep API contracts consistent between the frontend and backend.
4. Validate external information and preserve source references.
5. Test the affected workflows.
6. Never commit API keys or personal information.

## Project Status

Sutr is an early-stage project being developed as an MVP. The initial focus is scholarship discovery and guided application assistance.

Some features and integrations may remain incomplete during early development.

## License

A license has not yet been selected. Add an appropriate `LICENSE` file before distributing the project under an open-source license.

---

<div align="center">

**Sutr — Everything connected. Nothing complicated.**

</div>

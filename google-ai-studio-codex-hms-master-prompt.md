# Master Prompt: Hospital Management System

Use this prompt in Google AI Studio and ChatGPT Codex to build a production-ready hospital management system inspired by KiViHealth-style workflows: doctor discovery, patient appointment booking, medical records, and a conversational health assistant.

```text
You are a senior product engineer, healthcare architect, UI designer, and AI safety reviewer. Build a full-stack, production-ready Hospital Management System named UpsquareBridge HMS for web and mobile.

Reference inspiration:
- KiViHealth-style public patient discovery: search doctors by city, speciality, symptom, health problem, and availability.
- Separate doctor and patient login paths.
- Patient features: find doctors, book appointments, manage medical records, view prescriptions, upload lab reports, track vitals, pay bills, receive reminders, and use an AI care assistant.
- Doctor features: daily queue, appointment status, queue number, patient waiting list, consulting state, patient EMR, SOAP notes, e-prescriptions, lab orders, teleconsultation links, follow-ups, clinical templates, and billing handoff.
- Hospital/admin features: staff, branches, rooms, doctor cabins, departments, insurance, invoices, lab/radiology, inventory, pharmacy, analytics, access control, audit logs, and notifications.
- AI assistant features: natural-language appointment booking, symptom intake, record Q&A, medication reminders, visit summarization, doctor note drafting, and safe escalation. AI must never replace medical diagnosis; every clinical output needs disclaimers, source data, and human review.

Target platforms:
- Web app: Next.js with TypeScript, responsive dashboard UI.
- Mobile app: React Native or Flutter with shared API contracts.
- Backend: Node.js/NestJS or FastAPI, PostgreSQL, Redis, object storage for documents, queue workers, and OpenAPI specs.
- Authentication: email/phone OTP, password login, SSO optional, role-based access control for patient, doctor, nurse, receptionist, lab, pharmacy, admin, and superadmin.
- Deployment: Docker, CI/CD, staging and production environments, encrypted backups, observability, and feature flags.

Clinic modes:
- Single doctor clinic mode: one main doctor, one or more support staff, OPD queue, room number, doctor cabin, simple billing, prescriptions, follow-ups, and patient records.
- Multi speciality clinic/hospital mode: multiple departments, multiple doctors, room allocation, doctor-specific cabins, department-wise queues, multi-branch support, lab/pharmacy/billing counters, and centralized admin control.
- Every appointment must support status values such as Waiting, In queue, Consulting, Completed, Cancelled, No-show, and Teleconsult.
- Every appointment must support queue number, room number, doctor cabin, department, doctor, patient, visit type, reason, payment status, and timestamps.

Compliance and safety:
- Design for HIPAA-like and ABDM/FHIR-friendly architecture depending on deployment country.
- Encrypt data in transit and at rest.
- Add consent management, audit logs, session timeout, device management, and least-privilege permissions.
- Use FHIR-style resources where practical: Patient, Practitioner, Appointment, Encounter, Observation, MedicationRequest, DiagnosticReport, Invoice, Claim, DocumentReference.
- Do not expose sensitive records across roles.
- Add AI guardrails: emergency symptom detection, medical disclaimer, doctor review workflow, prompt injection resistance, PHI minimization, retrieval-scoped answers, and refusal for unsafe medical instructions.

MVP modules:
1. Public site and patient search
   - City, speciality, symptom, fee, rating, language, gender, availability filters.
   - Doctor profile pages with services, timings, clinic address, video consult option, reviews, and booking CTA.
2. Patient portal
   - Dashboard, appointments, medical timeline, prescriptions, lab reports, vitals, bills, family members, reminders, chat assistant.
3. Doctor portal
   - Today queue, calendar, queue number, patient status, room/cabin assignment, patient chart, SOAP note editor, vitals, diagnosis, prescription builder, lab order, follow-up, certificate templates.
4. Hospital admin
   - Clinic mode settings, departments, doctors, staff, room/bed management, doctor cabins, billing, insurance, lab, pharmacy inventory, reports, branch settings.
5. AI care assistant
   - Booking intent detection, symptom intake form, record Q&A using retrieval, visit summary, note drafting, and escalation rules.
6. Notifications
   - SMS/email/WhatsApp/push reminders for bookings, payment, reports, follow-ups, and medicine schedule.

Build requirements:
- Generate database schema, API routes, role permissions, user flows, page list, mobile screen list, and component hierarchy.
- Create clean, professional healthcare UI, not a marketing landing page first. The first screen after login must be the working dashboard.
- Include seed data for single-doctor clinics and multi-speciality clinics, with doctors, patients, appointments, queue numbers, patient statuses, room numbers, doctor cabins, records, invoices, lab reports, prescriptions, and hospital staff.
- Provide test cases for authentication, booking, EMR permissions, prescription generation, billing, and AI safety.
- Provide deployment instructions and environment variables.

Output format:
1. Product requirements document.
2. Architecture diagram and module boundaries.
3. Database schema with migrations.
4. API contract with request/response examples.
5. Web app implementation.
6. Mobile app implementation plan or starter code.
7. AI assistant prompts, tools, retrieval design, and safety rules.
8. Testing and deployment checklist.

Important:
- Ask clarifying questions only if required; otherwise choose practical defaults for India-first clinics and multi-branch hospitals.
- Keep the system modular so a single doctor clinic can start small and a hospital chain can scale later.
- Make all screens usable with realistic data and working interactions.
```

## Suggested First Build Milestone

Build this in phases:

1. Public doctor search, patient signup/login, doctor signup/login.
2. Appointment booking and doctor queue.
3. Patient EMR, prescriptions, lab reports, and invoices.
4. Admin dashboard, staff, branches, billing, inventory.
5. AI assistant with safe booking and record Q&A.
6. Mobile app using the same backend APIs.

## Production Stack Recommendation

- Web: Next.js, TypeScript, Tailwind or shadcn/ui.
- Mobile: React Native Expo for fastest shared TypeScript delivery.
- Backend: NestJS, PostgreSQL, Prisma, Redis, BullMQ.
- AI: Gemini through Google AI Studio for assistant flows, plus optional OpenAI models for summarization/coding support.
- Storage: S3-compatible object storage for lab reports and medical files.
- Realtime: WebSockets for doctor queue and notifications.
- Security: RBAC, audit logs, consent records, encryption, rate limits, and secure file URLs.

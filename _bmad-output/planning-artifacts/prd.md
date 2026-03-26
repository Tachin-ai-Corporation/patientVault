---
stepsCompleted:
  - step-01-init
  - step-02-discovery
  - step-02b-vision
  - step-02c-executive-summary
  - step-03-success
  - step-04-journeys
  - step-05-domain
  - step-06-innovation
  - step-07-project-type
  - step-08-scoping
  - step-09-functional
  - step-10-nonfunctional
  - step-11-polish
  - step-12-complete
inputDocuments: []
workflowType: 'prd'
documentCounts:
  briefs: 0
  research: 0
  brainstorming: 0
  projectDocs: 0
classification:
  projectType: web_app
  domain: healthcare_crm
  complexity: medium
  projectContext: greenfield
---

# Product Requirements Document - patientVault

**Author:** Neil
**Date:** 2026-03-25

## Executive Summary

patientVault is a lightweight, web-based patient CRM designed for clinic front desk staff. It demonstrates that patient management software can be built quickly and used intuitively — without the bloat, complexity, or visual clutter that plagues existing clinic tools. The application targets the core front desk workflow: creating and finding patients, managing demographics and contact information, attaching documents, and handling insurance with dependent relationships. Built as a responsive web app for desktop and mobile browsers, patientVault serves as a developer-facing demo proving that a clean, functional patient CRM is both fast to build and fast to use.

### What Makes This Special

Existing clinic CRMs treat patient management as inherently complex. patientVault rejects that premise. Front desk patient management is fundamentally simple — the tools just make it feel hard. By stripping the interface to exactly what front desk staff need and nothing more, every interaction becomes intuitive and fast. The demo audience (developers) sees both a polished end-user experience and evidence that building one doesn't require months of effort. Speed and simplicity at every layer — from code to click.

### Project Classification

- **Project Type:** Web Application (responsive — desktop & mobile)
- **Domain:** Healthcare CRM (patient management, not clinical/EHR)
- **Complexity:** Medium (PII handling, insurance data models, no HIPAA/FDA regulatory burden)
- **Project Context:** Greenfield

## Success Criteria

### User Success

- Patient creation feels immediate — smart defaults and minimal required fields get a new patient into the system in seconds
- Finding a patient is instant — type-ahead search, no hunting through menus
- Every interaction provides immediate visual feedback — no waiting, no uncertainty
- Navigating between patient record sections (demographics, documents, insurance) is seamless

### Business Success

- Developer audience reaction: "That was easy — this proves what the platform can do"
- Demo is self-evident — minimal explanation needed, the UI speaks for itself
- Showcases full patient lifecycle (create, find, update, document, insure) in a single fluid walkthrough
- Demonstrates responsive design as a first-class capability, not an afterthought

### Technical Success

- UI responds instantly to every user action — no perceptible lag
- Mobile-first responsive design that demos well on a phone screen
- All 7 core features functional end-to-end
- Clean, maintainable codebase that reinforces the "easy to build" message

### Measurable Outcomes

- Full patient creation in under 30 seconds with smart defaults
- Patient search returns results as the user types
- Zero dead-end screens — every view has a clear next action
- Mobile and desktop experiences are equally polished

## User Journeys

### Journey 1: Maria's Monday Morning Rush — New Patient Creation

**Maria** is a front desk coordinator at Riverside Family Clinic. It's Monday at 8:15 AM, the phone is ringing, and a new patient just walked in without an appointment.

**Opening Scene:** Maria greets the patient while the phone rings. She needs to get this person into the system fast — no time to navigate a maze of forms.

**Rising Action:** Maria opens patientVault and types the patient's last name into the search bar. No results — this is a new patient. A clear "Create New Patient" prompt appears right in the search results. She clicks it and lands on a clean, minimal form — just the essentials: name, date of birth, phone number.

**Climax:** Maria enters the basics and hits save. The patient record is created instantly. She's already looking at the new patient's record, ready to add insurance details. The whole interaction took 15 seconds.

**Resolution:** The patient is in the system. Maria picks up the ringing phone, pulls up the next patient by typing two letters of their name, and her morning keeps moving. No friction, no wasted clicks.

**Requirements revealed:** Type-ahead search, search-to-create flow, minimal required fields, instant save, immediate navigation to full patient record.

---

### Journey 2: Maria Handles a Returning Patient — Record Updates

**Opening Scene:** A returning patient approaches the desk and mentions they have a new phone number and just switched insurance providers.

**Rising Action:** Maria types the first few letters of the patient's name. The search results appear as she types — she spots the right patient and clicks into their record. The demographics section is right there.

**Climax:** Maria clicks the phone number field, updates it inline, and it saves immediately. She navigates to the insurance tab, adds the new policy details, and links the patient's two children as dependents on the policy — all without leaving the patient's record.

**Resolution:** Three updates — phone, insurance, dependents — done in under a minute. The patient barely finished sitting down in the waiting area. Maria didn't have to navigate away from the patient record once.

**Requirements revealed:** Inline editing with auto-save, tabbed/sectioned patient record, insurance management within patient context, dependent linking flow.

---

### Journey 3: Maria Adds Documentation — Document Upload

**Opening Scene:** A patient hands Maria a printed referral letter and their insurance card. Maria needs to attach both to the patient's record.

**Rising Action:** Maria searches for and opens the patient's record, then navigates to the documents section. She sees a clear upload area.

**Climax:** Maria uploads the referral letter and insurance card. Each document appears immediately in the patient's document list with a timestamp. Done.

**Resolution:** The documents are attached and visible. Next time anyone pulls up this patient, the referral and insurance card are right there. No filing cabinet, no lost papers.

**Requirements revealed:** Document upload within patient context, document list with metadata, support for common file types (PDF, images).

---

### Journey 4: Maria's Search Comes Up Empty — Error Recovery to Creation

**Opening Scene:** A caller says they're a patient but Maria can't find them in the system. Spelling variations, no match.

**Rising Action:** Maria tries different search terms — partial name, date of birth. The search returns no results each time but never feels like a dead end.

**Climax:** The "No results found — Create New Patient?" prompt appears naturally. Maria clicks it, and the search terms she already entered pre-populate the creation form. She confirms the details with the caller and saves.

**Resolution:** What could have been an awkward "I can't find you" moment turned into a smooth "Let me get you set up right now." The caller never knew there was a hiccup.

**Requirements revealed:** Graceful empty states, search-to-create with data carry-over, pre-populated forms from search context.

---

### Journey Requirements Summary

| Capability | Journeys | Priority |
|---|---|---|
| Type-ahead patient search | 1, 2, 4 | Critical |
| Search-to-create flow with data carry-over | 1, 4 | Critical |
| Minimal patient creation form | 1, 4 | Critical |
| Inline field editing with instant save | 2 | Critical |
| Sectioned patient record (demographics, insurance, documents) | 2, 3 | Critical |
| Insurance policy management | 2 | Critical |
| Dependent linking to insurance | 2 | Critical |
| Document upload with metadata | 3 | Critical |
| Graceful empty states | 4 | Critical |
| Pre-populated forms from search context | 4 | High |

## Domain-Specific Requirements

### PII Handling

- Patient records contain PII (names, DOB, phone numbers, addresses, insurance details)
- Demo scope: no encryption or audit trail required, but data model should support future security layers
- No HIPAA compliance required — CRM, not clinical/EHR

### Insurance Data Model

- Realistic enough to be believable: policy number, group number, member ID, provider name
- Dependent relationships: link family members to a single policy
- No real-time insurance verification or eligibility checks

### Document Storage

- Support common file types (PDF, images — JPG, PNG)
- Basic metadata: filename, upload date, file type
- No document preview, OCR, or categorization in MVP

### Domain Constraints

- Single-user demo — no role-based access or multi-tenancy
- No integration with external systems (EHR, billing, scheduling)
- Data model should feel realistic to clinic staff but doesn't need to match industry standards (HL7, FHIR, etc.)

## Web Application Requirements

### Architecture

- **Application Type:** Single-Page Application (SPA)
- **Rendering:** Client-side only — no SSR/SSG needed
- **Routing:** Client-side routing with clean URL structure for patient records
- **State Management:** Client-side state for patient data, search results, and form state
- **Data Layer:** API-driven with clean separation between UI and data
- **Bundling:** Code splitting for fast initial load

### Browser Support

- Chrome, Firefox, Safari, Edge (latest versions only)
- No IE11 or legacy browser support

### Responsive Design

- Mobile-first responsive layout — must demo well on a phone
- Desktop layout optimized for front desk workflow (wide screens, potentially side-by-side panels)
- Breakpoints: mobile (< 768px), desktop (>= 768px)
- Touch-friendly tap targets on mobile

### Interaction Patterns

- Standard request-response — no WebSocket or real-time requirements
- Optimistic UI updates — save feedback without waiting for server confirmation
- Client-side search debouncing for instant-feeling results
- No SEO requirements — no meta tags, sitemap, or structured data

## Project Scoping & Phased Development

### MVP Strategy

**Approach:** Experience MVP — demonstrate that a patient CRM can be built fast and feel great to use. The goal is developer audience conviction, not end-user adoption.

**Resources:** Solo developer, ~5 day build timeline (demo-ready early April 2026).

**MVP Boundary:** Single-user, no authentication, no persistent backend required for demo (mock/local data acceptable). Every feature must feel snappy and polished — breadth over depth, but nothing half-baked.

### MVP Feature Set (Phase 1)

**Core User Journeys Supported:** All 4 Maria journeys (new patient, returning patient updates, document upload, search-to-create recovery).

**Must-Have Capabilities:**

1. **Create Patient** — minimal required fields, smart defaults, instant feedback
2. **Find Patient** — type-ahead search across patient records
3. **Update Patient Record** — inline editing, immediate save
4. **Update Demographics & Contact Info** — phone, address, core demographic fields
5. **Add Document** — attach a document to an existing patient record
6. **Add Insurance** — associate insurance policy with a patient
7. **Add Dependents to Insurance** — link dependents to an existing insurance policy

### Phase 2: Growth (Post-MVP)

- Appointment scheduling integration
- Bulk patient import
- Document preview and categorization
- Insurance verification workflow
- Audit trail / activity log

### Phase 3: Expansion (Future)

- Multi-clinic support with role-based access
- Patient self-service portal
- Integration APIs for EHR systems
- Analytics dashboard for clinic operations

### Risk Mitigation

**Technical:** Insurance dependent relationships are the most complex data model. Mitigation: build patient CRUD and search first, layer insurance last so the core demo works even if dependents need simplification.

**Timeline:** 7 features in ~5 days solo is aggressive. Mitigation: keep UI patterns consistent (reuse form components, search patterns), use mock/local data to eliminate backend complexity, build features in journey order.

**Demo:** The demo must flow smoothly end-to-end. Mitigation: build in journey order (search -> create -> update -> documents -> insurance -> dependents) so each feature builds on the last and the demo narrative is always shippable.

## Functional Requirements

### Patient Management

- FR1: Front desk staff can create a new patient record with minimal required fields (name, DOB, phone)
- FR2: Front desk staff can view a patient's complete record after creation
- FR3: Front desk staff can update any field on a patient record via inline editing
- FR4: Front desk staff can archive a patient record

### Patient Search

- FR5: Front desk staff can search for patients by typing into a global search field
- FR6: Front desk staff can see search results update as they type (type-ahead)
- FR7: Front desk staff can search across multiple patient fields (name, DOB, phone)
- FR8: Front desk staff can navigate directly to a patient record from search results
- FR9: Front desk staff can initiate patient creation from an empty search result

### Demographics & Contact Information

- FR10: Front desk staff can view a patient's demographic information (name, DOB, gender, address)
- FR11: Front desk staff can edit a patient's demographic fields with immediate save
- FR12: Front desk staff can view a patient's contact information (phone, email, address)
- FR13: Front desk staff can add, edit, or remove phone numbers on a patient record
- FR14: Front desk staff can add, edit, or remove addresses on a patient record

### Document Management

- FR15: Front desk staff can upload one or more documents to a patient record
- FR16: Front desk staff can view a list of documents attached to a patient record
- FR17: Front desk staff can see document metadata (filename, upload date, file type)
- FR18: Front desk staff can upload PDF and image files (JPG, PNG)

### Insurance Management

- FR19: Front desk staff can add an insurance policy to a patient record
- FR20: Front desk staff can enter insurance details (provider, policy number, group number, member ID)
- FR21: Front desk staff can view insurance policies associated with a patient
- FR22: Front desk staff can edit existing insurance policy details
- FR23: Front desk staff can remove an insurance policy from a patient record

### Insurance Dependents

- FR24: Front desk staff can add dependents to an existing insurance policy
- FR25: Front desk staff can specify dependent details (name, relationship, DOB)
- FR26: Front desk staff can view dependents linked to an insurance policy
- FR27: Front desk staff can edit dependent information
- FR28: Front desk staff can remove a dependent from an insurance policy

### Navigation & UI

- FR29: Front desk staff can navigate between patient record sections (demographics, documents, insurance) without leaving the patient context
- FR30: Front desk staff can see immediate visual feedback on all save/update actions
- FR31: Front desk staff can access all features from both desktop and mobile viewports
- FR32: Front desk staff can see a clear next action from any screen (no dead ends)
- FR33: Front desk staff can have search terms pre-populate the patient creation form when creating from empty search results

## Non-Functional Requirements

### Performance

- UI interactions (clicks, field edits, tab switches) respond in under 100ms
- Search results appear within 200ms of keystroke
- Patient record save/update reflects in the UI within 100ms
- Page transitions complete in under 100ms — no loading spinners for navigation
- Initial app load completes in under 2 seconds on a modern connection
- Document upload displays progress feedback within 200ms of upload initiation

### Accessibility

- Semantic HTML structure throughout
- All interactive elements reachable via keyboard
- Form fields have associated labels
- No formal WCAG compliance target — basic usability only

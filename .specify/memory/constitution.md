<!--
Sync Impact Report
- Version change: 0.0.0 -> 1.0.0
- Modified principles: new constitution initializes five project principles
- Added sections: Additional Constraints; Development Workflow
- Removed sections: none
- Deferred items: TODO(RATIFICATION_DATE): confirm the original project adoption date or replace with the approved ratification date.
-->

# ContosoDashboard Constitution

## Core Principles

### I. Training-First Scope and Safety
This project exists for learning and demonstration. All features, examples, and security controls MUST be designed for a safe training environment and MUST NOT be treated as production-ready guidance. The repository MUST clearly label mock authentication, mock authorization, and offline-only patterns as educational examples, and any implementation choices that are intentionally insecure or simplified for training MUST be accompanied by explanatory documentation.

The rationale for this principle is that the project is explicitly non-production and the code is used to teach secure design patterns, architecture thinking, and common pitfalls. A clear training boundary prevents accidental use in operational settings and preserves the educational value of the examples.

### II. Offline-First Architecture with Cloud Migration Path
The application MUST favor local-first behavior and infrastructure abstractions that can be swapped for cloud services without rewriting business logic. Local databases, file handling, and identity flows are acceptable for training so long as they are isolated behind interfaces or clearly documented migration points. New code MUST preserve the separation between domain logic and infrastructure concerns.

This principle exists because the project is designed for offline learning and limited environments. By keeping dependencies abstracted, the code remains teachable while demonstrating how a real system can migrate to Azure services or enterprise identity providers without changing core workflows.

### III. Secure-by-Default Design
The project MUST enforce authentication and authorization checks at both the page and service layers. Any user-specific or project-specific data access MUST validate identity, role, and membership before returning or mutating data. The codebase MUST avoid insecure direct object reference patterns, unvalidated access paths, and silent privilege escalation during feature work.

The rationale is that the application intentionally demonstrates security controls for training, and those controls are part of the educational contract. Security practices are not optional add-ons; they are the baseline expectation for each feature and bug fix.

### IV. Test-First Evidence and Regression Safety
Changes to behavior MUST be backed by evidence before they are considered complete. New or modified feature logic MUST be validated with a focused test or repeatable verification step, and bug fixes MUST demonstrate the failing condition before the fix and the corrected condition after the fix. Documentation and examples MUST be updated when behavior changes materially.

This principle is required because the repository is used as a training environment for Spec-Driven Development. Evidence-based delivery ensures that features remain understandable, reliable, and consistent with the project’s instructional purpose.

### V. Simplicity, Clarity, and Maintainability
The codebase MUST prefer clear, understandable, and minimally complex solutions over clever or over-engineered implementations. New abstractions MUST have a direct purpose, and features that increase complexity without a clear business or learning benefit are not allowed without explicit justification.

This principle is important because the repository is designed for teaching. Clear and maintainable code is more valuable than broad generalization, and the project’s instructional goal requires a readable, explainable architecture.

## Additional Constraints

- The repository MUST remain suitable for offline training and local development without requiring external cloud services.
- Mock authentication, role-based access control, and sample data are instructional examples and MUST be documented as such.
- Any file-upload or storage feature MUST use unique identifiers and safe path handling to prevent collisions and orphaned data.
- Security-sensitive features MUST be reviewed for user isolation, authorization boundaries, and access control assumptions before merge.
- Production claims, deployment assumptions, and external service dependencies MUST be treated as explicit non-goals unless clearly documented as future migration work.

## Development Workflow

- Feature and bug-fix work MUST align with the project’s educational scope and not introduce production-only assumptions or unsupported infrastructure.
- Changes to user access, security, task logic, or project ownership MUST be reviewed for impact on role permissions and data isolation.
- All significant changes MUST preserve the repository’s local-first and training-safe behavior unless the work explicitly updates the project roadmap or migration guidance.
- Documentation, comments, and examples MUST be kept in sync with code changes that affect user flows, architecture, or security expectations.
- The project maintainers MUST verify that the implementation remains understandable for learners and does not obscure core concepts behind unnecessary abstraction.

## Governance

This constitution governs the project’s design expectations and delivery standards. It supersedes informal conventions when a conflict arises, and it requires explicit updates to the project documentation when governance, architecture, or security rules change materially.

Amendments to this constitution MUST be recorded in the project memory and include a clear version bump, rationale for the change, and any follow-up documentation or migration notes needed for compliance. Changes that affect security, access control, or training boundaries require a documented review before they are treated as accepted practice.

Compliance review is expected for changes that alter principle intent, architecture boundaries, or security posture. Any project member may raise a governance concern when behavior does not match the constitution, and the issue MUST be resolved before the change is considered complete.

**Version**: 1.0.0 | **Ratified**: TODO(RATIFICATION_DATE): confirm the original project adoption date or replace with the approved ratification date | **Last Amended**: 2026-09-15

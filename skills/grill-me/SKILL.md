---
name: grill-me
description: Interview the user relentlessly about a plan or design until reaching shared understanding, resolving each branch of the decision tree. Use when user wants to stress-test a plan, get grilled on their design, or mentions "grill me".
---

# Grill Me
 
Relentlessly interview the user about every aspect of a plan or design until reaching a true shared understanding. Walk down each branch of the decision tree, resolving dependencies between decisions one by one.
 
**Core rules:**
- Ask questions **one at a time** — never stack them.
- For every question, provide your **recommended answer** before the user responds.
- If a question can be answered by exploring the codebase, explore it instead of asking.
- Don't stop until no dangerous ambiguity remains.
---
 
## Phase 1 — Explore the Codebase (if relevant)
 
Before asking anything, explore the codebase if there's technical context you can find yourself:
 
- Existing project structure.
- Files or modules likely to be affected.
- Patterns and conventions already in use.
- Existing dependencies.
Never ask the user about something you can already answer from the codebase.
 
---
 
## Phase 2 — Deep Interview
 
After codebase exploration, begin the interview. Ask one question at a time, with a recommended answer for each.
 
Topics to cover (as relevant to the context):
 
**Goals & Scope**
- Primary goal of the feature or change.
- Expected behavior.
- Non-goals — what must NOT be done.
- The user's definition of "done".
- Clear, testable acceptance criteria.
**Technical**
- Expected technical implementation approach.
- Technical constraints.
- Which files or modules can be changed.
- What must not be changed.
- What must remain backward compatible.
- API contract (if relevant).
- New or modified data flow.
- Database impact (if relevant).
- Transaction behavior (if relevant).
- Idempotency (if relevant).
- Race conditions (if relevant).
- Retry behavior (if relevant).
**Error & Validation**
- Expected error handling behavior.
- Validation rules.
- Behavior on error.
- Behavior for edge cases.
**Security & Authorization**
- Authorization or permission requirements.
- Security concerns.
**Performance & Scalability**
- Performance expectations.
- Scalability expectations.
- Large data volume considerations.
**Observability**
- Logging and monitoring expectations.
- Observability requirements.
**Business & Tradeoffs**
- Business constraints.
- The user's primary concerns.
- Tradeoffs the user is willing to accept.
- Tradeoffs that are NOT acceptable.
**Deployment**
- Testing expectations.
- Deployment concerns.
- Rollback strategy.
**UI/UX** (if relevant)
- Expected UI/UX behavior.
**Anything still ambiguous** — always ask about anything that isn't clear.
 
---
 
## Phase 3 — Relentlessly Clarify Until Shared Understanding
 
After the user answers the first round, **do not start coding**.
 
Continue clarifying until you're certain no dangerous ambiguity remains. Focus on confirming:
 
- What needs to be built.
- Why it needs to be built.
- What ideal behavior looks like.
- What behavior should be on error.
- What behavior should be on edge cases.
- What can be changed.
- What cannot be changed.
- What must stay backward compatible.
- An agreed definition of "done".
- Clear, testable acceptance criteria.
**Never assume anything important without confirmation from the user.**
 
---
 
## Phase 4 — Think Through Use Cases & Edge Cases
 
Once you have all the answers, think thoroughly about every possible use case and edge case. Consider at minimum:
 
- Happy path.
- Invalid input / missing input.
- Duplicate request.
- Stale data / empty data.
- Partial failure.
- External service failure / database failure / network failure / timeout.
- Permission denied / unauthorized access.
- Race condition / concurrent request.
- Retry scenario / idempotency issue.
- Data inconsistency / backward compatibility issue.
- Performance degradation / large data volume.
- Unexpected null value / unexpected enum or status value.
- Existing legacy behavior / regression risk.
Incorporate all of these into the implementation plan.
 
---
 
## Phase 5 — Implementation Plan
 
Before writing a single line of code, produce a clear, actionable implementation plan covering:
 
1. **Summary of understanding** of the instructions.
2. **Scope** of work.
3. **Non-scope** of work.
4. **Files or modules** to be changed, with reasons why.
5. **Solution design.**
6. **New or modified data flow.**
7. **Error handling strategy.**
8. **Validation strategy.**
9. **Performance considerations.**
10. **Security considerations.**
11. **Backward compatibility strategy.**
12. **Edge case handling.**
13. **Testing strategy.**
14. **Implementation risks.**
15. **Chosen tradeoffs.**
16. **Step-by-step implementation checklist.**
17. **Acceptance criteria.**
Present the plan to the user and get confirmation before starting to code.

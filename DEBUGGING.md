# DEBUGGING.md
## Claude Code Debugging Operating Procedure

This document defines the required workflow for debugging issues using Claude Code.
Its purpose is to:
- Prevent runaway agent sessions
- Minimize token and context waste
- Force clean decision points
- Separate diagnosis from implementation

---

## Core Rule (Non-Negotiable)

Claude Code must never debug “until it works.”
It must debug until the next decision boundary, then stop.

---

## 0. Debug Brief (REQUIRED INPUT)

Every debugging session MUST start with this block filled out:

Debug Brief
-----------
Symptom (exact error message):
Where it occurs (step in flow):
Repro steps (1–5):
Frequency (always / intermittent):
Last known good (date or commit):
Environment (prod / staging / local):
Evidence (failing endpoint, status code, response body, console error):

---

## 1. Session Types (DO NOT MIX)

Each Claude session must be exactly one of the following.

### Session A — Diagnosis
Goal:
- Identify what class of failure this is

Allowed:
- Reading logs
- Checking health endpoints
- Asking for evidence
- Narrowing to 2–3 root causes

Forbidden:
- Writing code
- Deploying
- “Let me fix this real quick”

Hard stop condition:
- Failure classified and fix options identified

---

### Session B — Architecture Decision
Goal:
- Choose ONE fix path

Output required:
Chosen Fix:
Why:
Alternatives Rejected:
Risks:

Hard stop condition:
- Decision made

---

### Session C — Implementation
Goal:
- Implement the chosen fix only

Rules:
- One fix
- One deploy
- No verification

Hard stop condition:
- Code pushed and deployment triggered

---

### Session D — Verification
Goal:
- Confirm behavior matches expectations

If it fails:
- Capture evidence
- Produce ONE next hypothesis
- Stop

---

## 2. Mandatory Session Boundaries

Start a new Claude session when:
- A deploy occurs
- A root cause is identified
- A fix path is chosen
- A fix is implemented
- You say “wait, that’s weird”

These are decision boundaries.

---

## 3. Anti-Patterns (DO NOT DO THIS)

Do NOT:
- Deploy multiple times in one session
- Re-edit the same file repeatedly
- Chase new hypotheses without closing old ones
- Mix infra, backend, and frontend debugging
- Let Claude act as a CI system

---

## 4. Context Compression Rule

Before ending any session, ask Claude to summarize:
- Confirmed facts
- Root cause (if known)
- What was changed
- Remaining unknowns
- Next action

Paste this into the next session.

---

## 5. Deployment Reality Checks

Before assuming a bug:
- Confirm deployed branch
- Confirm auto-deploy is enabled
- Confirm replica count
- Confirm storage persistence model

---

## 6. Infrastructure Heuristics

- In-memory storage + redeploy = data loss
- /tmp + multiple instances = intermittent 404s
- Long synchronous requests = timeouts
- Background work must be async
- Stripe redirects amplify session fragility

---

## 7. Golden Rule

Short sessions + clean boundaries beat long heroic debugging.

---

End of file.

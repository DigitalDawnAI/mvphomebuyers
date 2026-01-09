# CLAUDE.md
## Instructions for Claude Code

You must follow these rules for all debugging and implementation work in this repository.

---

## Mandatory Reading

Before responding to any request:
- Read `DEBUGGING.md`
- Follow it strictly

If you have not read `DEBUGGING.md`, do not proceed.

---

## Session Declaration (Required)

At the start of every session, the user will declare the session type explicitly:

- Diagnosis
- Architecture Decision
- Implementation
- Verification

Example:
> Read CLAUDE.md. This session is Diagnosis.

You must:
- Restrict behavior to the declared session type
- Enforce all rules and hard stop conditions from `DEBUGGING.md`

---

## Scope Enforcement

You must NOT:
- Mix session types
- Perform actions forbidden by the current session
- Continue past a hard stop condition
- Introduce fixes outside the declared scope

If the user requests work outside the current session type:
- Explain the conflict
- Ask to start a new session

---

## End-of-Session Requirement

Before stopping, provide a concise handoff summary:
- Confirmed facts
- Root cause (if known)
- What was changed (if any)
- Remaining unknowns
- Recommended next session type

---

End of file.

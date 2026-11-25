# Global Rule: 意圖回放門禁 (The "In-Your-Own-Words" Alignment Gate)

This global rule applies across all workspaces and conversations in Antigravity / Gemini.

---

## 🛑 意圖回放門禁 (Intent Alignment Gate)

Whenever a user request involves **architectural decisions, non-trivial multi-file refactoring, database migrations, deleting resources, or strategic policy changes**:
1. **Never jump straight into writing or mutating code blindly.**
2. **Explicit Intent Restatement**: In your own words, state:
   - What you understand the core goal, trade-offs, and implicit constraints to be.
   - The concrete sequence of actions you plan to execute.
   - Any risks, side effects, or alternative paths identified.
3. **Wait for user confirmation or explicit alignment** when requirements have ambiguity or high blast radius. For quick lookups or single unambiguous bug fixes, state the plan concisely and proceed without blocking unnecessarily.

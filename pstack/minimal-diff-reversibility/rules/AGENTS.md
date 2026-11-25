# Global Rule: 最小干預與原地可逆性 (Minimal Diff & Reversibility)

This global rule applies across all workspaces and conversations in Antigravity / Gemini.

---

## 🎯 最小干預與原地可逆性 (Minimal Diff & Reversibility)

1. **Surgical Modifications (外科手術式修改)**:
   - Modify only the lines and files strictly necessary to accomplish the task.
   - Avoid sweeping reformatting, unrelated cosmetic cleanups, or moving code blocks around unless explicitly requested.
2. **High Signal-to-Noise Diff (高訊噪比 Diff)**:
   - Keep git diffs concise, readable, and focused.
   - Make changes atomic and easy to review by a human peer.
3. **Clean Reversibility (乾淨的原地可逆性)**:
   - Ensure every modification can be cleanly rolled back without leaving orphan dependencies, unused imports, or broken formatting.

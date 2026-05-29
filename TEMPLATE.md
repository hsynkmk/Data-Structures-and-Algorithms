# Topic Template & Contributor Guide

Every topic file in this repo follows the **same shape**. That consistency is what turns a
pile of notes into a *course*: once you've read two files, you know exactly where to look for
the intuition, the code, or the practice in every other file.

Copy the skeleton below when adding a new topic. Keep the section order and the emoji headers
(they double as visual anchors when skimming).

---

## The Sections (in order)

1. **`# Title: <one-line big idea>`** — the title states what it *is*; the subtitle states
   why you'd care in plain words.
2. **`## 🧠 Intuition`** — explain it like a story or analogy. **No code yet.** If a smart
   12-year-old wouldn't follow it, simplify.
3. **`## 📐 How It Works`** — the mechanism, step by step. Include a **Mermaid diagram** or a
   hand-traced example on a small input.
4. **`## 🧾 Pseudocode`** — language-agnostic. This is the part you should be able to
   reproduce from memory.
5. **`## 💻 C# Implementation`** — complete, idiomatic, runnable-looking C#. Prefer clarity
   over cleverness; add brief comments only where the *why* isn't obvious.
6. **`## ⏱️ Complexity`** — a time/space table **plus one or two sentences of reasoning**.
   Numbers without the "why" don't teach.
7. **`## ⚖️ When to Use It`** — trade-offs versus the alternatives. When is this the *wrong*
   tool?
8. **`## 🚫 Common Mistakes`** — `❌` wrong vs `✅` right snippets. Real bugs people hit.
9. **`## 🌍 Real-World Applications`** — where this actually shows up in production systems.
10. **`## 🎯 Practice (with full solutions)`** — 3–5 curated problems, **easy → hard**. For
    each: the problem in one line, the **approach/intuition**, a C# solution, its complexity,
    and *why this technique fits*. The solutions live **inside this repo** — no clicking out
    required to learn.
11. **`## ✅ Key Takeaways`** — a tight bullet summary, then **self-check questions** the
    reader should be able to answer before moving on.
12. **Navigation footer** — `◀ Prev` · `▲ Module index` · `▶ Next` relative links.

---

## Conventions

- **Audience:** assume the reader knows how to program but is *new to DSA*. Define jargon the
  first time it appears.
- **Cross-link liberally.** Use relative links like `[Recursion](00-Foundations/03.Recursion.md)`
  (add `../` when linking across module folders). A link to a not-yet-written file is fine — it
  marks intent.
- **Diagrams:** Mermaid (` ```mermaid `) renders on GitHub. Keep them small and legible.
- **C# style:** modern idioms (tuple swap `(a, b) = (b, a)`, generics, pattern matching,
  `var` where the type is obvious). Show `using`/collection types when relevant.
- **Difficulty labels** in practice: `Easy`, `Medium`, `Hard`. Order them ascending.
- **Tone:** direct and encouraging. Short sentences. The reader is here to *understand*, not
  to be impressed.

---

## Skeleton (copy me)

```markdown
# <Topic>: <one-line big idea>

## 🧠 Intuition
<analogy / mental model — no code>

## 📐 How It Works
<step-by-step + mermaid or traced example>

## 🧾 Pseudocode
\`\`\`
<language-agnostic steps>
\`\`\`

## 💻 C# Implementation
\`\`\`csharp
<complete code>
\`\`\`

## ⏱️ Complexity
| Operation | Time | Space | Why |
|-----------|------|-------|-----|
| ... | ... | ... | ... |

## ⚖️ When to Use It
<trade-offs vs alternatives>

## 🚫 Common Mistakes
<❌ / ✅ snippets>

## 🌍 Real-World Applications
<where it shows up>

## 🎯 Practice (with full solutions)
### 1. <Problem name> — `Easy`
**Problem:** ...
**Approach:** ...
\`\`\`csharp
...
\`\`\`
**Complexity:** ... · **Why this fits:** ...

## ✅ Key Takeaways
- ...

**Self-check:** <2–3 questions>

---
◀ [Prev](.) · ▲ [Module index](./README.md) · ▶ [Next](.)
```

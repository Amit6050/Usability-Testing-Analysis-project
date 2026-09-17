# User Research & Accessibility Audit
## Google Classroom — Student Experience

**Track:** UI/UX  
**Level:** Beginner-friendly  
**Review date:** 17 September 2026  
**Method:** Documented heuristic review + accessibility benchmark against WCAG 2.2 AA

---

## 1. Product studied

**Google Classroom** is a student-facing learning platform used to find classes, read announcements, access classwork, complete assignments, and submit work. Google documents both web and mobile student workflows, including assignment submission, class joining, and an assignment planner.

### Target user

A **college/university student** who mainly uses a laptop and Android phone to:
- join classes,
- find assignments and deadlines,
- open teacher-provided files,
- submit coursework,
- check announcements and feedback.

The review focuses on students with different levels of digital confidence and students who may rely on zoom, keyboard navigation, or screen readers.

---

## 2. Five interview / survey questions

1. How easy is it to find an assignment that is due soon?
2. Have you ever missed an announcement or deadline in Classroom? What happened?
3. Which part of submitting an assignment feels confusing or takes the most time?
4. When using Classroom on a phone, which controls or information are hardest to use?
5. Do you ever increase text size, use a screen reader, or rely on keyboard navigation? If yes, what problems do you face?

**Research status:** No participant responses are fabricated here. This submission uses the assignment's permitted **documented heuristic-review** route.

---

## 3. Review method

Five common student tasks were reviewed against:
- **Nielsen-style usability heuristics:** visibility of system status, consistency, recognition over recall, error prevention/recovery, and user control.
- **WCAG 2.2 AA benchmarks:** contrast (1.4.3), resize text (1.4.4), reflow (1.4.10), labels/instructions for inputs (3.3.2), error identification (3.3.1), and target size (2.5.8).

### Tasks reviewed

| Task | What was checked |
|---|---|
| Join a class | Navigation, account clarity, class-code form |
| Find an assignment | Information hierarchy and recognition |
| Open classwork | Navigation consistency and content density |
| Submit an assignment | Form/action clarity and confirmation |
| Use Classroom on mobile | Reflow, touch usability, and extra-app dependencies |

---

## 4. Findings

### Finding 01 — Assignment discovery can become fragmented
**Impact: High**  
**Evidence:** Google describes a personalized homepage with modules, while student workflows also use the class stream, Classwork, assignment planner, and individual assignment pages.  
**User pain point:** A student who remembers the assignment title but not where it was posted may search across several areas.  
**Heuristic:** Recognition over recall / information hierarchy.  
**Recommendation:** Add a persistent student **“Due next”** view that combines class, assignment, due date, and submission state in one compact list.

### Finding 02 — Class-code joining has avoidable input friction
**Impact: High**  
**Evidence:** Students must be signed in with the correct account, then enter a 6–8 character alphanumeric code; Google’s help content specifically tells users to check account selection and exact code entry when joining fails.  
**User pain point:** Wrong-account and typo errors can block the first-run task.  
**Heuristic:** Error prevention / error recovery.  
**Recommendation:** Show the active account prominently above the field, provide clear inline validation while typing, and explain the accepted code format next to the field.

### Finding 03 — Stream content can be visually dense
**Impact: Medium**  
**Evidence:** Reference views of Classroom show stacked announcement/assignment cards in the Stream, while Google documents the Stream and Classwork as distinct areas.  
**User pain point:** Important tasks can be visually mixed with older posts and comments.  
**Heuristic:** Aesthetic/minimalist information presentation.  
**Recommendation:** Make assignment cards visually distinguishable from announcements and expose due date + submission state as primary metadata.

> Note: This is a usability observation, not a claim that the current UI violates WCAG.

### Finding 04 — Contrast should be verified on the authenticated interface
**Impact: Medium — verification required**  
**Evidence:** WCAG 2.2 AA requires normal text to achieve at least **4.5:1** contrast (or **3:1** for large text). Public reference screenshots do not provide the exact rendered color values of every current Classroom state.  
**Finding:** A reliable pass/fail result cannot be claimed from screenshots alone.  
**Recommendation:** Run a color-contrast check on an actual logged-in Classroom class using browser DevTools plus a tool such as WAVE or axe. Record ratios for primary text, links, disabled controls, focus indicators, and status chips.

### Finding 05 — Mobile workflows can depend on multiple Google apps
**Impact: Medium**  
**Evidence:** Google says the Classroom app is available on Android and iOS and that using all Classroom mobile features may require Google Docs, Sheets, and Slides. Some mobile functions are available offline, but the offline feature set is limited.  
**User pain point:** Students may be sent between apps when completing attachment-heavy assignments.  
**Heuristic:** Consistency / user control.  
**Recommendation:** Give a clearer in-flow explanation when a file requires another app, and show the expected next step before switching away from Classroom.

### Finding 06 — Screen-reader support exists, but task-specific guidance matters
**Impact: Medium**  
**Evidence:** Google publishes dedicated student guidance for using Classroom with screen readers and lists supported browser/screen-reader combinations.  
**User pain point:** Support exists, but students still need to learn Classroom-specific navigation patterns.  
**Recommendation:** Add concise in-product accessibility hints for first-time screen-reader users and ensure key task states (assignment status, due date, submission confirmation) are announced clearly.

---

## 5. Accessibility audit

| Area | Result | Evidence / rationale |
|---|---|---|
| Navigation | **Needs improvement** | Multiple surfaces expose class and assignment information; a unified “Due next” view would reduce scanning. |
| Readability | **Needs verification** | Stream cards can be dense; text-size behavior should be tested at 200% zoom. WCAG 1.4.4 requires content to remain usable when text is resized to 200%. |
| Contrast | **Needs verification** | Exact current rendered colors were not available from public reference material; test against WCAG 1.4.3 (4.5:1 normal text, 3:1 large text). |
| Forms | **Needs improvement** | Class-code entry has strong documented prerequisites and validation rules; more inline guidance would reduce preventable errors. |
| Mobile usability | **Needs improvement** | Mobile works for core tasks, but some workflows require companion Google apps and offline support is partial. |
| Screen readers | **Supported; verify task flow** | Google provides dedicated screen-reader guidance for students. Real-device testing is still needed for the exact class/assignment configuration. |

---

## 6. WCAG test checklist for a live class

- [ ] Normal text contrast ≥ 4.5:1
- [ ] Large text contrast ≥ 3:1
- [ ] Text remains usable at 200% zoom
- [ ] At 400% zoom / 320 CSS px equivalent, content reflows without loss of function
- [ ] Every input has a programmatically associated label or clear accessible name
- [ ] Invalid class-code input receives an identifiable error message
- [ ] Error information does not rely on color alone
- [ ] Keyboard focus is visible
- [ ] Pointer targets meet WCAG 2.2 AA's 24×24 CSS pixel minimum or an applicable exception
- [ ] Assignment submission confirmation is announced to assistive technology

---

## 7. Priority improvements

1. **Unified “Due next” student view** — reduces navigation/scanning effort.
2. **Smarter class-code validation** — reduces first-run and account-selection errors.
3. **Clearer assignment cards** — make due date and submission state immediately visible.
4. **Accessibility verification pass** — run contrast, zoom, keyboard, and screen-reader tests on a real class.
5. **Better app-switch messaging** — explain when Docs/Sheets/Slides is required.

---

## 8. Short portfolio explanation

> **I audited Google Classroom from a student perspective using a documented heuristic review and WCAG 2.2 AA benchmarks. I focused on navigation, readability, contrast, forms, and mobile usability. The main opportunities are reducing assignment-discovery friction, improving class-code error prevention, making assignment status more scannable, and validating contrast/zoom/screen-reader behavior on a real authenticated class.**

---

## 9. Sources

[1] Google Classroom Help — Access class information & submit assignment  
https://support.google.com/edu/classroom/answer/16642670

[2] Google Classroom Help — Classroom mobile app FAQ  
https://support.google.com/edu/classroom/answer/6118390

[3] W3C — Web Content Accessibility Guidelines (WCAG) 2.2  
https://www.w3.org/TR/WCAG22/

[4] Google Classroom Help — Join a class with a class code  
https://support.google.com/edu/classroom/answer/15605102

[5] Reference screenshot used for interface orientation  
https://usadultliteracy.com/how-to-use-google-classroom-for-students-computer-tutorial/

[6] Google Classroom Help — Get started with Classroom for students (Android)  
https://support.google.com/edu/classroom/answer/9582544

[7] Google Classroom Help — Use a screen reader with Classroom on your computer (students)  
https://support.google.com/edu/classroom/answer/6084551

---

**Submission note:** This project is placed in a public GitHub repository. The contrast results are intentionally marked “needs verification” because screenshots alone cannot establish exact WCAG color ratios.

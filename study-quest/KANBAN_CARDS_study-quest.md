# STUDY QUEST
## Kanban Project Starter App
## 📋 KANBAN CARDS

Recommended board: `Backlog → In Progress → In Review → Done`
Recommended WIP limit: 2 per active column

---

### 🐛 BUG FIX CARDS (5)

---

**[BUG-01] Page refreshes when logging a study session**
Priority: 🔴 Critical

Clicking "Log Session +XP" causes the whole page to reload. Nothing ever
gets logged and the XP counter resets to 0 every time.

Acceptance criteria:
- Clicking "Log Session +XP" adds the session to the history without a page reload
- The XP counter updates immediately after logging
- The form fields clear after a successful submission

---

**[BUG-02] All subjects and sessions disappear after refreshing**
Priority: 🔴 Critical

Everything seems to save fine during use, but a full page refresh wipes
all subjects and sessions. localStorage should be keeping the data.

Acceptance criteria:
- After logging sessions and refreshing the page, all data is still present
- XP total persists across refreshes
- Subjects remain in the sidebar after a refresh

---

**[BUG-03] XP shows "04545" instead of 90 after logging sessions**
Priority: 🟠 High

The XP counter doesn't add up correctly. Instead of showing cumulative XP
as a number, it looks like it's pasting digits together.

Acceptance criteria:
- XP adds numerically (e.g. 45 min + 45 min = 90 XP, not "04545")
- The level and XP bar update correctly based on the total
- Existing sessions in localStorage still load correctly after the fix

---

**[BUG-04] Session history shows "Unknown" for every subject**
Priority: 🟠 High

Sessions log successfully and appear in the history panel, but every
single session says "Unknown" where the subject name should be.

Acceptance criteria:
- Each session in the history shows the correct subject name and color
- This works for both new sessions and sessions loaded from localStorage

---

**[BUG-05] The XP progress bar is always empty**
Priority: 🟡 Medium

The green XP bar track is visible in the header, but the fill never appears
no matter how much XP is earned. The level number updates correctly.

Acceptance criteria:
- The green fill grows proportionally as XP increases toward the next level
- At 0 XP the bar is empty; at 100 XP the bar is full before resetting
- The fill animates smoothly when XP changes

---

### ✨ FEATURE CARDS (8)

---

**[FEAT-01] Show an empty state when no subjects have been added**
Priority: 🟠 High

When there are no subjects, the "Log a Study Session" form still shows a
blank dropdown. There's no guidance for new users.

Acceptance criteria:
- If no subjects exist, the session form shows a message: "Add a subject first!"
- The Log Session button is disabled until at least one subject exists
- The message disappears as soon as a subject is added

---

**[FEAT-02] Show total study time stats in the header**
Priority: 🟡 Medium

The header only shows XP and level. Add a stat showing total hours studied.

Acceptance criteria:
- A "Total Study Time" stat shows total minutes logged, formatted as "Xh Ym"
- Updates immediately after each session is logged
- Persists across page refreshes

---

**[FEAT-03] Add a streak counter (days studied in a row)**
Priority: 🟡 Medium

Add a streak tracker that counts consecutive calendar days with at least one
logged session.

Acceptance criteria:
- A streak badge shows "🔥 X day streak" in the header or sidebar
- Streak increments when a session is logged on a new calendar day
- Streak resets to 1 if a day is skipped
- Streak persists across page refreshes

---

**[FEAT-04] Show a congratulations message on level-up**
Priority: 🟡 Medium

When a student earns enough XP to advance a level, nothing happens visually.
Add a level-up celebration message.

Acceptance criteria:
- When a session causes a level-up, display a temporary banner or popup
  like "⬆️ Level Up! You're now Level 3!"
- The message disappears after 3 seconds automatically
- Does not trigger on page load

---

**[FEAT-05] Delete individual sessions from history**
Priority: 🟡 Medium

There's no way to remove a session that was logged by mistake.

Acceptance criteria:
- Each session card in the history has a delete button
- Clicking it removes the session and subtracts its XP from the total
- XP display and bar update immediately
- Confirmation is not required (deleting a session is low-stakes)

---

**[FEAT-06] Show per-subject total minutes in the subject list**
Priority: 🟢 Low

The subject list just shows names. It would be useful to see how much time
has been logged per subject.

Acceptance criteria:
- Each subject item shows total minutes studied (e.g. "Calculus — 120 min")
- Updates live as new sessions are logged
- Shows "0 min" for subjects with no sessions

---

**[FEAT-07] Add a "Today's Goal" feature**
Priority: 🟢 Low

Let students set a daily study goal (in minutes) and see their progress toward it.

Acceptance criteria:
- An input in the sidebar lets students set a goal (e.g. 60 minutes)
- A progress bar shows today's logged minutes vs. the goal
- Goal persists across refreshes; progress resets each calendar day

---

**[FEAT-08] Let students rename or recolor a subject**
Priority: 🟢 Low

Once a subject is added, there's no way to edit it — only delete it.

Acceptance criteria:
- Each subject item has an edit button (pencil icon or "Edit" text)
- Clicking it makes the name and color inline-editable
- Saving updates all existing sessions linked to that subject

---

### 🎨 POLISH CARDS (4)

---

**[POLISH-01] Make the app mobile responsive**
Priority: 🟡 Medium

The two-column grid layout breaks on small screens. The sidebar and main
column need to stack on mobile.

Acceptance criteria:
- On screens under 768px, the sidebar stacks above the main column
- No horizontal overflow at any viewport width
- Inputs remain comfortably tappable on mobile

---

**[POLISH-02] Animate XP bar filling up after a session**
Priority: 🟢 Low

The XP bar updates correctly but jumps instantly. Add a satisfying fill animation.

Acceptance criteria:
- The bar animates smoothly from the old value to the new value over ~600ms
- On level-up, the bar fills to 100% and then resets to the new partial value

---

**[POLISH-03] Color-code the session history cards by subject**
Priority: 🟢 Low

Session cards have a left border but it's the same color for all subjects.

Acceptance criteria:
- Each session card's left border matches the subject's assigned color
- The subject name text in the card also uses the subject color

---

**[POLISH-04] Show a motivational message based on session length**
Priority: 🟢 Low

After logging a session, show a brief contextual message based on how long
the session was.

Acceptance criteria:
- Under 15 min: "Quick session — every bit counts! 💪"
- 15–45 min: "Solid work! Keep it up. 🎯"
- Over 45 min: "Beast mode! That's a long session. 🔥"
- Message appears near the form for 3 seconds after submit

---

## 📅 SUGGESTED DAY-BY-DAY FLOW

| Day | Focus | Ceremonies |
|-----|-------|------------|
| Day 1 | Board setup, backlog grooming, pull first cards | Standup (10 min) |
| Day 2 | Continuous flow — pull, build, review, move cards | Standup (10 min) |
| Day 3 | Continue flow; team identifies bottlenecks; WIP limits tested | Standup (10 min) |
| Day 4 | Final cards, freeze board at end of class, retrospective | Retro (20 min) |

## 📊 METRICS TRACKER GUIDANCE

Log at end of each day:
- Cards in Done / In Progress / In Review / Blocked

Present a throughput chart at retrospective (cards completed per day).

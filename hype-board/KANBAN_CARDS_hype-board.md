# HYPE BOARD
## Kanban Project Starter App

## 📋 KANBAN CARDS

Pre-written cards for the class Kanban board.
Recommended column setup: `Backlog → In Progress → In Review → Done`
Recommended WIP limit: 2 per In Progress, 2 per In Review

Cards are ordered by suggested priority within each category.
Students should groom (re-prioritize) the backlog on Day 1.

---

### 🐛 BUG FIX CARDS (5 cards)

---

**[BUG-01] Page refreshes when you submit a post**
Priority: 🔴 Critical

The board clears whenever you hit "Post It!" — something about how the form
submits is causing a full page reload. Nothing ever gets added.

Acceptance criteria:
- Clicking "Post It!" adds the post to the board without reloading the page
- The form inputs clear after a successful submission

---

**[BUG-02] Posts disappear after refreshing the page**
Priority: 🔴 Critical

Posts appear on the board normally, but after a page refresh they're all gone.
The app is supposed to save posts using localStorage.

Acceptance criteria:
- Posts survive a full browser refresh
- Verify by posting, refreshing, and confirming all posts are still visible

---

**[BUG-03] Upvote count shows "01", "011" instead of 1, 2, 3**
Priority: 🟠 High

Clicking the 🔥 button on a card doesn't increment the number — it just
keeps adding "1" to the end of whatever is already there.

Acceptance criteria:
- First upvote shows 1, second shows 2, etc.
- Upvote counts survive a page refresh

---

**[BUG-04] Delete button removes the wrong post**
Priority: 🟠 High

Clicking the 🗑️ button on a card deletes the card beneath it instead.
The last card on the board can't be deleted at all.

Acceptance criteria:
- Clicking delete on a card removes exactly that card and nothing else
- The last card on the board can be deleted

---

**[BUG-05] Cards stack in a single column instead of a grid**
Priority: 🟡 Medium

The board shows all cards in one tall single-file column. It should display
two cards side-by-side to use the available space.

Acceptance criteria:
- On a desktop-width screen, cards display in a 2-column layout
- Cards wrap naturally as new posts are added

---

### ✨ FEATURE CARDS (8 cards)

---

**[FEAT-01] Show an empty state when there are no posts**
Priority: 🟠 High

When the board is empty (either no posts at all, or all posts filtered out),
nothing shows — just blank space. That's confusing.

Acceptance criteria:
- When no posts exist: show a centered message like "No hype yet! Be the first. 🔥"
- When the filter returns zero results: show "No posts in this category yet."
- The message disappears as soon as a post is added / filter changes

---

**[FEAT-02] Add a character countdown on the message textarea**
Priority: 🟡 Medium

The textarea has a 150-character limit but users can't see how many characters
they've used. Add a live counter.

Acceptance criteria:
- Counter shows as "X / 150" below the textarea, updating with each keystroke
- Counter turns red when under 20 characters remaining
- Counter resets after a post is submitted

---

**[FEAT-03] Color-code each card's left border by category**
Priority: 🟡 Medium

Right now every card has the same purple left border regardless of category.
Give each category its own distinct color.

Acceptance criteria:
- Motivation = orange or yellow
- Sports = green
- Academics = blue
- Life = pink or teal
- The category badge color should match the border

---

**[FEAT-04] Add a timestamp to each post**
Priority: 🟡 Medium

There's no way to know when a post was made. Add a posted time to each card.

Acceptance criteria:
- Each card shows something like "Just now" or "3 min ago" or "Apr 6, 2026"
- Timestamp is stored with the post and survives a page refresh

---

**[FEAT-05] Confirm before deleting a post**
Priority: 🟡 Medium

Right now a card is deleted the instant the trash icon is clicked — no undo.
Add a simple confirmation step.

Acceptance criteria:
- Clicking 🗑️ shows a confirmation: "Delete this post? (Yes / Cancel)"
- Clicking Cancel leaves the post untouched
- Clicking Yes deletes the post as normal
- A plain browser confirm() dialog is acceptable

---

**[FEAT-06] Sort posts by Most Hype**
Priority: 🟢 Low

Right now posts always show newest-first. Add a way to sort by most upvotes.

Acceptance criteria:
- A "Sort by Most Hype" button or dropdown appears on the board header
- Clicking it re-orders visible posts from highest to lowest upvotes
- A "Newest First" option returns to the default order

---

**[FEAT-07] Add a "Clear All" button with confirmation**
Priority: 🟢 Low

There's no way to wipe the board and start fresh without going into DevTools.

Acceptance criteria:
- A "Clear All" button appears somewhere logical (board header or footer)
- Clicking it asks for confirmation before deleting everything
- After confirming, all posts are removed from the board and localStorage

---

**[FEAT-08] Cap the board at 20 posts**
Priority: 🟢 Low

If someone keeps posting, the board could grow forever. Limit it to 20 posts.

Acceptance criteria:
- If there are already 20 posts, submitting the form shows an error message
  instead of adding a new post: "Board is full! Delete a post to make room."
- The message appears near the form, not as an alert()
- The limit only applies to total posts stored, not per category

---

### 🎨 POLISH CARDS (4 cards)

---

**[POLISH-01] Make the app mobile responsive**
Priority: 🟡 Medium

The current layout uses a two-column grid that breaks on small screens.
Make it work on a phone-sized viewport.

Acceptance criteria:
- On screens under 768px wide, the form stacks on top of the board (single column)
- Cards stack in a single column on mobile (not two)
- No horizontal scrolling at any viewport width
- Form inputs are comfortably tappable on mobile

---

**[POLISH-02] Show total hype count in the header**
Priority: 🟢 Low

Add a live stat in the header showing the total number of upvotes across all
posts — a sense of the board's energy level.

Acceptance criteria:
- A line in the header reads something like "Total Hype: 142 🔥"
- The number updates immediately when an upvote is clicked
- The number persists across page refreshes

---

**[POLISH-03] Animate new cards sliding into the board**
Priority: 🟢 Low

New posts just pop in abruptly. Add a subtle entrance animation.

Acceptance criteria:
- Newly added cards slide or fade in smoothly (CSS keyframe or transition)
- The animation only triggers for the newest card, not on every render
- Animation is quick (under 400ms) and doesn't feel sluggish

---

**[POLISH-04] Add hover tooltips to icon buttons**
Priority: 🟢 Low

The upvote and delete buttons show emoji but no accessible label.
Add visible tooltip text on hover.

Acceptance criteria:
- Hovering the 🔥 button shows "Upvote this post"
- Hovering the 🗑️ button shows "Delete this post"
- Tooltips can use the native HTML title attribute or a CSS :after solution

---

## 📅 SUGGESTED DAY-BY-DAY FLOW

| Day | Focus | Ceremonies |
|-----|-------|------------|
| Day 1 | Board setup, backlog grooming, pull first cards | Standup (10 min) |
| Day 2 | Continuous flow — pull, build, review, move cards | Standup (10 min) |
| Day 3 | Continue flow; team identifies bottlenecks; WIP limits tested | Standup (10 min) |
| Day 4 | Final cards, freeze board at end of class, retrospective | Retro (20 min) |

## 📊 METRICS TRACKER GUIDANCE

The Metrics Tracker role should log the following at the end of each day:

- Cards in Done
- Cards in In Progress
- Cards in In Review
- Cards blocked (stuck >1 day without movement)

At the retrospective, they present a simple bar or line graph of
"Cards completed per day" as evidence of team throughput.
This is the Kanban equivalent of a burndown chart.

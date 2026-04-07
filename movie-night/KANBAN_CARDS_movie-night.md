# MOVIE NIGHT
## Kanban Project Starter App

## 📋 KANBAN CARDS

---

### 🐛 BUG FIX CARDS (5)

---

**[BUG-01] Clicking "Add to Watchlist" does nothing**
Priority: 🔴 Critical

Filling out the form and hitting the add button produces zero response.
No movie appears on the list. No error message shows on the page.
Check the browser console — there may be a clue there.

Acceptance criteria:
- Clicking the button adds the movie to the grid
- The form fields clear after a successful add
- The stats counters in the header update immediately

---

**[BUG-02] Movies disappear after every page refresh**
Priority: 🔴 Critical

Movies appear fine while using the app, but a full page refresh wipes
everything. The app is supposed to save movies using localStorage.

Acceptance criteria:
- All movies persist across page refreshes
- Ratings and watched status also persist
- Verify by adding movies, refreshing, and confirming they're still there

---

**[BUG-03] Star ratings always display one star too many**
Priority: 🟠 High

Clicking the third star should give a 3-star rating, but the card
displays 4 filled stars. Every rating is visually one higher than intended.

Acceptance criteria:
- Clicking star 1 shows exactly 1 filled star
- Clicking star 3 shows exactly 3 filled stars
- Clicking star 5 shows exactly 5 filled stars
- Ratings persist after a page refresh

---

**[BUG-04] "Watched" and "To Watch" filters show no results**
Priority: 🟠 High

Switching the status filter to "Watched" or "To Watch" always shows the
empty state, even when movies clearly have those statuses.
"All Movies" works fine.

Acceptance criteria:
- "Watched" filter shows only movies that have been marked watched
- "To Watch" filter shows only unwatched movies
- Filters can be combined with the genre filter

---

**[BUG-05] Star ratings are completely invisible**
Priority: 🟠 High

The star rating area is there — clicking it does change the rating —
but you genuinely cannot see any stars on the cards. It looks like
blank space.

Acceptance criteria:
- Unfilled stars are visible but dim
- Filled (rated) stars display in bright gold
- Stars are visible on both unwatched and watched (dimmed) cards

---

### ✨ FEATURE CARDS (8)

---

**[FEAT-01] Empty state with a helpful message and icon**
Priority: 🟠 High

The empty state just says "No movies here yet. Add some!" with a popcorn icon.
Make it more helpful, especially for the filtered empty state.

Acceptance criteria:
- Default empty state (no movies at all): "Your watchlist is empty — add your first movie! 🎬"
- Filtered empty state: "No [Genre/Status] movies found. Try a different filter."
- The message is different depending on whether filters are active

---

**[FEAT-02] Sort movies — by title, year, or rating**
Priority: 🟡 Medium

Right now movies always show newest-first. Add sorting options.

Acceptance criteria:
- A sort dropdown offers: Newest First / Oldest First / A–Z Title / Highest Rated
- Sorting works in combination with filters
- Sort preference does not need to persist across refreshes

---

**[FEAT-03] Add a genre color-coding system**
Priority: 🟡 Medium

All movie cards look identical. Differentiate them by genre with colors.

Acceptance criteria:
- Each genre has a unique accent color (border, poster background, or badge)
- At minimum: Action = red, Comedy = yellow, Horror = purple, Sci-Fi = blue, Drama = teal
- Color system is consistent and visible

---

**[FEAT-04] Show a "watched on" date when marking a movie watched**
Priority: 🟡 Medium

When a movie is marked as watched, record the date.

Acceptance criteria:
- The date is saved when the movie is first marked watched
- The card displays something like "Watched Apr 6, 2026" in small text
- Date persists across refreshes
- Un-watching a movie clears the date

---

**[FEAT-05] Let users edit a movie's title or note after adding it**
Priority: 🟡 Medium

There's currently no way to fix a typo in a movie's title or note.

Acceptance criteria:
- An "Edit" button on each card opens the title/note fields for inline editing
- Saving commits the changes; canceling reverts them
- Genre and year can optionally be editable too

---

**[FEAT-06] Add a "Recommend a random movie" button**
Priority: 🟢 Low

For when the group can't decide what to watch.

Acceptance criteria:
- A button labeled "Pick for me!" appears in the watchlist header
- Clicking it randomly selects one unwatched movie and highlights it
- If no unwatched movies exist, show "You've seen everything! 🎉"

---

**[FEAT-07] Show average rating stats in the header**
Priority: 🟢 Low

The header shows totals but not quality stats.

Acceptance criteria:
- A "Avg Rating" stat shows the average star rating of all rated movies (1 decimal)
- Movies with a rating of 0 are excluded from the average
- Updates live as ratings change

---

**[FEAT-08] Confirm before deleting a movie**
Priority: 🟢 Low

Movies can be deleted with one click and no undo. Add confirmation.

Acceptance criteria:
- Clicking the trash icon shows a simple confirm dialog before deleting
- Canceling leaves the movie untouched
- A plain browser `confirm()` dialog is acceptable

---

### 🎨 POLISH CARDS (4)

---

**[POLISH-01] Make the app mobile responsive**
Priority: 🟡 Medium

The grid layout needs to adapt for phone-sized screens.

Acceptance criteria:
- Cards stack to a single column on screens under 600px
- Header stats remain readable on mobile
- Form inputs are comfortably usable on a phone

---

**[POLISH-02] Add a subtle entrance animation for new cards**
Priority: 🟢 Low

New movie cards just appear abruptly when added.

Acceptance criteria:
- New cards fade or slide into the grid
- Animation is under 400ms and doesn't delay usability
- Existing cards don't re-animate when a filter changes

---

**[POLISH-03] Dim the poster emoji/icon for watched movies**
Priority: 🟢 Low

Watched cards already dim overall, but the poster area could have a
more distinct "seen it" visual treatment.

Acceptance criteria:
- Watched movies show a checkmark overlay or "WATCHED" stamp on the poster area
- The treatment is clearly intentional and not a bug

---

**[POLISH-04] Add keyboard shortcut to focus the title field**
Priority: 🟢 Low

Power users want to add movies quickly without reaching for the mouse.

Acceptance criteria:
- Pressing "/" on the keyboard focuses the movie title input
- Works unless the user is already typing in a field
- A small hint "(press / to add)" appears near the form title

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

Of course! Here’s the **Steps section** rewritten cleanly as Markdown so you can drop it straight into your repo:

---

# Steps

### 1. Parse `teams.json`

* Map each `user_id → display_name, team_name, avatar`.
* Build `avatar_url` as `https://sleepercdn.com/avatars/{hash}` if not already a full URL.
* Default to Sleeper’s generic silhouette if no avatar exists.

---

### 2. Parse `draft_picks.json`

* Assign each pick to the correct team (via `picked_by`).
* Count `"poop"` emoji reactions, total them per team, and store each event (`player, round, poops`).
* Track roster construction (positions, early/late QB/TE, WR/RB balance).

---

### 3. Use `draft.json`

* Pull `season` and `league_name` if available.
* Derive `scoring_type` from metadata (`ppr`, `half_ppr`, `standard`).

---

### 4. For each team

* Assign a **letter grade** (A, B+, C, etc.) based on positional balance, value picks, and draft approach.
* Write **blurbs**:

    * **blurb\_good** must be creative and varied — avoid repeating the same structure across teams. Think like sports commentary.

        * Examples:

            * “Jefferson and Taylor headline a draft built for fireworks.”
            * “Draft strategy paid off; Chase and Irving give this team weekly firepower.”
            * “McCaffrey sets the tone for a dangerous draft.”
    * **blurb\_bad** should roast — funny, sarcastic, or critical. Don’t be afraid to exaggerate weaknesses.

        * Examples:

            * “Top heavy roster—bench looks like quicksand.”
            * “Risk piled on risk; the waiver wire better be friendly.”
            * “Too many gambles—this draft might age poorly.”
    * **Important:** Do not start every blurb with the same phrase. Rotate intros for variety.

---

### 5. Creativity Score

* Rate `team_name` on a 1–10 scale.
* Puns, clever references, or unique formatting get higher scores.

---

### 6. Superlatives

* **most\_poops** = top 3 teams by poop\_count.
* **best\_team\_name** = top 3 by creativity score.
* **best\_draft** = team with the best overall value.

    * `"info"` must be a short, general phrase (e.g., “Well-rounded draft with strong overall value”).
    * Do **not** include player names or round numbers.
* **shakiest\_draft** = team with the most unsteady/risky draft.

    * `"info"` must also be a short, general phrase (e.g., “Unsteady roster construction with higher risk”).
    * Do **not** include player names or round numbers.

---

### 7. Output

* Return only valid JSON following the structure defined at the top.

---

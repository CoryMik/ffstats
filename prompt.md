# Fantasy Football JSON Generation Prompt

You are given three JSON files from Sleeper fantasy football:

1. **teams_league2.json** — contains user_id, display_name, metadata (team_name, avatar, etc.)
2. **draft_league2.json** — contains overall draft info (rounds, slots, etc.)
3. **draft_picks_league2.json** — contains each pick, player metadata, picked_by user_id, and reactions (with emoji counts).

---

## Task
Combine these into a single JSON file called `league_data.json` with the following structure:

```json
{
  "league_name": "<League Name from draft.json or manual input>",
  "season": <season year>,
  "scoring_type": "<ppr/half/standard>",
  "superlatives": {
    "most_poops": [<top 3 user_ids ranked by poop_count>],
    "best_team_name": [<user_ids with most creative names>],
    "best_draft": {
        "team_id": <user_id judged best draft value>,
        "info": "<short, general phrase about why it was the best draft (no player names or round numbers)>"
    },
    "shakiest_draft": {
         "team_id": <user_id judged weakest draft>,
         "info": "<short, general phrase about why it was the weakest draft (no player names or round numbers)>"
    }
  },
  "teams": [
    {
      "user_id": "<user_id>",
      "display_name": "<display_name>",
      "team_name": "<team_name or fallback to display_name>",
      "avatar_url": "<full Sleeper avatar URL or default>",
      "grade": "<Letter Grade you assign based on draft>",
      "creativity_score": <1–10 rating of team name creativity>,
      "blurb_good": "<fun, varied one-liner praising their draft>",
      "blurb_bad": "<playful roast or snarky one-liner highlighting weaknesses>",
      "poop_count": <total poop emojis from reactions in draft_picks.json>,
      "poop_events": [
        {
          "player": "<player drafted>",
          "round": <round number>,
          "poops": <number of poop reactions>
        }
      ]
    }
  ]
}

# Weekly content automation

The **Weekly YouTube Shorts recording pack** GitHub Actions workflow turns each week's ideas in `content/30-day-plan.csv` into a Markdown recording brief. It runs Mondays at 09:00 UTC during the four-week campaign and can also be started manually.

## Run it manually

1. Open the repository's **Actions** tab.
2. Select **Weekly YouTube Shorts recording pack** and choose **Run workflow**.
3. Choose `auto` to use the launch date or select a specific campaign week (1–4).
4. Open the completed run and download the `minute-momentum-weekly-recording-pack` artifact.

The scheduled run uses the launch date in `scripts/generate_weekly_pack.py` (currently **2026-11-09**). Change `DEFAULT_LAUNCH_DATE` there before launching a new campaign. Outside the four campaign weeks, scheduled runs stop without producing a pack; manual week selection remains available.

## What it automates—and what it doesn't

- Selects the week's CSV ideas and creates a consistent hook, demonstration, shot/caption outline, and review checklist for each.
- Uploads the generated Markdown as a workflow artifact, available from the Actions run.
- Does **not** create or publish videos, sign into YouTube, upload Shorts, generate finished scripts with AI, or guarantee channel growth. Review and personalize the briefs, record the videos, and upload manually.
- Uses no YouTube credentials or external service secrets.

## Test locally

From the repository root, run:

```bash
python3 scripts/generate_weekly_pack.py --week 1
```

The generated file appears under `output/`. The `output/` directory is generated and should not be committed.

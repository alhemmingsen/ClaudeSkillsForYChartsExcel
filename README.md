# ClaudeSkillsForYChartsExcel
Skills document to make Claude for Excel much more effective with the YCharts Addin

YCharts Excel Formulas, Claude Skill
A Claude skill that teaches Claude how to write YCharts Excel Add-in formulas (YCP, YCS, YCI, YCD, YCDS, YCH), pick the right calculation code from a catalog of ~1,500 metrics, and handle the usual gotchas (ticker prefixes, Bloomberg "US" suffix, array entry, OHLC quirks).
What you need
A Claude.ai Pro, Max, Team, or Enterprise plan (custom skills aren't available on Free)
Code execution and file creation turned on (Settings > Capabilities)
The YCharts Excel Add-in installed and signed in (separate from Claude, this is what actually pulls the data into your workbook)
Setup, 60 seconds
Download `ycharts-excel-formulas.zip` (do not unzip it, Claude wants the zip).
In Claude.ai, click your name (bottom left) and go to Customize > Skills. On some surfaces this lives under Settings > Capabilities > Skills or Settings > Features > Skills, same place either way.
Click Upload skill and pick the zip.
Toggle the skill on.
Start a new chat and ask something like "what's the YCharts code for trailing twelve months free cash flow?" or "write me a YCS formula to pull monthly closes for MSFT for the last year." The skill should fire automatically.
If it doesn't fire, open a fresh chat (the skill list is read at the start of a conversation) and try a prompt that names YCharts or one of the formula codes directly.
What's in the zip
```
ycharts-excel-formulas/
├── SKILL.md                              the instructions Claude reads
├── README.md                             this file
└── references/
    └── ycharts_metrics_catalog.md        ~1,500 calculation codes, loaded only when needed
```
The catalog is large on purpose. Claude only opens it when the metric isn't already covered in SKILL.md, and even then it reads the table of contents first and jumps to the right section with view_range, so it doesn't burn context.
Updating it later
Edit the files locally, re-zip the `ycharts-excel-formulas` folder (keep that top-level folder inside the zip), delete the old version in Customize > Skills, and upload the new one.
Troubleshooting
Skill is greyed out: code execution isn't enabled. Settings > Capabilities, turn it on.
Skill never fires: the description in SKILL.md is what Claude uses to decide when to invoke it. Ask Claude directly: "when would you use the ycharts-excel-formulas skill?" and adjust the description if the answer is off.
Claude writes a formula but Excel returns #NAME?: the YCharts add-in isn't loaded or you're not signed in on the Excel side. The skill is doing its job, the add-in isn't.

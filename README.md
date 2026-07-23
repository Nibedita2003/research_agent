# Research Agent

A GitHub Copilot research agent that turns a topic into a cited, board-ready Word report. It is designed for evidence-led business research: finding current web sources, assessing their quality, drafting a structured report, and saving a verified `.docx` file in `research/`.

## What it does

- Frames a research question and focused sub-questions.
- Researches current sources, prioritising regulators, official data, company disclosures, academic work, and reputable institutions.
- Cross-checks important claims and records evidence gaps.
- Writes a cited Markdown draft using a consistent business-report structure.
- Converts the draft to a non-empty Word document with Pandoc.

The agent treats its task as incomplete until the Word report has been created and verified.

## Repository layout

```text
.github/
  agents/research.agent.md             # Research agent instructions
  skills/research-report/SKILL.md      # Report structure and quality checks
  skills/web-research/SKILL.md         # Source discovery and evidence rules
.vscode/settings.json                  # Adds Pandoc to the terminal PATH
research/                               # Generated reports and working drafts
```

## Prerequisites

- Visual Studio Code with GitHub Copilot Chat.
- Pandoc installed and available on your `PATH`.

The included VS Code setting expects Pandoc at:

```text
C:\Users\ASUS\AppData\Local\Pandoc\pandoc.exe
```

If Pandoc is installed elsewhere, update `.vscode/settings.json` or add its directory to your system `PATH`.

## Using the agent

1. Open this folder in Visual Studio Code.
2. Open GitHub Copilot Chat and select the **research** agent.
3. Give it a topic, for example:

   ```text
   /research AI agent implementation in banking
   ```

4. Allow web research and document conversion when prompted.
5. Find the completed report in `research/`.

Generated filenames follow this pattern:

```text
research/[topic-slug]_[YYYYMMDD]_v[N].docx
```

Existing reports are not overwritten; the version number increases for reports with the same topic and date.

## Research standards

- At least six credible sources by default.
- Inline citations for material factual claims.
- Independent cross-checking for high-impact figures and assertions where possible.
- Clear separation of facts, estimates, forecasts, and analysis.
- Explicit limitations, counterarguments, risks, and evidence gaps.
- No fabricated citations, quotes, or statistics.

## Report structure

Reports normally include an executive summary, scope and methodology, context, findings, implications, risks, strategic options, recommendations, and references. The standard target length is 2,500–4,000 words, scaled to the requested scope.

## Included example

The `research/` folder includes an example report and its Markdown draft on implementing AI agents in banking.

## License

No license has been specified for this repository. Add a license file before distributing or reusing it publicly.

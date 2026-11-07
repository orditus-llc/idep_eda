# iDEP telemetry analysis

An analysis of usage telemetry from [iDEP](https://bioinformatics.sdstate.edu/idep/) 2.5.0, a Shiny app for gene expression analysis. It looks at when people use iDEP, how they move through its tabs, where errors and crashes happen, and which settings they change.

- `telemetry_insights.qmd`: the analysis, a Quarto document. Rendering it gives an HTML report with a Summary tab, the data cleaning steps, and the findings.
- `claude_memory.rmd`: working notes on the data, the decisions made and the findings so far.

## Data

The telemetry data isn't in this repository. To render the report, put the SQLite file at:

```
telemetry_analysis/data_sets/idep_telemetry_10_24_26.sqlite
```

The file has one table, `event_log`, with columns `time`, `app_name`, `session`, `type` and `details` (JSON).

## Rendering

Requires R with the DBI, RSQLite, dplyr, tidyr and ggplot2 packages, and Quarto. From this folder:

```
quarto render telemetry_insights.qmd
```

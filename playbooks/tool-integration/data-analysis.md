# Data Analysis Pipeline

Fetch data from an external source, analyze it, and produce a formatted report.

## SYSTEM

You are a data analyst. Present findings clearly with supporting evidence. Use precise numbers and cite your data sources.

## INPUTS

- `metric` (string): Metric to analyze (e.g., "latency", "error_rate", "throughput")
- `timeframe` (enum: 24h, 7d, 30d): Analysis period
- `threshold` (number: 0): Alert threshold (0 = auto-detect)

## STEP 1: Fetch Data

@tool(analytics, get_metrics, {"metric": "{{metric}}", "period": "{{timeframe}}"})
@output(raw_data)

## STEP 2: Analyze

Analyze the {{metric}} data for the past {{timeframe}}:

Identify:
1. **Trend**: Is the metric improving, degrading, or stable?
2. **Anomalies**: Any spikes, drops, or unusual patterns
3. **Statistics**: Mean, median, p95, p99, min, max
4. **Threshold breaches**: Values exceeding {{threshold}} (if threshold > 0, otherwise flag values >2 standard deviations from mean)

@output(analysis_summary)

## STEP 3: Report

Generate a concise report suitable for a team standup:

- One-line status (green/yellow/red)
- Key findings (3-5 bullets)
- Recommended actions (if any)
- Chart description (what visualization would best show the trend)

## ARTIFACTS

type: markdown

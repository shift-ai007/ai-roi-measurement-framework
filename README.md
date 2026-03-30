# AI ROI Measurement Framework

> A practical, no-BS framework for quantifying the return on AI investments — from initial pilot through production scale.

Most AI projects fail not because the technology doesn't work, but because nobody established clear success criteria before writing the first line of code. This framework fixes that.

## Why This Exists

After helping dozens of companies [plan and execute AI strategies](https://shift-ai.cloud/ai-strategy-planning/), we noticed a pattern: the projects that succeed always have three things in common:

1. **Clear baseline metrics** captured before any AI work begins
2. **Staged value gates** — not just a final ROI check, but incremental proof points
3. **Honest cost accounting** — including the costs nobody talks about (data prep, change management, ongoing maintenance)

This repo gives you the templates and thinking models to get all three right.

## Framework Overview

### Phase 1: Baseline & Opportunity Sizing

Before building anything, capture:

| Metric Category | What to Measure | Example |
|----------------|-----------------|---------|
| **Process time** | Hours per task, end-to-end cycle time | "Invoice processing takes 4.2 hours avg" |
| **Error rate** | Defect %, rework frequency | "12% of classifications need manual correction" |
| **Throughput** | Units processed per period | "Team handles 340 support tickets/week" |
| **Cost per unit** | Fully-loaded cost per transaction | "$47 per processed insurance claim" |
| **Customer impact** | NPS, resolution time, satisfaction | "Average first-response time: 6.2 hours" |

### Phase 2: Pilot ROI Model

Structure your pilot to prove value in 4-8 weeks:

```
Pilot ROI = (Baseline Cost - Pilot Cost) / Pilot Investment

Where:
  Baseline Cost = (volume × cost_per_unit × pilot_duration)
  Pilot Cost = (volume × new_cost_per_unit × pilot_duration) + maintenance
  Pilot Investment = development + data_prep + infrastructure + training
```

**Hidden costs to include:**
- Data labeling and preparation (often 60-80% of total effort)
- Integration engineering (APIs, auth, error handling)
- Change management (training, process redesign, documentation)
- Ongoing model monitoring and retraining
- Infrastructure (GPU compute, vector DB hosting, API costs)

### Phase 3: Production Value Tracking

Once in production, track these monthly:

```yaml
direct_savings:
  labor_hours_saved: 0
  error_reduction_value: 0
  throughput_increase_value: 0

indirect_value:
  customer_satisfaction_delta: 0
  employee_satisfaction_delta: 0
  competitive_advantage_score: 0  # 1-10 subjective

costs:
  infrastructure: 0
  api_calls: 0
  maintenance_hours: 0
  retraining_cycles: 0
  support_escalations: 0

roi_monthly: 0  # (direct_savings - costs) / cumulative_investment
payback_months: 0  # cumulative_investment / avg_monthly_savings
```

## Decision Templates

### Should We Build This AI Feature?

Use this scoring matrix before greenlighting any AI project:

| Factor | Score (1-5) | Weight | Notes |
|--------|-------------|--------|-------|
| Data availability | _ | 3x | Do we have labeled data? How much cleaning needed? |
| Process volume | _ | 2x | Is the task frequent enough to justify automation? |
| Error tolerance | _ | 2x | Can we accept AI mistakes? What's the cost of errors? |
| Integration complexity | _ | 2x | How hard to plug into existing systems? |
| Maintenance burden | _ | 1x | Who maintains the model? How often does it drift? |

**Score > 35**: Strong candidate for AI
**Score 25-35**: Viable but needs careful scoping
**Score < 25**: Consider simpler automation first

### Build vs Buy Decision

Not every AI need requires custom development. Sometimes an off-the-shelf solution or [managed AI integration](https://shift-ai.cloud/ai-integration/) gets you 80% of the value at 20% of the cost.

| Factor | Build | Buy | Hybrid |
|--------|-------|-----|--------|
| Time to value | 3-12 months | 1-4 weeks | 1-3 months |
| Customization | Full control | Limited | Moderate |
| Ongoing cost | High (team) | Predictable (license) | Mixed |
| IP ownership | Yes | No | Partial |
| Best when | Core differentiator | Commodity capability | Need custom + speed |

## Common Anti-Patterns

### 1. The "AI Will Fix Everything" Trap
Starting with technology instead of the problem. Always start with: "What specific metric will improve, and by how much?"

### 2. The Sunken Cost Spiral
Continuing to invest in an AI project because you've already spent $X. Set kill criteria upfront: "If we haven't achieved Y by month Z, we pivot."

### 3. The Pilot That Never Graduates
Running a "pilot" for 18 months. Real pilots have fixed timelines (4-8 weeks) and hard go/no-go criteria.

### 4. Ignoring Total Cost of Ownership
Celebrating a model that saves $100K/year while spending $120K/year on infrastructure, maintenance, and retraining.

## Getting Started

1. **Download the templates** in the `templates/` directory
2. **Fill in your baseline metrics** using `templates/baseline-capture.yaml`
3. **Score your project** using `templates/project-scoring.yaml`
4. **Track production value** using `templates/monthly-tracking.yaml`

Or if you want help building a complete AI strategy for your organization, [we've done this dozens of times](https://shift-ai.cloud/ai-consulting/) and can compress months of trial and error into a focused engagement.

## Contributing

Found a gap in the framework? Have a metric we should add? Open an issue or PR — we're actively maintaining this based on real project outcomes.

## License

MIT — use this framework however you want. If it helps you make better AI investment decisions, we've done our job.

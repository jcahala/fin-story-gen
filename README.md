# fin-story-gen

**Automated Narrative Factory** is a modular, data-driven equity research prototype with the goal to synthesize market, macroeconomic, sector, and company-level datasets into institutional-style investment narratives. The project is designed to automate the first-pass stock story by linking price action to likely performance drivers, transforming raw financial data into structured, explainable commentary.

This is not intended to be used as a stock prediction tool. Instead it is prototyped as a **grounded stock story generation system**: a deterministic-first research workflow that identifies likely performance drivers from validated data, then uses AI-assisted narrative generation to convert those findings into professional investment commentary.

## Project Purpose

Financial market narratives often require analysts to reconcile multiple sources of information: stock price movement, index performance, macroeconomic indicators, sector relationships, SEC filings, earnings context, and market sentiment. Manual synthesis is time-consuming, inconsistent, and vulnerable to unsupported conclusions when AI tools are used without structured evidence.

As `fin-story-gen` evolves, it will be tailored to addresses this by creating a deterministic research layer before narrative generation. The system is being structured to identify and rank likely performance drivers, then pass structured evidence to an LLM for controlled narrative synthesis.

## Core Design Principles

- **Deterministic first:** Calculations, rankings, and signal classifications are performed before narrative generation.
- **Evidence grounded:** The LLM receives structured analytical outputs rather than open-ended prompts.
- **Hallucination-aware design:** The workflow is designed to constrain unsupported narrative claims.
- **Analyst reviewable:** Outputs are designed as first-pass commentary for human review, not final investment recommendations.
- **Modular architecture:** Data ingestion, analysis, scoring, and narrative generation are separated into clear workflow stages.

## Workflow Overview

The project follows a staged research workflow:

1. **Market Intelligence**
   - Identifies notable stock movers.
   - Calculates stock, index, sector, and style benchmark returns.
   - Screens securities based on movement, liquidity, and index relevance.

2. **Macro Driver Analysis**
   - Pulls macroeconomic and market indicators.
   - Evaluates interest rates, yield curves, inflation, credit conditions, labor data, volatility, and risk appetite.
   - Maps macro signals to sector- and company-level sensitivity.

3. **Company Context**
   - Retrieves relevant company metadata.
   - Incorporates SEC filing context where available.
   - Reviews business descriptions, risk factors, management discussion, and recent filing language.

4. **Earnings Context**
   - Collects recent and upcoming earnings information.
   - Captures earnings dates, surprise data, and available earnings-related metadata.

5. **Narrative Generation**
   - Converts ranked evidence into a structured first-pass investment narrative.
   - Uses the LLM only after deterministic research outputs are created.
   - Produces explainable commentary suitable for analyst review.

## Data Sources and Tooling

The project is designed to integrate multiple financial, economic, and narrative-generation inputs, including:

- **Market data:** Stock, index, ETF, sector, and style benchmark price data.
- **Macroeconomic data:** Rates, inflation, labor, credit, growth, volatility, and risk indicators.
- **Company disclosures:** SEC filing context, including business descriptions, risk factors, and management discussion.
- **News context:** Market and company-related news signals where available.
- **Financial sentiment tools:** Financial-domain sentiment and tone scoring.
- **Local LLM workflow:** Controlled narrative synthesis using structured analytical inputs.

## Current Prototype Scope

The current version is an early-stage prototype focused on building the end-to-end research workflow in a single Jupyter notebook. The initial implementation prioritizes workflow design, data grounding, driver identification, and narrative control before expanding into a full application or dashboard interface.

## Project Status

This project is currently in active development. The core architecture is being built around a staged research workflow that separates data collection, deterministic analysis, sentiment scoring, and AI-assisted narrative generation.

Current focus areas:

- Building the market intelligence and mover-identification workflow.
- Mapping price action to macro, sector, and company-level drivers.
- Integrating SEC filing and earnings context.
- Designing controlled LLM prompts that reduce hallucination risk.
- Producing first-pass institutional investment commentary for analyst review.

```text
fin-story-gen/
├── README.md
├── docs/
│   ├── architecture-overview.md
│   ├── workflow-overview.md
│   └── roadmap.md
├── assets/
│   └── screenshots/
└── .gitignore
```

The current prototype is organized around a single Jupyter notebook, with persistent cache storage, a planned narrative repository for generated stock stories, and output folders for narrative files and future dashboard or web app assets.

## Development Roadmap

- Build the single-notebook prototype workflow.
- Add configuration and environment setup.
- Implement market mover identification.
- Add macro driver mapping.
- Integrate SEC filing and earnings context.
- Generate first-pass stock story narratives.
- Store generated narratives and metadata in a persistent repository.
- Explore dashboard or web app delivery.

## Author Note

`fin-story-gen` is an independently designed portfolio project by Jackie Cahalane. The project reflects an original workflow concept for reducing AI hallucination risk in financial narrative generation by grounding LLM output in structured, deterministic analysis.

## Disclaimer

This project is for research, education, and portfolio demonstration purposes only. It does not provide investment advice, price forecasts, or buy/sell recommendations.

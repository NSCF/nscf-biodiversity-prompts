# Data Analysis Prompts

Prompts in this category help analyze tabular biodiversity data. Common tasks include summarization, pattern detection, statistical interpretation, and data visualization description.

## Typical Use Cases

- **Biodiversity summary** – Summarize species richness, composition, and community structure
- **Temporal trend analysis** – Detect patterns in species observations over time
- **Abundance/distribution patterns** – Identify which species are common/rare, widespread/localized
- **Data quality assessment** – Flag missing data, outliers, or inconsistencies
- **Statistical interpretation** – Explain trends or relationships in biodiversity data
- **Comparative analysis** – Compare biodiversity between sites, regions, or time periods

## What Good Test Data Looks Like

- **Real biodiversity datasets** (camera trap counts, survey records, acoustic indices, population data, etc.)
- CSV or JSON format with clear structure:
  - Species/taxa identifiers (scientific names, common names, IDs)
  - Counts, presence/absence, or abundance metrics
  - Temporal context (dates, seasons, years)
  - Spatial context (sites, regions, coordinates)
  - Optional: habitat types, survey effort, data quality indicators
- Known patterns or trends (for validation)
- A mix of simple and complex scenarios

## Common Prompting Patterns

Data analysis prompts typically:
1. Define the analysis task (summarize, detect trends, compare, etc.)
2. Provide context (species expected, geographic region, time period)
3. Specify output format (summary table, text interpretation, JSON with findings)
4. Request explicit reasoning (explain what the data shows)
5. Handle missing/incomplete data gracefully

## Example Structure

```
You are an expert in biodiversity analysis...

Analyze this dataset of [survey type]:
[CSV or JSON with biodiversity data]

Task:
- Identify [patterns / trends / key findings]
- Compare [sites / time periods]
- Summarize [species richness / community composition]

Context:
- Study area: [location/habitat]
- Time period: [dates/season]
- Survey method: [camera trap / acoustic / visual survey / etc.]

Respond with:
- Key findings (text summary)
- Species list (if applicable)
- Trends (temporal/spatial)
- Data quality assessment
- Recommendations for interpretation

Examples:
[Example 1: complete, good-quality dataset]
[Example 2: incomplete dataset with gaps/outliers]

Analyze: [user provides data]
```

## What Makes a Strong Submission

✓ Tested on real biodiversity datasets (not synthetic data)  
✓ Clear about what analyses are possible given the data  
✓ Handles missing data, outliers, and edge cases  
✓ Provides interpretable, actionable output  
✓ Documents assumptions (e.g., "assumes effort is constant across time")  
✓ Includes sample dataset for testing  

## Special Considerations

**Data Assumptions:**
- Sampling effort: Is it constant or variable?
- Temporal resolution: Daily? Seasonal? Annual?
- Completeness: Which species/sites are well-sampled?
- Bias: Are some species/habitats under-represented?

**Output Interpretation:**
- Prompts should explain *what the data means* (e.g., "low species richness could indicate poor habitat quality, limited sampling effort, or seasonal absence")
- Distinguish between patterns and causal explanations
- Flag when data are insufficient for confident interpretation

**Common Pitfalls to Avoid:**
- Assuming trends are significant without statistical testing
- Overinterpreting small sample sizes
- Ignoring confounding variables (e.g., sampling effort differences)

## Questions?

Check [TEMPLATE.md](../TEMPLATE.md) for the full submission structure, or see [CONTRIBUTING.md](../CONTRIBUTING.md) for the submission process.

---

**Ready to contribute?** Use real biodiversity data, be explicit about assumptions, and test your prompt's interpretability. Good luck!

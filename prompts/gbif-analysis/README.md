# GBIF Analysis Prompts

Prompts in this category work with Global Biodiversity Information Facility (GBIF) data. These prompts help clean, analyze, visualize, and interpret species occurrence records.

## Typical Use Cases

- **Data quality assessment** – Flag potentially problematic records (coordinate errors, taxonomic issues)
- **Spatial analysis** – Identify range patterns, gaps, or range extensions
- **Temporal analysis** – Analyze species occurrence trends over time
- **Biodiversity assessment** – Summarize species richness and composition
- **Data cleaning** – Standardize taxonomy, remove duplicates, validate coordinates
- **Gap analysis** – Identify under-sampled regions or species

## What Good Test Data Looks Like

- **Real GBIF occurrence records** (download a dataset from GBIF.org)
- CSV or JSON format with typical GBIF fields:
  - `scientificName`, `taxonRank`, `occurrenceID`
  - `decimalLatitude`, `decimalLongitude`, `coordinateUncertaintyInMeters`
  - `eventDate`, `year`, `month`, `day`
  - `basisOfRecord`, `individualCount`, `occurrenceStatus`
  - Optional: `countryCode`, `stateProvince`, `locality`, `datasetName`
- Known issues in the data (coordinate errors, taxonomic problems, duplicates)
- Clear documentation of what the prompt should identify or fix

## Common Prompting Patterns

GBIF analysis prompts typically:
1. Define the analysis task (quality check, spatial analysis, temporal trend, etc.)
2. Provide context (target species/region, expected issues)
3. Request structured output (CSV with flags, JSON summary, text analysis)
4. Include decision rules ("flag records with coordinate uncertainty > 5km")
5. Handle edge cases ("what if only 1 record? handle gracefully")

## Example Structure

```
You are an expert in biodiversity data quality and GBIF analysis...

Analyze this GBIF dataset:
[CSV with occurrence records]

Task: [Identify coordinate errors / Assess data quality / Analyze temporal trends]

Rules to apply:
- Flag records with [criteria]
- Correct [common issues]
- Summarize [patterns]

Respond with:
- [Output structure: CSV with flags / JSON summary / Text analysis]
- Confidence/reliability of assessment
- Recommendations for data use

Examples:
[Example 1: clean, good-quality records]
[Example 2: records with issues (coordinates, taxonomy, etc.)]

Analyze: [user provides GBIF data]
```

## What Makes a Strong Submission

✓ Tested on real GBIF download (not toy data)  
✓ Clear decision rules for flags/corrections  
✓ Handles edge cases (single species, small regions, rare records)  
✓ Documents which GBIF fields are required vs. optional  
✓ Realistic about what can/can't be assessed from GBIF data  
✓ Includes a sample GBIF dataset (or link to test data)  

## Special Considerations

**GBIF Data Format:**
- Standard Darwin Core fields: https://dwc.tdwg.org/
- GBIF download format: CSV with standard column names
- Consider your prompt's assumptions about data completeness

**Known GBIF Quirks:**
- Coordinate precision varies widely
- Taxonomy updates over time
- Duplicate records across datasets
- Different `basisOfRecord` types have different reliability

## Questions?

Check [TEMPLATE.md](../TEMPLATE.md) for the full submission structure, or see [CONTRIBUTING.md](../CONTRIBUTING.md) for the submission process.

---

**Ready to contribute?** Download real GBIF data, write your prompt, and test it. Good luck!

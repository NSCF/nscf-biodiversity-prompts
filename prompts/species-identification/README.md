# Species Identification Prompts

Prompts in this category help identify species from images. Common uses include camera trap analysis, specimen photography, and field observation validation.

## Typical Use Cases

- **Camera trap species identification** – Classify animals from automated wildlife monitoring
- **Specimen photography** – Identify museum or herbarium specimens
- **Field observation validation** – Verify species identifications from field notes/photos
- **iNaturalist photo analysis** – Batch process citizen science observations
- **Biodiversity surveys** – Rapid species identification from survey photography

## What Good Test Data Looks Like

- **Real camera trap images** from your region of interest
- A mix of clear and challenging cases (blurry, nocturnal, partial obscuration)
- Diversity of species and age/sex classes
- Known correct identifications for validation

## Common Prompting Patterns

Species identification prompts typically:
1. Define the expert role ("You are a biodiversity expert...")
2. Provide taxonomic context (region, habitat, expected species)
3. Give few-shot examples (2-3 clear image examples)
4. Request structured output (JSON with species name, confidence, notes)
5. Handle uncertainty gracefully ("if uncertain, flag for human review")

## Example Structure

```
You are an expert [taxa] identification specialist...

Analyze the provided [image type]...

Respond with:
- Species (scientific name)
- Confidence (0-1 scale)
- Notes (visibility, partial obscuration, etc.)
- Requires human review? (yes/no)

Examples:
[Example 1: clear case]
[Example 2: ambiguous case]

Analyze: [user provides image]
```

## What Makes a Strong Submission

✓ Tested on 10+ real images from your field context  
✓ Handles edge cases (nocturnal, motion blur, juvenile animals, hybrids)  
✓ Confidence thresholds are realistic  
✓ Clear about what you're NOT identifying (e.g., "does not attempt age/sex classification")  
✓ Documents regional bias (e.g., "optimized for Southern African savanna mammals")  

## Questions?

Check [TEMPLATE.md](../TEMPLATE.md) for the full submission structure, or see [CONTRIBUTING.md](../CONTRIBUTING.md) for the submission process.

---

**Ready to contribute?** Use the template above as a starting point. Good luck!

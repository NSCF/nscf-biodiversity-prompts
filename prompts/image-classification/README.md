# Image Classification Prompts

Prompts in this category classify or analyze images beyond species identification. Common tasks include habitat assessment, condition scoring, activity classification, and multi-label classification.

## Typical Use Cases

- **Habitat assessment** – Classify landscape/habitat type from photos
- **Condition scoring** – Assess ecosystem health, vegetation condition, or species condition
- **Activity classification** – Identify what animals are doing (foraging, resting, interacting, etc.)
- **Threat detection** – Identify anthropogenic impacts (snares, poaching signs, pollution, etc.)
- **Multi-label classification** – Apply multiple labels to a single image (species + activity + habitat)
- **Quality assessment** – Judge image quality for scientific use

## What Good Test Data Looks Like

- **Real field images** from your context (camera traps, field photos, surveys, etc.)
- A diverse set covering the range of classes you want to detect
- Clear examples and ambiguous edge cases
- Known correct classifications for validation
- Documented metadata (location, date, conditions, etc.)

## Common Prompting Patterns

Image classification prompts typically:
1. Define the classification task clearly ("classify habitat type as:" or "score vegetation condition 1-5")
2. Provide visual context (region, expected categories, decision criteria)
3. Include few-shot examples (2-3 images per category)
4. Request structured output (JSON with classification + confidence + reasoning)
5. Handle ambiguity ("if unclear, mark as 'unclear' and explain")

## Example Structure

```
You are an expert in [habitat/condition/activity] assessment...

Classify the provided image based on these criteria:
- [Category 1]: [definition and examples]
- [Category 2]: [definition and examples]
- [Category 3]: [definition and examples]

Respond with:
- Primary classification
- Confidence (0-1 scale)
- Secondary classifications if applicable
- Reasoning (what features led to this classification?)

Examples:
[Example 1: clear-cut case for category 1]
[Example 2: ambiguous case, explain reasoning]

Classify: [user provides image]
```

## What Makes a Strong Submission

✓ Tested on 10+ real field images from your context  
✓ Clear, operationalizable definitions for each category  
✓ Handles edge cases and ambiguity gracefully  
✓ Confidence thresholds are realistic  
✓ Includes images showing category boundaries (what's borderline?)  
✓ Documents any regional or contextual assumptions  

## Special Considerations

**Image Format & Size:**
- Specify expected image types (JPG, PNG, etc.)
- Document image resolution assumptions (mobile vs. professional camera)
- Consider how image quality affects classification

**Multi-Label Scenarios:**
- If an image could belong to multiple categories, be explicit about how the prompt handles this
- Consider priority/hierarchy if categories overlap

**Bias & Context:**
- Be honest about regional bias (trained on Southern African images, may not work elsewhere)
- Note seasonal effects if applicable (dry season vs. wet season)

## Questions?

Check [TEMPLATE.md](../TEMPLATE.md) for the full submission structure, or see [CONTRIBUTING.md](../CONTRIBUTING.md) for the submission process.

---

**Ready to contribute?** Gather diverse field images, define your categories clearly, and test thoroughly. Good luck!

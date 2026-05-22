# [Prompt Name]

**Source:** [nscf-internal / community]  
**Contributor:** [Your name]  
**Date:** [YYYY-MM-DD]  
**Category:** [species-identification / acoustic-monitoring / gbif-analysis / image-classification / data-analysis]

---

## Use Case

[What problem does this prompt solve? Who needs it? Be specific.]

**Example:** "Taxonomically classify bird species from camera trap images in Southern African savannas, identifying species, confidence level, and noting partial visibility or obscured animals."

---

## Input Format

Describe what data the prompt expects.

**Data Type:**
- [ ] CSV / Tabular data
- [ ] JSON
- [ ] Images
- [ ] Text / Unstructured
- [ ] Mixed / Other: [specify]

**Structure:**
[Describe field names, column structure, image dimensions, file formats, etc.]

**Example:**
```
CSV with columns:
- image_id: unique identifier
- image_path: local path to image file
- location: GPS coordinates or location name
- date: YYYY-MM-DD format
- camera_type: [describe camera model if relevant]
```

**Size & Volume:**
- Maximum file size: [e.g., "individual images <5MB"]
- Volume: [e.g., "tested on 50-500 images per batch"]
- Batch processing? [Yes/No]

**Required vs Optional:**
[List which fields must be present; which are optional]

---

## Output Format

Describe what the AI produces.

**Output Type:**
- [ ] JSON
- [ ] CSV
- [ ] Markdown/Text summary
- [ ] List / Structured text
- [ ] Other: [specify]

**Schema/Structure:**
[Show example output or describe fields/structure]

**Example:**
```json
{
  "image_id": "trap_001_20230515",
  "species": "Panthera pardus",
  "species_common_name": "Leopard",
  "confidence": 0.92,
  "notes": "Partially obscured by vegetation, rear half visible",
  "requires_review": false
}
```

---

## The Prompt

[**Paste your complete, ready-to-use prompt below.**]

Make sure it includes:
- Clear role definition (e.g., "You are a biodiversity expert...")
- Context about the task
- Step-by-step instructions
- Examples (few-shot prompting improves output)
- Any specific formatting requests for the output

---

```
[INSERT YOUR PROMPT HERE]

Example:

---
You are an expert biodiversity analyst specializing in African mammal identification from camera trap imagery.

Your task is to analyze camera trap images and identify the species present.

For each image provided, respond with:
1. Species name (scientific name)
2. Common name
3. Confidence level (0-1 scale)
4. Visibility notes (e.g., "partial obscuration", "nocturnal", "motion blur")
5. Any caveats or uncertainty

Format your response as JSON with the following schema:
{
  "species": "scientific_name",
  "common_name": "common_name",
  "confidence": 0.0-1.0,
  "visibility_notes": "description",
  "requires_human_review": true/false,
  "reasoning": "brief explanation"
}

Here are three example images to calibrate your responses:

[Example 1: Clear image of leopard]
Response: {"species": "Panthera pardus", "common_name": "Leopard", "confidence": 0.95, ...}

[Example 2: Blurry nocturnal image]
Response: {"species": "Crocuta crocuta", "common_name": "Spotted Hyena", "confidence": 0.65, "visibility_notes": "nocturnal, motion blur", "requires_human_review": true, ...}

[Example 3: Ambiguous species]
Response: {"species": "uncertain", "common_name": "possible impala or warthog", "confidence": 0.3, "requires_human_review": true, ...}

Analyze these images:
[IMAGES PROVIDED BY USER]

Respond in JSON format.
```

---

## Test Data & Output

### Test Input

[**Provide your test data here, or describe where it's located.**]

If you have sample CSV data:
```
image_id,image_path,location,date
trap_001_20230515,images/trap001_20230515_001.jpg,Kruger_South,2023-05-15
trap_001_20230516,images/trap001_20230516_045.jpg,Kruger_South,2023-05-16
trap_002_20230515,images/trap002_20230515_120.jpg,Kruger_East,2023-05-15
```

If you have images, note:
- **Number of test images:** [e.g., 10 images]
- **Image types:** [camera trap, iNaturalist, field photography, etc.]
- **Location:** [where images are from]
- **Where to find them:** [attached to PR / in test-data folder / external link]

### Expected Output

[**Show what the AI actually produced for your test data.**]

```json
[
  {
    "image_id": "trap_001_20230515",
    "species": "Panthera pardus",
    "common_name": "Leopard",
    "confidence": 0.92,
    "visibility_notes": "Partially visible, clear facial features",
    "requires_human_review": false,
    "reasoning": "High-quality daytime image with distinctive rosette pattern"
  },
  {
    "image_id": "trap_001_20230516",
    "species": "uncertain",
    "common_name": "Possible large carnivore",
    "confidence": 0.4,
    "visibility_notes": "Nocturnal, extreme motion blur, only rear half visible",
    "requires_human_review": true,
    "reasoning": "Insufficient visual information for confident identification"
  }
]
```

### Test Validation

[**Did the output match expectations? How well did it work?**]

- Test data source: [e.g., "Kruger National Park camera traps, May 2023"]
- Number of test cases: [e.g., "10 images"]
- Success rate: [e.g., "8/10 correct identifications, 2 required human review"]
- Any surprises? [e.g., "Prompt struggled with [scenario]"]

---

## Performance Notes

[**Be specific about how well this prompt works.**]

### What It Handles Well
- ✓ Clear, well-lit daytime images
- ✓ Medium-sized mammals (10-200kg)
- ✓ Species commonly found in [region/habitat]
- ✓ [Other strengths]

### Known Limitations
- ✗ Struggles with nocturnal/blurry images
- ✗ Limited training on small rodents
- ✗ Not tested on [specific scenario]
- ✗ [Other weaknesses]

### Best Practices
- ⚠ Works best with high-resolution images (>1000px width)
- ⚠ Include camera metadata (date, time) for context
- ⚠ Batch processing: send 5-10 images per request
- ⚠ For uncertain results, always do human review

### Tested Against
- **Data source:** [e.g., "Kruger NP camera traps"]
- **Volume:** [e.g., "150 images"]
- **Species diversity:** [e.g., "22 species"]
- **Time period:** [e.g., "May-July 2023"]
- **Habitat:** [e.g., "savanna, acacia woodland"]

---

## Limitations & Assumptions

[**Be honest about the boundaries of this prompt.**]

### Data Assumptions
- Assumes images are [color/grayscale/RGB/other]
- Assumes camera positions are [fixed/mobile]
- Assumes temporal continuity [yes/no—does timing matter?]
- [Other structural assumptions]

### Scope Limitations
- **Geographic:** Tested only in [region/country]
- **Taxonomic:** Focused on [mammal group, bird family, etc.]
- **Habitat:** Tested in [savanna, forest, etc.]
- **Seasonal:** Only tested in [season]
- **Time of day:** Only works for [daytime/any time]

### When NOT to Use This Prompt
- ✗ For [specific scenario] – different prompt recommended
- ✗ With [data type] – not designed for this
- ✗ In [habitat type] – untested, likely unreliable
- ✗ [Other explicit non-use cases]

### Known Edge Cases
- [Scenario that causes issues]: [What happens, suggested workaround]
- [Another problematic scenario]: [What happens, suggested workaround]

---

## Versions & Related Prompts

[**If this updates an existing prompt or relates to others, note it here.**]

- **Replaces:** [Earlier version if updating an existing prompt]
- **Variant of:** [If based on or inspired by another prompt]
- **Related prompts:** [Links to similar prompts in the repo]
- **Future iterations:** [Planned improvements or variants]

---

## Additional Resources

[**Optional: links to datasets, papers, or documentation that informed this prompt.**]

- [GBIF API documentation](https://www.gbif.org/developer/summary)
- [iNaturalist dataset](https://www.inaturalist.org/pages/api+reference)
- [Research paper on species identification](link)
- [Dataset used for testing](link)

---

## Notes & Comments

[**Any other context that's helpful for users or reviewers?**]

- This prompt was developed in response to [specific NSCF need]
- It complements [other workflows]
- [Future improvements or known issues]
- [Contact info if contributors want to discuss improvements]

---

## Contributor Info

**Name:** [Your full name]  
**Role:** [NSCF staff / External collaborator / Partner organization]  
**Contact:** [Optional: email or GitHub handle for questions]  
**Bio:** [Optional: 1-2 sentences about your biodiversity expertise]

---

**Thank you for contributing!** Your prompt will be reviewed within 7 business days.

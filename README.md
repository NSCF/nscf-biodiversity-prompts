# NSCF Biodiversity Prompts

A curated repository of AI prompts designed for NSCF biodiversity workflows. All prompts are tested against real data, documented with clear limitations, and peer-reviewed for quality and applicability.

## Overview

This repository contains standardized AI prompts for common biodiversity analysis tasks. Whether you're classifying species from camera trap images, analyzing acoustic monitoring data, or querying GBIF datasets, you'll find tested prompts here—plus the test data and outputs they were validated against.

## Quick Start

1. **Browse prompts by category** in the `prompts/` folder
2. **Find what you need** – each prompt includes use case, test data, and expected output
3. **Copy the prompt** into your AI tool (ChatGPT, Claude, etc.)
4. **Adapt for your data** – see the limitations and performance notes first

## Categories

### [Species Identification](prompts/species-identification/)
Image-based species classification. Includes prompts for camera trap images, specimen photography, and iNaturalist photos.

### [Acoustic Monitoring](prompts/acoustic-monitoring/)
Biodiversity analysis from audio recordings. Covers species identification, activity pattern analysis, and acoustic indices.

### [GBIF Analysis](prompts/gbif-analysis/)
Prompts for working with Global Biodiversity Information Facility data. Includes data cleaning, spatial analysis, and quality assessment.

### [Image Classification](prompts/image-classification/)
General image classification tasks including habitat assessment, condition scoring, and multi-label classification.

### [Data Analysis](prompts/data-analysis/)
Tabular data interpretation, statistical summarization, and pattern detection in biodiversity datasets.

---

## Contributing

We welcome prompts from **NSCF staff** and **external collaborators**. All submissions are peer-reviewed and credited.

**Before you contribute:** Read [CONTRIBUTING.md](CONTRIBUTING.md) for the full submission process.

**Quick version:**
1. Fork this repository
2. Create a new branch: `add/your-prompt-name`
3. Copy the [TEMPLATE.md](TEMPLATE.md) file to your category folder
4. Fill in all sections (prompt, test data, test output, documentation)
5. Submit a Pull Request
6. We'll review and provide feedback within [X] business days

---

## How Prompts Are Organized

Each prompt lives in its category folder with this structure:

```
prompts/species-identification/
├── prompt-name/
│   ├── prompt.md                 # Actual prompt + documentation
│   ├── test_input.csv            # Sample input data
│   └── test_output.json          # Expected output
```

## Acceptance Criteria

Prompts are accepted if they:
- ✓ Are tested against real biodiversity data
- ✓ Clearly document use case, assumptions, and limitations
- ✓ Include working examples (test input + output)
- ✓ Follow the template structure
- ✓ Are novel or significantly improve an existing prompt

---

## Attribution & Credit

**All contributors are credited.** Each prompt includes:
- Contributor name
- Date submitted
- Source classification (nscf-internal / community / partner)

---

## Version Management

**Updating existing prompts:**
- If test data structure and assumptions **remain the same** → update the existing prompt
- If test data structure or assumptions **change** → create a new prompt variant

See [CONTRIBUTING.md](CONTRIBUTING.md#versions--updates) for details.

---

## Repository Maintainer

**Christiaan Steenkamp** (NSCF)  
Curator & Lead Reviewer

---

## License

[Add appropriate license—e.g., CC BY 4.0 for open sharing, or CC BY-NC if NSCF-only]

---

## Questions or Suggestions?

- **Issues & Feedback:** Use GitHub Issues
- **Want to contribute?** See [CONTRIBUTING.md](CONTRIBUTING.md)
- **Contact:** [Add contact details if appropriate]

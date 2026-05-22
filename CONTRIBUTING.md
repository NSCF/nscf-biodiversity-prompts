# Contributing to NSCF Biodiversity Prompts

Thank you for contributing! We welcome prompts from NSCF staff and external collaborators. All submissions are peer-reviewed to ensure quality, clarity, and real-world applicability.

---

## Before You Submit

Your submission must include **all** of the following:

1. **The prompt itself** – complete, with role definition and clear instructions
2. **Test data** – realistic sample input (CSV, images, JSON, etc.)
3. **Test output** – actual output from the AI using your test data
4. **Full documentation** – use case, limitations, data assumptions, edge cases, performance notes

Submissions missing any of these will be returned for revision.

---

## Submission Process

### Step 1: Fork the Repository
Go to the NSCF Biodiversity Prompts repo and click **Fork** (top right). This creates your own copy.

### Step 2: Clone Your Fork Locally
```bash
git clone https://github.com/YOUR-USERNAME/nscf-biodiversity-prompts.git
cd nscf-biodiversity-prompts
```

### Step 3: Create a Feature Branch
```bash
git checkout -b add/your-prompt-name
```

Use a descriptive name: `add/camera-trap-species-id`, `add/gbif-data-quality-check`, etc.

### Step 4: Copy the Template
Navigate to the appropriate category folder and copy `TEMPLATE.md`:

```bash
cp TEMPLATE.md prompts/species-identification/your-prompt-name.md
```

### Step 5: Fill in the Template
Open the file and complete **all sections**. See [Template Guide](#template-guide) below for details.

### Step 6: Add Test Data & Output Files
Create a subfolder for your test files:

```
prompts/species-identification/
├── your-prompt-name.md           # Your filled template
├── test_input.csv                # Sample input
└── test_output.json              # Expected output
```

**Test data guidelines:**
- Use **real biodiversity data** (or realistic samples)
- Keep files **small but representative** (a few rows/images, not entire datasets)
- Include a **brief description** of the test data in your prompt documentation
- If test data is sensitive, anonymize or use a subset

### Step 7: Commit & Push
```bash
git add prompts/species-identification/your-prompt-name.*
git commit -m "Add: camera trap species identification prompt"
git push origin add/your-prompt-name
```

### Step 8: Create a Pull Request
Go to GitHub and click **Create Pull Request**. Fill in:
- **Title:** Brief name of the prompt
- **Description:** Use the PR template (it auto-fills)
- **Checklist:** Confirm you've completed all sections

---

## Template Guide

When you copy `TEMPLATE.md`, you'll see these sections. **Complete all of them:**

### Metadata (Top of File)
```
**Source:** [nscf-internal / community]
**Contributor:** [Your name]
**Date:** [YYYY-MM-DD]
**Category:** [species-identification / acoustic-monitoring / gbif-analysis / image-classification / data-analysis]
```

### Use Case
- What problem does this prompt solve?
- Who needs it?
- Example: "Taxonomically classify bird species from camera trap images in Southern African savannas"

### Input Format
- What data type? (CSV, JSON, Images, etc.)
- What structure? (field names, image dimensions, etc.)
- Any size/volume limits?

### Output Format
- What does the AI produce?
- What structure? (JSON schema, CSV columns, etc.)

### The Prompt
- **Paste your actual prompt here**
- Include role definition (e.g., "You are a biodiversity expert...")
- Include context and examples
- Make it clear and self-contained

### Test Data & Output
- **Test Input:** Show your sample data (or describe its location)
- **Expected Output:** Show what the AI produced for that input
- This proves the prompt works

### Performance Notes
- How well does it work?
- What did you test it on?
- Any limits or caveats?

**Example:**
```
- ✓ Tested on 150 camera trap images from Kruger NP (2023)
- ✓ Works well for medium-sized mammals (10-200kg)
- ✗ Struggles with blurry/nocturnal images
- ⚠ Best used with high-resolution images (>1000px)
```

### Limitations & Assumptions
- **Be honest.** What are the known weaknesses?
- What data types/regions was it tested on?
- When should users NOT use this prompt?

**Example:**
```
- Only tested on savanna ecosystems
- Assumes images are labeled by camera location
- May not work for nocturnal species
- Not suitable for real-time monitoring without human review
```

---

## Acceptance Criteria

Your prompt will be **accepted** if it meets **all** of these:

- ✓ **Tested on real data** – You've run the prompt against actual biodiversity data
- ✓ **Complete documentation** – All template sections are filled in
- ✓ **Clear limitations** – You've honestly stated when/where it works and doesn't
- ✓ **Working examples** – Test input + output are included and valid
- ✓ **Follows template** – Structure matches TEMPLATE.md
- ✓ **Novel or significantly improved** – It's not a duplicate of existing prompts

Your prompt will be **returned for revision** if:
- ✗ Missing test data or test output
- ✗ Vague or incomplete documentation
- ✗ No clarity on limitations or assumptions
- ✗ Prompt is untested or only tested on toy data
- ✗ Structure doesn't follow template

---

## Review Process

### Timeline
- **Submission received:** You'll get an acknowledgment within 2 business days
- **Under review:** We'll test the prompt and review documentation
- **Feedback:** We may ask clarifying questions or request additions
- **Accepted or request revision:** Within 7 business days

### What Happens in Review
1. We test your prompt against the test data you provided
2. We check that output matches expected results
3. We verify documentation is clear and honest
4. We may ask for additional test cases or edge case scenarios
5. If everything checks out, we merge to `main`

### If Your PR Needs Changes
We'll leave a comment explaining what's needed. Common requests:
- "Can you add a test case for [specific scenario]?"
- "Can you clarify what happens when [edge case]?"
- "This assumes [X]—can you document that?"
- "Can you test on [another dataset type]?"

**You can revise and re-push to the same branch.** The PR will auto-update.

---

## Versions & Updates

### Updating an Existing Prompt

**If the test data structure and assumptions remain the same:**
- Edit the existing prompt file
- Update the test output if performance improved
- Submit as a pull request with `Update:` in the title
- Example: "Update: camera trap species id—better handling of juvenile animals"

**If the test data structure or assumptions change:**
- Create a **new prompt file** with a descriptive name
- Example: `camera-trap-species-id-nocturnal.md` (for night vision data)
- Document the relationship to the earlier prompt
- Both versions stay in the repo

---

## Attribution & Credit

**You will be credited for your contribution.**

Each accepted prompt includes:
- Your name
- Date submitted
- Source classification (community / nscf-internal)

If you contribute multiple prompts, consider adding a brief bio at the bottom of the README.

---

## Tips for Success

1. **Start with a real problem.** Don't create prompts for hypothetical use cases—work from actual NSCF workflows or conservation challenges.

2. **Test thoroughly.** Run your prompt against your test data multiple times. Try edge cases (blurry images, incomplete data, etc.).

3. **Document honestly.** The best prompts include clear limitations. That builds trust.

4. **Include context.** Explain *why* certain assumptions exist. ("This assumes images are RGB because camera trap footage is daytime-only.")

5. **Keep it concise.** Long prompts aren't better—precise prompts are.

6. **Use examples.** Few-shot prompting (including examples in the prompt) makes outputs more reliable.

---

## Questions?

- **How do I format my test data?** See the examples in `test-data/` folder
- **Can I contribute a prompt for [specific use case]?** Yes, if you can test it against real data
- **What if my prompt is rejected?** We'll explain why and welcome resubmission once issues are fixed
- **Can I update my prompt after it's merged?** Yes—see [Versions & Updates](#versions--updates)

---

## Code of Conduct

We expect all contributors to:
- Be respectful and professional
- Accept constructive feedback
- Test your work before submitting
- Be honest about limitations

---

**Ready to contribute?** Start with Step 1 above. Welcome aboard!

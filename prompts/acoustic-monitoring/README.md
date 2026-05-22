# Acoustic Monitoring Prompts

Prompts in this category analyze biodiversity data from audio recordings. These are used for species detection, activity pattern analysis, and acoustic index calculation.

## Typical Use Cases

- **Species identification from vocalizations** – Identify species by bird calls, frog songs, insect sounds, or mammal vocalizations
- **Activity pattern analysis** – Extract temporal patterns (when species are most active)
- **Acoustic index calculation** – Process acoustic indices (NDSI, BIO, ADI) from soundscapes
- **Passive acoustic monitoring (PAM)** – Analyze long-term audio files from recorders
- **Call type classification** – Distinguish between call types within a species

## What Good Test Data Looks Like

- **Real audio files** from your field context (not synthetic data)
- Metadata: date, time, location, recording conditions
- A mix of clean and challenging recordings (background noise, overlapping calls)
- Known species present (for validation)
- Varying recording quality and equipment types

## Common Prompting Patterns

Acoustic prompts typically:
1. Provide taxonomic context (species likely in the region)
2. Describe the audio characteristics (frequency range, call duration, etc.)
3. Include textual descriptions of calls (e.g., "high-pitched trill, 2-3 seconds")
4. Request structured output (species list, confidence, temporal pattern)
5. Handle ambiguous calls gracefully ("if uncertain, note as 'unknown songbird'")

## Example Structure

```
You are an expert in [region/taxon] animal vocalizations...

Analyze this audio recording (or description of audio):
[File metadata: date, time, location, duration]
[Audio description or transcription: "heard 3-4 high-pitched calls, rapid trill pattern"]

Species expected in this region/habitat: [list]

Respond with:
- Identified species (scientific name)
- Confidence (0-1 scale)
- Call characteristics (frequency, duration, pattern)
- Number of individuals (if determinable)
- Activity type (e.g., territorial, feeding, alarm call)

Examples:
[Example 1: clear call, single species]
[Example 2: ambiguous recording with multiple species]

Analyze: [user provides audio or description]
```

## What Makes a Strong Submission

✓ Tested on 5+ real audio recordings from your field context  
✓ Includes metadata (date, time, location, equipment type)  
✓ Handles overlapping calls and background noise  
✓ Realistic confidence thresholds for call identification  
✓ Documents regional and seasonal bias  
✓ Clear about call features used for identification  

## Special Considerations

**Audio format:** Consider whether submissions provide:
- Raw audio files (not always practical in GitHub)
- Sonogram/spectrogram images (visual representation of audio)
- Textual descriptions of calls (practical alternative)
- Audio metadata only (for prompts that analyze call patterns from field notes)

## Questions?

Check [TEMPLATE.md](../TEMPLATE.md) for the full submission structure, or see [CONTRIBUTING.md](../CONTRIBUTING.md) for the submission process.

---

**Ready to contribute?** Start with the template. Good luck!

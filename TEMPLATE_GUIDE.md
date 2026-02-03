# Custom Template Guide

This guide shows you how to create your own templates for different research domains.

## Template Structure

```javascript
'template-id': {
    name: 'Human-Readable Name',
    fields: ['field1', 'field2', 'field3'],
    structure: `## Section Title

## Another Section
- 
`
}
```

## Example Templates

### Example 1: Neuroscience Research

```javascript
'neuroscience': {
    name: 'Neuroscience Research',
    fields: [
        'title', 
        'authors', 
        'year', 
        'publication',
        'type',
        'brain-region',
        'modality',
        'species',
        'sample-size',
        'key-findings',
        'tags'
    ],
    structure: `## Summary

## Hypothesis
- 

## Methods
### Participants/Subjects
- 

### Procedure
- 

### Analysis
- 

## Results
- 

## Discussion
- 

## Personal Notes
- 
`
}
```

### Example 2: Software Engineering Papers

```javascript
'software-engineering': {
    name: 'Software Engineering',
    fields: [
        'title',
        'authors',
        'year',
        'publication',
        'type',
        'programming-language',
        'methodology',
        'evaluation-metrics',
        'tools-used',
        'tags'
    ],
    structure: `## Summary

## Problem Statement
- 

## Proposed Solution
- 

## Implementation
- 

## Evaluation
- 

## Comparison with Existing Work
- 

## Notes & Code Examples
- 
`
}
```

### Example 3: Climate Science

```javascript
'climate-science': {
    name: 'Climate Science',
    fields: [
        'title',
        'authors',
        'year',
        'publication',
        'type',
        'climate-variable',
        'geographic-region',
        'time-period',
        'model-type',
        'data-source',
        'tags'
    ],
    structure: `## Summary

## Research Question
- 

## Data & Methods
- 

## Key Findings
- 

## Implications
- 

## Limitations
- 

## Notes
- 
`
}
```

### Example 4: Psychology/Social Science

```javascript
'psychology': {
    name: 'Psychology & Social Science',
    fields: [
        'title',
        'authors',
        'year',
        'publication',
        'type',
        'study-design',
        'sample-population',
        'sample-size',
        'measures',
        'statistical-analysis',
        'effect-size',
        'tags'
    ],
    structure: `## Summary

## Research Question & Hypotheses
- 

## Methodology
### Design
- 

### Participants
- 

### Measures & Instruments
- 

## Results
- 

## Discussion
- 

## Limitations & Future Directions
- 

## Personal Reflections
- 
`
}
```

## Field Naming Best Practices

### Use Descriptive, Hyphenated Names
✅ Good: `study-design`, `sample-population`, `effect-size`
❌ Avoid: `design`, `pop`, `es`

### Common Field Types

**Basic Metadata** (use in all templates):
- `title`
- `authors` (array)
- `year` (number)
- `publication` (journal/conference name)
- `type` (research-article, review, meta-analysis, etc.)
- `tags` (array)
- `read-status` (to-read, reading, completed)

**Domain-Specific Examples**:
- Machine Learning: `ml-method`, `dataset`, `metrics`, `architecture`
- Biology: `organism`, `tissue-type`, `genetic-markers`
- Physics: `experiment-type`, `energy-scale`, `detector`
- Economics: `model-type`, `data-period`, `econometric-method`

### Value Types

- **Strings**: Single values like `"Nature Medicine"`
- **Arrays**: Multiple values like `["Smith J", "Chen L"]`
- **Numbers**: Numeric values like `2023`
- **Booleans**: True/false like `true` or `false`

## Structure Guidelines

### Use Markdown Headings
```markdown
## Main Section
### Subsection
#### Sub-subsection
```

### Include Bullet Points for Lists
```markdown
## Key Findings
- Finding 1
- Finding 2
```

### Leave Space for Notes
Always end with:
```markdown
## Personal Notes
- 

## Questions for Follow-up
- 
```

## Adding Your Template

1. Open `pdf-to-obsidian.html` in a text editor
2. Find the `templates` object (around line 260)
3. Add your template following the structure above
4. Add your template to the `<select>` dropdown:
```html
<option value="your-template-id">Your Template Name</option>
```

## Testing Your Template

1. Save your changes
2. Open the HTML file in a browser
3. Select your new template
4. Upload a PDF from your domain
5. Check that the generated note looks good

## Sharing Your Template

Consider submitting your template as a pull request so others can benefit!

1. Fork the repository
2. Add your template
3. Test it thoroughly
4. Submit a PR with:
   - Template code
   - Example of generated note
   - Description of the research domain

---

Happy customizing! If you create something cool, share it with the community! 🎨

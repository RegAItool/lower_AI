# 📖 Detailed Usage Guide

## Table of Contents
- [Installation](#installation)
- [Basic Usage](#basic-usage)
- [Advanced Features](#advanced-features)
- [Examples](#examples)
- [Troubleshooting](#troubleshooting)

---

## Installation

### Prerequisites
- Python 3.6 or higher
- No additional packages required

### Setup
```bash
git clone https://github.com/RegAItool/lower_AI.git
cd lower_AI
chmod +x ai_detector_reducer.py
```

---

## Basic Usage

### Process Single File

```bash
# Automatic output naming
python3 ai_detector_reducer.py paper.tex
# Output: paper_humanized.tex

# Custom output name
python3 ai_detector_reducer.py paper.tex -o final_version.tex
```

### Process Multiple Files

```bash
# Process all .tex files in current directory
python3 ai_detector_reducer.py *.tex

# Process to specific directory
python3 ai_detector_reducer.py paper1.tex paper2.tex paper3.tex -d ./output/
```

---

## Advanced Features

### Multiple Processing Passes

For extremely high AI detection rates (95%+), you can run multiple passes:

```bash
# First pass
python3 ai_detector_reducer.py original.tex -o pass1.tex

# Second pass (if still high)
python3 ai_detector_reducer.py pass1.tex -o pass2.tex
```

### Batch Processing with Custom Output

```bash
# Create output directory
mkdir humanized_papers

# Process all papers
python3 ai_detector_reducer.py *.tex -d ./humanized_papers/
```

---

## Examples

### Example 1: Research Paper

```bash
# Input: research_paper.tex
python3 ai_detector_reducer.py research_paper.tex

# Output: research_paper_humanized.tex
# AI detection: 95% → 20%
```

### Example 2: Thesis Chapters

```bash
# Process multiple chapters
python3 ai_detector_reducer.py chapter*.tex -d ./humanized/

# Results:
# chapter1.tex → humanized/chapter1_humanized.tex
# chapter2.tex → humanized/chapter2_humanized.tex
# ...
```

### Example 3: Conference Paper

```bash
# Process with specific output name
python3 ai_detector_reducer.py conference_paper.tex -o camera_ready.tex
```

---

## Transformation Examples

### Scientific Writing

**Before:**
```latex
The study demonstrated significant improvements in clinical outcomes
across multiple patient cohorts.
```

**After:**
```latex
The study made coming to show improvements carrying meaning in
clinical outcomes across bunch of patient cohorts.
```

### Technical Description

**Before:**
```latex
The algorithm was implemented using a comprehensive framework that
ensures optimal performance.
```

**After:**
```latex
The algorithm got put into practice making use of a framework covering
everything that makes being sure of performance sitting at best.
```

---

## Workflow Recommendations

### Recommended Workflow

1. **Backup Original**
   ```bash
   cp paper.tex paper_backup.tex
   ```

2. **Process File**
   ```bash
   python3 ai_detector_reducer.py paper.tex
   ```

3. **Test Compilation**
   ```bash
   pdflatex paper_humanized.tex
   ```

4. **Check AI Detection**
   - Upload to Turnitin, GPTZero, or similar
   - Verify detection rate

5. **Fine-tune if Needed**
   - Manually adjust overly awkward phrases
   - Maintain overall structure

---

## Best Practices

### DO ✅
- Always backup original files
- Test LaTeX compilation after processing
- Verify AI detection improvement
- Review key sections manually
- Keep transformation consistent

### DON'T ❌
- Don't expect 0% AI detection (15-25% is safe)
- Don't skip compilation testing
- Don't process without backup
- Don't ignore readability completely
- Don't overwrite originals directly

---

## Output Quality Control

### Checking Output Quality

1. **LaTeX Compilation**
   ```bash
   pdflatex output.tex
   bibtex output
   pdflatex output.tex
   pdflatex output.tex
   ```

2. **Visual Inspection**
   - Check all equations render correctly
   - Verify all citations appear
   - Confirm figures display properly

3. **AI Detection Testing**
   - Test with multiple tools
   - Compare before/after rates
   - Ensure target rate achieved

---

## Troubleshooting

See [FAQ.md](FAQ.md) for common issues and solutions.

---

## Performance Tips

### For Large Files

```bash
# Process in chunks if memory constrained
# Split large document into sections
# Process each section separately
```

### For Maximum Effectiveness

```bash
# Run 2-3 passes for best results
python3 ai_detector_reducer.py input.tex -o pass1.tex
python3 ai_detector_reducer.py pass1.tex -o pass2.tex
```

---

## Integration with Overleaf

### Download from Overleaf
1. Download project as .zip
2. Extract files
3. Process main .tex file
4. Re-upload processed file

### Example:
```bash
unzip overleaf_project.zip -d project/
cd project/
python3 ../ai_detector_reducer.py main.tex
# Upload main_humanized.tex back to Overleaf
```

---

For more help, see [FAQ.md](FAQ.md) or open an issue on GitHub.

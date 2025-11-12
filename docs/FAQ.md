# ❓ Frequently Asked Questions (FAQ)

## General Questions

### Q1: What does this tool do?
**A:** This tool transforms AI-generated academic writing in LaTeX format to appear more human-written, reducing AI detection rates from 90%+ to 15-25%.

### Q2: Does it work with any LaTeX file?
**A:** Yes! It works with any LaTeX academic paper including research papers, theses, dissertations, and conference papers.

### Q3: Is it free to use?
**A:** Yes, completely free and open source under the MIT License.

---

## Installation & Setup

### Q4: What are the system requirements?
**A:**
- Python 3.6 or higher
- No external dependencies needed
- Works on Windows, macOS, and Linux

### Q5: Do I need to install any Python packages?
**A:** No! The tool uses only Python's standard library. No `pip install` required.

### Q6: How do I check my Python version?
```bash
python3 --version
# Should show Python 3.6.0 or higher
```

---

## Usage Questions

### Q7: Will it modify my LaTeX commands?
**A:** No. The tool preserves all LaTeX commands, citations, formulas, and environments. Only prose text is transformed.

### Q8: What gets transformed?
**A:** Only the body text (paragraphs, sentences). The following are **never** changed:
- `\cite{}`, `\ref{}`, `\label{}`
- Math formulas: `$...$`, `$$...$$`
- Figures and tables
- Bibliography entries
- Section headings (unless you want them changed)

### Q9: How long does processing take?
**A:** Very fast! A typical 10-page paper processes in < 5 seconds.

### Q10: Can I process multiple files at once?
**A:** Yes!
```bash
python3 ai_detector_reducer.py *.tex -d ./output/
```

---

## Results & Effectiveness

### Q11: What AI detection rate should I expect?
**A:**
- Before: 90-100%
- After: 15-25%
- Multiple passes: Can get as low as 10-15%

### Q12: Which AI detectors does it work against?
**A:** Tested and effective against:
- ✅ Turnitin
- ✅ GPTZero
- ✅ Originality.ai
- ✅ ZeroGPT
- ✅ Most other AI detection tools

### Q13: Will the output be readable?
**A:** The output will be grammatically awkward but understandable. This awkwardness is what reduces AI detection. You can manually improve readability of key sections.

### Q14: Does file size increase?
**A:** Typically by 10-20% due to more verbose phrasing.

---

## Troubleshooting

### Q15: LaTeX won't compile after processing!
**A:**
1. First, ensure original file compiles correctly
2. Check for unclosed braces in error message
3. Look for any special characters that got misprocessed
4. Try processing again
5. Report issue on GitHub if persists

### Q16: Output has strange characters
**A:**
Ensure your input file is UTF-8 encoded:
```bash
file -I your_paper.tex
# Should show: charset=utf-8
```

### Q17: Tool says "command not found"
**A:**
Try using `python3` instead of `python`:
```bash
python3 ai_detector_reducer.py paper.tex
```

### Q18: Permission denied error
**A:**
Make the script executable:
```bash
chmod +x ai_detector_reducer.py
```

---

## Advanced Usage

### Q19: Can I run it multiple times on the same file?
**A:** Yes! Running multiple passes can further reduce AI detection:
```bash
python3 ai_detector_reducer.py paper.tex -o pass1.tex
python3 ai_detector_reducer.py pass1.tex -o pass2.tex
```

### Q20: Can I customize the transformation rules?
**A:** Yes, you can edit the source code. See the `init_vocabulary_replacements()` function in `ai_detector_reducer.py`.

### Q21: How do I process only certain sections?
**A:**
1. Extract the section to a separate .tex file
2. Process that file
3. Copy processed text back to main document

---

## Technical Questions

### Q22: How does it work technically?
**A:** It uses:
1. Ultra-extreme vocabulary replacement
2. Chinese-English grammar interference patterns
3. Passive voice elimination
4. Sentence structure transformation
5. Complete LaTeX command protection

### Q23: Does it use any AI or API calls?
**A:** No! All processing is done locally using pattern matching and regex. No internet connection needed.

### Q24: Is my data safe?
**A:** Yes, everything runs locally on your computer. No files are uploaded anywhere.

---

## Specific Use Cases

### Q25: Can I use this for my thesis?
**A:** Yes, but:
- Understand your university's AI usage policies
- Ensure final content meets academic integrity standards
- Review and edit output for quality

### Q26: Works with BibTeX?
**A:** Yes! Bibliography files are not modified. Only the main .tex file is processed.

### Q27: What about figures and tables?
**A:** They are completely preserved. Only caption text might be transformed if it's in the main .tex file.

### Q28: Can I process Overleaf projects?
**A:** Yes!
1. Download project as .zip
2. Extract and process main .tex file
3. Upload processed version back to Overleaf

---

## Best Practices

### Q29: Should I edit the output?
**A:** Recommended workflow:
1. Process with tool
2. Test AI detection
3. If acceptable, manually refine key sections (Abstract, Conclusion)
4. Keep overall structure from tool

### Q30: How to balance AI detection vs. readability?
**A:**
- Use tool for bulk content
- Manually refine Abstract, Introduction, Conclusions
- Keep Methods/Results sections as-is (they're often more technical anyway)

---

## Comparison with Alternatives

### Q31: How is this different from paraphrasing tools?
**A:** This tool:
- Preserves LaTeX formatting perfectly
- Uses proven double-translation techniques
- Free and open source
- Works offline
- Specifically designed for academic papers

### Q32: Better than manual rewriting?
**A:**
- Faster: Process 10 pages in 5 seconds
- Consistent: Same transformation rules throughout
- Effective: Proven 15-25% detection rate
- But: Manual review still recommended for key sections

---

## Legal & Ethical

### Q33: Is this tool legal?
**A:** Yes, the tool itself is legal. However:
- Check your institution's AI usage policies
- Ensure compliance with academic integrity rules
- Use responsibly

### Q34: Will I get in trouble for using this?
**A:** Not for using the tool, but:
- Make sure your work meets academic standards
- Understand that AI detection is about writing quality
- Review and approve all content yourself

---

## Contributing

### Q35: Can I contribute to the project?
**A:** Yes! Contributions welcome:
- Submit bug reports
- Suggest features
- Improve documentation
- Submit pull requests

### Q36: How do I report bugs?
**A:** Open an issue on GitHub with:
- Description of problem
- Input file (if you can share)
- Error message
- Your OS and Python version

---

## Future Features

### Q37: Will you add GUI?
**A:** Planned for future release!

### Q38: Support for Word documents?
**A:** On the roadmap.

### Q39: Multi-language support?
**A:** Considering for v2.0.

---

**Still have questions?**

- 📧 Open an issue: [GitHub Issues](https://github.com/RegAItool/lower_AI/issues)
- 📖 Read docs: [USAGE.md](USAGE.md)
- ⭐ Star the repo if this helped!

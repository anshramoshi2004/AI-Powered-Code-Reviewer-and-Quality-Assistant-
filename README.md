# AI-Powered Code Reviewer and Quality Assistant

## 📖 Overview
Modern codebases evolve rapidly, often without consistent review quality or standardized practices. Manual code reviews are time-intensive and depend heavily on reviewer expertise.  

This project provides an **AI-assisted code review tool** that automatically analyzes Python code for style, performance, and potential bugs. It leverages **static analysis, large language models (LLMs), and code embeddings** to provide actionable feedback in pull requests or CI pipelines.  

Developers can interact via a **CLI tool** or an optional **Streamlit UI**, reviewing, accepting, or ignoring suggestions. By integrating into Git workflows, the tool helps maintain high-quality code standards while reducing reviewer workload.

---

## ✨ Features
- **CLI Tool** for AI-assisted code reviews on Python projects.
- **Issue Detection**: unused imports, complexity spikes, missing tests, poor variable naming, etc.
- **AI Suggestions**: natural-language explanations and optional auto-fixes.
- **Configurable Rules**: PEP8 and custom linting checks.
- **Streamlit Dashboard**: visualize AI suggestions with side-by-side diffs.
- **Git Integration**: pre-commit hooks and CI/CD quality gates.
- **Reports**: export results in CSV/HTML formats.

---

## 🧩 Modules
### 1. Code Parsing & Analysis
- Parse Python files using `ast` and static analysis.
- Extract structure: imports, classes, functions, complexity, dependencies.
- Detect code smells: long functions, deeply nested loops, missing type hints.

### 2. AI Review Engine
- LLM-based prompt templates generate human-like feedback.
- Rank findings by severity (info, warning, critical).
- Auto-fix simple issues (naming, docstrings, spacing).

### 3. Validation & Metrics
- Evaluate code quality scores per file and overall.
- Track maintainability index, complexity metrics, and coverage hints.
- Export reports in multiple formats.

### 4. CLI & Configuration
- Commands: `scan`, `review`, `apply`, `report`, `diff`.
- Configurable rules in `pyproject.toml`.
- Supports severity thresholds and excluded paths.

### 5. VCS & CI Integration
- Git pre-commit hook to auto-review staged files.
- CI templates for GitHub/GitLab enforcing quality gates.

### 6. Review Web UI (Optional)
- Streamlit interface for visualizing issues and fixes.
- Side-by-side diff view with AI suggestions.

---

## 🗓️ Implementation Roadmap
### Milestone 1 (Weeks 1–2): Parsing & Baseline Generation
- AST-based extractor for functions, classes, and modules.
- Generate baseline docstrings in Google style.
- Produce initial docstring coverage report.

### Milestone 2 (Weeks 3–4): Synthesis & Validation
- Support for NumPy and reST styles.
- Improve generation with Raises/Yields/Attributes sections.
- Integrate `pydocstyle` checks and coverage reporting.

### Milestone 3 (Weeks 5–6): Workflow & CI
- Add pre-commit hook and CI workflow with coverage enforcement.
- Support configuration via `pyproject.toml`.
- Build Streamlit review UI prototype.

### Milestone 4 (Weeks 7–8): Packaging & Finalization
- Package tool as a pip-installable library.
- Add robust tests for edge cases.
- Improve Streamlit UI (filters, search, tooltips).
- Publish documentation and usage guides.

---

## ⚙️ Installation
```bash
# Clone the repository
git clone https://github.com/anshramoshi2004/AI-Powered-Code-Reviewer-and-Quality-Assistant-.git
cd AI-Powered-Code-Reviewer-and-Quality-Assistant-

# Install dependencies
pip install -r requirements.txt

# Install as a package
pip install .
```

---

## 🚀 Usage
### CLI Commands
```bash
# Scan project files
docstring-generator scan ./src

# Review with AI suggestions
docstring-generator review ./src

# Apply auto-fixes
docstring-generator apply ./src

# Generate reports
docstring-generator report --format html

# Compare changes
docstring-generator diff
```

### Streamlit UI
```bash
streamlit run .\main_app.py
```
Provides a dashboard to preview, accept, or reject AI suggestions.

---

## 🔧 Configuration
Defined in `pyproject.toml`:
```toml
[tool.docstring-generator]
style = "google"
include = ["src/**/*.py"]
exclude = ["**/__init__.py"]
coverage_threshold = 90
autofix = true
```

---

## 📊 Evaluation Criteria
- **Milestone 1:** ≥95% parser accuracy, baseline docstrings generated, coverage report successful.
- **Milestone 2:** PEP 257 compliance, ≥3 docstring styles supported, ≥90% coverage.
- **Milestone 3:** CI pipeline blocks builds under threshold, pre-commit runs <5s, Streamlit UI functional.
- **Milestone 4:** Pip-installable, end-to-end on medium projects (<2k functions) in <3 minutes, ≥80% acceptance rate of generated docstrings.

---

## 🏗️ Architecture
### Workflow Diagram
```
Source Code → Parser → Docstring Generator Engine → Validation & Reporting → Streamlit UI
```

### Components
- **Core Engine:** Parser, Generator, Validator
- **Integration Layer:** Pre-commit hook, CI/CD pipeline
- **User Interfaces:** CLI tool, Streamlit dashboard

---

## 🗄️ Database Schema
- **CODEPARSER:** stores file paths, functions, classes.
- **DOCSTRINGGENERATOR:** templates and sections.
- **VALIDATOR:** coverage scores and issues.
- **STREAMLITUI:** changes and patch files.
- **CLIINTERFACE:** command-line args and output formats.

---

## 📜 License
This project is licensed under the **MIT License** – free to use, modify, and distribute.

---

## 🤝 Contributing
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-name`).
3. Commit changes (`git commit -m "Add feature"`).
4. Push to branch (`git push origin feature-name`).
5. Open a Pull Request.

---

## 📬 Contact
Developed by **Ansh Ramoshi**  
For queries, reach out via GitHub Issues or Discussions.


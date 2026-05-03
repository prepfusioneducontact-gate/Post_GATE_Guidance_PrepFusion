# PrepFusion LaTeX Project
## GATE Counseling, Admission Process & PSU Recruitment Guide

---

## Folder Structure

```
prepfusion-latex/
│
├── main.tex                        # Master file — compile THIS
├── prepfusion_style.sty            # All branding, packages, environments
├── logo.png                        # ← PUT YOUR LOGO HERE (required)
│
├── frontmatter/
│   ├── title_page.tex
│   ├── disclaimer.tex
│   └── acknowledgements.tex
│
├── chapters/
│   ├── 01_counseling.tex           # COAP / CCMT process
│   ├── 02_psu_recruitment.tex      # PSU recruitment & prep
│   ├── 03_interview_prep.tex       # Interview strategy
│   ├── 04_college_selection.tex    # College & branch guidance
│   ├── 05_cutoffs.tex              # Score & cutoff analysis
│   ├── 06_financial.tex            # Fees & scholarships
│   ├── 07_research_ms.tex          # MS / M.Tech Research
│   ├── 08_drop_guidance.tex        # Drop year & career advice
│   ├── 09_institute_profiles.tex   # Institute-wise programs
│   └── 10_alternative_options.tex  # BITS, IIIT, abroad options
│
├── appendix/
│   ├── A_interview_questions.tex   # Question bank (Digital/Analog/Power)
│   ├── B_interview_experiences.tex # Student experiences (community-sourced)
│   ├── template_interview.tex      # Intern template for new experiences
│   └── experiences/                # ← Add individual experience .tex files here
│
└── assets/
    └── (place any images/diagrams here)
```

---

## How to Compile

**Recommended Engine: XeLaTeX or LuaLaTeX** (for Montserrat + Fira Code fonts)

```bash
# First pass (generates TOC)
xelatex main

# Second pass (resolves cross-references & hyperlinks)
xelatex main
```

**On Overleaf:**
- Set compiler to **XeLaTeX** in the project settings.
- Upload all files maintaining the exact folder structure above.
- Upload `logo.png` to the root folder.

**pdfLaTeX fallback:**
- If Montserrat / Fira Code are not available, the style file falls back to
  Helvetica and Fira Mono. The document will still compile cleanly.

---

## Adding a Logo

1. Place your logo file as `logo.png` in the **root** folder (same level as `main.tex`).
2. The logo appears in the header on every page automatically.
3. To change the logo size, edit `prepfusion_style.sty`, line with `height=22pt`.

---

## Enabling the Watermark

To add the PrepFusion text watermark, uncomment this line in `main.tex`:

```latex
% \watermarkon
```

---

## Adding a New Interview Experience

1. Copy `appendix/template_interview.tex` to
   `appendix/experiences/[institute]_[branch]_[year].tex`
2. Fill in all placeholder fields.
3. Open `appendix/B_interview_experiences.tex` and add:
   ```latex
   \input{appendix/experiences/your_file.tex}
   ```

---

## Custom Environments Reference

| Environment | Usage | Color |
|---|---|---|
| `\begin{protip}[Title]` | Expert insights | Blue |
| `\begin{deadline}[Event]` | Important dates | Orange |
| `\begin{eligalert}[Title]` | Eligibility info | Green |
| `\begin{disclaimer}` | Liability notice | Grey |
| `\begin{experience}{Name}{Institute}` | Student experiences | Blue frame |
| `\begin{faqentry}{Question}` | Q&A pairs | Inline |

---

## Color Reference

| Variable | Hex | Use |
|---|---|---|
| `pfBlue` | #1A365D | Headers, section titles |
| `pfOrange` | #F68059 | Links, action boxes, deadlines |
| `pfGreen` | #2D6A4F | Selected status, eligibility |
| `pfGrey` | #F7FAFC | Table backgrounds |

---

© 2026 PrepFusion. www.PrepFusion.in

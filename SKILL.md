---
name: resume-generator
description: "Collect, rewrite, tailor, and visually design resumes/CVs through a preview-first workflow: polish only truthful candidate information, explore high-aesthetic layouts with ChatGPT image generation, obtain user approval, then recreate the selected design as an editable Word document and verify its rendered pages before delivery. Also supports ATS, academic, Chinese, English, and bilingual resumes."
---

# Resume Generator

Use this skill when the user asks to create, revise, polish, translate, restructure, score, or tailor a resume/CV. It applies to resumes in Chinese, English, or bilingual form, and to both industry resumes and academic CVs.

## Core Principle

Treat resume creation as a staged approval workflow. Do not jump from raw information directly to Word unless the user explicitly asks to skip visual exploration.

- Preserve facts. Never invent employers, degrees, dates, titles, responsibilities, awards, publications, tools, metrics, patient counts, revenue, rankings, or outcomes.
- Improve structure, emphasis, phrasing, and evidence without changing the underlying meaning.
- Clearly distinguish an AI-generated style mockup from a text-accurate document preview.
- Do not create the editable Word file until the user has selected or approved a visual direction, unless the user explicitly requests immediate Word delivery.

## Stage 1: Collect Candidate Information

Prompt the user to upload an existing resume or provide the relevant personal information. Ask only for material gaps that affect the result:

- Name and contact information
- Target role, industry, seniority, and optional job description
- Education
- Work and internship experience
- Projects or research
- Skills, languages, certificates, publications, awards, and leadership
- Preferred language, one-page or two-page length, and whether a portrait should appear

Do not require every category. Omit irrelevant or unsupported sections. If the user provides enough material, proceed without unnecessary questions.

For portraits, offer two routes: the user supplies a real photo, or ChatGPT generates a clearly synthetic placeholder portrait for layout exploration. Never imply that a generated portrait is the candidate's real likeness.

## Stage 2: Polish Truthful Content

Before visual design, clean malformed HTML entities, encoding artifacts, duplicated punctuation, abnormal spaces, and inconsistent dates. Then:

- Clarify the target role and professional positioning.
- Reorder evidence by relevance and strength.
- Rewrite verbose responsibility statements into concise, evidence-rich bullets.
- Preserve all factual boundaries and flag unclear claims instead of guessing.
- Use known scope or deliverables when exact metrics are unavailable.

The polished content becomes the source of truth for later editable files.

Before generating any visual, create an internal fact sheet containing every permitted personal fact: name, contact details, schools, degrees, dates, employers, departments, titles, responsibilities, metrics, awards, certificates, tools, and languages. Nothing outside this fact sheet may appear as candidate information in a mockup or deliverable.

## Stage 3: Generate High-Aesthetic Style Mockups

Use ChatGPT image generation to create exactly three complete visual resume drafts that explore layout, typography hierarchy, color, whitespace, density, section rhythm, and portrait placement. Unless the user explicitly requests different styles, generate one draft from each preset in [references/style-presets.md](references/style-presets.md).

The style mockup is for aesthetic selection only, but it must never display invented candidate facts:

- Use the candidate's real name, schools, employers, dates, titles, credentials, and other readable facts exactly as supplied or truthfully polished.
- Never generate plausible replacement schools, companies, dates, job titles, certificates, rankings, metrics, locations, emails, or phone numbers. This prohibition applies even to temporary mockups.
- Style mockups must use the polished real resume text directly. Do not use non-semantic lines, blurred microtext, lorem ipsum,乱码式微文本, or placeholder labels in place of candidate content.
- Each of the three drafts must be generated directly by ChatGPT image generation as a complete resume containing the candidate's real personal information and real resume body text. Do not generate a blank template for later text overlay.
- Do not use programmatic or manual post-processing to add, replace, correct, or overlay resume text onto an otherwise blank generated template. The candidate chooses among three native ChatGPT-generated written drafts.
- Each draft must contain the complete set of sections and facts required for that version. Do not omit substantial experience merely to simplify image generation or improve the composition.
- Abbreviation is allowed only when it preserves the original fact, such as shortening a long responsibility statement. It must not change names, dates, organizations, roles, awards, or numbers.
- It must show the intended page count, major sections, approximate information density, and portrait/no-portrait structure.
- If image generation cannot render the real text accurately, reject that mockup. Do not show it to the user and do not excuse inaccurate text as a harmless placeholder.
- Do not present a programmatically drawn plain text page as the required ChatGPT-generated style exploration when image generation is available.

Prompt image generation with the complete polished resume text and a strict source-of-truth block. Add explicit constraints: “Use only the supplied real text. Do not invent, substitute, omit, or replace candidate facts. Do not use placeholder lines or pseudo-text.”

Inspect every generated mockup before showing it. Compare all readable candidate facts and body text against the fact sheet and polished source text. Reject and regenerate any image that contains a fabricated, substituted, misspelled, or omitted school, employer, date, role, credential, metric, contact detail, award, or material experience. A rejected image does not count toward the required three options. Show the user only after three distinct, complete drafts have passed this review.

Apply a compact-layout check to every style mockup. Pages should feel dense enough for professional screening while remaining readable. Rebalance sections, spacing, and page breaks when the lower half of a page contains a large unexplained blank area. Preserve intentional breathing room around headings, but avoid decorative whitespace that pushes meaningful content onto another page.

Show the mockups and stop for the user's choice or requested revisions. The user may adjust color, density, typography, portrait placement, one-page versus two-page structure, or overall visual tone.

## Stage 4: Recreate the Selected Design in Editable Word

Only after the user approves a direction, read [references/word-layout.md](references/word-layout.md) and build the `.docx` with the polished source-of-truth text.

- Recreate the hierarchy, spacing, color system, alignment, and portrait placement using native Word paragraphs, runs, tables, styles, and images.
- Do not insert the full-page style mockup as a flattened background or screenshot.
- Keep all resume text selectable and editable.
- Use the same verified real dates and content as the approved style mockup.
- Preserve ATS readability unless the user explicitly prioritizes a highly visual non-ATS version.

## Stage 5: Render and Confirm the Word File

Render every Word page to images and inspect them before delivery. Check page breaks, font substitution, date alignment, clipped or overlapping text, table wrapping, margins, whitespace balance, and portrait crop/proportion.

Show the rendered Word preview to the user and ask for confirmation. If revisions are requested, update the Word file and render it again. Do not substitute the earlier AI style mockup for this document-accurate QA preview.

## Stage 6: Deliver

After confirmation, deliver the editable `.docx`. Provide PDF or LaTeX only when requested. Keep intermediate mockups and QA renders separate from the final deliverables.

## First Decision

Identify the user's immediate goal:

- Build a new resume from raw background information.
- Polish or rewrite an existing resume.
- Tailor a resume to a job description.
- Translate a resume between Chinese and English.
- Convert between academic CV and industry resume.
- Create a structured draft for Word, PDF, LaTeX, or Markdown.
- Run the complete preview-first design and editable Word workflow.

Ask only for missing information that materially affects the result. The most useful missing inputs are target role, target industry, job description, education, work/project/research experience, skills, publications, awards, and preferred language/length.

## Default Output

Unless the user requests a file format, produce a clean Markdown resume draft. Keep sections standard and easy to parse:

- Contact
- Summary or Objective, only when it adds clear positioning
- Education
- Experience
- Projects or Research
- Skills
- Publications, Awards, Certifications, or Leadership when relevant

For industry resumes, prioritize relevance to the target role over chronology. For academic CVs, preserve scholarly completeness and read [references/academic-cv.md](references/academic-cv.md).

## Word Resume Workflow

When the user asks for a formatted Word resume, a polished layout, a "排版好的 Word 文档", or an editable resume file:

1. Produce or confirm the truthful polished resume text.
2. Generate ChatGPT image style mockups and obtain the user's visual choice.
3. Read [references/word-layout.md](references/word-layout.md).
4. Recreate the approved direction with editable Word elements and real text.
5. Render the Word pages, inspect them, and show the accurate document preview.
6. Revise as needed and deliver the `.docx` only after confirmation.

Do not conflate the two preview types. The ChatGPT-generated style mockup establishes aesthetic direction and must use the verified real resume text, while the later rendered Word preview proves that the editable document preserves that text and its actual pagination. A plain Markdown draft is neither preview type.

If the user asks to skip confirmation, or explicitly asks for the Word file immediately, generate the `.docx` directly and still provide a rendered preview for visual QA when possible.

## Bullet Writing

Prefer evidence-rich bullet points over responsibility lists. Use this pattern when enough information exists:

`Action + method/tool + task/context + measurable result or concrete impact`

Replace vague phrasing such as "responsible for", "participated in", "helped with", "familiar with", and "learned about" with specific actions such as built, designed, analyzed, optimized, automated, evaluated, led, coordinated, deployed, published, or presented.

If exact metrics are unavailable, use concrete scope instead of inventing numbers: dataset size, number of users, frequency, project duration, model type, system component, team size, domain, or deliverable.

Do not fabricate employers, degrees, dates, awards, publications, tools, or quantified outcomes. When the resume would benefit from missing metrics, provide a polished version using the known facts and optionally list targeted questions for improvement.

## Tailoring

When a job description is provided, align the resume to it by:

- Extracting role priorities, keywords, required tools, domain terms, and seniority signals.
- Reordering or rewriting bullets so the strongest matching evidence appears first.
- Adding relevant keywords only where the candidate's experience supports them.
- Removing or compressing low-relevance details when space is limited.

For ATS-focused work, read [references/ats-guidelines.md](references/ats-guidelines.md).

## Language And Style

For Chinese resumes, use concise professional Chinese and avoid inflated or bureaucratic wording. Read [references/chinese-resume.md](references/chinese-resume.md) for Chinese-specific guidance.

For English resumes, use natural business English, active verbs, consistent tense, and direct phrasing. Read [references/english-resume.md](references/english-resume.md) for English-specific guidance.

For bilingual resumes, align meaning and section structure rather than translating mechanically. Read [references/bilingual-resume.md](references/bilingual-resume.md).

For project-heavy resumes, read [references/project-bullets.md](references/project-bullets.md) when rewriting project bullets.

## Final Check

Before finalizing a resume, check:

- The target role is clear.
- The first page or first screen contains the strongest matching evidence.
- Bullets show actions and outcomes rather than duties.
- Skills are supported by experience.
- Dates, titles, tense, punctuation, and formatting are consistent.
- No unsupported claims or invented metrics were added.

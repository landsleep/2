---
name: resume-generator
description: Generate, rewrite, polish, translate, tailor, and format resumes/CVs, including ATS-friendly industry resumes, Chinese/English/bilingual resumes, academic CVs, job-description targeted versions, and polished Word resume previews before editable DOCX delivery.
---

# Resume Generator

Use this skill when the user asks to create, revise, polish, translate, restructure, score, or tailor a resume/CV. It applies to resumes in Chinese, English, or bilingual form, and to both industry resumes and academic CVs.

## First Decision

Identify the user's immediate goal:

- Build a new resume from raw background information.
- Polish or rewrite an existing resume.
- Tailor a resume to a job description.
- Translate a resume between Chinese and English.
- Convert between academic CV and industry resume.
- Create a structured draft for Word, PDF, LaTeX, or Markdown.
- Create a polished Word resume with preview-first approval before editable DOCX delivery.

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

1. First produce or confirm the final resume text.
2. Read [references/word-layout.md](references/word-layout.md).
3. Create a visual preview image of the resume layout before generating the final editable Word document.
4. Show the preview image to the user and ask whether the layout/content should be adjusted.
5. Generate the editable `.docx` only after the user approves the preview or explicitly asks to proceed despite the preview.

The preview should reflect the actual intended Word layout closely enough for the user to judge spacing, hierarchy, typography, and overall visual style. Do not treat a plain Markdown draft as the visual preview.

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

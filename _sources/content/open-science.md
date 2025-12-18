# Open Science Principles and Practices
This page offers a practical guide to conducting open, transparent, and reproducible research from day one. It focuses on **what to do, when to do** it, and provides **ready‑to‑use templates** you can adopt immediately.

## A successful example: Open Science Framework (OSF)
The [Open Science Framework](https://osf.io/) (OSF) is a free, open-source online platform developed by the [Center for Open Science](https://www.cos.io) (COS) that enables researchers to manage, document, share, and archive each stage of their research project — from planning and preregistration through data collection, analysis, preprints, and final publication. In essence, it offers a centralized “digital home” for all materials related to a scientific project: data, code, protocols, manuscripts, documentation.

OSF fosters transparency and reproducibility by strongly supporting preregistration: researchers can timestamp and publicly register their study design and analysis plan before collecting or analyzing data. This practice helps to guard against problematic academic practices such as selective reporting or “p-hacking,” because deviations from the original plan remain **visible**. P-hacking, also termed [_Data dredging_](https://en.wikipedia.org/wiki/Data_dredging), refers to the practice of repeated statistical testing of results until a significant pattern is found, at the cost of a massive increase in false-positive rate. 

Moreover, OSF allows flexibility: all your projects remain private while under development until they are read to be made public. You, the researcher, decide. Parts of the project can also stay embargoed for a period. Once public, projects and associated materials receive persistent identifiers (DOIs), enabling proper citation, long-term accessibility, and re-use by others. Through these features, OSF supports a shift from “final-paper only” thinking to a more life-cycle oriented view of scientific work, in which planning, methodology, data, analysis code and, importantly, also null or negative results produce shareable, citable research products.

In doing so, OSF lowers practical and infrastructural barriers, it empowers researchers across disciplines and across countries to conduct more rigorous, sharable, and trustworthy science. Used properly, OSF can help make scientific research not only more open, but more credible and cumulative.

## Why Open Science in EXPRA?

Open practices are not extra work added to the experimental job, and only at the end. They constitute a workflow that saves time, prevents mistakes, strengthens your findings, and makes data available for others to use, saving money and in the case of animal studies, preventing cruelty.

In EXPRA, adopting open practices will help you to:

-	**Plan clearly** (preregistration of an experiment forces you to clarify hypotheses, variables, and analysis pipeline).
- **Collaborate smoothly** (everyone sees and updates the same files, versions, and decisions are instantly shared).
-	**Reuse efficiently** (Yourself in the future, as well as other teams, can reproduce and build on your work).
-	**Communicate credibly** (transparent reporting increases trust and visibility).

The core principles of Open Science are:

1. **Transparency** – Document what you did and why; share materials, data, and code whenever legally and ethically possible. (link to Nature data policy: https://www.nature.com/nature-portfolio/editorial-policies/reporting-standards
2. **Reproducibility** – A competent researcher should be able to rerun your analysis and obtain the same results. Furthermore, since the introduction of Large Language Models, your data might be re-used by machines: https://www.nature.com/articles/sdata201618
3. **Accessibility** – When possible, share data using open rather than proprietary formats, in and stable repositories: https://opendataformat.github.io
4. **Integrity** – Follow ethical and data‑protection rules; be upfront about the uncertainty and limitations of your study.
5. **Inclusivity and Credit** – Make your work understandable and citable; credit all contributions fairly.

## The EXPRA Open Science Workflow (checklist)
Use the following as an example of your default timeline. The links refer to relevant site sections where available.

1) Plan & Register (Weeks 3-4)
-	Find the EXPRA **project template** on {doc}`lifos`. Define team roles and enable versioning.
-	Write a **preregistration** (see {doc}`preregistration` section) that covers: research question, hypotheses, variables, sampling plan, exclusion rules, analysis plan, and data‑collection stopping rule (when you have enough data, normally this is pre-determined using a power analysis).
-	Prepare a **data management plan** (DMP): file names, folder structure, backups, pseudonymisation.
-	Draft **materials** (instructions, questionnaires, stimuli) and **pilot** them.

2) Collect Data (Weeks 5–8)
-	Use unique **participant IDs for research data**; never store direct identifiers (the participant’s real name, for example) with research data.
-	Log all **deviations** from the preregistration plan in a DEVLOG.md or .txt (date + explanation).
-	Keep **raw data untouched**; all preprocessing occurs via scripts creating a derived dataset.

3) Analyse Data (Weeks 9–10)
-	Create **scripts** (Matlab, R, Python, or JASP .jasp file) that read raw/derived data and output tables/figures.
-	Record **software versions** and random initializing seeds in scripts.
-	Produce a draft **report** and a finalized **poster**.

4) Share & Communicate (Weeks 11–end)
-	Upload: materials, code, preregistration, and (de‑identified) data to **LIFOS**.
-	Add clear **licence** file (see below).
-	Link your **poster/report** to the repository; include a **data/code availability statement**.


Minimum Requirements for EXPRA are:
-	A **time‑stamped preregistration** created **before** data collection.
-	A public project repository (LIFOS recommended) containing:
  - README.md or a README.txt file describing the project and how to reproduce results.
  - **Materials** (stimuli, instructions, questionnaires, task scripts).
  - **Analysis code** that recreates results.
  - A **codebook** describing variables and units.
  - A **de‑identified dataset** or a documented reason why data cannot be shared.
  - **Licence** files for data, code, and materials.
-	A **reproducibility test**: someone outside your team should be able to run your code and reproduce key numbers.

Aim higher with the “Good → Better → Best” ladder below.

### Good → Better → Best

| Area | Good | Better | Best |
| ---- | ---- | ---- | ---- |
| Planning |	Simple preregistration on LIFOS |	Registered Report‑style preregistration (more detail) |	External feedback from Supervisor before locking preregistration |
| Data |	De‑identified .csv uploaded |	FAIR metadata + codebook | 	Full raw + preprocessed |
| Code |	Single analysis script |	Modular scripts |	Fully reproducible pipeline |
| Reporting |	Data/code availability statements |	Reproducible manuscript (Quarto/Jupyter) |	Continuous integration (CI) reproduces figures on commit |
| Credit |	Author list in README |	Contributor Roles (CRediT) |	CITATION.cff + ORCID links, releases with changelog |



### Example of File Organisation

project-root/  
├─ README.txt  
├─ LICENCE_DATA file (e.g., CC0 or CC BY 4.0)  
├─ CITATION file  
├─ DEVLOG.txt  
├─ data/  
│  ├─ raw/           # never edited by hand  
│  └─ preprocessed/       # produced by scripts  
├─ materials/        # stimuli, instructions, questionnaires  
├─ scripts/  
│  ├─ 00_packages.R  # Example  
│  ├─ 01_clean.R  
│  ├─ 02_analysis.R  
│  └─ 03_figures.R  
├─ reports/  
│  └─ draft  
└─ docs/             # exported figures/tables for poster  

## Practical notes 
Licensing (what to choose and where)
-	**Code** → permissive licence such as [MIT](https://opensource.org/license/mit) (for an easy reuse).
-	**Data** → **CC0** (public domain) or **CC BY 4.0** (requires attribution). If data cannot be public, include a DATA_AVAILABILITY.md or .txt.
-	**Materials** (stimuli, questionnaires, figures) → **CC BY 4.0** unless third‑party content prevents this.
-	Put licences as separate files and **state them in the README file**.

Ethical & Data‑Protection Notes (GDPR‑compliant)
-	Collect **only** data you need; explain purpose in the informed consent.
-	Store identifiers separately from research data; use **pseudonymisation**.
-	Share **de‑identified** data only; if not possible, share **summary** data + full code.
-	Update your preregistration and repository with any **protocol deviations**.
When in doubt: protect participants first, document everything transparently and share only what is safe and lawful.

Tools we recommend
-	**LIFOS** – the data sharing platform of the Institute of Psychology, Goethe University Frankfurt. 
-	**OSF** (Open Science Framework) – project hub, preregistration, files, DOIs.
-	**GitHub/GitLab** – version control for code and text; can mirror to OSF.
-	**Zotero** – reference manager with group libraries and web import.
-	**R / Python** – scripted analysis for reproducibility (JASP is also fine).

Common Conceptual Pitfalls (and how to avoid them)
- **Ambiguous variable names**. → Use a codebook, prefer snake_case when you name a variable.
-	**Results not reproducible on another computer**. → Make sure this is justified and clearly tracked. Add a Disclaimer if you did not test this specific issue.
-	**Unclear authorship**. → Record credit roles from the start in the README file.



----

**Acknowledgments**  
This section was contributed by [Alessandro Tavano](https://fiebachlab.org/team/tavano). 

_This checklist is a practical, opinionated guide for sanity-checking the writing quality, structure, and presentation of CS papers—especially for conference (and journal) submissions. While some items are subjective, the goal is to provide concrete reminders and highlight common pitfalls. It is a living document and will continue to be updated based on feedback._

> 🤖 **Drafting with an AI agent?** Many items below (especially §6 Writing Quality and Style and §10 Citation Sanity) are things an agent can get right *while drafting*, not only things you catch at the end. Point your agent at [**agent-style**](https://github.com/yzhao062/agent-style): 12 writing rules distilled from Strunk & White, Orwell, Pinker, and Gopen & Swan, plus 9 field-observed LLM anti-patterns, that load at generation time. Install with `pip install agent-style`, then `agent-style enable claude-code` (or `cursor`, `agents-md`, `copilot`). Use this checklist as the final human gate: prevention before detection.

---

## 1. 🎯 Title and Abstract

- [ ] 1.1 Title is ≤ 15 words. Check for generic phrasing (e.g., “A Novel Framework...,” which conveys little information) and overly narrow focus (which may reduce the paper’s audience)—aim for concise but informative.
- [ ] 1.2 Title clearly reflects both the **problem** and the **solution**, and includes at least one technical keyword (e.g., jailbreak, OOD detection, graph learning).
- [ ] 1.3 Title avoids rare or ambiguous abbreviations. Terms like LLM, AI, and ML are acceptable in CS venues, but avoid abbreviations like AD (which could refer to advertisement or anomaly detection).
- [ ] 1.4 Abstract includes at least four key components: (1) problem/task definition, (2) proposed method or idea, (3) main results, and (4) broader impact or significance (some may be combined).
- [ ] 1.5 Abstract avoids undefined abbreviations and vague descriptors (e.g., “important,” “novel,” “state-of-the-art” without context).
- [ ] 1.6 Bonus: Abstract includes at least one concrete, quantitative result or insight to make the work stand out. For instance, “our method achieves 11.2× acceleration in test-time inference for jailbreak detection.”


---

## 2. 📚 Introduction

- [ ] 2.1 The main problem or task is clearly defined within the first two paragraphs.
- [ ] 2.2 Motivation includes either (a) real-world use cases or (b) citations to prior work—ideally both.
- [ ] 2.3 The introduction ends with a brief overview of the proposed method and its name.
- [ ] 2.4 Contributions are explicitly itemized (e.g., “(1) first framework for ..., (2) new dataset for ..., (3) extensive evaluation on ...”).
- [ ] 2.5 Each contribution is specific and verifiable—avoid vague claims such as “we provide insights” or “we improve understanding.”
- [ ] 2.6 Bonus: Include a compelling figure on the first page—e.g., comparison to prior work, performance highlight, or visual explanation of the core idea.




---

## 3. 🔍 Related Work

- [ ] 3.1 All cited works are connected to your method, baseline, or task.
- [ ] 3.2 At least one baseline from the top-3 most cited recent papers on the topic is mentioned.
- [ ] 3.3 Related work does not exceed 1.5 pages (unless survey-style paper).
- [ ] 3.4 You may use LLMs for searching the related work, but double triple check each of the paper -- do not trust LLMs!!!!
- [ ] 3.5 Bonus: use related work section to introduce baseline algorithms -- show a table for your proposal better than the existing ones




---

## 4. 🧪 Method

- [ ] 4.1 All symbols are defined before use.
- [ ] 4.2 Each equation is referenced with inline explanation (e.g., “Eq. (3) defines the loss over…”). If an equation is never referenced, consider making it inline to save space.
- [ ] 4.3 All modules or components of the method are illustrated or described in text or figures.
- [ ] 4.4 Each subsection ideally aligns with parts of the overview figure. Add a short summary paragraph before diving into subsections.
- [ ] 4.5 You do not need both overview figure and pseudo code in the main text -- move the pseudo code to the appendix
- [ ] 4.6 The method is reproducible without referring to the appendix or external code—reviewers should understand everything from the main text.
- [ ] 4.7 Bonus: Can anything be removed from this section without reducing clarity? Do not hesitate to cut: more math ≠ better paper.




---

## 5. 📊 Experiments

- [ ] 5.1 At least 3 datasets are used (unless the paper introduces a new dataset).
- [ ] 5.2 At least 3 baseline methods are compared. Are they state-of-the-art? Justify why these baselines are chosen.
- [ ] 5.3 At least 1 ablation study is included.
- [ ] 5.4 Standard deviation or confidence intervals are reported where appropriate.
- [ ] 5.5 Hardware environment, software libraries, and hyperparameter settings are described.
- [ ] 5.6 Negative results (if any) are explained, not omitted—failure cases are valuable.
- [ ] 5.7 Evaluation metrics are clearly defined and justified.
- [ ] 5.8 All figures and tables are referenced in the main text.
- [ ] 5.9 Beyond showing numbers and saying “we perform well,” at least one deeper insight or analysis is provided (e.g., why it works, where it fails).
- [ ] 5.10 Bonus: Think about how easy others can reproduce your work? If you have any "dirty tricks" -- remove them pls.





---

## 6. 🧾 Writing Quality and Style

- [ ] 6.1 All abbreviations are defined at first use (even ML, LLM, etc.) -- do not redefine them again and again.
- [ ] 6.2 No sentence exceeds 25 words without a comma or period.
- [ ] 6.3 No paragraph exceeds 10 lines.
- [ ] 6.4 Passive voice usage < 30% of the total number of sentences.
- [ ] 6.5 Bonus: Have you noticed that your paper are full of the fancy LLM words, like encompass, intricate, etc?




---

## 7. 🖼️ Figures and Tables

- [ ] 7.1 Each figure/table has a caption ≥ 2 lines that includes interpretation or context. Do not just place it without explanation—reviewers will get lost.
- [ ] 7.2 Font size in all figures is ≥ 8pt and all labels are fully visible (not cropped).
- [ ] 7.3 Plots use colors that remain distinguishable when printed in grayscale—some reviewers will print your paper.
- [ ] 7.4 Each method mentioned in the results appears in either the legend or table column headers.
- [ ] 7.5 Figures appear at the top of pages rather than mid-text or at the bottom (soft rule, but improves readability).
- [ ] 7.6 Figures and tables are not redundant—each provides new or complementary information.
- [ ] Bonus: All figures are in **lossless formats** (e.g., PDF for vector graphics). Absolutely no low-resolution images allowed.





---

## 8. 🧱 Structure and Formatting

- [ ] 8.1 All LaTeX warnings and bad boxes have been resolved.
- [ ] 8.2 Section headers follow the standard paper structure (e.g., Introduction, Method, Experiments, etc.).
- [ ] 8.3 All appendix sections are explicitly referenced in the main text (e.g., “Appendix B.2 shows…”).
- [ ] 8.4 No **orphan lines** anywhere in the paper—avoid single-line section headers or short lines at the top/bottom of columns.
- [ ] 8.5 No two figures or tables are placed consecutively without explanatory text between them.




---

## 9. 📎 References

- [ ] 9.1 All references are in the correct format for the target venue.
- [ ] 9.2 All datasets, toolkits, and models used are cited.
- [ ] 9.3 At least one paper from the target venue (conference/journal) is cited.
- [ ] 9.4 Self-citations ≤ 20% of total citations.
- [ ] 9.5 BibTeX file has been deduplicated and spell-checked.




---

## 10. 🛑 Citation Sanity Check (LLM-Generated Risk)

- [ ] 10.1 All citations were **manually verified to exist**—title, authors, venue, and year match a real, published paper.
- [ ] 10.2 No hallucinated references from LLM tools are included.
- [ ] 10.3 If a citation was generated by ChatGPT, Copilot, or similar, it has been cross-checked on **Google Scholar**, **Semantic Scholar**, or publisher sites.




---

## 11. 🧠 Sanity Checks Before Submission

- [ ] 11.1 PDF compiles in Overleaf/TeX with no errors or bad boxes.
- [ ] 11.2 File name follows the submission guideline format (e.g., no underscores or author names if anonymized).
- [ ] 11.3 No author-identifying information exists in metadata, supplementary files, or file names. Check your code repository and images too.
- [ ] 11.4 The paper length complies with the page limit, including references and appendices (if counted).
- [ ] 11.5 The paper has been read start-to-finish by someone not on the author list, without them needing to stop for clarification.
- [ ] 11.6 All co-authors are listed and properly acknowledged—this is surprisingly often overlooked.
- [ ] 11.7 Bonus: After submission, log in from a different device and OS (e.g., Mac, Windows) to verify that the uploaded version renders correctly.


---

_This checklist is part of the [`cs-paper-checklist`](https://github.com/yzhao062/cs-paper-checklist) project. Contributions welcome via PR._

---

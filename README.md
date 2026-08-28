# Awesome Citation Fabrication & Trust

A curated, verified collection of research papers, datasets, tools, implementations, and learning resources
on **citation fabrication in AI-generated text and its effect on human trust** — the topic of my AI-assisted
research paper *"The Influence of Citation Formatting on Human Trust in Fabricated References."*

## Contents

- [Overview](#overview)
- [AI-Assisted Research Paper](#ai-assisted-research-paper)
- [Citation Integrity Audit](#citation-integrity-audit)
- [Survey Papers](#survey-papers)
- [Foundational Papers](#foundational-papers)
- [Recent Research Papers](#recent-research-papers)
- [Datasets](#datasets)
- [Tools and Libraries](#tools-and-libraries)
- [GitHub Implementations](#github-implementations)
- [Tutorials and Learning Resources](#tutorials-and-learning-resources)
- [License](#license)

## Overview

Large language models (LLMs) are now widely used to draft literature reviews, but multiple audits show they
frequently generate references that *look* real — correct formatting, plausible author names, valid-looking
DOIs — while pointing to papers that do not exist. This is called **citation fabrication** or **reference
hallucination**. Separately, communication and cognitive psychology research shows that humans treat the mere
*presence* and *format* of a citation as a trust signal, largely independent of whether they ever verify it.
This repository organizes the research at the intersection of these two problems: how citation formatting
influences human trust, how bad AI citation habits exploit that trust, and how researchers are building tools
to detect and correct fabricated references. It is organized so that another student or researcher — with no
prior context — can understand the problem space and locate the right resource without opening every file.

## AI-Assisted Research Paper

**The Influence of Citation Formatting on Human Trust in Fabricated References**
A review synthesizing credibility-heuristics research, the MAIN model, "truthiness"/processing-fluency
findings, and recent empirical audits of LLM citation fabrication, arguing that citation *format* functions
as a heuristic trust cue that is frequently mistaken for a validity signal.
[View Paper](paper/AI_Assisted_Research_Paper.pdf)

## Citation Integrity Audit

Every reference in the paper above was checked against Crossref, Google Scholar, Semantic Scholar, and
publisher records before being added here, following the verification workflow required by this assignment.
[View Audit](citation-audit/Citation_Integrity_Audit.pdf)

## Survey Papers

- **Large Language Models Hallucination: A Comprehensive Survey**
  arXiv preprint, 2025
  [Paper](https://arxiv.org/abs/2510.06265)
  Broad survey of LLM hallucination detection/mitigation datasets; Section 8 catalogs benchmark datasets
  relevant to citation-style factual hallucination.

## Foundational Papers

- **Credibility and Trust of Information in Online Environments: The Use of Cognitive Heuristics**
  Metzger, M. J., & Flanagin, A. J., 2013, *Journal of Pragmatics*, 59, 210–220
  [DOI](https://doi.org/10.1016/j.pragma.2013.07.012)
  Establishes the cognitive-heuristics framework (authority, endorsement, consistency heuristics) this
  project's whole argument is built on.

- **Social and Heuristic Approaches to Credibility Evaluation Online**
  Metzger, M. J., Flanagin, A. J., & Medders, R. B., 2010, *Journal of Communication*, 60(3), 413–439
  [DOI](https://doi.org/10.1111/j.1460-2466.2010.01488.x)
  Focus-group evidence that surface/formatting cues are used as fast, low-effort credibility shortcuts.

- **The MAIN Model: A Heuristic Approach to Understanding Technology Effects on Credibility**
  Sundar, S. S., 2008, in *Digital Media, Youth, and Credibility* (pp. 73–100), MIT Press
  Framework explaining how interface/format affordances (like citation styling) trigger credibility heuristics.

- **Nonprobative Photographs (or Words) Inflate Truthiness**
  Newman, E. J., Garry, M., Bernstein, D. M., Kantner, J., & Lindsay, D. S., 2012, *Psychonomic Bulletin & Review*, 19(5), 969–974
  [DOI](https://doi.org/10.3758/s13423-012-0292-0)
  Origin of the "truthiness" effect — non-probative cues inflating perceived truth — used as the cognitive
  mechanism analogy for citation-format effects.

- **Truthiness: How Non-Probative Photos Shape Belief**
  Newman, E. J., & Zhang, L., 2020, in *The Psychology of Fake News* (pp. 90–114), Routledge/Taylor and Francis
  Review of the processing-fluency mechanism behind truthiness; directly transferable to citation formatting.

- **The Role of Trust and Authority in the Citation Behaviour of Researchers**
  Thornley, C., et al., 2015, *Information Research*, 20(3), Paper 677
  [Paper](http://informationr.net/ir/20-3/paper677.html)
  Qualitative study of why researchers cite what they cite, and how citing signals authority.

- **Trust and Antitrust**
  Baier, A., 1986, *Ethics*, 96(2), 231–260
  Source of the "trust as anti-monitoring" concept used by Ding et al. (2025) to explain why checking a
  citation reduces trust in it.

## Recent Research Papers

- **Fabrication and Errors in the Bibliographic Citations Generated by ChatGPT**
  Walters, W. H., & Wilder, E. I., 2023, *Scientific Reports*, 13, 14045
  [DOI](https://doi.org/10.1038/s41598-023-41032-5)
  Foundational quantitative audit: 55% of GPT-3.5 and 18% of GPT-4 citations in test literature reviews were
  fully fabricated, yet closely followed APA formatting.

- **Influence of Topic Familiarity and Prompt Specificity on Citation Fabrication in Mental Health Research Using Large Language Models: Experimental Study**
  Linardon, J., et al., 2025, *JMIR Mental Health*, 12(1), e80371
  [DOI](https://doi.org/10.2196/80371)
  Shows fabrication rate varies 6%–46% depending on topic visibility and prompt specificity within one field.

- **Citations and Trust in LLM Generated Answers**
  Ding, Y., et al., 2025, arXiv preprint
  [Paper](https://arxiv.org/abs/2501.01303)
  Randomized experiment: citation presence increases trust even when the citation is random/irrelevant;
  checking a citation lowers trust. Central empirical source for this project's argument.

- **CiteCheck: Retrieval-Grounded Detection of LLM Citation Hallucinations in Scientific Text**
  arXiv preprint, 2026
  [Paper](https://arxiv.org/abs/2605.27700)
  Introduces a hybrid retrieval + LLM-verifier pipeline and a 982-citation physics benchmark with controlled
  metadata corruptions; 88.7 macro-F1, beating GPT/Claude/Gemini baselines.

- **CiteAudit: You Cited It, But Did You Read It? A Benchmark for Verifying Scientific References in the LLM Era**
  arXiv preprint, 2026
  [Paper](https://arxiv.org/abs/2602.23452)
  Multi-agent verification pipeline (extraction → memory lookup → web retrieval → scholar search → judgment)
  with a large, human-validated, multi-domain hallucinated-citation dataset.

- **Who Checks the Citations? Benchmarking Legal Hallucination Detection**
  arXiv preprint, 2026
  [Paper](https://arxiv.org/abs/2606.21155)
  Extends citation-hallucination auditing to legal case citations; shows agentic verifiers catch fabricated
  cases well but struggle with misquotes and content misrepresentation — a useful cross-domain comparison.

- **Visualizing and Benchmarking LLM Factual Hallucination Tendencies via Internal State Analysis and Clustering (FalseCite)**
  arXiv preprint, 2026
  [Paper](https://arxiv.org/abs/2602.11167)
  Introduces FalseCite, an 82k-claim benchmark studying how fabricated citations amplify a model's confidence
  in false claims.

- **How LLMs Cite and Why It Matters: A Cross-Model Audit of Reference Fabrication in AI-Assisted Academic Writing and Methods to Detect Phantom Citations**
  arXiv preprint, 2026
  [Paper](https://arxiv.org/abs/2603.03299)
  Cross-model audit situating fabrication rates by topic visibility/specialization; useful literature-review
  chapter summarizing many other studies in this list.

- **Compound Deception in Elite Peer Review: A Failure Mode Taxonomy of 100 Fabricated Citations at NeurIPS 2025**
  Ansari, S., 2026, arXiv preprint
  [Paper](https://arxiv.org/abs/2602.05930)
  Shows fabricated citations reaching top peer-reviewed AI venues despite expert review; five-category failure
  taxonomy.

- **The Case of the Mysterious Citations**
  arXiv preprint, 2026
  [Paper](https://arxiv.org/abs/2602.05867)
  Longitudinal (2021 vs. 2025) audit of four HPC conference proceedings showing a rise in unverifiable
  citations coincident with generative-AI adoption.

- **HypoTermQA: Hypothetical Terms Dataset for Benchmarking Hallucination Tendency of LLMs**
  arXiv preprint, 2024
  [Paper](https://arxiv.org/abs/2402.16211)
  Surveys prior hallucination benchmarks (HaluEval, PHD, AutoHall, HILT, FACTCHD) and proposes a new one;
  useful map of the broader hallucination-benchmark landscape beyond citations specifically.

## Datasets

- **CiteCheck Physics Citation Benchmark** — 982 real physics citations with controlled corruptions (author,
  year, title, identifier perturbations, and full fabrications), used to train/evaluate citation verifiers.
  Source: [arXiv:2605.27700](https://arxiv.org/abs/2605.27700). Use: benchmarking citation-verification models.

- **CiteAudit Dataset** — large-scale, human-validated, multi-domain dataset of hallucinated vs. valid
  citations spanning multiple citation formats and hallucination types.
  Source: [arXiv:2602.23452](https://arxiv.org/abs/2602.23452). Use: training/evaluating multi-agent citation
  verification pipelines.

- **HALLMARK: Citation Hallucination Detection Benchmark for ML Papers** — 2,525+ annotated entries, 14
  hallucination types, 3 difficulty tiers, with 10 baseline verifiers evaluated.
  Source: [GitHub — rpatrik96/hallmark](https://github.com/rpatrik96/hallmark). Use: benchmarking detection
  tools against a graded-difficulty hallucination taxonomy.

## Tools and Libraries

- **Crossref REST API** — free, authoritative API for resolving DOIs to real bibliographic metadata; the
  primary tool for checking whether a cited DOI actually exists and matches its claimed title/authors.
  [https://www.crossref.org/documentation/retrieve-metadata/rest-api/](https://www.crossref.org/documentation/retrieve-metadata/rest-api/)

- **OpenAlex API** — open, free scholarly-metadata index (successor to Microsoft Academic Graph); used by
  several tools below for candidate retrieval during citation verification.
  [https://openalex.org/](https://openalex.org/)

- **Semantic Scholar API** — free API providing paper search, citation graphs, and metadata; used to verify
  author names and venues for a candidate citation.
  [https://www.semanticscholar.org/product/api](https://www.semanticscholar.org/product/api)

- **Zotero** — free, open-source reference manager; useful for tracking and organizing the verified references
  collected in this repository, with built-in DOI/metadata lookup.
  [https://www.zotero.org/](https://www.zotero.org/)

- **Unpaywall** — free API/browser extension that finds legal open-access versions of papers, useful for
  confirming a citation resolves to an actual, readable document rather than a broken or paywalled dead end.
  [https://unpaywall.org/](https://unpaywall.org/)

## GitHub Implementations

- **Vikranth3140/Citation-Hallucination-Detection** — hybrid pipeline combining exact bibliographic lookup
  (Crossref/OpenAlex/Semantic Scholar), fuzzy matching, and optional LLM verification to label citations as
  valid, partially valid, or hallucinated.
  [https://github.com/Vikranth3140/Citation-Hallucination-Detection](https://github.com/Vikranth3140/Citation-Hallucination-Detection)

- **gianlucasb/hallucinator** — CLI tool that scans academic PDFs for potentially hallucinated references
  using local/online IACR, ACL Anthology, and OpenAlex indexes; explicitly built in response to fabricated
  citations found at real conferences (ACSAC 2025, ICLR/ICML 2026 incidents).
  [https://github.com/gianlucasb/hallucinator](https://github.com/gianlucasb/hallucinator)

- **markrussinovich/refchecker** — reference-validation tool supporting single papers, bulk batches, and
  automated scanning of entire OpenReview conference venues, with LLM-assisted re-verification when a better
  metadata match is found.
  [https://github.com/markrussinovich/refchecker](https://github.com/markrussinovich/refchecker)

- **rpatrik96/hallmark** — benchmark + baseline-evaluation codebase for citation hallucination detection
  (paired with the HALLMARK dataset above); includes DOI-only, agentic-LLM, and ensemble baselines.
  [https://github.com/rpatrik96/hallmark](https://github.com/rpatrik96/hallmark)

- **OpenKG-ORG/EasyDetect** — general-purpose, extensible hallucination-detection framework for LLMs (text
  and multimodal); useful as a comparison point for how citation-specific tools relate to general
  hallucination-detection research.
  [https://github.com/OpenKG-ORG/EasyDetect](https://github.com/OpenKG-ORG/EasyDetect)

## Tutorials and Learning Resources

- **Crossref REST API Documentation** — official docs for querying DOI metadata programmatically.
  [https://www.crossref.org/documentation/retrieve-metadata/rest-api/](https://www.crossref.org/documentation/retrieve-metadata/rest-api/)

- **OpenAlex API Documentation** — official guide to querying works, authors, and venues.
  [https://docs.openalex.org/](https://docs.openalex.org/)

- **Semantic Scholar API Documentation** — official guide to the paper/author/citation-graph endpoints.
  [https://api.semanticscholar.org/api-docs/](https://api.semanticscholar.org/api-docs/)

- **GitHub Docs: Hello World** — official beginner walkthrough of repositories, commits, branches, and pull
  requests, useful for the Git/commit-practice portion of this assignment.
  [https://docs.github.com/en/get-started/quickstart/hello-world](https://docs.github.com/en/get-started/quickstart/hello-world)

- **GitHub Docs: Basic Writing and Formatting Syntax (Markdown)** — official Markdown reference used to build
  this README.
  [https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

## License

Content in this repository (README text, the audit document, and my own paper) is released under the
[MIT License](LICENSE) unless otherwise noted. Linked external papers, datasets, and tools remain under their
original licenses/copyright — this repository links to them rather than redistributing copyrighted PDFs.

---
layout: page
title: Artifact Evaluation
---

CAV allows authors of accepted papers to submit paper artifacts to strengthen confidence in validity of the claims in the papers, in reproducibility of the obtained results, and in usability of the developed tools by other researchers. **New in CAV 2026**: artifact submission is not required for papers of any category, it is, however, encouraged for papers of all categories, especially for (short) tool papers. Results of artifact evaluation do not affect paper decisions. We note that during submission of a paper, authors will be required to indicate whether they plan to submit an artifact in the case their paper is accepted.

# Important Dates
All deadlines are AoE (Anywhere on Earth).

* Paper notification: April 17, 2026
* Artifact registration: April 22, 2026
* Artifact submission: April 27, 2026
* Smoke test phase: April 28–May 3, 2026
* Artifact revision period: May 4–May 8, 2026
* Full review period; May 9–May 24, 2026
* Artifact notification: Friday, May 29, 2026

# Submission Site

[https://submissions.floc26.org/cav-ae](https://submissions.floc26.org/cav-ae)

# Setup
CAV 2026 artifact evaluation will be single-blind (you don’t need to modify the paper that you submitted to CAV with the authors if it didn’t have them, e.g. for regular or application papers, but they will be seen in the submission system).

We will be attributing 3 kinds of badges, aligned with [ACM artifact criteria](https://www.acm.org/publications/policies/artifact-review-and-badging-current):

* **Available**: available on a publicly accessible archival repository with a DOI
* **Functional**: documented, consistent, complete, exercisable
* **Reusable**: artifacts are of a quality that significantly exceeds *Functional*; see below for details

# Process
The artifact evaluation consists of two phases: the **smoke test** phase and the **full review** phase.  Each artifact will be evaluated by at least two AEC members.

In the **smoke test** phase, reviewers will download artifacts, read the artifact instructions, set up the artifacts on their machines, and attempt to run provided smoke tests. At this stage, they will not yet verify any claims from the papers. Any technical difficulties (e.g., the image does not start up, experiment script crashes) will be documented in a smoke test review. After the smoke test phase is completed, the artifact submission will be reopened to allow authors to revise the artifact. Please keep in mind that the smoke test phase is solely for resolving technical issues.

In the **full review** phase, reviewers will evaluate artifacts according to the [evaluation criteria](#evaluation-criteria) with respect to the claims in the papers and decide on the badge(s) awarded to each submission. At this stage, there may be a continuous discussion between the authors and the reviewers if necessary.

# Submission Guidelines

**TODO**

# Packaging Guidelines

**TODO**

# Evaluation Criteria

Reviewers will read the paper and run the artifact to evaluate how well the artifact supports the claims and results of the paper.  The criteria for awarding badges follow the [ACM artifact criteria](https://www.acm.org/publications/policies/artifact-review-and-badging-current) with several refinements:

## Available badge
To be **Available**, an artifact needs satisfy the following requirements:

1. Have a **DOI**.  Please upload the artifact to a repository that provides a DOI, such as [Zenodo](http://zenodo.org/), [figshare](https://figshare.com/), or [Dryad](https://datadryad.org/) and use this DOI link in your artifact submission.  If the repository also provides a *Concept DOI* (a DOI that automatically resolves to the latest version of the artifact), do not provide it; instead, provide the DOI for the specific submitted version.  
1. Have a **license** that allows running/examining the artifact within and outside of CAV 2026 Artifact Evaluation.  This does not necessitate, e.g., to allow running the artifact on different benchmarks than the provided ones, allowing modifications of the artifact, etc.

## Functional badge

To be **Functional**, the *documented*, *consistent*, *complete*, and *exercisable* criteria from [ACM artifact criteria](https://www.acm.org/publications/policies/artifact-review-and-badging-current) should be met with the following clarification:

* **Completeness**: in some cases, having an artifact reproducing all results in a paper is challenged by the need to use, e.g., proprietary software whose license does not allow it to be distributed with the artifact (e.g. MATLAB, Microsoft Office, Wolfram Mathematica, or commercial verification tools), non-standard hardware (e.g., FPGAs, GPUs, neuromorphic processors, quantum computers), external services (e.g., LLMs, running computation in the cloud, libraries accessing certain URLs), or use cases that cannot be shared with the public (e.g., they are a trade secret or are subject to responsible disclosure at the time of submitting the artifact).  In these cases, special care needs to be taken when preparing the artifact.  Possible directions are, for example,
  * substituting a proprietary software for a free equivalent (e.g., MATLAB for GNU Octave, Microsoft Office for LibreOffice or Python notebooks), with an option to switch to a non-free software (e.g., an evaluator could set his/her license key) if the free equivalent is, e.g., slower,
  * using proxies for external services (e.g., a cache of replies for prompts to LLMs), or
  * omitting inclusion of problematic use cases in the artifact.
  
  Note, however, that despite the best intentions on both sides, the effect of the changes may be too large and the results obtained during the artifact evaluation may, in turn, not be consistent with the trends in the paper any more, in which case the **Functional** badge cannot be awarded.  Please contact the AE chairs if you have questions.

## Reusable badge

We note that **Reusable** subsumes **Functional**, so in case the **Reusable** badge is awarded, the **Functional** badge is not awarded any more.
Artifacts claiming to be **Reusable** need to clear a significantly higher bar than **Functional** artifacts. First, they must be available, i.e., receive the **Available** badge. Second, we expect a higher level of quality during the evaluation of the **Functional** level, taking into account, e.g., the following criteria:

* Does the artifact have a license that allows reuse, repurposing, and is easy to use?
* Are all dependencies and used libraries well documented and up to date?
* Does the artifact's README explain how the artifact can be used beyond the paper in sufficient detail?
* Does the artifact provide documented interfaces for extensions or is the artifact open source?
* Can the artifact be used in a different environment (e.g., built on another system, used outside of the Docker or VM image, etc.)?

# Contact

For any questions regarding Artifact Evaluation, please [contact the AE chairs](mailto:lengal@fit.vutbr.cz;myreen@chalmers.se?subject=[CAV'26%20AE] FILL IN SUBJECT):

* [Ondřej Lengál](https://www.fit.vut.cz/person/lengal/), Brno University of Technology
* [Magnus Myreen](https://www.cse.chalmers.se/~myreen/), Chalmers



**\#\#END\#\#**



Members of the artifact evaluation committee and the program committee are asked to use submitted artifacts for the sole purpose of evaluating the contribution associated with the artifact.

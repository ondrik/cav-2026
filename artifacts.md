---
layout: page
title: Artifact Evaluation
---

**Self-Nominations**: We are looking for artifact reviewers!  If you are interested to serve on the CAV 2026 Artifact Evaluation Committee, please fill in [the form](https://forms.gle/N49xuaofDk1JtkBDA).

CAV allows authors of accepted papers to submit paper artifacts to strengthen confidence in validity of the claims in the papers, in reproducibility of the obtained results, and in usability of the developed tools by other researchers. **New in CAV 2026**: artifact submission is not required for papers of any category, it is, however, encouraged for papers of all categories, especially for (short) tool papers. Results of artifact evaluation do not affect paper decisions. We note that during submission of a paper, authors will be required to indicate whether they plan to submit an artifact in the case their paper is accepted.

# Important Dates
All deadlines are AoE (Anywhere on Earth).

* Paper notification: April 17, 2026
* Artifact registration: April 22, 2026
* Artifact submission: April 27, 2026
* Smoke test phase: April 28–May 3, 2026
* Artifact revision period: May 4–May 8, 2026
* Full review period; May 9–May 24, 2026
* Artifact notification: May 29, 2026

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

Unless the artifact is provided publicly (e.g., on Zenodo, figshare, Dryad), it is considered *confidential* to the CAV 2026 Artifact Evaluation. Reviewers are asked to use the artifact only as permitted by its license (this should affect you only if you are very strict about what can be done with your artifact; in that case, please make sure the license allows the reviewers to evaluate the artifact).

# Submission Guidelines

A final artifact submission consists of the following items (these are to be filled in and uploaded at the submission page):

* **ID and Title** of the CAV'26 accepted paper.
* **Paper Abstract**: Abstract of the paper accepted at CAV'26.
* **Paper PDF**: the PDF of the paper accepted at CAV'26.
* **URL**  at which the artifact package .zip file can be downloaded; if you are applying for the **Available** badge, this should be a DOI link.  For preserving reviewer anonymity, you will be required to confirm that the authors of the paper cannot track users accessing the URL. 
* **SHA256** checksum of the .zip artifact package; on the most popular operating systems, this can be obtained, e.g., by the following command line commands:
  * Linux: `sha256sum <file>`
  * Windows: `CertUtil -hashfile <file> SHA256`
  * MacOS: `shasum -a 256 <file>`
* **Type of Artifact**:
  * *virtual machine* image or *Docker* image
  * architecture for which the artifact is intended: `x86_64` (Intel) or `arm64` (Apple Silicon)
  * in the case your artifact does not fit in these categories, please contact the AE chairs as soon as possible
* **External Connectivity**: Please indicate if your artifact requires external connectivity and describe the reasons why.
* **Requested Badges**: Badges that you are applying for.

# Packaging Guidelines

Your artifact .zip file must contain the following elements:

* **image** or **package contents**:
  * either a VM or a Docker *image*
  * or a *package* to be downloaded on some standard VM image with a DOI (in that case, the contents can be directly in the artifact .zip file).  The DOI of the VM image should then be on the web page of the artifact and also in the `README` file.
* `README` file: see [below](#readme-file-structure) for recommended structure
* `LICENSE` file: the license needs to allow running/examining the artifact within the CAV 2026 Artifact Evaluation.

If you are not able to prepare the artifact as above, please contact AE chairs early for an alternative arrangement. An example of such a situation is when you cannot provide a VM or Docker image that contains licensed software (e.g., MATLAB) or similar (also see [below](#general-advice-for-creating-artifacts) for suggestions).


## README file structure

**Details will appear here later**

<!-- Describe which steps require external connectivity and why. -->

## Examples of the structure of a .zip file with an artifact:

1. VM image

    ```
    artifact
    ├── image.ova
    ├── LICENSE.txt
    └── README.md
    ```

1. Docker image

    ```
    artifact
    ├── image.tar.gz
    ├── LICENSE
    └── README
    ```

1. package

    ```
    artifact
    ├── deb-packages
    │   ├── autoconf_2.72-3ubuntu1_all.deb
    │   ├ ...
    │   └── openmpi-common_5.0.7-1_all.deb
    ├── install.sh
    ├── LICENSE
    ├── pip-packages
    │   ├── asttokens-3.0.0-py3-none-any.whl
    │   ├ ...
    │   └── wcwidth-0.2.14-py2.py3-none-any.whl
    ├── README.txt
    ├── run-all.sh
    ├── run-smoke.sh
    └── tool
        ├── CMakeLists.txt
        ├ ...
        └── README.md 
    ```


# Evaluation Criteria

Reviewers will read the paper and run the artifact to evaluate how well the artifact supports the claims and results of the paper.  The criteria for awarding badges follow the [ACM artifact criteria](https://www.acm.org/publications/policies/artifact-review-and-badging-current) (**if you are not familiar with them, please read them carefully before you proceed**) with several refinements:

## Available badge
To be **Available**, an artifact needs satisfy the following requirements:

1. Have a **DOI**.  Please upload the artifact to a repository that provides a DOI, such as [Zenodo](http://zenodo.org/), [figshare](https://figshare.com/), or [Dryad](https://datadryad.org/) and use this DOI link in your artifact submission.  If the repository also provides a *Concept DOI* (a DOI that automatically resolves to the latest version of the artifact), do not provide it; instead, provide the DOI for the specific submitted version.  In case you are submitting a *package* artifact, the DOI of the basic VM image should be given on the web page with the artifact.
1. Have a **license** that allows running/examining the artifact within and outside of CAV 2026 Artifact Evaluation.  This does not necessitate, e.g., to allow running the artifact on different benchmarks than the provided ones, allowing modifications of the artifact, etc.

## Functional badge

To be **Functional**, the *documented*, *consistent*, *complete*, and *exercisable* criteria from [ACM artifact criteria](https://www.acm.org/publications/policies/artifact-review-and-badging-current) should be met with the following clarification:

* **Completeness**: in some cases, having an artifact that reproduces all results in a paper is challenged by the need to use, e.g., proprietary software whose license does not allow it to be distributed with the artifact (e.g. MATLAB, Microsoft Office, Wolfram Mathematica, or commercial verification tools), non-standard hardware (e.g., FPGAs, GPUs, neuromorphic processors, quantum computers), external services (e.g., LLMs, running computation in the cloud, libraries accessing certain URLs), or use cases that cannot be shared with the public (e.g., they are a trade secret or are subject to responsible disclosure at the time of submitting the artifact).  In these cases, special care needs to be taken when preparing the artifact.  Possible directions are, for example,
  * substituting a proprietary software for a free equivalent (e.g., MATLAB for GNU Octave, Microsoft Office for LibreOffice or Python notebooks), with an option to switch to a non-free software (e.g., evaluators could set their license key) if the free equivalent is, e.g., slower,
  * using proxies for external services (e.g., a cache of replies for prompts to LLMs), or
  * omitting inclusion of problematic use cases in the artifact.
  
  Note, however, that despite the best intentions on both sides, the effect of the changes may be too large and the results obtained during the artifact evaluation may, in turn, not be consistent with the trends in the paper anymore, in which case the **Functional** badge cannot be awarded.  Please contact the AE chairs if you have questions.

## Reusable badge

We note that **Reusable** subsumes **Functional**, so in case the **Reusable** badge is awarded, the **Functional** badge is not awarded any more.
Artifacts claiming to be **Reusable** need to clear a significantly higher bar than **Functional** artifacts. First, they must be available, i.e., receive the **Available** badge. Second, we expect a higher level of quality during the evaluation of the **Functional** level, taking into account, e.g., the following criteria:

* Does the artifact have a license that allows reuse, repurposing, and is easy to use?
* Are all dependencies and used libraries well documented and up to date?
* Does the artifact's README explain how the artifact can be used beyond the paper in sufficient detail?
* Does the artifact provide documented interfaces for extensions or is the artifact open source?
* Can the artifact be used in a different environment (e.g., built on another system, used outside of the Docker or VM image, etc.)?

# General Advice for Creating Artifacts

1. **Start early.**  There are 10 days between CAV paper notification and the artifact submission deadline, which is not so much time.  We advise you to start preparing an artifact already before the paper notification date.  After all, if the paper is rejected from CAV'26, you will most probably want to resubmit it to a different conference, together with the same or a similar artifact.  Moreover, having a nicely structured artifact pays off in the long run, as you can use it as a basis for other artifacts in the future.
1. **Users are not your beta testers.**  You should have a second person (other than the one(s) who prepared the artifact) to try to run it from the scratch, i.e., as the reviewers will run it, starting from its download and using the same instructions.  If issues are found and fixed, next time, try it again from the scratch, as other things could have broken.  Keep repeating until everything works.  If you do not have a second person, do it yourself, but start from scratch.
1. **Keep it simple, stupid.**  The provided instructions should allow the results to be reproduced by any computer science graduate with a working knowledge of the command line.  Do not assume any expertise in your field.  If appropriate, provide toy examples and instructions on how to use them.  Do not assume the user is a Docker expert—if you are submitting a Docker artifact, give step-by-step instructions on how to set it up. 
1. **Be clear.**  Be clear about how the outputs obtained using the artifact map to the results in the paper (e.g. "After the scripts finishes, the graph in `figs/results-Fig1.pdf` should match the graph in Fig. 1 in the paper").
1. **Time is dear.**  Please provide an estimate how long each non-trivial step in the instructions takes, so that reviewers can use it for planning (e.g., longer steps can be run overnight).  Provide *progress indicators* (e.g. `running task 42/1337`). If it takes your artifact a long time (e.g. several days or weeks) to reproduce the results in the paper (there is nothing wrong about it *per se*), please provide an option to reproduce a representative subset of the results that can be run in about 8 hours on a laptop.
1. **Make it all replicable.**  While submitting a VM/Docker image with a binary of your tool, one script, and the benchmarks is possible and sufficient to satisfy the formal requirements for the **Functional** badge, this will not make your artifact easy to use (and certainly will not qualify for the **Reusable** badge).  Instead, having a package (e.g., in the form of a .zip file containing a git repository) that one can download on some standard VM image and setup there makes your artifact more user-friendly and reusable.  Note that this may require also bundling, e.g., `.deb` files and `pip` packages with your artifact (see, e.g., [here](https://zenodo.org/records/2759473) for guidelines on how to prepare such a package). 
1. **Make it standalone.**  Avoid connecting to external services as much as possible.  For instance, include required packages to avoid installing from the Internet (web services can move/terminate over time, packages can be removed, API endpoints can change, free services can become paid).  See the above note on **Completeness** in the [Functional badge](#functional-badge) section for ideas on how to deal with the situation if external services are required for your artifact.


# Contact

For any questions regarding Artifact Evaluation, please [contact the AE chairs](mailto:lengal@fit.vutbr.cz;myreen@chalmers.se?subject=[CAV'26%20AE] FILL IN SUBJECT):

* [Ondřej Lengál](https://www.fit.vut.cz/person/lengal/), Brno University of Technology, Czech Republic
* [Magnus Myreen](https://www.cse.chalmers.se/~myreen/), Chalmers, Sweden
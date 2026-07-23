# GEMINI.md - Repository Instructional Context

This file provides foundational context, directory structure, and operational guidance for Gemini CLI (and other AI assistants) when interacting with the `wg_WGMLEARN` repository.

## Directory Overview

The `wg_WGMLEARN` repository belongs to the **ICES Working Group on Machine Learning in Marine Science (WGMLEARN)**. 

### Mission and Purpose
The field of Machine Learning (ML) and Artificial Intelligence (AI) is developing rapidly. These technologies are instrumental for marine research and resource management. WGMLEARN aims to:
- Provide advice, comments, or inputs to other ICES expert groups seeking AI/ML guidance.
- Identify AI/ML challenges unique to the marine domain that mainstream ML research does not adequately address.
- Highlight unique marine science challenges and link them to appropriate training sets and test cases to steer broader ML research toward high-value opportunities in marine science and management.

This repository serves as a **collaborative workspace, planning center, and documentation store** for tracking Terms of Reference (ToRs), deliverables, meeting outputs, and resources. While it is primarily a **Non-Code Project**, it supports scripts/tools for analytics and prototype modeling (e.g., in Python or R).

---

## Directory Structure & Key Files

The repository is organized around the working group's Terms of Reference (ToRs), references, and static documentation.

```
.
├── .gitignore                          # R-project & general git ignore rules
├── LICENSE                             # MIT License (ICES Expert Groups)
├── README.md                           # Main WGMLEARN mission statement and meeting log
├── test.py                             # Local scratchpad or prototyping script (currently empty)
├── docs/                               # Target directory for built documentation (pkgdown/ignored)
├── references/                         # Intended directory for storing literature and reference files
└── ToR/                                # Terms of Reference (ToR) tracking folders
    ├── ToR a - identify unmet challenges/
    │   ├── readme.md                   # Goals and description of ToR a
    │   └── table-unmet_challenges.md   # Comprehensive list of marine-specific ML challenges
    ├── ToR b - coordinate ICES working groups/
    │   └── readme.md                   # Collaboration and strategic coordination objectives (ToR b)
    └── ToR c - organize events/
        └── readme.md                   # Events execution (tutorials, hackathons, workshops) (ToR c)
```

### Key Files and Contents

1. **`README.md`**
   - Introduces the main WGMLEARN mission.
   - Contains a placeholder for Meetings.

2. **`ToR/ToR a - identify unmet challenges/readme.md`**
   - **Description**: Develop a list of AI/ML topics/tasks highlighting unmet challenges specific to the marine domain and potential benefits. Integrates output from WKAAII and links to relevant ICES working groups, research groups, and public datasets.
   - **Deliverables**: A review paper (food-for-thought format).

3. **`ToR/ToR a - identify unmet challenges/table-unmet_challenges.md`**
   - A highly valuable, living matrix mapping marine-specific AI/ML challenges, details, and context. Key challenges identified include:
     - *Data Quality & Noise*: Weather/waves, small vessels.
     - *Data Complexity*: Multi-modal, complex, hierarchical (non-flat) labels (e.g., plankton data).
     - *Collection & Robotics*: Fleet management of autonomous platforms.
     - *Edge/Remote Solutions*: Real-time edge computing (e.g., satellite, LiDAR, drones).
     - *Advanced AI*: LLMs, active learning, self-optimizing models.
     - *Labeling & Annotation*: Overcoming the annotation challenge (e.g., acoustics vs. trawl samples, SAM+DINO, active learning).
     - *AI-Ready Marine Data*: Standardization, actual adoption of FAIR standards.
     - *Data Governance*: Shared platforms, code reuse.
     - *Deployment & Operations*: Moving pilots to value creation, DevOps.
     - *Hybrid Modeling*: Merging physical/mechanistic models with data-driven approaches.
     - *Foundation Models*: Species and annotation foundation models (e.g., AqQua for plankton).
     - *Underwater Systems*: Temporal camera data and behavior patterns.
     - *Specialized Domains*: Acoustics scale, plankton imaging, otolith/scale information extraction.

4. **`ToR/ToR b - coordinate ICES working groups/readme.md`**
   - **Description**: Establish contact with other ICES working groups to explore collaboration, chart research needs, and support AI at the ICES strategic level.
   - **Deliverables**: List of networking contacts (mailing list/database), participation in relevant symposia/meetings.

5. **`ToR/ToR c - organize events/readme.md`**
   - **Description**: Organize 5-10 capacity-building events (tutorials, hackathons, workshops, conference sessions) co-organized with ICES groups or other entities.
   - **Deliverables**:
     - *Tutorials*: Reusable online learning modules, video recordings.
     - *Hackathons*: Open-source code repositories (GitHub) containing prototype algorithms, workflows, or data products, and peer-reviewed technical manuscripts.

---

## Usage & Interaction Guidelines

### For AI Assistants & Contributors
When helping maintain, update, or expand this repository:

1. **Document-First Approach**:
   - Updates should focus on clarity, precise Markdown styling, and structured representation of metadata.
   - Keep the Terms of Reference directories synchronized with the actual group's progress and deliverables.
   - When updating lists, tables (e.g., `table-unmet_challenges.md`), or files, preserve existing columns and ensure semantic linkage to other ICES working groups or public datasets.

2. **Technology Context**:
   - **R Environment**: The `.gitignore` is pre-configured for R projects (e.g., `.Rhistory`, `.RData`, `vignettes/`, and `docs/` built via `pkgdown`). Assume R may be used for analytical tasks, package creation, or static documentation generation.
   - **Python Environment**: `test.py` indicates a lightweight Python setup. Python is typical for implementing advanced AI/ML algorithms mentioned in the challenges (e.g., SAM+DINO, LLMs, Foundation Models).
   - **Static Assets & Documentation**: Do not manually stage, modify, or commit built documentation in `docs/` or session caches, as these should be generated dynamically or remain excluded per `.gitignore`.

3. **Writing Conventions**:
   - Use clear, professional, and scientific language consistent with ICES expert group standards.
   - Ensure all markdown lists are easy to read and use appropriate emojis for readability if requested (matching the style established in `table-unmet_challenges.md`).
   - Use clean relative paths for linking documents within the repository (e.g., linking a future list of contacts in ToR b to the main `README.md`).

4. **Git Etiquette**:
   - Never stage or commit changes unless explicitly instructed by the user.
   - Propose draft commit messages when preparing updates.

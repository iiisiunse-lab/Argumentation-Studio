# Argumentation Studio

Interactive reference implementations of the **Labeled Argumentation Frameworks (LAF)** research line and its extensions, developed at the Institute for Research in Computer Science and Information Systems (IIISI), FCEyT, Universidad Nacional de Santiago del Estero, Argentina.

**▶ Live demo:** https://iiisiunse-lab.github.io/Argumentation-Studio/

---

## What this is

Six formalisms, one thread: reasoning with arguments that *support* and *attack* each other, enriched with labels, similarity, interpretations, social endorsement, hashtags and graded strength — and made to talk to one another.

Each module is a self-contained, faithful implementation of the corresponding paper, with every worked example from that paper preloaded and ready to run. The tools are not illustrations: they compute extensions, verify structural conditions, and in the case of IAF re-verify the formal results of the paper by exhaustive search over the loaded instance.

The whole platform is a single HTML page. No build step, no server, no external dependencies, no installation. Open it in a browser and it runs.

## The six modules

| Module | Focus | Reference |
|---|---|---|
| **InterArg** | Translation between DeLP, ABA and Labeled AFs using LAF as a pivot, tracking what is preserved, approximated or lost | *In preparation* |
| **L-BAF** | Propagation of multi-feature label algebras through support and attack; gradual status, value-based extensions and pruning | M. G. Escañuela Gonzalez, M. C. D. Budán, G. I. Simari, G. R. Simari. Labeled Bipolar Argumentation Frameworks. *Journal of Artificial Intelligence Research* 70:1557–1636, 2021. [doi:10.1613/jair.1.12394](https://doi.org/10.1613/jair.1.12394) |
| **S-BAF** | Similarity between arguments as a first-class notion: cohesion and controversy values refining attack and support | P. D. Budán, M. G. Escañuela Gonzalez, M. C. D. Budán, M. V. Martinez, G. R. Simari. Similarity notions in bipolar abstract argumentation. *Argument & Computation* 11(1-2):103–149, 2020. [doi:10.3233/AAC-190479](https://doi.org/10.3233/AAC-190479) |
| **IAF** | The pre-argumentative layer: coherent interpretations, rational positions, and construction of the induced AF/BAF | C. A. Habiñak, D. C. Martinez, G. I. Simari, M. C. D. Budán. A Pre-Argumentative Framework for Formalizing Interpretation and Rational Positions. *Information Sciences*, Elsevier. **Under review** |
| **AdP-LAF** | Popularity-based endorsement in labeled frameworks: propagation of social support and detection of ad-populum schemes | P. D. Budán, M. J. Debórtoli, M. C. D. Budán, G. I. Simari, M. V. Martinez. Unveiling argumentative communities through ad-populum argumentation schemes. *Argument & Computation*, SAGE, 2026. [doi:10.1177/19462174261466579](https://doi.org/10.1177/19462174261466579) |
| **L-HAF** | Structuring multi-topic debate through hashtagged arguments: individual neighbourhoods of proximity and neighbourhood-based admissibility | I. M. Coronel, M. G. Escañuela Gonzalez, D. C. Martínez, G. I. Simari, M. C. D. Budán. Neighborhood-based argumental community support in the context of multi-topic debates. *International Journal of Approximate Reasoning* 170:109189, 2024. [doi:10.1016/j.ijar.2024.109189](https://doi.org/10.1016/j.ijar.2024.109189) |

### Foundations

The label-based approach underlying all six modules was introduced in:

- Budán, Gómez Lucero, Chesñevar & Simari. Modeling time and valuation in structured argumentation frameworks. *Information Sciences* 290:22–44, 2015.
- Budán, Simari, Viglizzo & Simari. An approach to characterize graded entailment of arguments through a label-based framework. *International Journal of Approximate Reasoning* 82:242–269, 2017.
- Budán, Cobo, Martinez & Simari. Proximity semantics for topic-based abstract argumentation. *Information Sciences* 508:135–153, 2020.

## Usage

Open the [live demo](https://iiisiunse-lab.github.io/Argumentation-Studio/), or download `index.html` and open it directly in any modern browser. Both work identically; the file is fully self-contained.

From the landing page, select **Enter the studio** and switch between modules using the top navigation bar. Each module loads its own worked examples from the corresponding paper.

### Optional: language-model features

The IAF module offers three assisted routes for eliciting interpretations (single-call generation, multi-agent personas, and ambiguity-marker detection). The first two require a language-model server reachable from the browser; the address is configured inside the module and defaults to a local Ollama instance at `http://localhost:11434`.

**All formal computation works without it.** The elicitation routes populate candidate readings; the semantics, the well-formedness audit, the certifier and the induced frameworks are exact and run entirely offline.

## The IAF module

The most developed module implements the Interpretative Argumentation Framework as an eight-stage workflow that follows the structure of the paper: source and knowledge pieces → interpretations → conflict and refinement relations → interpretative structure → guidelines → positions → certification → induced AF/BAF.

Three features are worth singling out:

- **Well-formedness audit.** The four structural conditions of the framework are re-checked after every edit and after every automated pass, with a repair action that enforces them (symmetry and irreflexivity of conflict, the preorder closure of refinement, pruning of dangling links, and stabilisation of the partition on interpretations).
- **Certification.** Every proposition and theorem of the paper is re-verified by exhaustive search over the guideline and position families of the loaded instance, and reported as verified, vacuous (hypotheses do not hold here) or failing.
- **Exact enumeration.** Guidelines and positions are enumerated in full rather than sampled; the predicted and enumerated counts are compared at runtime as a consistency check.

## How to cite

Please cite the paper corresponding to the module you used (see the table above). To cite the software itself, use the metadata in [`CITATION.cff`](CITATION.cff) or the **Cite this repository** button.

## Authorship

Developed at the **Instituto de Investigación en Informática y Sistemas de Información (IIISI)**, Facultad de Ciencias Exactas y Tecnologías, Universidad Nacional de Santiago del Estero, Argentina.

Principal investigator: **Dr. Maximiliano C. D. Budán** — CONICET / IIISI–FCEyT–UNSE
[ORCID 0000-0002-9900-6511](https://orcid.org/0000-0002-9900-6511) · mbudan@unse.edu.ar

Co-author researchers: Paola D. Budán, Melisa G. Escañuela Gonzalez, Diego C. Martínez, María Vanina Martinez, Gerardo I. Simari, Guillermo R. Simari.
Research fellows: Irene M. Coronel, Carlos Habiñak, Javier M. Debórtoli.

This work is supported by the projects *Inteligencia Artificial al servicio de la comunidad: un enfoque predictivo y personalizado* (CICyT-UNSE 23/C222-Bint-2025) and *Aplicaciones de Topología y la Teoría de Categorías a la Argumentación Rebatible* (CICyT-UNSE 23/C207-Bint-2024), and by sustained collaboration with the Institute for Computer Science and Engineering (ICIC, CONICET–UNS).

## License

Distributed under the MIT License. See [`LICENSE`](LICENSE).

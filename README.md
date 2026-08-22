# euler-diagrams-llm

_Evaluating syllogistic reasoning in large language models using Euler and linear diagrams_

This repository contains datasets associated with two papers:

- the Diagrams 2024 paper, ["Can Euler Diagrams Improve Syllogistic Reasoning in Large Language Models?"](https://link.springer.com/chapter/10.1007/978-3-031-71291-3_19)
- the Diagrams 2026 paper, ["Do Diagrams Help Large Language Models Reason? Evidence from Syllogistic Reasoning"](https://link.springer.com/chapter/10.1007/978-3-032-34178-5_30)

The Diagrams 2026 study extends the validity-checking dataset from the Diagrams 2024 study with logical notation and ASCII linear-diagram representations. The original VC285 data and Euler-diagram images are shared between the two studies.

## Contents

- [Datasets](#datasets)
  - [Dataset Overview](#dataset-overview)
  - [Euler Diagram Images](#euler-diagram-images)
  - [Validity Checking Task Format](#validity-checking-task-format)
  - [Linear Diagram Representations](#linear-diagram-representations)
  - [Multiple-Choice Task Format](#multiple-choice-task-format)
- [Citation](#citation)
  - [Diagrams 2024](#diagrams-2024)
  - [Diagrams 2026](#diagrams-2026)
- [License](#license)

## Datasets

### Dataset Overview

| Resource | Location | Used in | Description |
| ---- | ---- | ---- | ---- |
| Euler diagram images | `data/images/` | Diagrams 2024 and 2026 | Euler diagrams representing pairs of premises |
| Validity-checking dataset | `data/EulerDiagramSynth_VC285.tsv` | Diagrams 2024 and 2026 | 285 syllogistic validity-checking problems |
| Linear representations | `data/LinearDiagramSynth_VC285.tsv` | Diagrams 2026 | Self-contained VC285 task data with logical notation and ASCII linear diagrams |
| Multiple-choice dataset | `data/EulerDiagramSynth_MC194.tsv` | Diagrams 2024 | 194 multiple-choice syllogistic problems |

### Euler Diagram Images

#### Files

[`data/images/*.png`](https://github.com/kmineshima/euler-diagrams-llm/tree/main/data/images/)

#### Description

Images of Euler diagrams representing premises of syllogistic reasoning problems.

### Validity Checking Task Format

#### File

[`data/EulerDiagramSynth_VC285.tsv`](https://github.com/kmineshima/euler-diagrams-llm/blob/main/data/EulerDiagramSynth_VC285.tsv)

#### Description

| Column Name | Description |
| ---- | ---- |
| premises_en | two premises in English |
| hypothesis_en | one hypothesis in English |
| gold | correct answer, the relationship of the hypothesis to the premises (*entailment*, *contradiction*, *neutral*) |
| content-type | classification based on belief congruency (*symbolic*, *congruent*, *incongruent*) |
| conversion | associated with conversion error (*yes*, *no*) |
| conversion-type | the type of conversion error (*A*, *O*, *n/a*) |
| mood | the form of each premise and conclusion (three letters composed of A, E, I and O) |
| figure | code for the order in which each term appears (1-4) |
| image_id | image ID of Euler diagram |
| image_path | image path of Euler diagram (see [Euler Diagram Images](#euler-diagram-images)) |
| term1 | term 1 used in the syllogism |
| term2 | term 2 used in the syllogism |
| term3 | term 3 used in the syllogism |

- See [our paper](#citation) for details.

### Linear Diagram Representations

#### File

[`data/LinearDiagramSynth_VC285.tsv`](https://github.com/kmineshima/euler-diagrams-llm/blob/main/data/LinearDiagramSynth_VC285.tsv)

#### Description

This self-contained file provides the task information, logical notation, and ASCII linear-diagram representations used in the Diagrams 2026 paper. It can be used independently for experiments and analysis.

Each record corresponds to a problem in `EulerDiagramSynth_VC285.tsv`. The two files can also be linked using the combination of `image_id` and `mood`.

| Column Name | Description |
| ---- | ---- |
| premises_en | two premises in English |
| hypothesis_en | one hypothesis in English |
| gold | correct answer (*entailment*, *contradiction*, or *neutral*) |
| content-type | classification based on belief congruency (*symbolic*, *congruent*, or *incongruent*) |
| conversion | whether the problem is associated with a conversion error (*yes* or *no*) |
| figure | code for the order in which each term appears (1-4) |
| image_id | image ID used to link the record to VC285 |
| mood | syllogistic mood; used with `image_id` as the record key |
| premise1_logic | logical notation for the first premise |
| premise2_logic | logical notation for the second premise |
| premise1_ascii | ASCII linear diagram for the first premise |
| premise2_ascii | ASCII linear diagram for the second premise |

In the linear diagrams:

- each line represents a set;
- overlapping line segments represent overlapping sets;
- separated line segments represent disjoint sets; and
- `x` represents the existence of at least one element.

### Multiple-Choice Task Format

#### File

[`data/EulerDiagramSynth_MC194.tsv`](https://github.com/kmineshima/euler-diagrams-llm/blob/main/data/EulerDiagramSynth_MC194.tsv)

#### Description

| Column Name | Description |
| ---- | ---- |
| ID | problem ID |
| premises_en | two premises in English |
| hypothesis_en_1 | hypothesis 1 in English |
| hypothesis_en_2 | hypothesis 2 in English |
| hypothesis_en_3 | hypothesis 3 in English |
| hypothesis_en_4 | hypothesis 4 in English |
| hypothesis_en_5 | hypothesis 5 in English |
| mood_premises | the form of each premise (two letters composed of A, E, I and O) |
| figure | code for the order in which each term appears (1-4) |
| has-conclusion | whether the problem has a valid conclusion (*yes*, *no*) |
| gold | correct answer (1-5) |
| content-type | classification based on belief congruency (*symbolic*, *contentual*, *congruent*, *incongruent*) |
| conversion | associated with conversion error (*yes*, *no*) |
| conversion-type | the type of conversion error (*A*, *O*, *n/a*) |
| image_id | image ID of Euler diagram |
| image_path | image path of Euler diagram (see [Euler Diagram Images](#euler-diagram-images)) |
| term1 | term 1 used in the syllogism |
| term2 | term 2 used in the syllogism |
| term3 | term 3 used in the syllogism |

- **NOTE:** One of the five hypotheses is "none of them".

## Citation

Please cite the paper corresponding to the dataset or representation you use.

### Diagrams 2024

For the original VC285 and MC194 datasets and Euler-diagram images:

- Risako Ando, Kentaro Ozeki, Takanobu Morishita, Hirohiko Abe, Koji Mineshima, and Mitsuhiro Okada, ["Can Euler Diagrams Improve Syllogistic Reasoning in Large Language Models?"](https://link.springer.com/chapter/10.1007/978-3-031-71291-3_19), *Proceedings of 14th International Conference on the Theory and Application of Diagrams* (Diagrams 2024), Lecture Notes in Computer Science (LNAI), Volume 14981, Springer, 232-248, 2024.

```
@InProceedings{ando-et-al-2024-euler-diagrams-llm,
author="Ando, Risako and Ozeki, Kentaro and Morishita, Takanobu and Abe, Hirohiko and Mineshima, Koji and Okada, Mitsuhiro",
editor="Lemanski, Jens and Johansen, Mikkel Willum and Manalo, Emmanuel
and Viana, Petrucio and Bhattacharjee, Reetu and Burns, Richard",
title="Can Euler Diagrams Improve Syllogistic Reasoning in Large Language Models?",
booktitle="Diagrammatic Representation and Inference",
series="Lecture Notes in Computer Science (LNAI)",
volume="14981",
year="2024",
publisher="Springer",
pages="232--248",
doi="https://doi.org/10.1007/978-3-031-71291-3_19"
}
```

### Diagrams 2026

For the logical and linear-diagram representations:

- Risako Ando and Koji Mineshima, ["Do Diagrams Help Large Language Models Reason? Evidence from Syllogistic Reasoning"](https://link.springer.com/chapter/10.1007/978-3-032-34178-5_30), *Diagrammatic Representation and Inference* (Diagrams 2026), Lecture Notes in Computer Science (LNAI), Volume 16833, Springer Nature Switzerland, 284-292, 2027.

The paper was presented at Diagrams 2026; the Springer proceedings volume is dated 2027.

```
@InProceedings{ando-mineshima-2027-diagrams-help-llms,
author="Ando, Risako and Mineshima, Koji",
editor="Soboci{\'{n}}ski, Pawe{\l} and Bellucci, Francesco and Moktefi, Amirouche
and Beisecker, Dave and Shimojima, Atsushi and de Vries, Erica
and Bhattacharjee, Reetu",
title="Do Diagrams Help Large Language Models Reason? Evidence from Syllogistic Reasoning",
booktitle="Diagrammatic Representation and Inference",
series="Lecture Notes in Computer Science (LNAI)",
volume="16833",
year="2027",
publisher="Springer Nature Switzerland",
address="Cham",
pages="284--292",
doi="10.1007/978-3-032-34178-5_30",
isbn="978-3-032-34178-5"
}
```

## License

This work is licensed under Creative Commons Attribution 4.0 International.

[![CC4](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)

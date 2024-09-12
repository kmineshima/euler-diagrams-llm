# euler-diagrams-llm

_Evaluating the logical reasoning capabilities of large language models using Euler diagrams_

Datasets and scripts for the Diagrams 2024 paper: ["Can Euler Diagrams Improve Syllogistic Reasoning in Large Language Models?"](https://link.springer.com/chapter/10.1007/978-3-031-71291-3_19)

## Contents

- [Contents](#contents)
- [Datasets](#datasets)
  - [Euler Diagram Images](#euler-diagram-images)
  - [Validity Checking Task Format](#validity-checking-task-format)
  - [Multiple-Choice Task Format](#multiple-choice-task-format)
- [Citation](#citation)

## Datasets

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

If you use this data in any published research, please cite the following:

- Risako Ando, Kentaro Ozeki, Takanobu Morishita, Hirohiko Abe, Koji Mineshima, and Mitsuhiro Okada, ["Can Euler Diagrams Improve Syllogistic Reasoning in Large Language Models?"](https://link.springer.com/chapter/10.1007/978-3-031-71291-3_19), *Proceedings of 14th International Conference on the Theory and Application of Diagrams* (Diagrams 2024), Lecture Notes in Artificial Intelligence (LNAI), Springer, 232-248, 2024.

```
@InProceedings{ando-et-al-2024-euler-diagrams-llm,
author="Ando, Risako and Ozeki, Kentaro and Morishita, Takanobu and Abe, Hirohiko and Mineshima, Koji and Okada, Mitsuhiro",
editor="Lemanski, Jens and Johansen, Mikkel Willum and Manalo, Emmanuel
and Viana, Petrucio and Bhattacharjee, Reetu and Burns, Richard",
title="Can Euler Diagrams Improve Syllogistic Reasoning in Large Language Models?",
booktitle="Diagrammatic Representation and Inference",
series="Lecture Notes in Computer Science",
volume="14981",
year="2024",
publisher="Springer",
pages="232--248",
doi="https://doi.org/10.1007/978-3-031-71291-3_19"
}
```


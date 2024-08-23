# euler-diagrams-llm
Evaluating the logical reasoning capabilities of large language models using Euler diagrams


Datasets and scripts for the Diagrams2024 paper: "Can Euler Diagrams Improve Syllogistic Reasoning in LLMs?"

<!-- ## Contents -->

<!-- - [Datasets](#datasets)
  - [NLI (Natural Language Inference) Task Format](#nli-natural-language-inference-task-format)
  - [Multiple-Choice Task Format](#multiple-choice-task-format)
  - [Data used in the NALOMA2023 experiments](#data-used-in-the-naloma2023-experiments)
- [Running scripts](#running-scripts)
- [Citation](#citation) -->

<!-- ## Datasets

### NLI (Natural Language Inference) Task Format

#### File



#### Description

| Column Name | Description |
| ---- | ---- |
| ID | problem ID |
| ORIGINAL_ID | (INTERNAL) original problem ID |
| premises_ja | two premises in Japanese |
| hypothesis_ja | one hypothesis in Japanese |
| premises_en | two premises in English |
| hypothesis_en | one hypothesis in English |
| gold | correct answer, the relationship of the hypothesis to the premises (*entailment*, *contradiction*, *neutral*) |
| mood | the form of each premise and conclusion (three letters composed of A, E, I and O) |
| inference-type | type of logical inferences (*syllogism*, *propositional*) |
| content-type | classification based on belief congruency (*symbolic*, *congruent*, *incongruent*) |
| conversion | associated with conversion error (*yes*, *no*) |
| atmosphere | associated with atmosphere effect (*yes*, *no*) |

- See [our paper](#citation) for details on content-type, inference-type, conversion, and atmosphere.


### Multiple-Choice Task Format



-->

## Citation

Risako Ando, Kentaro Ozeki, Takanobu Morishita, Hirohiko Abe,
Koji Mineshima, and Mitsuhiro Okada,
"Can Euler Diagrams Improve Syllogistic Reasoning in LLMs?",
To appear in *Proceedings of 14th International Conference on the Theory and Application of Diagrams* (DIAGRAMS 2024), Lecture Notes in Artificial Intelligence (LNAI), Springer, 2024.
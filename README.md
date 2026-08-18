# NIYYAH: A Human-Validated Saudi Arabic Intent Benchmark Dataset

**NIYYAH** is a human-validated Saudi Arabic benchmark dataset for **task-oriented intent classification**.

The dataset contains **10,500 utterances** across **30 intent classes**, with **350 utterances per intent**, and represents multiple Saudi Arabic language varieties alongside Modern Standard Arabic.

NIYYAH was designed to support reproducible evaluation of intent classification systems across dialects and model families.

The dataset is publicly released before submission of the associated research paper to support transparency, reproducibility, and reuse by the research community.

---

## Dataset Overview

| Property | Value |
|---|---:|
| Dataset Name | NIYYAH |
| Task | Intent Classification |
| Language | Arabic |
| Primary Variety | Saudi Arabic |
| Total Utterances | 10,500 |
| Number of Intents | 30 |
| Utterances per Intent | 350 |
| Hijazi per Intent | 130 |
| Najdi per Intent | 130 |
| Shared Saudi/Gulf per Intent | 60 |
| MSA per Intent | 30 |
| Out-of-Scope Intent | Included |
| Dataset Split | Fixed Train / Development / Test |
| Test Set Size | 1,575 |
| Validation | Human-validated |
| Intended Use | Research and benchmarking |

---

## Language Variety Distribution

Each intent contains **350 utterances** distributed across four language varieties.

| Language Variety | Utterances per Intent | Total Utterances |
|---|---:|---:|
| Hijazi | 130 | 3,900 |
| Najdi | 130 | 3,900 |
| Shared Saudi/Gulf | 60 | 1,800 |
| Modern Standard Arabic | 30 | 900 |
| **Total** | **350** | **10,500** |

This structure allows researchers to evaluate both overall intent-classification performance and robustness across different Saudi Arabic language varieties.

---

## Dataset Description

NIYYAH focuses on **task-oriented Saudi Arabic intent classification**.

The dataset was constructed to provide:

- Balanced intent classes
- Multiple Saudi Arabic language varieties
- Modern Standard Arabic examples
- Out-of-scope examples
- Human validation
- Leakage-aware dataset splitting
- A fixed evaluation split
- A benchmark suitable for traditional machine-learning, transformer-based, embedding-based, and large language models

The dataset is intended to support research into Arabic natural language processing and conversational AI, particularly in settings involving Saudi Arabic.

---

## Dataset Structure

Each record contains an Arabic utterance together with its corresponding intent label and language-variety information.

A typical record follows a structure similar to:

~~~text
text        : Arabic utterance
intent      : Intent label
variety     : Hijazi / Najdi / Shared Saudi Gulf / MSA
split       : train / validation / test
~~~

The exact column names should be verified against the released dataset files.

---

## Recommended File Structure

~~~text
NIYYAH/
│
├── README.md
├── LICENSE
├── CITATION.cff
│
├── data/
│   ├── train.csv
│   ├── validation.csv
│   └── test.csv
│
├── metadata/
│   └── intents.csv
│
└── examples/
    └── load_dataset.py
~~~

The exact structure may differ slightly between GitHub, Kaggle, and Hugging Face.

---

## Dataset Splits

NIYYAH uses a **fixed train/development/test split**.

The held-out test set contains **1,575 utterances**.

The official split is designed to provide a consistent basis for comparison across different models and experimental settings.

Researchers who want to compare directly with the benchmark results reported in the associated paper should use the official provided split.

---

## Leakage-Aware Splitting

The dataset uses a leakage-aware splitting procedure intended to reduce unintended overlap between training, development, and test data.

This is particularly important for high-performing intent classification models, where near-duplicate or highly similar examples across splits can lead to overly optimistic evaluation results.

Researchers are encouraged to preserve the provided split when reproducing or extending the reported benchmark.

---

## Out-of-Scope Intent

NIYYAH includes an **Out-of-Scope (OOS)** intent.

The OOS category allows evaluation of whether a model can identify utterances that do not belong to the supported in-domain intent set.

This makes the benchmark more representative of practical task-oriented conversational systems, where users may submit requests that fall outside the system's supported capabilities.

---

## Human Validation

The dataset underwent human validation as part of its construction process.

Human validation was used to improve the quality and consistency of the final utterances and labels.

Further details regarding dataset construction, validation, and quality-control procedures are provided in the associated research paper.

---

## Intended Uses

NIYYAH is intended primarily for research and educational use in areas such as:

- Saudi Arabic natural language processing
- Arabic intent classification
- Task-oriented dialogue systems
- Conversational AI
- Arabic dialect processing
- Out-of-scope detection
- Multidialect classification
- Cross-dialect robustness evaluation
- Arabic language representation learning
- Transformer benchmarking
- Embedding-model evaluation
- Few-shot language-model evaluation
- Traditional machine-learning benchmarking

---

## Benchmark Model Families

The associated NIYYAH study evaluates multiple model families, including:

- TF-IDF-based machine-learning models
- Linear classifiers
- Arabic transformer models
- Multilingual transformer models
- Multilingual embedding models
- Few-shot large language models

The benchmark is designed to allow comparison across models with very different computational requirements and modeling approaches.

---

## Benchmark Metrics

The associated experiments evaluate models using:

- Accuracy
- Macro-Precision
- Macro-Recall
- Macro-F1

**Macro-F1** is used as the primary evaluation metric.

Researchers comparing new methods with NIYYAH benchmark results are encouraged to report the same metrics.

---

## Loading the Dataset

### Using Python and Pandas

~~~python
import pandas as pd

train = pd.read_csv("data/train.csv")
validation = pd.read_csv("data/validation.csv")
test = pd.read_csv("data/test.csv")

print(train.head())
print(train.shape)
print(validation.shape)
print(test.shape)
~~~

---

## Loading from Hugging Face

After the official Hugging Face release, NIYYAH can be loaded using the `datasets` library.

~~~python
from datasets import load_dataset

dataset = load_dataset("NIYYAH/NIYYAH")

print(dataset)
print(dataset["train"][0])
~~~

Install the Hugging Face `datasets` package if necessary:

~~~bash
pip install datasets
~~~

The final Hugging Face identifier should replace `NIYYAH/NIYYAH` if the published repository uses a different organization or dataset name.

---

## Using NIYYAH on Kaggle

After publication on Kaggle, the dataset can be downloaded through the Kaggle interface or Kaggle API.

~~~bash
kaggle datasets download -d <USERNAME>/niyyah
~~~

Then extract the downloaded archive:

~~~bash
unzip niyyah.zip
~~~

Replace `<USERNAME>` with the final Kaggle account or organization name.

---

## GitHub Repository

The official GitHub repository is intended to provide:

- Dataset documentation
- Dataset files or release links
- Metadata
- Dataset version history
- Usage examples
- Citation information
- Links to Kaggle and Hugging Face
- Links to the associated research paper
- Links to any archival DOI release

Official repository:

~~~text
https://github.com/niyyah/NIYYAH
~~~

Update this URL if the final GitHub account or repository name differs.

---

## Associated Research Paper


---

## Citation

If you use NIYYAH in your research, please cite the dataset release.

Until the associated paper is formally published, use the dataset citation provided with the official release.

### BibTeX


~~~

Replace the repository name, URL, and DOI with the final release information.

After publication of the associated research paper, the corresponding paper citation will also be added here.

---

## Authors

### Mohammed A. Alawfi
Email: `moalawfi@hotmail.com`

### Abdulrahman M. Almutairi
Email: `abdul.almutairi12@gmail.com`

### Yasser M. Althibyani
Email: `yasiralthubyani@gmail.com`

### Ibrahim F. Moawad
Email: `ibrahim_moawad@cis.asu.edu.eg`

---

## Affiliation

**College of Computer Science and Engineering**  
**Taibah University**  
**Al-Madinah, Saudi Arabia**

---

## Limitations

NIYYAH is designed specifically for task-oriented Saudi Arabic intent classification.

Users should consider several limitations when interpreting benchmark results or applying models trained on NIYYAH.

- The dataset focuses on a predefined collection of task-oriented intents.
- The represented language varieties do not cover every regional or social variety spoken in Saudi Arabia.
- The dataset is not intended to represent all forms of Arabic.
- Performance on NIYYAH should not be interpreted as general Arabic-language understanding.
- Models trained on NIYYAH may perform differently on unseen domains or dialects.
- The benchmark uses an official fixed split for reproducibility.
- Results on the dataset may not directly reflect performance in deployed conversational systems.

Researchers are encouraged to perform additional evaluation before using models trained on NIYYAH in real-world applications.

---

## Responsible Use

NIYYAH is intended primarily for:

- Academic research
- Educational use
- Natural language processing research
- Benchmarking
- Development and evaluation of Arabic-language technologies

Users are responsible for ensuring that systems developed using NIYYAH are used ethically and in accordance with applicable laws, institutional requirements, and dataset licensing terms.

The dataset should not be treated as a comprehensive representation of Saudi speakers, Saudi culture, or Arabic language use.

---

## License

**License:** `[TO BE FINALIZED]`

The final dataset license will be stated clearly before or at the time of the official public release.

Users should review the license before redistributing, modifying, or using the dataset in commercial applications.

---

## Dataset Versioning

Official NIYYAH releases should be versioned so that experiments can be traced to a specific dataset release.

The initial public release may be labeled:

~~~text
NIYYAH v1.0.0
~~~

Example version history:

~~~text
v1.0.0 — Initial public release
~~~

Any later corrections or extensions should be released as separate versions rather than silently replacing the dataset used in the associated paper.

Researchers should report the dataset version used in their experiments.

---

## Reproducibility

When reporting results on NIYYAH, we recommend including:

- Dataset version
- Dataset split
- Model name
- Model version
- Random seed
- Training configuration
- Preprocessing steps
- Accuracy
- Macro-Precision
- Macro-Recall
- Macro-F1

For direct comparison with the associated benchmark paper, researchers should use the official NIYYAH split.

---

## Official Releases

NIYYAH is intended to be available through multiple platforms.

### GitHub
`[GitHub URL]`

### Hugging Face
`[Hugging Face URL]`

### Kaggle
`[Kaggle URL]`

### DOI / Archival Repository
`[DOI URL]`

These links should be updated after each official release is completed.

---

## Recommended Citation Practice

For work conducted before publication of the associated paper:

**Cite the NIYYAH dataset release.**

After publication of the paper:

**Cite both the dataset release and the associated research paper when appropriate.**

This helps distinguish between citation of the reusable dataset artifact and citation of the research study describing its development and evaluation.

---

## Reporting Issues

If you identify:

- Incorrect labels
- Duplicate or suspicious examples
- Metadata inconsistencies
- Documentation errors
- Loading problems
- Potential data-quality issues

please report them through the official GitHub Issues page.

When reporting a dataset issue, include the dataset version and the relevant record identifier where possible.

---

## Contributing

Contributions related to documentation, loading utilities, metadata, reproducibility, and confirmed dataset issues are welcome through the official GitHub repository.

Researchers who create extensions, translations, additional dialects, or modified versions should clearly distinguish those derived datasets from the official NIYYAH release.

---

## Contact

For questions about NIYYAH and the associated research:

niyyah.research@gmail.com

For repository-specific technical issues, please use GitHub Issues.

---

## Acknowledgment

If NIYYAH contributes to your research, please cite the official dataset release and, once published, the associated research paper.

---

## NIYYAH

**A Human-Validated Saudi Arabic Intent Benchmark Dataset**

10,500 utterances · 30 intents · Hijazi · Najdi · Shared Saudi/Gulf · MSA

# Parallel Artificial Membrane Permeability Assay (PAMPA) 7

Parallel Artificial Membrane Permeability Assay (PAMPA) is an in vitro surrogate for the permeability of drugs across cellular membranes. PAMPA at pH 7.4 was experimentally determined by NIH-NCATS in a dataset of 5,473 unique compounds. Half the dataset was used to train an SVM classifier, validated on the remaining half with AUC = 0.88. Peff was log-transformed: log Peff below 2.0 was taken as low to moderate permeability and above 2.5 as high permeability, with intermediate compounds omitted. A subset of the data is available at PubChem (AID 1645871).

This model was incorporated on 2023-04-07.Last packaged on 2025-10-16.

## Information
### Identifiers
- **Ersilia Identifier:** `eos9tyg`
- **Slug:** `ncats-pampa74`

### Domain
- **Task:** `Annotation`
- **Subtask:** `Property calculation or prediction`
- **Biomedical Area:** `ADMET`
- **Target Organism:** `Homo sapiens`
- **Tags:** `ADME`, `Permeability`, `LogP`

### Input
- **Input:** `Compound`
- **Input Dimension:** `1`

### Output
- **Output Dimension:** `1`
- **Output Consistency:** `Fixed`
- **Interpretation:** Probability of a compound being poorly permeable (logPeff < 1)

Below are the **Output Columns** of the model:
| Name | Type | Direction | Description |
|------|------|-----------|-------------|
| pampa74_proba1 | float | low | Probability of poor permeability at pH=7.4 (cut-off logPeff < 1) |


### Source and Deployment
- **Source:** `Local`
- **Source Type:** `External`
- **DockerHub**: [https://hub.docker.com/r/ersiliaos/eos9tyg](https://hub.docker.com/r/ersiliaos/eos9tyg)
- **Docker Architecture:** `AMD64`, `ARM64`
- **S3 Storage**: [https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos9tyg.zip](https://ersilia-models-zipped.s3.eu-central-1.amazonaws.com/eos9tyg.zip)

### Resource Consumption
- **Model Size (Mb):** `84`
- **Environment Size (Mb):** `2443`
- **Image Size (Mb):** `2592.76`

**Computational Performance (seconds):**
- 10 inputs: `28.82`
- 100 inputs: `18.75`
- 10000 inputs: `112.49`

### References
- **Source Code**: [https://github.com/ncats/ncats-adme](https://github.com/ncats/ncats-adme)
- **Publication**: [https://doi.org/10.1177/24725552211017520](https://doi.org/10.1177/24725552211017520)
- **Publication Type:** `Peer reviewed`
- **Publication Year:** `2021`
- **Ersilia Contributor:** [pauline-banye](https://github.com/pauline-banye)

### License
This package is licensed under a [GPL-3.0](https://github.com/ersilia-os/ersilia/blob/master/LICENSE) license. The model contained within this package is licensed under a [None](LICENSE) license.

**Notice**: Ersilia grants access to models _as is_, directly from the original authors, please refer to the original code repository and/or publication if you use the model in your research.


## Use
To use this model locally, you need to have the [Ersilia CLI](https://github.com/ersilia-os/ersilia) installed.
The model can be **fetched** using the following command:
```bash
# fetch model from the Ersilia Model Hub
ersilia fetch eos9tyg
```
Then, you can **serve**, **run** and **close** the model as follows:
```bash
# serve the model
ersilia serve eos9tyg
# generate an example file
ersilia example -n 3 -f my_input.csv
# run the model
ersilia run -i my_input.csv -o my_output.csv
# close the model
ersilia close
```

## About Ersilia
The [Ersilia Open Source Initiative](https://ersilia.io) is a tech non-profit organization fueling sustainable research in the Global South.
Please [cite](https://github.com/ersilia-os/ersilia/blob/master/CITATION.cff) the Ersilia Model Hub if you've found this model to be useful. Always [let us know](https://github.com/ersilia-os/ersilia/issues) if you experience any issues while trying to run it.
If you want to contribute to our mission, consider [donating](https://www.ersilia.io/donate) to Ersilia!

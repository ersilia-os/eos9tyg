# Parallel Artificial Membrane Permeability Assay (PAMPA) 7

Parallel Artificial Membrane Permeability is an in vitro surrogate to determine the permeability of drugs across cellular membranes. PAMPA at pH 7.4 was experimentally determined in a dataset of 5,473 unique compounds by the NIH-NCATS. 50% of the dataset was used to train a classifier (SVM) to predict the permeability of new compounds, and validated on the remaining 50% of the data, rendering an AUC = 0.88. The Peff was converted to logarithmic, log Peff value lower than 2.0 were considered to have low to moderate permeability, and those with a value higher than 2.5 were considered as high-permeability compounds. Compounds with a value between 2.0 and 2.5 were omitted from the dataset. A subset of the data is available at PubChem (AID 1645871)

This model was incorporated on 2023-04-08.


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
- **Environment Size (Mb):** `2447`
- **Image Size (Mb):** `2510.39`

**Computational Performance (seconds):**
- 10 inputs: `33.97`
- 100 inputs: `24.56`
- 10000 inputs: `458.81`

### References
- **Source Code**: [https://github.com/ncats/ncats-adme](https://github.com/ncats/ncats-adme)
- **Publication**: [https://slas-discovery.org/article/S2472-5552(22)06765-X/fulltext](https://slas-discovery.org/article/S2472-5552(22)06765-X/fulltext)
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

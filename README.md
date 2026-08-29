# Generating sustainability aware event log for global logistics
Constructing event log from a realistic supply chain data and adding sustainability factors to it (synthetically).

## Table of Contents
- [About](#about)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Methodology](#methodology)
- [Status / Roadmap](#status--roadmap)
- [Tech Stack](#tech-stack)
- [Author](#author)
- [License](#license)


## About
Generating/constructing event log from realistic but flat transactional data, understand its behaviour and then to synthetically add a sustainability layer onto that, primarily using Python and some SQL.

The project is motivated from a job posting I came across for a research position for sustainability aware event data engineering in global logistics. One of the goals stated was to generate sustainability aware event log for process mining.

I found the problem interesting. So to deepen my understanding, I came up with a simple approach and interpretation of my own to explore it on a small scale, finding a publicly available realistic supply chain dataset to use as the base data.

## Dataset
- DataCo SMART SUPPLY CHAIN, https://data.mendeley.com/datasets/8gx2fvg2k6/5,

A DataSet of Supply Chains used by the company DataCo Global was used for the analysis. Contains 3 files:

DataCoSupplyChainDataset.csv- A Structured Dataset, DescriptionDataCoSupplyChain.csv- Description of the dataset, tokenized_access_logs.csv- Unstructured dataset.

- For this project, we use DataCoSupplyChainDataset.csv as the base data and DescriptionDataCoSupplyChain.csv as the data dictionary.Some limitations could be that the dataset is not a native event log but a flat transactional table and it lacks sustainability attributes.Hence we need to generate and add these,synthetically,to achieve the project objective.

- Download the necessary datasets from the provided link.

## Project Structure
project-folder/
├── data/
│ └── raw/
├── Code/
├── .gitignore
└── README.md

## Prerequisites
- Python 3.10 or higher
- Jupyter

[I used VSCode with Jupyter extension, Python 3.12.2]

## Installation
```bash
git clone https://github.com/SweetyRoshith/PM_Project1.git
cd PM_Project1
pip install -r requirements.txt
```

## Usage
- Before running the notebooks, ensure:
The dataset DataCoSupplyChainDataset.csv is downloaded and placed in data/raw.The description file DescriptionDataCoSupplyChain.csv will already be present in data/raw when you clone the repository.

- From Code/ run the script 'Database_setup.ipynb' for a one time setup.It will create a database folder with a .db database inside. Database will be of use in later stages of the project.

- Next, run the script 'Data_preparation.ipynb' from Code/.

## Methodology
My approach/pipeline.
- Identify a publicly available,realistic and industry style dataset for global logistics operations.
- Set up VS Code, Python and Jupyter(as extensions in VS Code),pandas, SQLite, git, github repo.
- Data Preparation and Cleaning(Handlin encoding issues to read data,Cross checking fields against the data description file,  Handling Missing Values, duplicates, dateformats, datatypes)
- Event log construction or log extraction (derive case ids, activities, timestamps from the cleaned dataset)
- Understand the behaviour and control flow from the constructed event log(to calibrate realistic patterns).
- Add sustainability attributes synthetically onto the above result, referring to the GLEC Framework for emission factors and their benchmark ranges.
- Validating the synthetic log for fidelity.


## Status / Roadmap
- [x] Source Data
- [x] Initial data inspection
- [ ] Data cleaning
- [ ] Event log construction
- [ ] Analyzing constructed event logs
- [ ] Adding sustainability layer to the logs
- [ ] Validate the logs for fidelity


## Tech Stack
VS Code, Jupyter, git, Python, pandas, SQLite.

## Author
Sweety Abraham (sweety.roshith@gmail.com)

## License
This project is licensed under the MIT License — see [LICENSE](LICENSE) for details








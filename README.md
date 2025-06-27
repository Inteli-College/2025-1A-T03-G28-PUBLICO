# KapAloca – Optimized Trade Allocation Platform

KapAloca is a **micro-SaaS** that automates the allocation of trades across funds and custodians.  
By replacing manual spreadsheets with an optimization algorithm, it delivers **speed, accuracy and full transparency**, reducing operational risk and ensuring regulatory compliance.:contentReference[oaicite:0]{index=0}

---

## 1. Problem Statement  
Manual allocation is time-consuming, prone to calculation errors and often ignores real-time price movements, creating distortions between funds and exposing institutions to regulatory and financial risks.:contentReference[oaicite:1]{index=1}

## 2. Solution Overview  
KapAloca embeds a mathematical optimizer that decides the best split of each order in near real time, based on market data and predefined fairness rules. Key benefits include:​:contentReference[oaicite:2]{index=2}

| Benefit | Impact |
|---------|--------|
| **Automation** | Eliminates manual dependency and re-work |
| **Accuracy & Transparency** | Guarantees equitable distribution, auditable by managers and investors |
| **Risk Reduction** | Mitigates human errors and ensures compliance |
| **Speed** | Responds instantly to price fluctuations |
| **Scalability** | SaaS architecture integrates easily with existing desks |

---

## 3. Repository Structure


├── data/
│ └── data source/
│    └── Data_Sources.ipynb 
│ └── input/
│    └── boletasdia.xlsx
│    └── carteira.xlsx
│    └── proporcao.xlsx
│    └── restricaomultiplo.xlsx 
├── doc/
│    └── img/
│    └── Kapaloca - TAPI.pdf
│    └── ProjectPlanModule2.md
├── src/
│    └── Allocation_Algorithm.ipynb
│    └── Allocation_AlgorithmV2.ipynb
│    └── LogicAlocator.xlsx
│
├── Public Report.md 
│
└── README.md 


## 4. Quick Start

1. **Clone the repo**

   ```bash
   git clone https://github.com/Inteli-College/2025-1A-T03-G28-PUBLICO.git
   cd kapaloca 

2. Create a virtual environment

    ```bash
    python -m venv .venv
    source .venv/bin/activate  
    pip install -r requirements.txt 

3. Run the optimizer
    ```bash
    jupyter notebook src/alocator/Allocation_Algorithm.ipynb


## 5. Licence
This project is licensed under the MIT License – see LICENSE for details.

## 8. Authors & Acknowledgements

Iago Medeiros Tavares – Project lead

Mentors & reviewers at Inteli – Instituto de Tecnologia e Liderança

For questions, open an issue or contact the team at iago.tavares@sou.inteli.edu.br



   
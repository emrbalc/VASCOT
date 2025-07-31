VASCOT: Vulnerability Analyzer for Smart Contracts Using Transformers
VASCOT is a deep learning-based tool for detecting vulnerabilities in Ethereum smart contracts by analyzing EVM opcode sequences using Transformer models. Unlike many prior tools that rely on source code, VASCOT operates directly on compiled bytecode, making it applicable even when source code is unavailable.

### Overview
Smart contracts are critical components of decentralized applications (dApps), yet they remain highly vulnerable to exploitable bugs such as reentrancy, access control flaws, unhandled exceptions. Smart contract vulnerabilities, particularly those triggered through sequences of operations (also known as trace vulnerabilities), pose significant risks to dApps. VASCOT is designed to detect such vulnerabilities using a Transformer architecture with sliding window support for handling long opcode sequences.

### Key Features
- Transformer-based classification of smart contracts as **vulnerable** or **non-vulnerable**.
- Support for identifying specific vulnerability types (e.g., greedy contracts).
- Dataset of 16,000+ verified Ethereum contracts labeled using symbolic and concrete analysis.
- Sliding window mechanism to handle long opcode sequences beyond Transformer input limits.

### Project Structure
vascot/

├── data/ # Preprocessed datasets 

├── notebooks/ # Sample training/evaluation notebooks

└── README.md

###  Dataset
The repository includes three datasets:
1. **Verified Greedy and Non-Vulnerable Contracts (2022)**: A curated set of smart contracts verified on Etherscan and labeled using MAIAN, with concrete validation to reduce false positives. Consists of 1,202 non-vulnerable and 713 greedy contracts.
2. **Unverified Greedy and Non-Vulnerable Contracts (2015–2017)**: Publicly available data from Google BigQuery, labeled using prior vulnerability studies. Consists of 8,000 non-vulnerable and 5,801 greedy contracts.
3. **Unverified Greedy, Prodigal, Suicidal and Non-Vulnerable Contracts (2015–2017)**: Publicly available data from Google BigQuery, labeled using prior vulnerability studies. Consists of 8,000 non-vulnerable contracts and 8,469 contracts that are marked as greedy, suicidal and prodigal.

Each contract entry includes:
- Contract address
- Opcode sequence
- One-hot encoded vulnerability label (`non-vulnerable’, `greedy’, etc.)

### Citation
If you use VASCOT or the provided dataset in your work, please cite:
@inproceedings{balci2023accelerating,
  title={Accelerating smart contract vulnerability scan using transformers},
  author={Balc{\i}, Emre and Y{\i}lmaz, G{\"o}rkem and Uzuno{\u{g}}lu, An{\i}l and Soyak, Ece Gelal},
  booktitle={2023 IEEE Asia-Pacific Conference on Computer Science and Data Engineering (CSDE)},
  pages={1--6},
  year={2023},
  organization={IEEE}
}

Contributions
Contributions to the vulnerability scanner are welcome. If you find a bug or want to suggest an improvement, please open an issue on this GitHub repository.
License
This project is licensed under the MIT License. See the LICENSE file for details.

### Acknowledgments
    • MAIAN tool for trace vulnerability analysis
    • Ethereum Foundation for public data access

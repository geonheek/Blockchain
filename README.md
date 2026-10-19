# On-Chain Trust Research

Research projects on Ethereum asset availability, ERC-20 allowance risk, and LLM-based malicious spender detection.

**GeonHee Kim**  
M.S. Student, SIFT Lab  
Kyung Hee University

## Research Projects

### 1. NFT Asset Availability

Large-scale measurement of NFT image availability across Web2, IPFS, and Arweave.

- Approximately 5 million NFT mint transactions
- Approximately 2.5 million image URIs
- Multi-stage accessibility verification using HEAD, partial GET, and full GET
- IPFS CID revalidation across multiple gateways
- Published in *Computer Networks* (Elsevier)
- First author

Repository: [`nft-asset-availability`](./nft-asset-availability)

---

### 2. ERC-20 Approval Analysis

Six-year measurement of ERC-20 approvals and `transferFrom` executions on Ethereum.

- Approximately 399.67 million approval events
- Approximately 12.26 million `transferFrom` executions
- Analysis period: 2020–2025
- Approval-to-execution matching
- Malicious spender and recipient analysis
- Large-scale processing using Python and SQLite
- Under review

Repository: [`erc20-approval-analysis`](./erc20-approval-analysis)

---

### 3. LLM-as-a-Judge

Evaluation of LLM-based malicious spender classification using on-chain behavioral features.

- Claude API
- Seven behavioral features
- Few-shot and domain-knowledge prompting
- Logistic Regression baseline
- Best ROC-AUC: 0.821
- Stability analysis across multiple few-shot seeds

Repository: [`llm-as-a-judge`](./llm-as-a-judge)

---

## Publications

### Selling Air: A Large-scale Evaluation of NFT Asset Availability

G. Kim et al.  
*Computer Networks*, 2026.  
First author.

DOI: https://doi.org/10.1016/j.comnet.2026.112706

### I Know What You Approved Last Summer: A Six-Year Measurement of Dormant and Exercised ERC-20 Allowances on Ethereum

Under review.  
First author.

### LLM-as-a-Judge를 활용한 ERC-20 승인 오남용 탐지 성능 비교 연구

CISC 2026.  
First author.

### Beyond Tool Poisoning: Attack Surfaces of Malicious Remote MCP Servers Across LLM Platforms

*MDPI Electronics*, 2026.  
Second author.

---

## Environment

Main tools used across the projects:

- Python
- pandas
- SQLite
- matplotlib
- Alchemy
- Etherscan
- Blockscout
- GraphSense
- Claude API
- LaTeX / Overleaf

---

## Notes

Raw blockchain databases and API credentials are not included in this repository.

Large datasets used in the experiments are excluded because of storage size and data-source restrictions. Small samples are provided where possible to illustrate the expected data format.

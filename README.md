# AML & Sanctions ML

A curated reference for people building transaction monitoring, sanctions screening and entity matching: peer-reviewed research, patents, datasets, open-source tools and dated industry news. Each entry carries a short note on why it earns its place.

This is a research-and-tools reference, not legal or compliance advice.

## Peer-reviewed research

Venue named per entry. Preprints live in their own subsection below and are not presented as peer reviewed.

- Weber et al., "Anti-Money Laundering in Bitcoin: Experimenting with Graph Convolutional Networks for Financial Forensics" (KDD 2019 Workshop on Anomaly Detection in Finance - workshop paper) - the paper behind the Elliptic dataset. https://arxiv.org/abs/1908.02591
- Altman et al., a synthetic financial network and agent-based AML benchmark dataset (Scientific Data, Nature portfolio). https://doi.org/10.1038/s41597-023-02569-2
- Zhang et al., "Rule-graph alignment via optimal transport for weakly supervised anomaly detection on transaction graphs" (Journal of King Saud University Computer and Information Sciences, 2026) - weakly supervised transaction-graph anomaly detection that aligns decision-tree rule paths with transaction embeddings via optimal transport, easing the expert-label bottleneck; evaluated on four datasets including Libra Bank. https://doi.org/10.1007/s44443-026-01381-3
- Pavlenko and Hnatushenko, "Semantic Embeddings as a Candidate-Generation Channel for Sanctions Name Screening" (Computer Systems and Information Technologies, 2026) - controlled stress test of commercial embedding models as candidate-generation channels over a fixed OFAC SDN snapshot (7,426 individuals) across four Slavic-name transliteration regimes and hard look-alikes; Gemini embeddings hold Recall@1 under transliteration distance where OpenAI embeddings degrade. https://csitjournal.khmnu.edu.ua/index.php/csit/article/view/660

### Preprints

Clearly marked; promoted to the peer-reviewed section only when a venue is confirmed.

- "Pricing Cross-Bank Context in Federated Anti-Money Laundering" (arXiv preprint, Oct 2026) - pricing shared cross-bank context in federated AML; pairs with the federated-AML patents below. https://arxiv.org/abs/2610.35996
- "AMLBench: A Real-Incident Benchmark for Agentic Blockchain Anti-Money Laundering" (arXiv preprint, Nov 2026) - 24 real-world cases and 5.05M Ethereum transfer records for testing whether LLM agents can trace illicit funds from limited clues. https://arxiv.org/abs/2611.02530
- "TRACK: Multiple Instance Learning for Anti-Money Laundering in Transaction Networks" (arXiv preprint, Nov 2026; per the preprint, accepted at WSDM 2027) - recasts account-level AML detection as multiple instance learning over an account's transactions instead of aggregating first; outperforms tabular and graph baselines on five AML datasets under account-window supervision alone. https://arxiv.org/abs/2611.06035
- "Leveraging Time-Series Foundation Models for Financial Crime Detection" (arXiv preprint, Oct 2026) - summarizes each account's transaction history with a frozen time-series foundation model and enriches each transaction's representation with that temporal context; improves PR-AUC over the strongest evaluated baseline on five of six AMLWorld datasets, with further gains feeding the representations into a GNN. https://arxiv.org/abs/2610.29667
- "Tracing Money Laundering Across DeFi, Bridges, and Mixers on Ethereum" (arXiv preprint, Oct 2026) - FPTracer recovers intra-transaction asset-flow paths, classifies cross-chain intent without pre-collected bridge information, and analyzes post-mixer laundering flows; evaluated on 20 real laundering cases, surfacing 30 previously unreported bridge uses. https://arxiv.org/abs/2610.32210
- "PersonaAgent: Retrieval-Augmented Transaction Anomaly Scoring with Refreshable Multi-Entity Persona Memory" (arXiv preprint, Nov 2026) - keeps refreshable persona memory of entity behavior signals and retrieves them at inference to augment a base anomaly classifier, addressing behavior drift between production model refreshes; benchmarked with anomaly detection models at Visa. https://arxiv.org/abs/2611.08094
- "SALT-GNN: Handling Dense Neighborhoods in Anti-Money Laundering Graphs via Statistics-Aware Attention" (arXiv preprint, Jul 2026) - recipient-degree stratified evaluation shows AML GNN performance degrades in dense recipient contexts on HI-Small, HI-Medium and AMLSim, tracing the gap to multiset non-discriminability and cardinality blindness; a useful check before trusting aggregate F1 on transaction graphs. https://arxiv.org/abs/2607.10131

- "MINT: Mitigating Structural Inconsistency via Attentive Message Passing for Financial Anomaly Detection" (arXiv preprint, Oct 2026) - combines discrepancy-aware directed message passing, transaction-salience edge weighting and positive-unlabeled learning for scarce illicit-account labels; evaluated on two public transaction benchmarks and one proprietary dataset. https://arxiv.org/abs/2610.34950
- "Directed-Hypergraph Analytics and Fragility Testing for Anti-Money Laundering" (arXiv preprint, Oct 2026) - adds graph and directed-hypergraph features to Elliptic++ illicit-address classification and tests suspicious-flow motifs by removing high-risk intermediaries; a study of higher-order structure, not proof of real-world disruption. https://arxiv.org/abs/2610.24274

## Patents

Publication type is stated per entry: a B-number publication is a granted patent, an A-number publication is an application. Publication type says nothing about current legal status or enforceability, which we do not assess.

- US12045716B2 (granted) - Federated learning system and method for detecting financial crime behavior across participating entities. https://patents.google.com/patent/US12045716B2/en
- US10607227B2 (granted) - System, method, and computer program product for detecting potential money laundering activities. https://patents.google.com/patent/US10607227B2/en
- US10438297B2 (granted) - Anti-money laundering platform for mining and analyzing data to identify money launderers. https://patents.google.com/patent/US10438297B2/en
- US20250103810A1 (application, not granted) - Large language model for sanctions AI-assisted automation. https://patents.google.com/patent/US20250103810A1/en

## Datasets

- IBM AMLSim - synthetic AML transaction generator and benchmark; the standard sandbox when real laundering labels are unobtainable. https://github.com/IBM/AMLSim
- Elliptic Data Set - 200k Bitcoin transactions with licit/illicit labels; the benchmark most graph-AML papers report on. https://www.kaggle.com/datasets/ellipticco/elliptic-data-set
- IEEE-CIS Fraud Detection - real e-commerce transactions from Vesta; the reference tabular fraud benchmark. https://ieee-dataport.org/documents/ieee-cis-fraud-detection
- PaySim - synthetic mobile-money simulation for testing detection logic at scale. https://github.com/EdgarLopezPhD/PaySim

## Open-source tools

- OpenSanctions - consolidated sanctions/PEP/crime data as an open dataset and API. https://github.com/opensanctions/opensanctions
- Moov Watchman - sanctions list search and screening API; production-grade screening code you can read and run. https://github.com/moov-io/watchman

## Regulator list sources

Primary sources for sanctions list data.

- OFAC Sanctions List Search (US). https://sanctionssearch.ofac.treas.gov/
- UN Security Council Consolidated List. https://main.un.org/securitycouncil/en/content/un-sc-consolidated-list
- EU Consolidated Financial Sanctions List. https://data.europa.eu/data/datasets/consolidated-list-of-persons-groups-and-entities-subject-to-eu-financial-sanctions?locale=en
- UK OFSI Consolidated List. https://www.gov.uk/government/publications/the-uk-sanctions-list

## Industry news

Dated entries only: advisories, guidance and enforcement actions with a lesson for builders. News is never cited as research; marketing noise stays out.

Sources watched:

- FinCEN advisories. https://www.fincen.gov/resources/advisoriesbulletinsfact-sheets/advisories
- FATF publications. https://www.fatf-gafi.org/en/publications.html

Entries:

- 2026-09-03: FinCEN Alert FIN-2026-Alert005 on scam centers - typologies worth encoding in monitoring rules. https://www.fincen.gov/system/files/2026-08/FinCEN-Alert-Scam-Centers.pdf
- 2026-10-01: FinCEN Alert FIN-2026-Alert007 on the A7 shadow banking network - typologies and SAR filing terms for sanctions-evasion monitoring, including digital asset channels. https://www.fincen.gov/system/files/2026-10/FinCEN-Alert-A7-Network.pdf
- 2026-10-15: FinCEN Alert FIN-2026-Alert008 on abuse of religious charity networks - typologies and SAR filing request relevant to NGO/correspondent-bank monitoring rules. https://www.fincen.gov/system/files/2026-10/FinCEN-Alert-Iranian-Charity-Network-Abuse.pdf
- 2026-10-30: FinCEN Alert FIN-2026-Alert009 on risks associated with foreign-agent-directed transactions through U.S. money services businesses - SAR key term FIN2026FOREIGNAGENT for cross-border MSB monitoring rules. https://www.fincen.gov/system/files/2026-10/FinCEN-Alert-Foreign-Agent-Directed-Transactions.pdf
- 2026-10-30: FinCEN Notice FIN-2026-NTC2 on the use of charities and non-profit organizations for illicit activity - NGO-abuse typologies paired with the Minnesota fraud-prevention measures. https://www.fincen.gov/system/files/2026-10/FinCEN-Notice-Illicit-Activity-Charities-Non-Profit-Org.pdf
- 2026-10-30: FATF October 2026 Plenary outcomes - Bulgaria, Cote d'Ivoire, Democratic Republic of the Congo and Monaco removed from increased monitoring (grey-list effective dates for screening); Mexico and U.S. mutual evaluation reports adopted; first report under the FATF fraud roadmap on scam compounds. https://www.fatf-gafi.org/en/publications/Fatfgeneral/outcomes-fatf-plenary-october-2026.html
- 2026-10-30: FATF launches a targeted review of virtual-asset Standards implementation - country-by-country review focused on jurisdictions with materially important VASP activity (MIVA), pushing R.15 implementation; expect tighter expectations for VASP compliance and wallet/VA screening tooling. https://www.fatf-gafi.org/en/publications/Fatfrecommendations/launch-targeted-review-strengthen-standards-virtual-assets.html
- 2026-11-05: FATF publishes "Combating End-to-End Illicit Financial Flows linked to Scam Compounds" (the fraud-roadmap report adopted at the October plenary) - maps the payment, virtual-asset, technology and telecom infrastructure scam networks depend on, with disruption approaches before and after victim payments; typology source for scam-flow monitoring rules. https://www.fatf-gafi.org/en/news/combating-illicit-financial-flows-linked-to-scam-compounds.html
- 2026-11-06: FinCEN order under Operation Economic Outcast severs MEXC Global from the U.S. financial system - the CVC exchanger facilitated at least $16 billion in illicit finance including IRGC-Qods Force flows; counterparty-risk signal for crypto on/off-ramp screening rules. https://home.treasury.gov/news/press-releases/sb0685
- 2026-11-06: OFAC sanctions eight Canadian money services businesses enabling the Iranian regime (Operation Economic Outcast) - MSB-based sanctions-evasion typology to pair with the Oct 1 FinCEN A7 shadow-banking alert. https://home.treasury.gov/news/press-releases/sb0686

## Reproducible evaluations

- stream-fraud - reproducible streaming fraud-detection evaluation (maintainer's own project). https://github.com/RishabhPande/stream-fraud

## Neighbor lists

- AI4Risk awesome-fraud-detection. https://github.com/AI4Risk/awesome-fraud-detection
- benedekrozemberczki awesome-fraud-detection-papers. https://github.com/benedekrozemberczki/awesome-fraud-detection-papers
- safe-graph graph-fraud-detection-papers. https://github.com/safe-graph/graph-fraud-detection-papers

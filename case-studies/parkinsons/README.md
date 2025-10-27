# Parkinson's Disease AOP Case Study

This folder contains SPARQL queries for the VHP4Safety Parkinson's disease case study, focusing on Adverse Outcome Pathways related to parkinsonian motor deficits.

## Key Entities

**Primary AOP:** AOP 464 (VHP4Safety project focus)
- URL: https://aopwiki.org/aops/464

**Primary Adverse Outcome:** Event 896 - Parkinsonian motor deficits
- URL: https://aopwiki.org/events/896
- This AO is part of multiple Parkinson's-related AOPs, creating a pathway network

## Query Organization

### P-Q1: Discovery & Core Queries
Initial queries to understand the AOP structure and identify all Parkinson's-related pathways.

- **P-Q1-AOP464-Overview.rq** - Complete structure of AOP 464 (MIEs, KEs, AO)
- **P-Q1-AllParkinsonsAOPs.rq** - All AOPs leading to parkinsonian motor deficits (AO 896)
- **P-Q1-ParkinsonsAOPNetwork.rq** - Network of Parkinson's-related AOPs by title matching and AO 896

### P-Q2: Pathway Analysis
Detailed queries examining the causal relationships within pathways.

- **P-Q2-AOP464-KeyEvents.rq** - All Key Events in AOP 464 with measurement methods
- **P-Q2-AOP464-KERs.rq** - Key Event Relationships showing causal connections in AOP 464
- **P-Q2-MIEsToAO896.rq** - Complete pathways from MIEs to parkinsonian motor deficits

### P-Q3: Chemical & Stressor Queries
Queries focused on identifying chemicals and substances linked to Parkinson's pathways.

- **P-Q3-AOP464-Chemicals.rq** - Chemicals/stressors linked specifically to AOP 464
- **P-Q3-ParkinsonsChemicals.rq** - All chemicals across Parkinson's-related AOPs
- **P-Q3-ChemicalIDs.rq** - External database identifiers (CAS, ChEBI, PubChem) for chemicals

### P-Q4: Network Integration
Advanced queries analyzing the AOP network structure and convergence patterns.

- **P-Q4-SharedKEs.rq** - Key Events shared across multiple Parkinson's AOPs (network convergence points)
- **P-Q4-ConvergingPathways.rq** - How different MIEs converge through KEs to parkinsonian motor deficits

## Usage with SNORQL

These queries are designed for the AOP-Wiki SPARQL endpoint through the SNORQL interface.

### Modifying Filters

Most queries include hardcoded filters that can be customized:

- **AOP 464 filter:** `FILTER (?AOP = aop:464)` - Change to query different AOPs
- **AO 896 filter:** `FILTER (?AO = aop.events:896)` - Change to explore other adverse outcomes
- **Text filters:** `FILTER regex(?AOPTitle, "parkinson", "i")` - Modify search terms

### Network Exploration

To explore the broader Parkinson's AOP network:
1. Start with P-Q1-AllParkinsonsAOPs.rq to identify all relevant AOPs
2. Use P-Q4-SharedKEs.rq to find convergence points
3. For each identified AOP, modify the filters in P-Q2 queries to examine its structure

## VHP4Safety Context

This case study is part of the VHP4Safety (Virtual Human Platform for Safety) project, which aims to improve chemical safety assessment through integration of in vitro, in silico, and systems biology approaches. The Parkinson's case study demonstrates how AOP-Wiki data can be systematically queried to understand neurotoxic pathways.

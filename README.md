# EU AI Act Ontology (Proof-of-Concept)
## Overview

This repository contains a proof-of-concept ontology that models key regulatory concepts of the EU AI Act. The ontology captures core elements of the regulation, including AI system categories, actors involved in the AI lifecycle, prohibited practices, and regulatory obligations.

The goal of this project is to demonstrate a rapid ontology engineering workflow supported by AI-assisted concept extraction, combined with principled semantic modelling.

This work was developed as a small experimental prototype rather than a complete legal knowledge representation of the regulation.

⸻
## Namespaces

The ontology uses the following namespace prefix:

: http://example.org/eu-ai-act-ontology#

Standard RDF/OWL vocabularies used include:

- rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
- rdfs: http://www.w3.org/2000/01/rdf-schema#  
- owl: http://www.w3.org/2002/07/owl#
- org: <http://www.w3.org/ns/org#>
- prov: <http://www.w3.org/ns/prov#>
- dct: <http://purl.org/dc/terms/>
- lkif: <http://www.estrellaproject.org/lkif-core/>

## Repository Structure
```
eu-ai-act-ontology/
│
├── ontology/
│   └── eu-ai-act.owl
│
├── docs/
│   └── documentation.pdf
│
├── queries/
│   └── example_queries.sparql
│
├── prompts/
│   └── example_prompts.md
│
└── README.md
```
## Folder Description

ontology/
Contains the ontology file implemented in OWL.

docs/
Short documentation describing the modelling scope, AI-assisted workflow, key design decisions, and evaluation approach.

queries/
Example SPARQL queries demonstrating how the ontology can answer competency questions.

prompts/
Example prompts used during the AI-assisted concept extraction and modelling process.

## Ontology Scope

The ontology focuses on representing the following core aspects of the EU AI Act:

- AI Systems regulated under the Act
- Risk Classification (High Risk, Limited Risk, Minimal Risk, Unacceptable Risk)
- Actors in the AI Lifecycle (Provider, Deployer, Importer, Distributor, Authorities)
- Regulatory Obligations imposed on high-risk AI systems
- Prohibited AI Practices

The ontology intentionally models the structural logic of the regulation rather than attempting full coverage of all legal provisions.

⸻

## Example Query

Retrieve AI systems classified as high risk:

```
SELECT ?system
WHERE {
  ?system rdf:type :AI_System .
  ?system :hasRiskCategory :High_Risk .
}
```
Example queries are provided in the queries/ folder.

## AI-Assisted Workflow

A lightweight AI-assisted pipeline was used to support rapid ontology construction:

1. **Concept Extraction**  
   Candidate regulatory entities were extracted from summaries of the EU AI Act using a large language model.

2. **Candidate Ontology Generation**  
   Extracted concepts were converted into preliminary ontology elements such as classes, relationships, and annotations.

3. **Manual Ontology Engineering**  
   The ontology structure was refined and implemented manually in Protégé using OWL.

4. **Query Generation and Validation**  
   Competency questions and example SPARQL queries were generated with AI assistance and used to test the ontology.
AI assistance was primarily used for concept exploration and idea generation, while the final ontology design and validation remained human-driven.

## Validation

The ontology was loaded and validated in Protégé and checked for logical consistency using an OWL reasoner.

⸻

## Competency Questions

The ontology is designed to support queries such as:
	1.	Which AI systems are classified as high-risk?
	2.	What obligations apply to providers of high-risk AI systems?
	3.	Which AI practices are prohibited?
	4.	Which actors are responsible for fulfilling regulatory obligations?
	5.	What risk category is assigned to a given AI system?

⸻
## Tools Used

The ontology was developed and validated using the following tools:

- Protégé (ontology development)
- OWL 2 (ontology representation language)
- HermiT reasoner (logical consistency checking)
- SPARQL (querying and competency question testing)

## Future Work

Future extensions of this prototype could include:

- modelling additional provisions of the EU AI Act
- representing conformity assessment procedures
- linking the ontology with existing legal knowledge representation standards
- integrating regulatory reasoning rules

⸻

## License

This repository is shared for research and demonstration purposes.

# Competency questions for the EU AI Act Ontology 

The given SPARQL are _examples_ that may be reinterpreted and reused for applications.

### Competency Question 1:
**Question: 1.	Which AI systems are classified as high-risk?** 

**SPARQL Query:**
```
PREFIX : <http://example.org/eu-ai-act#>
SELECT ?system
WHERE {
  ?system a :AI_System ;
          :hasRiskCategory :High_Risk .
}
```
<img width="451" height="180" alt="image" src="https://github.com/user-attachments/assets/d20d953a-5ed8-4493-97c8-b39133529db4" />

### Competency Question 2:
**Question: What obligations apply to providers of AI systems?** 

**SPARQL Query:**
```
#Obligations of providers:
PREFIX : <http://example.org/eu-ai-act#>

SELECT ?provider ?obligation
WHERE {
  ?provider a :Provider ;
            :hasObligation ?obligation .
}
```
<img width="451" height="180" alt="image" src="https://github.com/user-attachments/assets/9f3ed555-1806-41d8-828e-bc12423c3cda" />

### Competency Question 3:
**Question: Which AI practices are prohibited under the Act?** 

**SPARQL Query:**
```
#Prohibited AI practices:
PREFIX : <http://example.org/eu-ai-act#>
SELECT ?practice
WHERE {  ?practice rdfs:subClassOf :Prohibited_AI_Practice .}
```

<img width="451" height="180" alt="image" src="https://github.com/user-attachments/assets/8b5a9ded-e775-44f4-a3e3-7fb4c71d76f5" />

### Competency Question 4:
**Question: Which Obligations are Derived from Risk Classification** 

**SPARQL Query:**
```

PREFIX : <http://example.org/eu-ai-act#>

SELECT ?system ?risk ?obligation
WHERE {
  ?system a :AI_System ;
          :hasRiskCategory ?risk .

  ?risk :triggersObligation ?obligation .
}
```
<img width="451" height="180" alt="image" src="https://github.com/user-attachments/assets/ff614c65-a4d9-40c1-b01c-926554da167a" />

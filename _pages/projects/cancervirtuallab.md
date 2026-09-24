---
project_id: cancervirtuallab
title: Cancer Virtual Lab
permalink: /projects/cancervirtuallab/
excerpt: "Integrazione semantica, Knowledge Graph e intelligenza artificiale per l'analisi di dati clinici e omici a supporto della ricerca oncologica e della medicina di precisione."
classes: labsd-wide justified-text
---

{% include base_path %}

{% assign project = site.data.projects | where: "id", page.project_id | first %}
{% include project_header.html project=project %}

## Il progetto

Il **Cancer Virtual Lab (CVL)** è una piattaforma di ricerca e analisi avanzata progettata per affrontare la frammentazione e la complessità strutturale dei dati oncologici. Sfruttando la sinergia tra **Tecnologie Semantiche**, **Knowledge Graph** e **Intelligenza Artificiale**, il progetto crea un ambiente computazionale in grado di integrare, correlare e simulare flussi di dati clinici, fenotipici e multi-omici (genomica, trascrittomica, proteomica, metabolomica).

L'obiettivo principale è superare i limiti dei tradizionali silos informativi per trasformare dati biomedici eterogenei in una rete di conoscenza interconnessa, offrendo a ricercatori e oncologi uno strumento interoperabile per la medicina di precisione, la scoperta di biomarker e il supporto alle decisioni cliniche.

* Scopri Cancer Virtual Lab: la piattaforma di decision support in oncologia [https://disi.unibo.it/it/notizie/cancer-virtual-lab-una-piattaforma-di-decision-support-in-oncologia]

## Pilastri Tecnologici

* **Rappresentazione Semantica e Standard FHIR**: Utilizzo dei principi FAIR e di standard internazionali (come HL7 FHIR) abbinati a tecnologie W3C (RDF, OWL) per armonizzare e normalizzare le cartelle cliniche elettroniche in formati "research-ready".
* **Knowledge Graph Oncologico**: Costruzione di un grafo della conoscenza dinamico che mappa esplicitamente le relazioni tra entità cliniche e biologiche, abbattendo le barriere di interoperabilità dei dati reali dell'oncologia.
* **Intelligenza Artificiale e LLM**: Impiego di Large Language Models e intelligenza artificiale per l'estrazione di informazioni da testi non strutturati e per facilitare l'esplorazione conversazionale e semantica della conoscenza medica in ambienti protetti.
* **Infrastruttura Sicura per la Ricerca**: Un framework concepito in ottica privacy-preserving che permette la creazione di coorti di ricerca ed esplorazioni di dati sensibili nel pieno rispetto delle normative sulla sicurezza.

## Pubblicazioni

* Carbonaro, Antonella, Luca Giorgetti, Lorenzo Ridolfi, Roberto Pasolini, Andrea Pagliarani, Martina Cavallucci, Alice Andalò, Livia Del Gaudio, Paolo De Angelis, Nicola Gentili, e Roberto Vespignani. "From raw data to research-ready: A FHIR-based transformation pipeline in a real-world oncology setting." *Computers in Biology and Medicine* 197, Pt B (2025): 111051. [https://doi.org/10.1016/j.compbiomed.2025.111051](https://doi.org/10.1016/j.compbiomed.2025.111051).

* De Angelis, Paolo, Alice Andalò, Nicola Gentili, Luca Giorgetti, Lorenzo Ridolfi, Roberto Pasolini, Andrea Pagliarani, Martina Cavallucci, Roberto Vespignani, e Antonella Carbonaro. "Cancer Virtual Lab: una piattaforma sicura e interoperabile basata su knowledge graph e large language model per la ricerca oncologica." *Recenti Progressi in Medicina* 116, no. 10 (2025): 601–602. [https://doi.org/10.1701/4573.45795](https://doi.org/10.1701/4573.45795).

* Carbonaro, Antonella, Luca Giorgetti, Lorenzo Ridolfi, Roberto Pasolini, Andrea Pagliarani, Paolo De Angelis, e Nicola Gentili. "Enabling Clinical Research with Semantic Knowledge Graphs: The Cancer Virtual Lab Platform." In *Proceedings of the 9th International Workshop on Semantic Web Solutions for Biomedical and Healthcare Data (SeWeBMeDa@ESWC)*, CEUR Workshop Proceedings, 2026.

---
project_id: renata
title: RENata
permalink: /projects/renata/
excerpt: "Un assistente virtuale basato su GPT per supportare lo sviluppo e la gestione metodologica di Percorsi Diagnostico-Terapeutici Assistenziali (PDTA) multidisciplinari nel carcinoma renale."
classes: labsd-wide justified-text
---

{% include base_path %}

{% assign project = site.data.projects | where: "id", page.project_id | first %}
{% include project_header.html project=project %}

## Il progetto

**RENata** è un assistente conversazionale specializzato, basato sull'Intelligenza Artificiale Generativa (modello GPT), progettato per semplificare, strutturare e standardizzare la redazione dei Percorsi Diagnostico-Terapeutici Assistenziali (PDTA) in ambito oncologico, con un focus iniziale sul carcinoma renale in Romagna. 

La stesura di un PDTA è un processo tipicamente complesso e dispendioso in termini di tempo, che richiede il coordinamento di molteplici figure professionali spesso già sovraccaricate dall'attività clinica. Questo scenario espone al rischio di frammentazione, duplicazioni e incongruenze rispetto alle linee guida. Sviluppato nell'ambito di tirocini e tesi con l'**IRCCS IRST "Dino Amadori"** e il Dipartimento di Interpreti e Traduttori dell'**Università di Bologna** (Campus di Forlì), RENata risponde a questa sfida agendo come un vero e proprio supporto metodologico per il medico coordinatore.

Attraverso un'interazione intuitiva in linguaggio naturale, la piattaforma guida i gruppi multidisciplinari in ogni fase della creazione del documento, generando checklist mirate, bozze di paragrafi, suggerimenti per la raccolta dati e garantendo la massima aderenza formale e clinica ai protocolli vigenti.

## Pilastri Tecnologici e Metodologici

* **Intelligenza Artificiale Generativa e LLM**: Impiego di Large Language Models avanzati (architettura GPT-4o) specializzati nell'elaborazione del linguaggio naturale per l'ambito medico-sanitario, in grado di interagire fluidamente e dinamicamente con gli utenti, adattandosi ai vari livelli di competenza informatica dei clinici.
* **Knowledge Base Strutturata ed Evidence-Based**: Integrazione diretta nella base di conoscenza del sistema delle linee guida nazionali (AIOM), delle direttive regionali (ASSR Emilia-Romagna) e dei modelli locali (AUSL Romagna). Questo approccio garantisce la produzione di testi rigorosi e aggiornati.
* **Prompt Engineering Avanzato**: Utilizzo di tecniche come *Chain-of-Thought (CoT)*, *Persona-based Priming* e *Constraint-based Prompting* per limitare drasticamente le allucinazioni dell'IA, forzare il rispetto dei vincoli clinici e mantenere un tono neutrale, professionale e inclusivo.
* **Innovazione Ottica LEAN**: Applicazione dei principi di snellimento dei processi in sanità (value-based care). RENata elimina i colli di bottiglia e le inefficienze documentali (time-saving), genera codice per diagrammi di flusso decisionali (Mermaid) e redige comunicazioni strutturate (email) per la raccolta dei dati mancanti, riducendo le ridondanze.
* **Focus sull'Esperienza del Paziente**: Il sistema è programmato per stimolare costantemente i team clinici all'inclusione di figure trasversali (psicologo, nutrizionista) e all'implementazione di nuovi indicatori centrati sul paziente (raccolta di PREMs e PROMs) e nuove tecnologie come la telemedicina.

## Pubblicazioni

* Cavallucci, M., Andalò, A., Gentili, N., Margagnoni, D., Santangelo, D. P., Lolli, C., Florescu, C., Massa, I., Bertoni, L., Deales, A., & Ferraresi, A. "RENata: A GPT-Based Virtual Assistant for Supporting the Development and Management of Multidisciplinary Diagnostic-Therapeutic Care Pathways (PDTA) in Renal Carcinoma." *Poster presentato ad AI4Oncology 2026, Milano*.
* Claudia Pimpini, Alice Andalò, Paolo De Angelis, Alessandro Mongardini, Ilaria Massa, Federica Ruffilli, Valentina Ravaioli, Alice Conficconi, Celeste Chieffo, Adriano Ferraresi, Pathway Assistant: un sistema multi-agente basato su IA generativa per l’orientamento informativo nei percorsi oncologici. *Poster presentato Annual Meeting SIIAM 2026, Genova*.
* CAlessandro Mongardini, Alice Andalò, Paolo De Angelis, Claudia Pimpini, Ilaria Massa, Cristian Lolli, Alberto Farolfi, Adriano Ferraresi, RENata v2.0: progettazione e valutazione preliminare di un assistente multi-agente per i PDTA oncologici. *Poster presentato Annual Meeting SIIAM 2026, Genova*.

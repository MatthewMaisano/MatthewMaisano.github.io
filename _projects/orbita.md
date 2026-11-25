---
layout: project
title: Orbita.
description: Una newsletter che ti avvisa quando esce un nuovo bando di dottorato o post-dottorato in fisica o matematica, filtrato per ambito.
kind: Web app · Newsletter
year: 2026
thumb: assets/img/thumbs/orbita.jpg
importance: 5
category: work
related_publications: false
stack: [GitHub Actions, Supabase, Resend, JavaScript]
links:
  - label: Apri la demo
    url: /projects/pj_finder/
    icon: fa-solid fa-arrow-up-right-from-square
    primary: true
highlights:
  - value: "PhD · Postdoc"
    label: scegli il tipo di posizione che ti interessa
  - value: "1 email"
    label: solo quando esce un bando nel tuo ambito
  - value: "0 €"
    label: infrastruttura interamente su servizi gratuiti
---

## L'idea

Trovare i bandi di dottorato e post-dottorato in fisica e matematica significa oggi controllare a mano decine di siti diversi — università, portali accademici, aggregatori — sperando di non perdersi quello giusto per il proprio ambito. **Orbita** capovolge il problema: ti iscrivi una volta sola indicando il tuo ambito e il tipo di posizione che cerchi (PhD, Postdoc, o entrambi), e ricevi un'email solo quando esce un bando che ti riguarda davvero.

<figure class="pj-figure">
  <a href="{{ '/projects/pj_finder/' | relative_url }}"><img src="{{ 'assets/img/thumbs/orbita.jpg' | relative_url }}" alt="Pagina di iscrizione di Orbita" loading="lazy"></a>
  <figcaption>La pagina di iscrizione: due campi e un doppio interruttore PhD/Postdoc.</figcaption>
</figure>

## Come funziona

<div class="pj-features">
  <div class="pj-feature"><strong>1 · Raccolta</strong><p>Una routine automatica controlla ogni giorno le principali fonti globali di annunci accademici in fisica e matematica.</p></div>
  <div class="pj-feature"><strong>2 · Classificazione</strong><p>I nuovi bandi vengono classificati per ambito e per tipo di posizione (PhD/Postdoc), eliminando i duplicati.</p></div>
  <div class="pj-feature"><strong>3 · Notifica</strong><p>Ogni iscritto riceve un'email solo per i bandi compatibili, più un riepilogo dei bandi recenti al momento dell'iscrizione.</p></div>
</div>

## Perché è interessante da costruire

Il progetto tocca sia il lato "prodotto" (un'interfaccia minimale in cui ridurre a due campi e un doppio interruttore un bisogno reale) sia il lato infrastrutturale: aggregare fonti eterogenee, evitare duplicati, e orchestrare un flusso automatico di raccolta e notifica interamente su servizi a costo zero (GitHub Actions, Supabase, Resend).

<div class="pj-callout" markdown="1">
<span class="pj-callout-title">Stato</span>
Front-end pubblicato e funzionante; backend attivo con una fonte già operativa (INSPIRE-HEP, fisica delle particelle/teorica). **Prossimo passo:** estendere la copertura ad altre fonti (Euraxess, AcademicJobsOnline, MathJobs) per coprire tutti gli ambiti disponibili nel form.
</div>

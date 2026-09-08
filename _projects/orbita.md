---
layout: page
title: Orbita.
description: Una newsletter che ti avvisa quando esce un nuovo bando di dottorato o post-dottorato in fisica o matematica, filtrato per ambito.
img:
importance: 2
category: work
related_publications: false
---

**Live demo: [matthewmaisano.github.io/projects/pj_finder](/projects/pj_finder/)**

**L'idea.** Trovare i bandi di dottorato e post-dottorato in fisica e matematica significa oggi controllare a mano decine di siti diversi — università, portali accademici, aggregatori — sperando di non perdersi quello giusto per il proprio ambito. Orbita capovolge il problema: ti iscrivi una volta sola indicando il tuo ambito e il tipo di posizione che cerchi (PhD, Postdoc, o entrambi), e ricevi un'email solo quando esce un bando che ti riguarda davvero.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <strong>Come funziona</strong>
        <ul>
            <li>Una routine automatica controlla ogni giorno le principali fonti globali di annunci accademici in fisica e matematica</li>
            <li>I nuovi bandi vengono classificati per ambito e per tipo di posizione (PhD/Postdoc)</li>
            <li>Ogni iscritto riceve un'email solo per i bandi compatibili con i propri criteri, oltre a un riepilogo iniziale dei bandi recenti al momento dell'iscrizione</li>
        </ul>
    </div>
</div>

**Perché è interessante da costruire.** Il progetto tocca sia il lato "prodotto" (un'interfaccia minimale in cui ridurre a due campi e un doppio interruttore un bisogno reale) sia il lato infrastrutturale: aggregare fonti eterogenee, evitare duplicati, e orchestrare un flusso automatico di raccolta e notifica interamente su servizi a costo zero (GitHub Actions, Supabase, Resend).

**Status.** Front-end pubblicato e funzionante; backend attivo con una fonte già operativa (INSPIRE-HEP, fisica delle particelle/teorica). Prossimo passo: estendere la copertura ad altre fonti (Euraxess, AcademicJobsOnline, MathJobs) per coprire tutti gli ambiti disponibili nel form.

# Time Manager

Un task manager personale basato sulla matrice Urgenza × Importanza (Eisenhower). Gira interamente nel browser — nessun server, nessuna dipendenza esterna, nessun account.

v1.0 · MIT License 2026 · Mario Rossi

→ **[Apri l'app](https://tuonome.github.io/time-manager/time-manager.html)**

---

## Funzionalità

- **Matrice Eisenhower** — classifica ogni task per urgenza e importanza; l'app calcola automaticamente l'orizzonte temporale (oggi / settimana / prossime settimane / backlog)
- **Escalation automatica** — i task si spostano verso orizzonti più urgenti man mano che la scadenza si avvicina o il progresso rallenta
- **Progetti con sottotask** — traccia il progresso con next action esplicita
- **Gantt** — vista visuale dei progetti con date di inizio e fine
- **In attesa** — marca i task che dipendono da altri; avvisi automatici dopo 7 giorni lavorativi
- **Allegati** — allega file ai task (salvati localmente nel browser via IndexedDB)
- **Cestino** — task e allegati eliminati recuperabili
- **Ricerca** — filtra per titolo, descrizione, sottotask, "in attesa di"
- **Ore occupate** — dichiara le ore già bloccate in agenda; il calcolo del carico si adatta
- **Review di fine giornata** — processa i task aperti e l'inbox
- **Dark / Light mode**
- **Export / Import JSON** — backup completo dei dati

## Come si usa

1. Scarica `time-manager.html`
2. Aprilo in qualsiasi browser moderno (Chrome, Safari, Firefox)
3. Nessuna installazione, nessuna connessione richiesta

I dati sono salvati nel browser locale (localStorage + IndexedDB). Per spostarli su un altro dispositivo, usa i pulsanti **↑ Esporta** e **↓ Importa** nell'header.

> **Nota sugli allegati:** l'export JSON non include i file allegati (solo i metadati). Per trasferire gli allegati è necessario riallegarli manualmente sul nuovo dispositivo.

## Struttura

```
time-manager.html   # app completa — tutto in un singolo file
README.md
LICENSE
```

L'app è costruita con React (via Babel standalone) e non richiede alcun build step. L'intero codice sorgente è leggibile direttamente nell'HTML.

## Licenza

MIT — vedi [LICENSE](LICENSE).

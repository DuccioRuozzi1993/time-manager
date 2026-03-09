# Time Manager

Un task manager personale basato sulla matrice Urgenza × Importanza (Eisenhower). Gira interamente nel browser — nessun server, nessuna dipendenza esterna, nessun account.

v1.5 · MIT License 2026 · Duccio Ruozzi

→ **[Apri l'app](https://tuonome.github.io/time-manager/)**

---

## Funzionalità

### Organizzazione
- **Matrice Eisenhower** — classifica ogni task per urgenza e importanza; l'app calcola automaticamente l'orizzonte temporale (oggi / settimana / prossime settimane / backlog)
- **Escalation automatica** — i task si spostano verso orizzonti più urgenti man mano che la scadenza si avvicina o il progresso rallenta
- **Ordinamento intelligente** — all'interno di ogni sezione, i task si ordinano automaticamente per scadenza, rischio escalation e next action definita
- **Pin** — fissa manualmente un task in cima alla sua sezione quando l'ordine automatico non basta
- **Task ricorrenti** — cadenza giornaliera, settimanale o mensile; alla chiusura viene creata automaticamente la prossima occorrenza
- **Modelli di sottotask** — salva e riutilizza liste di sottotask predefinite; i task del modello si aggiungono a quelli già presenti

### Esecuzione
- **Focus Mode** — schermata dedicata per lavorare su un singolo task, con timer countdown opzionale (15 / 25 / 50 min o personalizzato), pausa/riprendi, e completamento diretto
- **Sottotask con next action** — marca il prossimo passo concreto di ogni progetto; appare in evidenza sotto il task in lista
- **Progetti con sottotask** — traccia il progresso automaticamente; la barra di avanzamento è calcolata dai sottotask

### Cattura e revisione
- **Quick Capture** — barra sempre visibile per catturare un pensiero in inbox senza interrompere il flusso
- **Review di fine giornata** — processa i task aperti e classifica l'inbox
- **In attesa** — marca i task che dipendono da altri; avvisi automatici dopo 7 giorni lavorativi

### Intelligenza adattiva
- **Suggerimenti contestuali** — avvisi su overcommitment, inbox in accumulo, progetti senza next action, backlog sovraccarico
- **Suggerimenti comportamentali** — l'app impara dai tuoi pattern: segnala i task posticipati più volte e quelli fermi in backlog da oltre 14 giorni, con azione diretta per eliminarli o tenerli
- **Monitoraggio memoria** — controlla l'uso del localStorage in tempo reale; avvisa a 75% e 90% del limite con indicazione della fonte e azioni dirette per liberare spazio

### Interfaccia
- **Scorciatoie da tastiera** — `N` nuovo task, `F` focus mode, `G` Gantt/Agenda, `E` modifica, `Enter` completa, `Backspace` cestina, `Cmd/Ctrl+K` cerca, `?` guida, `Esc` chiudi; disabilitate automaticamente mentre si digita
- **Gantt** — vista visuale dei progetti con date di inizio e fine
- **Dark / Light mode**
- **Ricerca** — filtra per titolo, descrizione, sottotask, "in attesa di"
- **Ore occupate** — dichiara le ore già bloccate in agenda; il calcolo del carico si adatta

### Dati
- **Export / Import JSON** — backup completo dei dati
- **Reminder backup automatico** — avvisa dopo 7 giorni dall'ultimo export
- **Allegati** — allega file ai task (salvati localmente via IndexedDB)
- **Cestino** — task e allegati eliminati recuperabili

---

## Come si usa

1. Scarica `time-manager.html`
2. Aprilo in qualsiasi browser moderno (Chrome, Safari, Firefox)
3. Nessuna installazione, nessuna connessione richiesta

I dati sono salvati nel browser locale (localStorage + IndexedDB). Per spostarli su un altro dispositivo, usa i pulsanti **↑ Esporta** e **↓ Importa** nell'header.

> **Nota sugli allegati:** l'export JSON non include i file allegati (solo i metadati). Per trasferire gli allegati è necessario riallegarli manualmente sul nuovo dispositivo.

---

## Struttura

```
time-manager.html   # app completa — tutto in un singolo file
README.md
LICENSE
```

L'app è costruita con React 18 (via Babel standalone) e non richiede alcun build step. L'intero codice sorgente è leggibile direttamente nell'HTML. I dati sono isolati nel browser — nessun dato viene mai trasmesso all'esterno.

---

## Changelog

### v1.5 — 2026
- Focus Mode con timer countdown e completamento diretto
- Task ricorrenti (giornaliero / settimanale / mensile)
- Modelli di sottotask riutilizzabili
- Ordinamento intelligente automatico all'interno delle sezioni
- Pin manuale per fissare un task in cima
- Scorciatoie da tastiera complete con pannello guida
- Suggerimenti comportamentali basati sui pattern di utilizzo (task posticipati, backlog stagnante)
- Monitoraggio memoria localStorage con avvisi e azioni dirette
- Reminder backup automatico dopo 7 giorni
- Ottimizzazione rendering con `useCallback` su tutti i mutatori

### v1.0 — 2025
- Prima release pubblica

---

## Licenza

MIT — vedi [LICENSE](LICENSE).

---

*Designed by Duccio Ruozzi and Claude in 2026*

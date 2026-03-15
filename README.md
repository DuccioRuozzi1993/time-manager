# Time Manager

Un task manager personale basato sulla matrice Urgenza × Importanza (Eisenhower). Gira interamente nel browser — nessun server, nessuna dipendenza esterna, nessun account.

v1.2 · MIT License 2026 · Duccio Ruozzi

→ **[Apri l'app](https://tuonome.github.io/time-manager/)**

---

## Funzionalità

### Organizzazione
- **Matrice Eisenhower** — classifica ogni task per urgenza e importanza; l'app calcola automaticamente l'orizzonte temporale (oggi / settimana / prossime settimane / backlog)
- **Escalation automatica** — i task si spostano verso orizzonti più urgenti man mano che la scadenza si avvicina o il progresso rallenta
- **Ordinamento intelligente** — all'interno di ogni sezione, i task si ordinano automaticamente per scadenza, rischio escalation e next action definita
- **Pin** — fissa manualmente un task in cima alla sua sezione quando l'ordine automatico non basta
- **Snooze** — rimanda a più tardi un task di oggi selezionando un orario specifico; al rientro viene contrassegnato con un badge visivo
- **Task ricorrenti** — cadenza giornaliera, settimanale o mensile; alla chiusura viene creata automaticamente la prossima occorrenza
- **Modelli di sottotask** — salva e riutilizza liste di sottotask predefinite; i task del modello si aggiungono a quelli già presenti

### Esecuzione
- **Focus Mode** — schermata dedicata per lavorare su un singolo task, con timer countdown opzionale (15 / 25 / 50 min o personalizzato), pausa/riprendi e completamento diretto; i sottotask sono interattivi anche in questa vista
- **Sottotask con next action** — marca il prossimo passo concreto di ogni progetto; appare in evidenza sotto il task in lista
- **Progetti con sottotask** — traccia il progresso automaticamente; la barra di avanzamento è calcolata dai sottotask
- **Barra di progresso giornaliero** — linea verticale (8:00–18:00) a sinistra della sezione Oggi indica visivamente a che punto della giornata ci si trova

### Cattura e revisione
- **Quick Capture** — barra sempre visibile per catturare un pensiero in inbox senza interrompere il flusso; riconosce linguaggio naturale (nomi di giorno, "domani", "questa settimana", "urgente", "importante") per pre-classificare il task
- **Filtro Solo Oggi** — mostra solo la sezione Oggi (e In attesa) per ridurre il rumore visivo; attivabile dal pulsante in header o con il tasto `T`
- **Review di fine giornata** — processa i task aperti e classifica l'inbox
- **In attesa** — marca i task che dipendono da altri; avvisi automatici dopo 7 giorni lavorativi

### Intelligenza adattiva
- **Suggerimenti contestuali** — avvisi su overcommitment, inbox in accumulo, progetti senza next action, backlog sovraccarico
- **Suggerimenti comportamentali** — l'app impara dai tuoi pattern: segnala i task posticipati più volte e quelli fermi in backlog da oltre 14 giorni lavorativi, con azione diretta per eliminarli o tenerli
- **Monitoraggio memoria** — controlla l'uso del localStorage in tempo reale; avvisa a 75% e 90% del limite con indicazione della fonte e azioni dirette per liberare spazio

### Interfaccia
- **Scorciatoie da tastiera** — `N` nuovo task, `T` Solo Oggi, `F` focus mode, `G` Gantt/Agenda, `E` modifica, `Enter` completa, `Backspace` cestina, `Cmd/Ctrl+K` cerca, `?` guida, `Esc` chiudi; in focus mode `Spazio` mette in pausa/riprende il timer; disabilitate automaticamente mentre si digita
- **Gantt** — vista visuale dei progetti con date di inizio e fine, navigazione per settimane e linea "oggi"
- **Sottotitoli temporali** — ogni sezione riporta il range di date contestuale (es. "Lunedì 17 mar" o "17–21 mar")
- **Simboli di orizzonte** — ● ◕ ◑ ○ affiancano il colore nelle intestazioni di sezione per garantire leggibilità anche in condizioni di scarsa percezione cromatica
- **Dark / Light mode**
- **Ricerca** — filtra per titolo, descrizione, sottotask, "in attesa di"
- **Ore occupate** — dichiara le ore già bloccate in agenda; il calcolo del carico si adatta
- **Toast di completamento** — notifica discreta con contatore giornaliero al completamento di ogni task

### Dati
- **Export / Import JSON** — backup completo dei dati (task attivi e cestino)
- **Reminder backup automatico** — avvisa dopo 7 giorni dall'ultimo export
- **Allegati** — allega file ai task (salvati localmente via IndexedDB)
- **Cestino** — task e allegati eliminati recuperabili separatamente

---

## Come si usa

1. Scarica `index.html`
2. Aprilo in qualsiasi browser moderno (Chrome, Safari, Firefox)
3. Nessuna installazione, nessuna connessione richiesta

I dati sono salvati nel browser locale (localStorage + IndexedDB). Per spostarli su un altro dispositivo, usa i pulsanti **Esporta** e **Importa** nel menu ···.

> **Nota sugli allegati:** l'export JSON non include i file allegati (solo i metadati). Per trasferire gli allegati è necessario riallegarli manualmente sul nuovo dispositivo.

---

## Struttura

```
index.html   # app completa — tutto in un singolo file
README.md
LICENSE
```

L'app è costruita con React 18 (via Babel standalone) e non richiede alcun build step. L'intero codice sorgente è leggibile direttamente nell'HTML. I dati sono isolati nel browser — nessun dato viene mai trasmesso all'esterno.

---

## Changelog

### v1.2 — 2026
- Focus Mode con timer countdown (15 / 25 / 50 min o personalizzato), pausa/riprendi e completamento diretto
- Task ricorrenti (giornaliero / settimanale / mensile)
- Modelli di sottotask riutilizzabili (crea, rinomina, applica, salva dall'editor task)
- Ordinamento intelligente automatico all'interno delle sezioni (deadline, rischio escalation, next action)
- Pin manuale per fissare un task in cima alla sua sezione
- Snooze: rimanda un task a un orario specifico nella stessa giornata
- Filtro Solo Oggi (`T`) per ridurre il rumore visivo
- Barra di progresso giornaliero nella sezione Oggi (8:00–18:00)
- Scorciatoie da tastiera complete con pannello guida (`?`)
- Parser linguaggio naturale in Quick Capture (giorno della settimana, "domani", "urgente", ecc.)
- Suggerimenti comportamentali basati sui pattern di utilizzo (task posticipati, backlog stagnante)
- Monitoraggio memoria localStorage con avvisi a 75% e 90%, azioni dirette per liberare spazio
- Reminder backup automatico dopo 7 giorni dall'ultimo export
- Toast di completamento con contatore giornaliero
- Sottotitoli temporali contestuali nelle intestazioni di sezione
- Simboli di orizzonte (● ◕ ◑ ○) come supporto all'accessibilità cromatica
- Ottimizzazione rendering con `useCallback` su tutti i mutatori

### v1.0 — 2026
- Prima release pubblica

---

## Licenza

MIT — vedi [LICENSE](LICENSE).

---

*Designed by Duccio Ruozzi and Claude in 2026*

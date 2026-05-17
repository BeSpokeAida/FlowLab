# Sandbox n8n · Sistema di ticketing (PCTO)

Un **laboratorio tutto in un file HTML**: niente installazioni, niente server da avviare. Apri la pagina nel browser e costruisci workflow come su **n8n**, con un tocco da aula.

> Stack: **HTML + CSS + JavaScript** — zero dipendenze, zero `npm install`.

---

## Cosa c’è dentro

| Zona | A cosa serve |
|------|----------------|
| **Canvas** | Nodi, collegamenti, zoom, drag — il cuore del workflow |
| **Libreria** | Aggiungi trigger, Code, Data Table, Form Response… |
| **Esegui** | Motore locale: form → codice → tabella → messaggi di completamento |
| **Data Table** | Vista dati e schema (ticket, email, stato…) |
| **Executions** | Storico delle esecuzioni |
| **Sistema** | Tre “webhook” didattici: **nessuna chiamata rete** — si esegue il canvas con il JSON che invieresti davvero |
| **Importa / Salva** | JSON con `name`, `nodes`, `connections` — stesso formato in uscita e in entrata |

File principale: **`n8n-sandbox.html`** (accanto a **`logo.png`** per il logo in alto).

---

## Avvio rapido

1. Scarica o clona la cartella del progetto.
2. Fai doppio clic su **`n8n-sandbox.html`** *oppure* aprilo da “Apri file” nel browser (Chrome / Edge / Firefox vanno bene).
3. Trascina i nodi dalla barra laterale, collega le porte, poi **Esegui**.

> Suggerimento: se il browser blocca funzioni “file://”, usa un piccolo server statico (es. `npx serve .`) — spesso non serve.

---

## Perché “Sistema” non chiama localhost

In aula spesso **n8n non gira** sul PC di ogni studente. La sezione **Sistema** chiede tre URL “da vero progetto” per abitudine e per **abbinare** il flusso:

- Con nodi **Webhook** + slug nel parametro del nodo → match sull’URL.
- Con solo **Form trigger** (come nei workflow esportati da qui) → conta l’**ordine da sinistra** sul canvas: 1° inserimento, 2° check, 3° aggiornamento.

L’esecuzione è **identica** al tasto **Esegui**: stesso motore, risposta visibile nel pannello.

---

## Import del workflow

- **Salva** → scarica un `.json` con struttura già compatibile.
- **Importa** → scegli un file JSON con `name`, `nodes`, `connections` (accettato anche il campo `conns`).

Prima di sostituire il canvas, ti chiede conferma se hai già nodi sullo schermo.

---

## Suggerimenti per studenti e docenti

- Usa **Form trigger** per raccogliere dati, **Code** per logica (es. generare `ticket_id`), **Data Table** per persistenza in memoria nella sessione, **Form Response** per messaggi di chiusura.
- Dopo un’esecuzione, nel pannello nodo compaiono **Input / Output** utili per copiare espressioni `{{ $json.… }}`.
- Il menu sul nodo (**clic sinistro**) offre *Configura*, *Duplica*, *Elimina*; **clic destro** apre subito i parametri.

---

## Limiti (onesti e utili)

- È un **simulatore didattico**, non n8n in produzione: nodi e comportamenti sono quelli implementati nel file.
- I dati della **Data Table** vivono nella pagina: chiudendo il tab si perdono (come una sessione di prova).

---

## Licenza e crediti

Contenuto pensato per **PCTO / laboratorio**: adatta testi, logo e workflow agli obiettivi della tua classe.

Se migliori il file, **Salva** spesso il JSON del workflow — è il tuo “backup” portatile.

---

*Buon lavoro sul canvas.*

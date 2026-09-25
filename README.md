# 🌌 Guida galattica alla ricerca di lavoro

🇬🇧 [English version](README.en.md)

**Un coach "tutto in uno" per la ricerca di lavoro, dal CV all'offerta firmata, che gira dentro
[Claude Code](https://claude.com/claude-code).** Lavora in locale, i tuoi dati restano sul tuo computer, e si basa sulle
[Guide galattiche](https://github.com/GuidoPenta) per sviluppatori.

> Incolli un annuncio di lavoro. Lui studia l'azienda, ti dice come un recruiter valuterà il tuo CV, ti prepara al
> colloquio, ti suggerisce le domande giuste da fare e ti accompagna nella negoziazione.

## Cosa fa

| Fase | Skill | Cosa ottieni |
|---|---|---|
| Si parte | `galactic-job-search` | Uno spazio di lavoro privato, il tuo profilo, e la risposta a "cosa faccio adesso?" |
| CV | `galactic-cv` | Revisione secondo la [Guida galattica al CV](https://github.com/GuidoPenta/galactic-CV-guide-for-developers), punteggio "come ti vede chi seleziona" su un annuncio (rubrica di [cv-review](https://github.com/matteobaccan/cv-review)), riscritture oneste |
| LinkedIn | `galactic-linkedin` | Mappa delle parole chiave, titolo/About/esperienze riscritti e pronti da incollare, risposte tipo per i recruiter ([guida](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers)) |
| Candidatura | `galactic-application` | L'annuncio decifrato, ricerca sull'azienda con le fonti, analisi del fit, una scheda di una pagina da leggere prima della call |
| Colloquio | `galactic-interview-prep` | Piano di preparazione, archivio di storie (metodo STAR), colloqui simulati con feedback, risorse per ruolo ([guida](https://github.com/GuidoPenta/galactic-tech-interview-guide)) |
| Le tue domande | `galactic-reverse-interview` | Domande su misura da fare, segnali d'allarme, confronto tra aziende ([guida](https://github.com/GuidoPenta/galactic-reverse-interview-guide-for-developers)) |
| Offerta | `galactic-negotiation` | Come rispondere sulla RAL, valutazione dell'offerta, testo della controproposta, simulazione della trattativa ([guida](https://github.com/GuidoPenta/galactic-negotiation-guide-for-developers)) |
| Community | `galactic-communities` | Gruppi, mentor, fonti di lavoro da remoto ed eventi adatti a te ([lista](https://github.com/GuidoPenta/awesome-italian-tech-communities)) |
| Tracking | `galactic-tracker` | Le tue candidature in un colpo d'occhio, cosa ricontattare, statistiche, export in CSV o verso [TrackZilla](https://www.trackzilla.cv/) |

## Privacy prima di tutto

- Tutto quello che condividi (CV, annunci, appunti, offerte) resta in semplici file di testo nella cartella
  `workspace/`, che **non viene mai caricata su GitHub**.
- Niente account, niente server, niente programmi da installare oltre a Claude Code.
- Il web serve solo per cercare informazioni **pubbliche** su aziende, ruoli e stipendi. Le skill hanno l'istruzione
  di non mettere mai i tuoi dati personali nelle ricerche.
- Da sapere: Claude è un modello che gira nel cloud, quindi quello che scrivi nella conversazione viene elaborato da
  Anthropic secondo i termini del tuo piano. "In locale" qui vuol dire che i tuoi file e la tua cronologia restano sul
  tuo disco e non vengono caricati su nessun altro servizio.

## Come si comincia

1. Installa [Claude Code](https://claude.com/claude-code): va bene l'app desktop, il terminale o l'estensione per l'editor.
2. Scarica questo progetto: dalla pagina GitHub premi **Code → Download ZIP** ed estrailo, oppure, se usi git:
   ```bash
   git clone https://github.com/GuidoPenta/Guida-galattica-job-search.git
   ```
3. Apri la cartella in Claude Code. Le skill si caricano da sole.
4. Scrivi **"Iniziamo la mia ricerca di lavoro"**. Claude prepara il tuo spazio di lavoro e ti chiede il CV.

Poi basta parlargli, per esempio:
- *"Rivedi il mio CV"*
- *"Ecco un annuncio che mi interessa: [incolla]"*
- *"Giovedì ho il colloquio tecnico da Acme, aiutami a prepararmi"*
- *"Cosa chiedo all'engineering manager?"*
- *"Mi hanno offerto 45k di RAL, è buona?"*
- *"A che punto sono con le candidature?"*

Le istruzioni interne delle skill sono in inglese, così c'è una sola versione da mantenere, ma Claude ti risponde
nella lingua in cui gli scrivi.

## Crediti

- Guide di [Guido Penta](https://github.com/GuidoPenta) (MIT): CV, LinkedIn, colloquio tecnico, colloqui,
  reverse interview, negoziazione, ruoli tech e community tech italiane.
- Rubrica di valutazione adattata da [cv-review](https://github.com/matteobaccan/cv-review) di
  [Matteo Baccan](https://github.com/matteobaccan), usata con il suo permesso.
- Community: La Locanda del Tech, [Full Remote](https://www.fullremote.it/), [Dataskew](https://dataskew.io/),
  coffeechat e chi mantiene le liste citate in `galactic-communities`.

## Contribuire

Issue e pull request sono benvenute, soprattutto per le risorse di preparazione dei ruoli non ancora coperti
(`.claude/skills/galactic-interview-prep/references/resources-by-role.md`) e per nuove community.
Le istruzioni delle skill restano in inglese, fedeli alle guide da cui derivano, e il progetto resta senza dipendenze.

## Licenza

[MIT](LICENSE)

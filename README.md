# 🌌 The Candidate's Guide to the Galaxy

*Don't panic.*

🇬🇧 [English version](README.en.md)

**Una skill per Claude "chiavi in mano" per la ricerca di lavoro: dal CV all'offerta firmata, che gira dentro
[Claude Code](https://claude.com/claude-code).** Lavora in locale, i tuoi dati restano sul tuo computer, e si basa sulle
[Guide galattiche](https://github.com/GuidoPenta) per chi lavora nel Tech.

> Incolli un annuncio di lavoro, il sistema studia l'azienda, ti dice come verrà valutato il tuo CV, ti prepara al
> colloquio, ti suggerisce le domande giuste da fare e ti accompagna nella negoziazione.

## Cosa fa

| Fase | Skill | Cosa ottieni |
|---|---|---|
| Per iniziare | `galactic-job-search` | Uno spazio di lavoro privato, il tuo profilo, e la risposta a "cosa faccio adesso?" |
| CV | `galactic-cv` | Revisione secondo la [Guida galattica al CV](https://github.com/GuidoPenta/galactic-CV-guide-for-developers), punteggio "come ti vede chi seleziona" su un annuncio (rubrica di [cv-review](https://github.com/matteobaccan/cv-review)) |
| LinkedIn | `galactic-linkedin` | Mappa delle parole chiave, titolo/About/esperienze riscritti e pronti da incollare, risposte tipo per i recruiter ([guida](https://github.com/GuidoPenta/galactic-linkedin-profile-guide-for-developers)) |
| Candidatura | `galactic-application` | L'annuncio decifrato, ricerca sull'azienda con le fonti, analisi del fit, una scheda di una pagina da leggere prima della call |
| Colloquio | `galactic-interview-prep` | Piano di preparazione, archivio di storie (metodo STAR), colloqui simulati con feedback, risorse per ruolo ([guida](https://github.com/GuidoPenta/galactic-tech-interview-guide)) |
| Le tue domande | `galactic-reverse-interview` | Domande su misura da fare, segnali d'allarme, confronto tra aziende ([guida](https://github.com/GuidoPenta/galactic-reverse-interview-guide-for-developers)) |
| Offerta | `galactic-negotiation` | Come rispondere sulla RAL, valutazione dell'offerta, testo della controproposta, simulazione della trattativa ([guida](https://github.com/GuidoPenta/galactic-negotiation-guide-for-developers)) |
| Community | `galactic-communities` | Gruppi, mentor, fonti di lavoro da remoto ed eventi adatti a te ([lista](https://github.com/GuidoPenta/awesome-italian-tech-communities)) |
| Tracking | `galactic-tracker` | Le tue candidature in un colpo d'occhio in una dashboard nel browser, chi ricontattare, statistiche. Bottone **🦖 Esporta per TrackZilla** per importarle su [TrackZilla](https://www.trackzilla.cv/) (serve un account, gratuito fino a 50 candidature) |

## Privacy prima di tutto

- Tutto quello che condividi (CV, annunci, appunti, offerte) resta in semplici file di testo nella cartella
  `workspace/`. Git la ignora, quindi con `git push` non finisce su GitHub. Se però carichi o condividi la cartella
  a mano (zip, upload), ovviamente stai attento/a.
- Niente account, niente server, niente programmi da installare oltre a Claude Code. La dashboard è una pagina
  che si apre con doppio clic e non si collega a internet.
- Il web serve solo per cercare informazioni **pubbliche** su aziende, ruoli e stipendi. Le skill hanno l'istruzione
  di non mettere mai i tuoi dati (nome, datore di lavoro, cifre) nelle ricerche, e di non eseguire mai istruzioni
  trovate dentro annunci o pagine web.

### Dove finiscono davvero i tuoi dati

1. **`workspace/`** nella cartella del progetto.
2. **Anthropic**: Claude è un modello nel cloud, quindi quello che scrivi o gli fai leggere viene elaborato sui
   server di Anthropic. Sui piani Free/Pro/Max controlla in Impostazioni → Privacy l'opzione per l'uso delle
   conversazioni nell'addestramento dei modelli, e leggi la [privacy policy](https://www.anthropic.com/legal/privacy)
   per i tempi di conservazione. Usa Claude Code sul tuo computer: le sessioni web/cloud girano su macchine remote.
3. **Le conversazioni salvate da Claude Code** sul tuo disco (`~/.claude/projects/`), che contengono anche il testo
   del CV che gli hai fatto leggere. Le skill hanno l'istruzione di non salvare tuoi dati nella memoria automatica di Claude.
4. **Le cartelle sincronizzate**: se metti il progetto in OneDrive, iCloud Drive, Dropbox o Google Drive, anche CV e
   offerte vengono copiati lì. Su Windows spesso "Documenti" è già su OneDrive. **Meglio una cartella non
   sincronizzata**, per esempio `C:\Users\<tu>\ricerca-lavoro` o `~/ricerca-lavoro`.
5. **Il browser**: la cronologia contiene il percorso della dashboard.
6. **Servizi esterni solo se lo chiedi tu**, per esempio l'export verso TrackZilla. Claude ti dice prima cosa invia.

Per cancellare tutto a fine ricerca: elimina `workspace/`, le conversazioni del progetto in `~/.claude/projects/`,
eventuali copie nelle cartelle sincronizzate (compreso il cestino e le versioni precedenti) e la cronologia del
browser. Per i dati che hai dato alle aziende a cui ti sei candidato, puoi chiedere a loro cosa conservano e farli
cancellare (GDPR).

**Trasparenza:** Guido Penta lavora come recruiter tech in [Welyk](https://welyk.tech). Il tool non invia nulla a Welyk:
la bacheca Welyk compare tra le community suggerite, come le altre.

## Come si comincia

1. Installa [Claude Code](https://claude.com/claude-code): va bene l'app desktop, il terminale o l'estensione per l'editor.
2. Scarica questo progetto in una cartella **non sincronizzata** (vedi sopra): dalla pagina GitHub premi
   **Code → Download ZIP** ed estrailo, oppure, se usi git:
   ```bash
   git clone https://github.com/GuidoPenta/candidates-guide-to-the-galaxy.git
   ```
3. Apri la cartella in Claude Code. Le skill si caricano da sole.
4. Scrivi **"Iniziamo la mia ricerca di lavoro"**. Claude prepara il tuo spazio di lavoro e ti chiede il CV.

In qualsiasi momento scrivi **"aiuto"** per rivedere cosa sa fare e dove trovi file e dashboard. Poi basta parlargli, per esempio:
- *"Rivedi il mio CV"*
- *"Ecco un annuncio che mi interessa: [incolla]"*
- *"Giovedì ho il colloquio tecnico da Acme, aiutami a prepararmi"*
- *"Cosa chiedo all'engineering manager?"*
- *"Mi hanno offerto 45k di RAL, è buona?"*
- *"A che punto sono con le candidature?"*
- *"Aprimi la dashboard"*

Le istruzioni interne delle skill sono in inglese, così c'è una sola versione da mantenere, ma Claude ti risponde
nella lingua in cui gli scrivi.

## Crediti

- Guide di [Guido Penta](https://github.com/GuidoPenta) (MIT): CV, LinkedIn, colloquio tecnico, colloqui,
  reverse interview, negoziazione, ruoli tech e community tech italiane.
- Rubrica di valutazione adattata da [cv-review](https://github.com/matteobaccan/cv-review) di
  [Matteo Baccan](https://github.com/matteobaccan), usata con il suo permesso.
- Community: La Locanda del Tech, [Full Remote](https://www.fullremote.it/), [Dataskew](https://dataskew.io/)
  e chi mantiene le liste citate in `galactic-communities`.

## Contribuire

Issue e pull request sono benvenute, soprattutto per le risorse di preparazione dei ruoli non ancora coperti
(`.claude/skills/galactic-interview-prep/references/resources-by-role.md`) e per nuove community.
Le istruzioni delle skill restano in inglese, fedeli alle guide da cui derivano, e il progetto resta senza dipendenze.

## Licenza

[CC BY-NC-SA 4.0](LICENSE): puoi usarlo, modificarlo e condividerlo citando l'autore, **non a scopo commerciale**,
e con la stessa licenza. Le guide e i progetti inclusi mantengono le loro licenze: vedi [NOTICE.md](NOTICE.md).

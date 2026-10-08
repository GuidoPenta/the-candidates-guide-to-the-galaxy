# 🌌 The Candidate's Guide to the Galaxy

*Don't panic.*

🇬🇧 [English version](README.en.md)

**Un insieme di skill AI "chiavi in mano" per la ricerca di lavoro, dal CV all'offerta firmata. Pensato per
[Claude Code](https://claude.com/claude-code), funziona anche con altri agent AI (per esempio Cursor).** I tuoi file restano sul tuo computer ([cosa passa invece dall'AI](#privacy-cosa-resta-sul-tuo-computer-e-cosa-no)), e si basa sulle
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

## Privacy: cosa resta sul tuo computer e cosa no

**In una frase:** i tuoi **file** restano sul tuo computer, ma tutto quello che fai **leggere all'AI** passa dai
server del fornitore del modello che usi. Il progetto non ha un server suo: né Guido né Welyk ricevono i tuoi dati.

### ✅ Cosa resta sul tuo computer
- **I tuoi file**: CV, profilo, annunci, appunti, offerte, in semplici file di testo nella cartella `workspace/`.
  Git la ignora, quindi con `git push` non finisce su GitHub. Se però carichi o condividi la cartella a mano (zip,
  upload), ovviamente stai attento/a.
- **La dashboard**: è una pagina che si apre con doppio clic e non si collega a internet.
- **Niente account e niente server** del progetto: ti serve solo il tuo agent AI (Claude Code o simili).

### ⚠️ Cosa esce dal tuo computer
1. **Verso il fornitore del modello AI: sempre.** È così che funziona qualsiasi assistente AI, non solo questo:
   quello che scrivi e quello che fai leggere all'agent (CV compreso) viene elaborato sui server di **chi fornisce
   il modello**. Con Claude Code è Anthropic; con Cursor, un altro editor, un'app o un client da riga di comando è il
   fornitore del modello che hai scelto (Anthropic, OpenAI, Google…) e a volte anche lo strumento stesso.
   Controlla le impostazioni privacy di entrambi (per esempio se le conversazioni vengono usate per addestrare i
   modelli) e le loro privacy policy, come quella di [Anthropic](https://www.anthropic.com/legal/privacy).
   Preferisci l'agent sul tuo computer: le sessioni web/cloud girano su macchine remote.
2. **Verso il web: solo ricerche su informazioni pubbliche** (aziende, ruoli, stipendi). Le skill hanno l'istruzione
   di non mettere mai i tuoi dati (nome, datore di lavoro, cifre) nelle ricerche, e di non eseguire mai istruzioni
   trovate dentro annunci o pagine web.
3. **Verso altri servizi: solo se lo chiedi tu**, per esempio l'export verso TrackZilla. Prima ti viene detto
   cosa viene inviato.

### 📁 Copie che forse non sai di avere
- **Le conversazioni salvate dal tuo agent** sul tuo disco (con Claude Code in `~/.claude/projects/`): contengono
  anche il testo del CV che gli hai fatto leggere. Le skill hanno l'istruzione di non salvare i tuoi dati nella
  memoria automatica dell'agent.
- **Le cartelle sincronizzate**: se metti il progetto in OneDrive, iCloud Drive, Dropbox o Google Drive, anche CV e
  offerte vengono copiati lì. Su Windows spesso "Documenti" è già su OneDrive. **Meglio una cartella non
  sincronizzata**, per esempio `C:\Users\<tu>\ricerca-lavoro` o `~/ricerca-lavoro`.
- **Il browser**: la cronologia contiene il percorso della dashboard.

### 🧹 Per cancellare tutto a fine ricerca
Elimina `workspace/`, le conversazioni del progetto salvate dal tuo agent, eventuali copie nelle cartelle
sincronizzate (compreso il cestino e le versioni precedenti) e la cronologia del browser. Per i dati che hai dato
alle aziende a cui ti sei candidato/a, puoi chiedere a loro cosa conservano e farli cancellare (GDPR). Per quelli
elaborati dal fornitore dell'AI, vedi la sua privacy policy.

**Trasparenza:** Guido Penta lavora come recruiter tech in [Welyk](https://welyk.tech). Il tool non invia nulla a Welyk:
la bacheca Welyk compare tra le community suggerite, come le altre.

## ATS: miti e verità

Nelle community se ne sentono di tutti i colori. In breve, con le fonti nel file
[ats.md](.claude/skills/galactic-cv/references/ats.md):

- **"L'ATS scarta in automatico il 75% dei CV"**: leggenda. Il dato risale a una società di ottimizzazione CV del
  2012 che non ha mai pubblicato uno studio.
- **Un ATS è il software dove arrivano e si gestiscono le candidature**: archivio, fasi, ricerca. Non è un robot che
  decide al posto delle persone.
- **I filtri automatici esistono, ma li configura qualcuno**: soprattutto le domande eliminatorie nel form (sede,
  permesso di lavoro, disponibilità). Rispondi con cura.
- **Il CV "a prova di ATS" non esiste.** Conta un CV chiaro e pertinente: PDF testuale (non una foto), contatti nel
  corpo della pagina, parole chiave dell'annuncio solo per quello che hai fatto davvero.
- **LinkedIn o sito dell'azienda?** Se l'azienda ha un ATS cambia poco: finisci comunque lì. Se non ce l'ha, il canale
  decide in quale "contenitore" finisci e chi lo guarda per primo. E il sito ti conferma che la posizione è ancora aperta.

Chiedi a Claude **"cos'è un ATS?"** o **"mi candido da LinkedIn o dal sito?"** per la versione completa.

## Come si comincia

1. Installa [Claude Code](https://claude.com/claude-code): va bene l'app desktop, il terminale o l'estensione per l'editor.
   Usi già un altro agent (Cursor o simili)? Funziona anche lì: le skill sono istruzioni in file di testo che l'agent
   legge e segue. È pensata e collaudata soprattutto su Claude Code.
2. Scarica questo progetto in una cartella **non sincronizzata** (vedi sopra): dalla pagina GitHub premi
   **Code → Download ZIP** ed estrailo, oppure, se usi git:
   ```bash
   git clone https://github.com/GuidoPenta/the-candidates-guide-to-the-galaxy.git
   ```
3. Apri la cartella nel tuo agent. In Claude Code le skill si caricano da sole.
4. Scrivi **"Iniziamo la mia ricerca di lavoro"**. Claude prepara il tuo spazio di lavoro e ti chiede il CV.

### Prova veloce (2 minuti)

1. Apri la cartella del progetto nel tuo agent.
2. Scrivi **"aiuto"**: compare il vademecum con tutto quello che sa fare.
3. Trascina il tuo CV (PDF o immagine) nella cartella `workspace/cv/original/`, oppure incollalo, e scrivi
   **"rivedi il mio CV"**.

Se vedi il vademecum e ricevi una revisione che cita la Guida galattica al CV, funziona.

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

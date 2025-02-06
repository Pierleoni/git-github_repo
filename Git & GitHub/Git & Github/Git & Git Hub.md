
# Git

## Che cos'è Git?

Git è una controllo di versione di sistema (Version control system/VCS) free e open source. 
Per controllo di versione si intende:  
==la gestione di modifiche ai documenti, programmi del computer, grossi siti web e altre raccolte di informazioni.==  
<span style="background:#ff4d4f">Quindi è un sistema che registra, nel tempo i cambiamenti ad un file o ad una serie di file, cosi da poter richiamare una specifica versione in un secondo momento.  </span>  
Mentre un VCS ti permette di ripristinare i file ad una versione precedente (ripristinare l'intero progetto a uno stato precedente), revisionare le modifiche nel tempo , vedere i cambiamenti fatti da terzi (chi ha introdotto un problema e quando e molto altro ancora).  
Usare un VCS, in generale, significa anche che se fai un pasticcio, ad esempio, perdere/cancellare/eliminare qualche file puoi facilmente recuperalo troppa fatica.  
Quindi in sostanza i programmatori tengono traccia delle modifiche del loro codice: 
salvano una versione iniziale di esso in git, poi quando lo aggiornano lo salvano sempre in git e questa operazione viene ripetuta sempre più volte(potenzialmente fino all'infinito). 
Questi salvataggi non sono solo utili per salvare le modifiche ma permettono di ritornare suoi propri passi per vedere i vari passaggi, questo ci aiuta a capire e vedere cosa abbiamo fatto.  
Tutto ciò può essere utile anche quando dobbiamo rintracciare dei bug o per tornare a una versione precedente del codice.  
Esistono diversi software che permettono di utillizare il controllo di versione, quello più usato è Git. Essendo un sistema di controllo distribuito ci permette di lavorare ai vari progetti anche senza avere una connessione internet, questo perchè all'interno della nostra repository locale abbiamo tutti le modifiche fatte da noi stessi o da altre persone.  
![[CV distribuito.png]]


Questo sistema è molto più conveniente rispetto ad un sistema centralizato, dove bisogna avere un server centrale nel quale salvare tutte queste informazioni. 
![[Central CVS.jpg]]  
N.B. se lavoriamo in un team o più semplicemente vogliamo rendere pubblico il nostro progetto, chiunque scaricherà la repository avrà localmente sulla sua macchina tutte le modifiche apportate fino a quel momento.




## 
## Info Tecniche

Può esserti utile sapere che il commando git reset file copia la versione del file presente nel HEAD nell'Index, esattamente come git restore --staged file.  
Tuttavia è bene notare che git restore, a differenza di questa particolare forma di git reset, può sovrascrivire la copia della working tree di alcuni file, se gli dici di farlo. Di conseguenza l'opzione --staged, senza l'opzione --worktree, lo indirizza a scrivere solo all'indice.
## La working directory e la staging Area 
Per comprendere come Git gestisce i file e le directory locali prima di archiviarli in un repository remoto, è fondamentale conoscere la distinzione tra la working directory e la staging area.

![[Schema commit.png|400]]  
Seguendo questo schema, partendo dal basso verso l'alto, cercheremo di capire meglio il meccanismo di quello che abbiamo fatto fino ad adesso:
immaginiamo la struttura di Git suddivisa in 3 aree di lavoro:

1. La prima area è la working directory:
   È la cartella locale dove si hanno i file del progetto, qui si apportano le modifiche ai file.
   Quindi nella working directory  sono contenuti i nostri file/sub-directory che, tramite il comando [[Comandi di git#Git add|git add]], vengono messi nella staging area o index di git. 
> [!info]
> per usare un tecnicismo si dice in cash 
  
Questi file/sub-directory non sono state ancora committate ma sono state messe in una zona temporanea la quale serve per mettere insieme questi file ed sub-directory che poi andremo a salvare con la commit.
   Quindi questo è anche il luogo dove Git memorizza la cronologia dei commit:
   con il comando [[Comandi di git#Git commit|`git commit`]] le modifiche dalla staging area vengono salvate nella repository locale. 
2. la seconda area è la Staging Area:
   È un'area temporanea dove prepari le modifiche che desideri includere nel prossimo commit. 
   Quindi questa non è altro che questa zona temporanea nella quale vengono riposti questi file che poi andremo a salvare.  
3. Repository locale o remota (o History):
   La differenza tra la repository locale e/o remota è:
   1) La **repository locale**: 
      è il luogo in cui vengono salvati i commit, ovvero le "istantanee" del progetto nel tempo.
  A questo punto bisogna introdurre anche l'**HEAD:**
  -  ==È un riferimento (reference) all'ultimo commit nel branch corrente.== 
   - ==Possiamo considerarlo un puntatore che, di default, indica sempre l'ultima commit del branch attivo (ad esempio, il branch `main`).==   
   Tuttavia, HEAD può anche puntare direttamente a un commit specifico (detto "detached HEAD"), permettendo di navigare nella cronologia senza essere legati a un branch.  ^head-def

   Con il comando [[Comandi di git#Git commit|`git commit`]], le modifiche dalla Staging Area vengono salvate nella repository locale e HEAD si aggiorna.
   Invece la repository remota è: 
   la copia del tuo progetto su un server remoto, come GitHub. 
   E per inviare le modifiche dalla repository locale a quella remota si utilizza il comando [[Comandi di git#Git Push|`git push`]] 
   
> [!deep] Approfondimento
> - `git checkout main` → HEAD punta all'ultima commit del branch `main`.
>- `git checkout <commit-hash>` → HEAD entra in modalità **detached**, puntando direttamente a quel commit.

   Utilizzi [[Comandi di git#Git Push|`git push`]] per inviare i tuoi commit dalla repository locale a quella remota. 
   
> [!example] Esempio di flusso di lavoro
> 1. Modifica i file nella tua working directory.
> 2. Inizializzazione della repository con `git init`
>1. Aggiungi le modifiche alla staging area con `git add`.
>2. Salva le modifiche nella tua repository locale usando `git commit`.
>3. Invia le modifiche alla repository remota con `git push`.


> [!faq] Cosa si intende per Commit?
> Quando committiamo andiamo a creare una istantanea o "fotografia" dello stato attuale del codice dei nostri file, che volendo, come già detto prima, possiamo riutilizzare in futuro nel caso dovessimo tornare indietro nel caso dovessimo fare delle modifiche.  

> [!info]
>  Ovviamente possiamo sia andare in una direzione che in un altra, cioè posso sia aggiungere dalla working directory dei file all'index sia rimuoverli come posso anche sia commitarli che rimuovere le commit effetuate.

Quindi ==le varie commit effettuate vanno a formare la history del nostro progetto.==  
![[Schema Commit2.png|400]]

## Differenza tra working tree, Index ed Head

Working tree (working directory, workspace):  
è la workspace locale dove vengono posti i file sorgente che posso editare e visualizzare  
L'Index di Git:  
è dove vengono posti i file che vuoi salvare nella repository di Git. Quindi, come visto prima l' index è una staging area dove i file appena aggiunti vengono posti in attesa che venga effettuata la commit.  
HEAD:  
è un riferimento che punta all'ultima commit effettuata nel branch corrente. 

![[Esempio HEAD.png]]
> [!NOTE] 
>  [[Comandi di git#git log|`git log`]]:   
> come si nota dall'immagine il comando `git log` mostra la commit effettuata, il nome dell'autore, la data di quando è stata fatta e il messaggio della commit.  ^gitLog-use



## SHA-1 (Secure Hash Algorithm 1 )
Ogni commit (e altri oggetti) ha un identificatore **univoco** rappresentato da una stringa esadecimale di **40 caratteri**,  serve per generare chiavi univoche che serviranno per evitare che ci siano conflitti fra le varie Commit.  
Questa chiave viene generata prendendo il contenuto dei file su cui noi abbiamo fatto la commit.
Lo SHA-1 è generato in base ai contenuti della commit (messaggio, autore, timestamp, genitore del commit, ecc.)
Per ogni commit ci vengono fornite altre informazioni come l'autore, la data e il testo(cioè il messaggio; titolo e descrizione) che è stato aggiunto alla commit.  
![[Esempio HEAD.png]]

2. `cat .git/HEAD`:  
Questo comando serve per verificare, all'interno del file HEAD stesso, su quale branch è puntato l'HEAD.  
![[Esempio HEAD.png]]  
Possiamo vedere che all'interno del file c'è la referenza a main che a sua volta fa riferimento all'ultimo commit eseguito su questo branch.
Git log accetta varie opzioni tra cui. git log --oneline:  
l'opzioni per compattare il log che viene stampato nella console. Le varie commit vengono visualizzate cronologicamente dal basso verso l'alto in ordine ascendente(dalla prima alla ultima commit effettuata).  
Quindi utilizzando questa opzione visualizzeremo il log un pò più compatto che ci dara comunque le informazioni necessarie (l'id della commit, branch che stiamo utilizzando e titolo della commit). Questo torna utile quando abbiamo tante commit e dobbiamo cercarne una in particolare
3. git log --oneline --reverse:  
cambia l'ordine in cui sono stampati i vari commit, vengono visualizzate cronologicamente dall'alto verso il basso.
4. push:  
carica i commit di Git in una repository remota, come Github



## Facciamo il punto

Una volta aver apportato le modifiche localmente diciamo a git di monitorarle tramite il comando add, dopodichè salvi il/i file tramite il comando commit, infine bisogna caricare questi file in una repository remota (GitHub, Bitbucket, get lab,etc.) e lo si fa tramite il comando push.

5. pull:  
    è l'opposto di push; scarica le modifiche dalla repository remota al host.

Andiamo a vedere nello specifico come applicare questi comandi su Github:  
Prima di tutto bisogna registrarsi al sito, dopodichè si accede al tuo profilo e per creare una repository ci sono 2 modi:

6. cliccare sull'icona del gatto in alto a sinistra che ti porta alla pagina di dashboard → sempre sulla sinistra si trova un pulsante verde con scritto new → cliccandoci sopra ti pota alla pagina per creare una repository.
7. In alto a destra, dopo la navbar, si trova un'icona con il piu → cliccandoci sopra si apre una tendina di pop-up dove la prima voce è "New Repository".

Quindi la repository in sostanza è un progetto che contiene tutti i file e cartelle di codifica di qualsiasi progetto tu stia costruendo.  
una volta creata la repository tutto i file e documenti che sono nel host possono essere spostati nella repository appena creata oppure posso crearli online direttamente sul sito di GitHub.

## Creare file di Markdown su GitHub

Per creare un file di markdown online su git hub bisogna andare sull link "creating new file" che si trova nel riquadro "Quick Setup - if you've done this kind of thing before", proprio sotto questo titolo.  
N.B. Tutta questa operazione la si fa una volta creata la nuova repository, poichè dopo aver cliccato su create nella pagina dedicata per creare una repository, vieni trasferito alla seguente pagina. Una volta creato lo andro a nominare dopodiche posso scriverci sopra (l'intestazione la si richiama con l'hastag).  
Per salvare il file cliccare in alto a destra il tasto "commit new file"→ una volta cliccato apparirà una finestra dove in alto c'è una casella nella quale se non si scrive nulla userà il testo segnaposto per nominare il file.

## Clone, add, commit e push da Visual Studio Code a una Repo Git

### Clone Git File

Tramite questo Code Editor posso accedere a un terminale interno tramite il menù Terminal → New Terminal (Ctrl + shift + ò).  
per clonare ed estrare una repository da github:  
bisogna rimanare sul terminale locale (in questo caso su powershell) → menù file → open folder → dopodiche su terminale ci troveremo scritto (PS C:\Users\user\Documents\Programmazione\Git & GitHub\demo clone>) → digitare git clone → andare su git hub all'interno della repository → andare su code > tab clone e copiare l'indirizzo che trovate → tornate sul terminale di visual studio code → incollate l'indirizzo → premete invio → e cosi il file viene estratto da github sul vostro computer.  

### Git Add

Git Add è il comando che ti permette di aggiungere un file alla repository Git.  
Molte persone scrivino nella riga di commando git add .: il punto in questo caso va a significare che stai dicendo a Git di tenere traccia di tutti i file elencati, ma puoi anche indicargli solo i nomi di ogni singolo file o cartella (es: git add index.html) in questo modo git traccerà solo quel file o directory.

### Git Commit -m

dopo aver fatto il git add dobbiamo salvare i salvattaggi:  
nella riga di commando del terminale scrivere git commit -m; questo ultimo comando è per il messaggio e devi un messaggio per poter committare i tuoi file. Quindi: git commit -m "added index.html file" ad esempio, il messaggio potrebbe contenere anche solo un carattere senza alcun significato, ma deve esserci sempre il messaggio!!! Questo perche indica cosa hai aggiunto e perchè; questo è solo il titolo del messaggio se ci volessi aggiungere una descrizione dovrei aggiungere un ulteriore -m "" e scrivere tra le virgolette una descrizione.
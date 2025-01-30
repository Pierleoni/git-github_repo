
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

## Differenza tra working tree, Index ed Head

Working tree (working directory, workspace):  
è la workspace locale dove vengono posti i file sorgente che posso editare e visualizzare  
L'Index di Git:  
è dove vengono posti i file che vuoi salvare nella repository di Git. Quindi, come visto prima l'index è una staging area dove i file appena aggiunti vengono posti in attesa che venga effettuata la commit.  
HEAD:  
l'HEAD è una reference dell'ultima commit nel branch corrente, possiamo dire che è un puntantore che punta all'ultima commit effettuata nel branch o ramo in cui ci troviamo in questo momento(nel mio caso punta al branch main).

![[Esempio HEAD.png]]

1. git log:  
    Serve per vedere la history list dei commit eseguiti, più altre informazioni(è giusto sapere che git salva ogni commit effettuata all'interno del suo database in un formato chiave-valore dove la chiave è la stringa affianco alla scritta commit).  
    


## Scia 1

lo scia 1 è una stringa lunga 40 caratteri e serve per generare chiavi univoche che serviranno per evitare che ci siano conflitti fra le varie Commit.  
Questa chiave viene generata prendendo il contenuto dei file su cui noi abbiamo fatto la commit

Per ogni commit ci vengono fornite altre informazioni come l'autore, la data e il testo(cioè il messaggio; titolo e descrizione) che è stato aggiunto alla commit.  
![[Esempio HEAD.png]]

22. `cat .git/HEAD`:  
Questo comando serve per verificare, all'interno del file HEAD stesso, su quale branch è puntato l'HEAD.  
![[Esempio HEAD.png]]  
Possiamo vedere che all'interno del file c'è la referenza a main che a sua volta fa riferimento all'ultimo commit eseguito su questo branch.
Git log accetta varie opzioni tra cui23. git log --oneline:  
l'opzioni per compattare il log che viene stampato nella console. Le varie commit vengono visualizzate cronologicamente dal basso verso l'alto in ordine ascendente(dalla prima alla ultima commit effettuata).  
Quindi utilizzando questa opzione visualizzeremo il log un pò più compatto che ci dara comunque le informazioni necessarie (l'id della commit, branch che stiamo utilizzando e titolo della commit). Questo torna utile quando abbiamo tante commit e dobbiamo cercarne una in particolare
24. git log --oneline --reverse:  
cambia l'ordine in cui sono stampati i vari commit, vengono visualizzate cronologicamente dall'alto verso il basso.
25. push:  
carica i commit di Git in una repository remota, come Github

![](/Media/Photo/puntoesclamativo.jpg)

## Facciamo il punto

Una volta aver apportato le modifiche localmente diciamo a git di monitorarle tramite il comando add, dopodichè salvi il/i file tramite il comando commit, infine bisogna caricare questi file in una repository remota (GitHub, Bitbucket, get lab,etc.) e lo si fa tramite il comando push.

27. pull:  
    è l'opposto di push; scarica le modifiche dalla repository remota al host.

Andiamo a vedere nello specifico come applicare questi comandi su Github:  
Prima di tutto bisogna registrarsi al sito, dopodichè si accede al tuo profilo e per creare una repository ci sono 2 modi:

1. cliccare sull'icona del gatto in alto a sinistra che ti porta alla pagina di dashboard → sempre sulla sinistra si trova un pulsante verde con scritto new → cliccandoci sopra ti pota alla pagina per creare una repository.
2. In alto a destra, dopo la navbar, si trova un'icona con il piu → cliccandoci sopra si apre una tendina di pop-up dove la prima voce è "New Repository".

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
Git Comands

Andiamo a spiegare i vari comandi di Git che digiteremo nel terminale o nella riga di comando del computer.  

> [!NOTE] N.B.
> Tutti questi comandi vanno scritti in minuscolo e non maiuscolo.

### Creare una directory 
Per creare una repository per git in locale ci sono 2 modi:
- tasto destro del mouse → nuova cartella (o ctrl+ shift+N)
- oppure tramite il terminale di git ( per aprirlo tasto destro del mouse → git bash) → digitare, sulla riga di comando del terminale, `mkdir + il nome della directory` che si vuole creare.
### Git Help
 - `git help`:   
   è il comando che stampa le informazioni di Git Help. 
   Fornisce un rapido riferimento a l'uso di base di Git e i comandi Git più comunemente usati. Questo commando è utile quando si ha la necessita di visualizzare un reminder veloce delle funzionalità di Git o si vuole esplorare i comandi disponibili.    
 ^a117ab
- `git help <command>`: 
  per visualizzare le informazioni di help per un comando specifico di git 
```bash
git help commit
```
in questo caso farà visualizzare nel browser le info per il comando di commit in modo dettagliato.
- `git help -a`:
  elenca tutti i comandi disponibili nel terminale di git 
- `git help -g`:
   mostra le categorie di aiuto disponibili


> [!bug] 
> se provassi a visualizzare le info di un comando che non è di git, come ad esempio `cd`: 
>```bash
> git help cd
> fatal: 'C:/Program Files/Git/mingw64/share/doc/git-doc/gitcd.html': documentation file not found.
>```
>Mi da messaggio di errore perché questo comando non è nativo di Git ma è un comando della shell.
>
>> [!info] Info sui comandi di shell 
> >Per avere info sui comandi di shell, come ad esempio `cd`, scrivere sul prompt dei comandi:  ^cd-command
>>```shell
> >cd /?
>>```

### Git Version
`git version` è un comando che fa visualizzare la versione di git installata sul tuo sistema. Questo comando è utile per verificare quale versione di Git si sta usando, il che può essere importante per la compatibilità con certe caratteristiche o quando ci sono problemi da risolvere. 


> [!faq] `git version` o `git --version`, [[#^a117ab|`git help`]] o `git --help`?
> I comandi `git version`, `git --version`, `git help` e `git --help` sono tutti comandi utilizzati per interagire con Git, ma hanno scopi diversi:
>
>1. **`git version`**: Questo comando mostra la versione di Git installata sul tuo sistema. È un modo per verificare rapidamente quale versione di Git stai utilizzando.
 >   
>2. **`git --version`**: Questo comando ha lo stesso effetto di `git version`. Entrambi i comandi restituiscono la versione di Git installata. La differenza principale è che `--version` è una forma più standardizzata di specificare le opzioni nei comandi di Git.
 >   
>3. **`git help`**: Questo comando apre la pagina di aiuto di Git, mostrando un elenco di comandi e opzioni disponibili. È utile per ottenere informazioni generali su come utilizzare Git.
>    
>4. **`git --help`**: Anche questo comando apre la pagina di aiuto di Git, proprio come `git help`. La differenza è che `--help` è un'opzione standard che può essere utilizzata con molti comandi per ottenere informazioni dettagliate su di essi.
 >  
>In sintesi, `git version` e `git --version` sono equivalenti e mostrano la versione di Git, mentre `git help` e `git --help` sono equivalenti e forniscono accesso alla documentazione di Git.

### Il comando di list (`ls`)
Questo comando è utilizzato nei sistemi operativi Unix e Unix-like (come Linux e macOS) per elencare i file e le directory presenti nella directory corrente. È uno dei comandi fondamentali della shell e viene comunemente utilizzato per visualizzare il contenuto di una directory.
#### funzionamento 
Quando esegui `ls` nella riga di comando, il sistema restituisce un elenco dei file e delle directory nella directory in cui ti trovi attualmente. 
Si possono anche utilizzare diverse opzioni per modificare il modo in cui i risultati vengono visualizzati, come ad esempio:
- `ls`: 
  Elenca i file e le directory
- `ls -l`: 
  Elenca i file con dettagli (permessi, dimensioni, date, ecc.)
- `ls -a`:  
  È il comando che mostra la lista dei file nascosti  dentro le directory (Es: `.git`). 
- `ls - la`: 
  Elenca i file con dettagli e include i file nascosti 
- `ls -S`: 
  Elenca i file in ordine di dimensione
- `ls -lt`: 
  Elenca i file in ordine di data di modifica

> [!Important]  Opzioni comuni di `ls`
> - `-l`: 
>   Mostra i dettagli dei file in un formato lungo.
>- `-a`: 
>  Mostra tutti i file, inclusi quelli nascosti.
>- `-h`: 
>  Mostra le dimensioni dei file in un formato leggibile (es. KB, MB).
>- `-t`: 
>  Ordina i file per data di modifica.
>- `-S`: 
>  Ordina i file per dimensione.


> [!caution] Attenzione!
> Anche `ls`, come [[#^cd-command|`cd`]], è un comando non nativo di Bash, quindi se si cerca di avere maggiori info su di esso git bash restituirà  errore, esattamente come per il comando `cd`. 
>
>> [!info] Per avere le info sui comandi Unix su Git Bash
>>```bash
> > man ls
>>```
>>Siccome il comando `man` non è sempre disponibile si può anche scrivere:
>>``` bash
>>ls --help
>>```

### Il comando `clear`
Il comando `clear` in Git Bash (e in generale nei terminali Unix/Linux) viene utilizzato per pulire o svuotare lo schermo della console. 
Quando esegui `clear`, il terminale rimuove tutto il testo precedentemente visualizzato, fornendoti una schermata pulita e ordinata.
Dopo aver scritto questo comando, basta premere invio e il contenuto precedente della console scompare, lasciando solo il prompt dei comandi

> [!done] Vantaggi di `clear`
> - **Organizzazione**: 
>   Aiuta a mantenere il terminale ordinato, specialmente dopo aver eseguito molti comandi e visualizzato molte informazioni.
>- **Focalizzazione**: 
>  Ti consente di concentrarti su un nuovo comando o output senza distrazioni.

> [!hint] 
> In alternativa, puoi anche utilizzare la combinazione di tasti `Ctrl + L` per ottenere lo stesso effetto di `clear` in molti terminali, incluso Git Bash. Questo è un modo rapido per pulire lo schermo senza dover digitare il comando.


> [!info] Il comando `clear` non refresha la RAM
> Il comando `clear` non cancella i comandi precedentemente digitati dalla RAM o dalla cronologia del terminale. Invece, `clear` semplicemente pulisce lo schermo della console, rimuovendo il testo visibile dalla vista.
>
>Quindi riassumendo
>
>- **Pulizia dello schermo**: Rimuove il contenuto visualizzato nel terminale, ma non elimina i comandi dalla cronologia.
>- **Cronologia dei comandi**: I comandi che hai digitato in precedenza rimangono memorizzati nella cronologia del terminale. Puoi accedervi utilizzando le frecce su e giù sulla tastiera per navigare tra i comandi precedenti.
>
>Accesso alla cronologia
>
>Puoi visualizzare i comandi precedenti anche dopo aver utilizzato `clear`. Ad esempio, se hai digitato diversi comandi e poi esegui `clear`, puoi comunque utilizzare le frecce per scorrere i comandi precedenti. Inoltre, puoi digitare `history` per visualizzare un elenco di tutti i comandi che hai eseguito nella sessione corrente.

#### In sintesi

Il comando `clear` è utile per avere uno schermo pulito, ma non influisce sulla cronologia dei comandi. Se desideri cancellare la cronologia dei comandi, dovresti utilizzare comandi specifici per farlo, come `history -c` in alcune shell, ma questo è un'operazione separata.

### Git init
Questo comando inizializza una nuova repository di Git nella directory corrente, creando una nuova sub-directory nominata `.git`:  
questa sub-directory contiene tutti i metadata necessari per le nuove repository.  ^d4295a

> [!info] Abilitare la visualizzazione delle cartelle nascoste
> Se abbiamo la visualizzazione dei file e cartelle nascosti non abilita non visualizzeremo neanche questa directory, per abilitare questa funzione aprire il media explore → tab visualizza → sezione mostra/nascondi → spuntare la casella "elementi nascosti".

Questo è il primo comando da far correre quando si inizia un nuovo progetto che si vuole gestire con Git. 
Dopo aver fatto correre questo comando, si può iniziare a tracciare i file e rendere le commit in una nuova repository di Git. 


### Git Clone 
Questo comando crea una copia della repository remota di Git sulla macchina locale. 
Scarica tutti i file, i branches e la cronologia della commit, permettendo così di iniziare a lavorare con il progetto in modo immediato.  
Quindi è molto utile quando si desidera lavorare su un progetto già esistente.
`git clone <repository-url> <folder-name>`: 
questa è la sintassi di base del comando, per fare un esempio se si volesse clonare una repository una repository da GitHub: 
```bash
git clone https://github.com/username/repository.git
```
Questo comando creerà una nuova directory chiamata `repository` (o il nome del repository se non specificato diversamente) nella tua directory corrente, contenente tutti i file e la cronologia del repository.


Anche per questo comando ci sono diverse Opzioni, le più comuni sono: 
- `bashgit clone https://github.com/username/repository.git my-directory`:
  Avendo messo  il nome della directory di destinazione clonerà il repository nella directory `my-directory`.
  
- `git clone --branch` (o `b`):
  Se desideri clonare solo un branch specifico.
- `git clone --depth <numero> <repository-URL>`:
  Clona in modo "shallow", ovvero clona solo l'ultima versione del repository senza la cronologia completa. 
  Il numero da inserire è opzionale: 
```bash
git clone --depth 1 https://github.com/username/repository.git
```
In questo caso si indica a Git di clonare una repository con solo l'ultimo commit effettuato. 


## La cartella .git
Una volta creata la cartella `.git` , andiamo a studiarla da vicino:
[[#^d4295a|come già detto poco sopra ]]In questa cartella è contenuto tutta la history dei nostri salvataggi effettuati durante lo sviluppo del progetto, se mai volessimo ripartire da zero basta solo cancellare la cartella .git 

> [!NOTE] N.B.
>  Rara procedura, meglio evitare perché così facendo si cancellano tutte le commit effettuate, le informazioni sui branch, i tag associati a versioni specifiche e le impostazioni di configurazione della repository. Inoltre può portare a confusione e conflitti se si lavora in team. 
>  Quindi è meglio evitare a meno che non si sia sicuri di quello che si sta facendo, in ogni caso è consigliato di fare un backup prima di procedere.

Se apriamo questa directory possiamo notare come al suo interno si trovino delle sub-directory e dei file, tutto questo serve a git per creare la time-line con tutti i vari salvataggi
### Comandi per creare file e scrivere del testo
1.  `touch + "nome file".txt`:  
   Il comando `touch` viene utilizzato per creare un file vuoto con il nome  specificato. Se il file esiste già, `touch` aggiorna la data e l'ora dell'ultima modifica.
2. `echo + le parole che voglio aggiungere > "nome file".txt`:  
   Il comando `echo` stampa il testo specificato. L'operatore `>` reindirizza l'output di `echo` in un file. Se il file esiste già, verrà sovrascritto; se non esiste, verrà creato.
1. `cat +"nomefile".txt` :  
   Il comando `cat` (concatenate) viene utilizzato per visualizzare il contenuto di uno o più file. Mostra il contenuto del file specificato nel terminale
A questo punto abbiamo creato un file e aggiunto del contenuto, ma Git non è ancora a conoscenza di questo file nella working directory. Per verificarlo, possiamo utilizzare il comando `git status`.
### Git Status
questo commando serve per mostrare l'attuale  stato corrente della directory di lavoro del repository Git e la staging Area. 
Visualizza le informazioni su quali file sono stati modificati, aggiunti o cancellati e se tali modifiche sono in stage per la prossima commit
![[Git Status.png]]
  
Esaminando questa foto possiamo vedere che ci troviamo nel branch master, non sono stati ancora aggiunti commits ed il file in rosso vuole dire non è stato ancora aggiunto allo staging o all'index di Git. Inoltre nelle ultime due righe di commando ci dice pure come aggiungere questo file all'index di Git tramite al commando git add.13. git add: traccia i tuoi file e li cambia in Git.  
    Questo comando è utile per quando devi cancellare i file localmente e vuoi che anche Git tracci queste modifiche.  
    Se scriviamo git add .; il punto siginifica che vogliamo aggiungere tutti i file indiscriminatamente.  
    Se voglio invece aggiungere solo alcuni file o un file specifico devo scrivere solo il/i nome/i del/i file.  
    Se voglio aggiungere un set di file (ad esempio solo i file .txt) devo scrivere *.txt/*.CSS/etc.; l'asterisco sta ad indicare che vado ad aggiungere qualsiasi file con quella estensione.  
    ![[Git Add.png]]
Come possiamo notare dall'immagine ora il file è colorato di verde e mi conferma che è stato aggiunto all'index di Git, ma non è stato ancora effettuato nessun commit e mi da una indicazione che mi dice che ci sono alcuni cambiamenti che possono essere commitati.14. git commit:  
    Salva i tuoi file in Git(difatti si dice commit changes).  
    Se si usa il commando Git commit senza digitare nient'altro si apre l'editor impostato di default dal nostro sistema operativo all'interno della Shell (a seconda del sistema operativo può essere VIM o Vema).  
    N.B. è possibile impostare un altro editor di default, per usare l'editor di default bisogna usare i comandi da tastiera



## Commandi da tastiera per l'editor di default

i: per aggiungere del testo per descrivere la nostra commit.  
Il testo verra inserito nella riga in alto, e tutto questo testo che è preceduto prima del cancelletto si chiama "commento" e non verrà considerato da Git.  
![[command i.png]]  
Una volta inserito il commento andiamo a premere il tasto esc:  
ci fa uscire dalla modalità scrittura.  
dopodichè digitiamo i tasti :wq, per semplificarci la vita sul terminale bash accanto al commando git commit mettiamo lo spazio e digitiamo -m "" e tra le virgolette mettiamo il commento che vogliamo aggiungere.

Il testo che mettiamo tra viroglette è obbligatorio, inoltre se fosse la nostra prima commit può anche andare bene scrivere "first commit" mentre dalle commit successive e bene indicare con più precisione lo scopo di quella commit. Questo va fatto anche nell'ottica che se dovessi mai andare a ricecare nella repository le varie commit antecedenti mi sarà più facile ritrovare quella/e che mi servono risparmiando tempo e senza fare troppa fatica. Per fare ciò potrei pensare di utilizzare la seconda parte del messaggio che diventerà la mia descrizione.  
N.B. committate abbastanza spesso, ma senza svilluppare un DOC per la commit, tuttavia più commit si fanno più ci è facile tornare indietro nel tempo in punti più precisi poichè l'ideale sarebbe avere più salvattaggi per andare avanti o indietro fra i vari commit.  
Se dopo la commit digitassimo git status potremmo vedere che la nostra directory è sgombra, non c'è nulla da aggiungere, e non ci sono commit da eseguire.


## La working directory e la staging Area 

![[Schema commit.png|400]]  
Seguendo questo schema, partendo dal basso verso l'alto, cercheremo di capire meglio il meccanismo di quello che abbiamo fatto fino ad adesso:
immaginiamo la struttura di Git suddivisa in 3 aree di lavoro:

1. La prima area èla working directory:
   È la cartella locale dove si hanno i file del progetto, qui si apportano le modifiche ai file.
   Quindi nella working directory  sono contenuti i nostri file/sub-directory che, tramite il comando [[#Git add|git add]], vengono messi 

> [!info]
> per usare un tecnicismo si dice in cash 

   nella staging area o index di git. 
   Questi file/sub-directory non sono state ancora committate ma sono state messe in una zona temporanea la quale serve per mettere insieme questi file ed sub-directory che poi andremo a salvare con la commit.
   Quindi questo è anche il luogo dove Git memorizza la cronologia dei commit:
   con il comando [[`git commit`]] le modifiche dalla staging area vengono slavate nella repository locale. 
2. la seconda area è la Staging Area:
   È un'area temporanea dove prepari le modifiche che desideri includere nel prossimo commit. 
   Quindi questa non è altro che questa zona temporanea nella quale vengono riposti questi file che poi andremo a salvare.  
3. Repository remota (o History):
   la copia del tuo progetto su un server remoto, come GitHub. 
   Utilizzi [[`git push`]] per inviare i tuoi commit dalla repository locale a quella remota. 
   
> [!example] Esempio di flusso di lavoro
> 1. Modifica i file nella tua working directory.
> 2. Inizializzazione della repository con `git init`
>3. Aggiungi le modifiche alla staging area con `git add`.
>4. Salva le modifiche nella tua repository locale usando `git commit`.
>5. Invia le modifiche alla repository remota con `git push`.


> [!faq] Cosa si intende per Commit?
> Quando committiamo andiamo a creare una istantanea o "fotografia" dello stato attuale del codice dei nostri file, che volendo, come già detto prima, possiamo riutilizzare in futuro nel caso dovessimo tornare indietro nel caso dovessimo fare delle modifiche.  

> [!info]
>  Ovviamente possiamo sia andare in una direzione che in un altra, cioè posso sia aggiungere dalla working directory dei file all'index sia rimuoverli come posso anche sia commitarli che rimuovere le commit effetuate.

Quindi ==le varie commit effettuate vanno a formare la history del nostro progetto.==  
![[Schema Commit2.png|400]]


### Git add
Il comando `git add` è utilizzato per aggiungere modifiche alla staging area (o index) in Git. Questo è un passaggio fondamentale nel flusso di lavoro di Git, poiché consente di preparare i file che desideri includere nel prossimo commit.
#### Opzioni comuni del comando `git add`
la sintassi di base è:
```bash
git add <file>
```
Detto ciò ci sono vari esempi di utilizzo che si possono fare per il `git add`:
1. `git add nomefile.txt`:
   Aggiungo un file specifico, in questo caso è un file di testo ma posso aggiungere qualsiasi file con qualsiasi estensione. Questo è un modo più specifico per aggiungere i file alla staging area 
2. `git add .`:
   Aggiungo tutti i file modificati, nuovi file e file eliminati presenti nella mia working directory e nelle sottodirectory. 
3. `git add *.estensione-file`: 
   Aggiunge file specifici per il tipo di estensione
4. `git add -u`: 
   Aggiunge file eliminati, se si ha eliminato alcuni file e si vuole riflettere queste eliminazioni si usa questo comando. 
   Quindi Questo comando aggiorna la staging area per includere le modifiche ai file già tracciati (inclusi i file eliminati).
   5. `git add -p`(o `git add --patch`): 
   Consente di mettere in stage in modo interattivo e selettivo le modifiche dalla tua directory di lavoro suddividendole in blocchi (hunks), che consentono di rivedere e aggiungere selettivamente parti delle modifiche all'indice prima di committarli.
6. `git add -i`:
   Inserisce la modalità interattiva di aggiunta dei file. 
   Fornisce un menu interattivo basato sul testo in cui è possibile selezionare varie azioni da eseguire, come la messa in scena di singole modifiche, l'aggiornamento dei file o visualizzare lo stato.

Ora che sappiamo come creare dei file, aggiungerli all' index e commitarli andiamo a vedere come fare i passaggi inversi:
19. `git --rm cached "nome"`:  
    questo commando rimuove la copia del file dall'Index/Staging Area ripotandola nella working directory, senza toccare però la copia della working tree.  
    Di conseguenza nella nuova commit effettuata mancherà il file indicato in questo commando; quindi se nella commit corrente il file è presente, nella nuova commit mancherà quel determinato file.
20. `git restore --staged + "nome file"`:  
    questo comando copia il file dal HEAD commitati dentro l'indice, senza toccare la copia del working tree.  
    La copia dell' index e quella del HEAD sono matchiate indipendentemente dal fatto se erano accoppiati prima. Quindi una nuova commit effettuata avrà la stessa copia del file cosi come c'è l'aveva la commit corrente  

> [!info] N.B.
>  Questo commando viene spesso confuso con il commando git rm --cached perchè ==_nel caso in cui nella commit corrente manchi il file, esso avrà l'effetto di rimuovere il file dall'index._== Quindi in questo caso funzionerà come git rm --cached  

## Git Comands

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

```bash
git init
```

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
  
Esaminando questa foto possiamo vedere che ci troviamo nel branch master, non sono stati ancora aggiunti commits ed il file in rosso vuole dire non è stato ancora aggiunto allo staging o all'index di Git. Inoltre nelle ultime due righe di commando ci dice pure come aggiungere questo file all'index di Git tramite al commando git add.  
![[Git Add.png]]
Come possiamo notare dall'immagine ora il file è colorato di verde e mi conferma che è stato aggiunto all'index di Git, ma non è stato ancora effettuato nessun commit e mi da una indicazione che mi dice che ci sono alcuni cambiamenti che possono essere commitati.14. git commit:  
    Salva i tuoi file in Git(difatti si dice commit changes).  
    Se si usa il commando Git commit senza digitare nient'altro si apre l'editor impostato di default dal nostro sistema operativo all'interno della Shell (a seconda del sistema operativo può essere VIM o Vema).  
    N.B. è possibile impostare un altro editor di default, per usare l'editor di default bisogna usare i comandi da tastiera


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

### Git commit
Il comando `git commit` è uno dei comandi fondamentali di Git e viene utilizzato per registrare le modifiche apportate ai file nel tuo repository locale. Quando esegui un commit, stai creando una "istantanea" del tuo progetto in un determinato momento, che può essere successivamente recuperata o confrontata con altre versioni.
#### Sintassi di base 
```bash
git commit -m "Messaggio del commit"
```

#### Opzioni comuni
- `-m"messaggio"`:
  Specifica un messaggio di commit in linea. 
  È importante fornire un messaggio chiaro e descrittivo che spieghi le modifiche apportate.
Il testo che mettiamo tra virgolette è obbligatorio, inoltre se fosse la nostra prima commit può anche andare bene scrivere "first commit" mentre dalle commit successive e bene indicare con più precisione lo scopo di quella commit. Questo va fatto anche nell'ottica che se dovessi mai andare a ricercare nella repository le varie commit antecedenti mi sarà più facile ritrovare quella/e che mi servono risparmiando tempo e senza fare troppa fatica. Per fare ciò potrei pensare di utilizzare la seconda parte del messaggio che diventerà la mia descrizione.  
> [!info] N.B.
>  È consigliato committare abbastanza spesso, ma senza sviluppare un D.O.C. per la commit, tuttavia più commit si fanno più ci è facile tornare indietro nel tempo in punti più precisi poichè l'ideale sarebbe avere più salvataggi per andare avanti o indietro fra i vari commit.  
> Se dopo la commit digitassimo `git status` potremmo vedere che la nostra directory è sgombra, non c'è nulla da aggiungere, e non ci sono commit da eseguire.

- `-a`: 
  Aggiunge automaticamente tutti i file tracciati che sono stati modificati al commit. Non include i file non tracciati.
```bash
  git commit -a -m "Messaggio del commit"
```

- `--amend`: 
  Modifica l'ultimo commit. Torna utile utilizzare questa opzione se desideri aggiungere modifiche all'ultimo commit invece di crearne uno nuovo.
```bash
  git commit --amend -m "Nuovo messaggio del commit"
```

- `--no-edit`: 
  Utilizzato con `--amend`, mantiene il messaggio di commit originale senza modificarlo.
  
```bash
 git commit --amend --no-edit 
```

#### Importanza del Messaggio di Commit

È buona pratica scrivere messaggi di commit chiari e significativi. Un buon messaggio di commit aiuta te e gli altri membri del team a comprendere le modifiche apportate nel tempo. Un messaggio di commit dovrebbe rispondere a domande come:

- Cosa è stato cambiato?
- Perché è stato cambiato?
- Qual è l'impatto di queste modifiche?

### [[Git & Git Hub#^gitLog-use|Git log ]] 
==Il comando `git log` è utilizzato per visualizzare la cronologia dei commit nel tuo repository Git.== 
Permette di vedere un elenco di tutti i commit effettuati, insieme a informazioni dettagliate su ciascun commit, come l'autore, la data e il messaggio di commit. 
È uno strumento fondamentale per comprendere la storia del tuo progetto e per tracciare le modifiche nel tempo. 
 
#### Sintassi di base
```bash
git log
```

#### Opzioni comuni 
- `oneline`: 
  Mostra ogni commit su una sola riga, visualizzando solo l'ID del commit abbreviato e il messaggio di commit.
```bash
  git log --oneline
```

- `--graph`: 
  Mostra un grafico ASCII della cronologia dei commit, utile per visualizzare i branch e le fusioni.
```bash
 git log --graph 
```

- `--decorate`: 
  Mostra i riferimenti (come i nomi dei branch e dei tag) accanto ai commit.
```bash
git log --decorate
```

> [!info] Combinazione di opzioni
> Puoi combinare le opzioni per ottenere una visualizzazione più informativa.
>```bash
> git log --oneline --graph --decorate
>```

- **`-n <numero>`**: 
  Limita il numero di commit visualizzati. 
  Ad esempio, per vedere solo gli ultimi 5 commit:
```bash
git log -n 5 
```

- **`--author=<nome>`**: 
  Filtra i commit per autore. 
  Ad esempio, per vedere solo i commit di un autore specifico:
```bash
git log --author="Nome Autore"
```

- **`--since` e `--until`**: 
  Filtra i commit in base a date specifiche. 
  Ad esempio, per vedere i commit effettuati dopo una certa data fino ad un'altra data:
```bash
git log --since="2023-01-01" --until="2023-12-31"
```

- **`--grep=<pattern>`**: 
  Filtra i commit in base a un pattern nel messaggio di commit. 
  Ad esempio, per trovare commit che contengono la parola "bug":
```bash
git log --grep="bug"
```

Grazie a questo comando quindi è possibile esplorare la cronologia dei commit nel tuo repository e utilizzando le varie opzioni disponibili, puoi personalizzare la visualizzazione della cronologia per ottenere le informazioni di cui hai bisogno in modo chiaro e conciso.

### Git Push
Il comando `git push` è utilizzato per inviare le modifiche locali (commits) dalla repository locale a un repository remoto, come GitHub, GitLab o Bitbucket. Questo comando è fondamentale per condividere il tuo lavoro con altri membri del team o per mantenere una copia aggiornata del tuo progetto su un server remoto.

#### Sintassi di base
```bash
git push <remote> <branch>
```

- **`<remote>`**: 
  Il nome del repository remoto. 
> [!NOTE] Di solito, il nome predefinito è `origin`
 
- **`<branch>`**: 
  Il nome del branch che desideri inviare. 
> [!NOTE] Di solito, il nome predefiniti è `main` o `master`

### Esempi di utilizzo 
1. `git push origin main`: 
   invia il branch `main` al Remote `origin` 
```bash
git push origin main
```

2. `git push --all origin`: 
   Invia tutti i branch locali al repository remoto.
```bash
git push --all origin
```
3. `git push --tags`: 
   Invia i tag al repository remoto
```bash
 git push --tags  
```

4. `git push --force origin main`: 
   Forza un Push. 
   Utile quando hai bisogno di sovrascrivere il branch remoto con le modifiche locali.
> [!Attention] questo può causare la perdita di dati nel repository remoto

```bash
git push --force origin main
```

5. `git push -u origin nome-del-nuovo-branch`:
   Push di un Nuovo Branch. 
   Utile quando si crea un nuovo branch e si desidera inviarlo al repository remoto.
```bash
git push -u origin nome-del-nuovo-branch 
```

L'opzione `-u` (o `--set-upstream`) imposta il branch remoto come upstream per il branch locale, facilitando i futuri push e pull.


> [!faq] Errori comuni 
> - **Rejection**: Se ricevi un messaggio di errore che indica che il push è stato rifiutato, potrebbe essere necessario eseguire un `git pull` per integrare le modifiche remote nel tuo branch locale prima di poter eseguire il push.
   > 
>- **Conflitti**: Se ci sono conflitti tra le modifiche locali e quelle remote, dovrai risolverli prima di poter eseguire il push.

Questi appena elencati sono la serie di comandi base per [[Comandi di git#Git init|inizializzare]], [[#Git add|aggiungere]], [[Comandi di git#Git commit|committare]] e [[Comandi di git#Git Push|pushare]] una repository locale e inviare i file alla repository remota. 
Ora che sappiamo come creare dei file, aggiungerli all' index e commitarli andiamo a vedere come fare i passaggi inversi
### Rimuovere i file dalla Staging Area 
Per fare un esempio, mettiamo che abbia aggiunto un file e/o una directory alla staging area e mi accorgo che quel file o directory non andava aggiunto, posso rimuoverli tramite i comandi 
 1. `git --rm cached "nome"`:  
	questo commando rimuove la copia del file dall'Index/Staging Area riportandola nella working directory, senza toccare però la copia della working tree.  
	Di conseguenza nella nuova commit effettuata mancherà il file indicato in questo commando; quindi se nella commit corrente il file è presente, nella nuova commit mancherà quel determinato file.
 2. `git restore --staged + "nome file"`:  
	questo comando copia il file dal HEAD committati dentro l'indice, senza toccare la copia del working tree.  
	La copia dell' index e quella del HEAD sono matchiate indipendentemente dal fatto se erano accoppiati prima. Quindi una nuova commit effettuata avrà la stessa copia del file cosi come c'è l'aveva la commit corrente  

> [!info] N.B.
>  Questo commando viene spesso confuso con il commando git rm --cached perchè ==_nel caso in cui nella commit corrente manchi il file, esso avrà l'effetto di rimuovere il file dall'index._== Quindi in questo caso funzionerà come git rm --cached  

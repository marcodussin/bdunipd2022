Benvenuti nella lezione di prerequisito del laboratorio del corso di Basi di Dati 2022

In questa lezione cercherò di darvi tutti i prerequisiti necessari per poter partecipare al laboratorio usando il 
vostro pc.

# Installazione di MySQL
1. Prima di tutto è necessario che installiate (nel caso non lo abbiate già fatto) MySQL nel vostro computer. È
   necessario avere un computer (con sistema operativo Windows, MacOS o Linux), un tablet o un cellulare non sono 
   supportati. Se questo è un problema, vi chiedo di comunicarmelo prima possibile.

2. Trovate il pacchetto di installazione di MySQL adatto al vostro sistema operativo al link https://dev.mysql.com/downloads/mysql/ 

3. Qui trovate alcuni video (con un simpatico accento) che vi possono aiutare nell'installazione 

- Setup in Windows https://www.youtube.com/watch?v=OM4aZJW_Ojs
- Setup in MacOS https://www.youtube.com/watch?v=-BDbOOY9jsc e https://www.youtube.com/watch?v=NflJqdqNN-Q
  e qui un tutorial per Windows https://www.onlinetutorialspoint.com/mysql/install-mysql-on-windows-10-step-by-step.html

  CONSIGLIO: scegliete un nome utente e una password facili da ricordare!

4. Guardatevi il video che ho caricato su Moodle e che vi mostra come testare se la vostra installazione funziona

5. Consigliato: installate un editor di testo migliore di blocco note. Se non ne avete uno già installato vi 
   consiglio Sublime Text https://www.sublimetext.com/3



Una dritta per gli utenti Mac 🍏 che hanno visto il video qui sopra: nelle ultime versione del sistema operativo (da Big Sur in poi) potreste aver selezionato una linea di comando diversa da  `bash`  di nome  `zsh`. Per non complicarvi la vita, il suggerimento è di creare due files nella vostra home, uno è `.bash_profile`  come suggerito nel video, l'altro è  `.zshrc` .
Andiamo per ordine: prima di crearli verificate se li avete già: lo potete fare digitando `ls -a ~` da riga di comando. Se nei risultati appaiono questi due files non dovete crearli, altrimenti la procedura è lanciare da linea di comando, uno per uno, questi comandi:

```bash
touch ~/.bash_profile 
open ~/.bash_profile
touch ~/.zshrc
open ~/.zshrc
```

Se ci scrivete dentro (o aggiungete se è già scritto)
```bash
PATH="/usr/local/mysql/bin:${PATH}"
export PATH
```
poi potrete lanciare (dopo aver fatto log out ed essere ri-entrati) il comando mysql da riga di comando senza  dovere ogni volta ripercorrere tutto il percorso per raggiungerlo in `/usr/local/mysql/bin`

👉 Se tutta questa procedura vi sembra assurda, fatevi aiutare da un collega che magari è più pratico, o comunque potrete lanciare MySQL scivendo in terminale.

```bash
cd /usr/local/mysql/bin
mysql -u nomeutente -p
```

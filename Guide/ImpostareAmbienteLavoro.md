# Ambiente di sviluppo

## Preparazione

1.  Creare un account su [*https://github.com/*](https://github.com/)

1.  Installare Git
    [*http://git-scm.com/download/win*](http://git-scm.com/download/win)

1.  Configurare il file di impostazioni git ```<users>\<user>\.gitconfig```
    nella maniera seguente:

    ```markdown

    [user]
      name = nome cognome
      email = nome.cognome@samtrevano.ch

    [core]
      autocrlf = true
      excludesfile = C:\Users\samt\Documents\gitignore_global.txt

    [filter "lfs"]
      clean = git-lfs clean %f
      smudge = git-lfs smudge %f
      required = true

    [http]
      proxy = http://nome.cognome:proxypass@proxy:8080

    [https]
      proxy = https://nome.cognome:proxypass@proxy:8080
      ```

1. Installare source Tree da questo sito
    [*https://www.sourcetreeapp.com/*](https://www.sourcetreeapp.com/)

1.  Impostare il Git di sistema per SourceTree.

    ![Settings](../Documentazione/img/ST_img1.png)

1.  Completata l’istallazione mettendo le credenziali dell’account github
    creato in precedenza

1.  Dopo l’accettazione dei termini di utilizzo l’installazione sarà
    completata

1.  Aprire source Tree. Nelle impostazioni mettere l’url del progetto:
    [*https://github.com/LuMug/iSete.git*](https://github.com/LuMug/iSete.git)

1.  In seguito inserire il percorso della cartella locale nella quale sincronizzare il repository

     > **Non cambiare il percorso della cartella, se la cartella è già creata allora andrà a fare riferimento a quella cartella, altrimenti la creerà lui**

1. Sempre in impostazioni inserire le credenziali (nome e email) per
    mostrare chi modifica cosa.

A questo punto nella vostra cartella locale dovreste poter vedere i file
che sono stati messi sul server. Potrete modificarli ma non potrete uplodare finchè il proprietario del repository non vi concede il permesso di ```push```.


## Creazione documenti
Installare Atom: [*https://atom.io/*](https://atom.io/)

Installare PanDoc: [*http://pandoc.org/*](http://pandoc.org/)

Installare MikTex [*http://miktex.org/download*](http://miktex.org/download)



Per creare il pdf da un md:

```markdown
pandoc source.md -s -o dest.pdf --highlight-style=tango
```
Al momento della conversione dovranno essere scaricati alcuni pacchetti. Selezionare la modalita via internet e configurare il proxy.

Trasformare un docx in markdown:

```markdown
pandoc test1.docx -f docx -t markdown -s -o test1.md
```


## Uso di Git

Il seguente schema mostra il funzionamento di massima di Git.

![Git LifeCycle](../Documentazione/img/git-workflow.png)

### Da linea di comando

Da una qualsiasi shell spostarsi nella cartella nella quale volete
lavorare.

|Comando  |Descrizione          |
|---------                      |------------------------------------|
|```git clone [remote repository]```  |Crea una copia locale del repository|
|```git pull     ```                  |Aggiorna completamente il repository locale e la working copy|
|```git fetch ```                     |Aggiorna il repo sitory locale|
|```git merge                  ```    |Aggiorna la working copy con le modifiche locali|
|```git add *                  ```    |Permette di decidere quali file (tutti) aggiungere al repository locale|
|```git commit -m "Messaggio"  ```    |Porta le modifiche al repository locale con un'etichetta|
|```git push -u origin master   ```   |Apporta le modifiche al repository remoto|

Per modificare il metodo di push:

```markdown
git config --global push.default matching
git config --global push.default simple
```

### SourceTree
Quando modificherete un file, source tree vi farà notare il file che
avete modificato ma non lo caricherà in remoto. Per fare ciò bisogna selezionare i
file che si vogliono caricare, selezionare il check che vi è sotto ( invia
immediatamente la commissione a origin/master) e premere ~~invia~~ commit.

> Prima di modificare un file ricordarsi di premere commit per avere le
eventuali modifiche che sono state fatte dagli altri ma che voi non
avete in locale

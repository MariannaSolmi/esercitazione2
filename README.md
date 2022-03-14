# esercitazione2
1) Rinominare un file della propria HOME directory
cat <paperino >paperino1
2)  Spostare uno dei file della propria HOME directory in una sottodirectory precedentemente creata
  mkdir sottodir
  mv paperino ./sottodir/paperino
  
3) Creare un link software per un file della propria HOME directory in una sottodirectory precedentemente creata; verificare il numero di link, le proprietà del link software e il suo uso
  ln -s pluto ./sottodir/plutosw
  ls -l sottodir
4) Cancellare (casomai dopo averne fatta una copia, se il contenuto è importante) il file della propria HOME directory usato come sorgente del link software; verificare cosa succede ad usare il link software
  rm pluto
  cat plutosw
5) Dopo aver ricreato il file sorgente del link software, cancellare a questo punto il link software e verificare che il file sorgente continui ad essere accessibile
  vi pluto
  scrivo il file
  cd sottodit
  rm plutosw
6) Provare a creare un link HW ad una directory: il comando ha successo?
  ln sottodir ./newsottodir
  NON SI PUò FARE
7) Provare a creare un link SW ad una directory: il comando ha successo? 
   ln -s sottodir ./newsottodir
      
  CAT
8) Usando la ridirezione dello standard output del comando-filtro cat, creare un file di nome prova (inserire almeno 5-6 linee con più parole per linea).
  cat >nomeprova
  scrivi il testo
  
9) Usando la ridirezione dello standard output del comando pwd e del comando ls -l, aggiungere tale output al file prova precedente.
  pwd >>nomeprova
  ls -l >>nomeprova
  
10) Usando il comando cat con le opportune ridirezioni, creare una copia del file prova e dargli nome p.txt.
  cat <nomeprov >p.txt
11) Usando più volte la ridirezione dello standard output in append aggiungere il contenuto del file prova al file p.txt almeno altre 5 volte in modo da avere un file che contenga molte linee.
  cat <nomeprov >>p.txt
  
MORE
12) Usando la ridirezione dello standard input e il comando-filtro more, visualizzare il contenuto del file p.txt.
  more <p.txt
13) Verificare il comportamento del comando more, usando il comando more p*.
  more p*       
              
SORT
14) Usando la ridirezione dello standard input e il comando-filtro sort, verificare se il file di nome prova è ordinato alfabeticamente.
 sort -c <pippo
15) Usando la ridirezione dello standard input e il comando-filtro sort, mostrare il contenuto del file prova ordinato secondo il normale ordinamento alfabetico.
  sort < pippo      
16) Stessa cosa di 15 ma invertendo l’ordinamento.
      sort -r < pippo      
17) Stessa cosa di 15, ma ignorando la differenza fra maiuscole e minuscole.
   sort -f < pippo      
18) Stessa cosa di 15, ma ridirigendo lo standard output su un file di nome ordinato.
   sort < pippo >ordinato             
19) Stessa cosa di 14, ma sul file di nome ordinato.
  sort -c >ordinato
20) Editare il file prova andando a duplicare e/o triplicare alcune linee.
  vi ordinato
  aggiungi linee
21) Stessa cosa di 15, ma attuando l’ordinamento alfabetico senza replicazioni e scrivendo lo standard output su un file di nome ordinato-senza-doppi.
  sort -u <ordinato > ordinato-senza-doppi

  GREP
22) Usando la ridirezione dello standard input e il comando-filtro grep, cercare le linee che contengono una certa stringa (o anche un semplice carattere) nel file ordinato-senza-doppi.
  grep ciao <ordinato-senza-doppi
23) Stessa cosa di 22, ma mostrando anche i numeri di linea.
   grep -n ciao <ordinato-senza-doppi
24) Assicurandosi di avere nel file ordinato-senza-doppi la stessa stringa scritta in maiuscola e in maiuscolo almeno 2-3 volte, stessa cosa di 22, ma cercando la stringa ignorando maiuscole/minuscole.
   grep - i ciao <ordinato-senza-doppi
25) Stessa cosa di 22, ma cercando le linee che NON contengono una certa stringa (o anche un semplice carattere).
    grep -v ciao <ordinato-senza-doppi
26) Stessa cosa di 22, ma cercando solo le linee che INIZIANO per una certa stringa (o anche un semplice carattere).
   grep '^ciao' <ordinato-senza-doppi
27) Stessa cosa di 22, ma cercando solo le linee che TERMINANO per una certa stringa (o anche un semplice carattere).
  grep 'ciao$' <ordinato-senza-doppi                                    
28) Stessa cosa di 22, ma cercando solo le linee che TERMINANO per il carattere ‘.’ (PUNTO), assicurandosi di averne almeno UNA!
grep '\.' <ordinato-senza-doppi
 29) Utilizzando la soluzione di uno degli esercizi fra 22 e 28, ridirigere lo standard output in un file di nome provagrep.
 grep '\.' <ordinato-senza-doppi >provagrep
  
  
WC
30) Usando la ridirezione dello standard input e il comando-filtro wc, contare le linee del file p.txt (vedi esercizio
11).
  wc -l <p.txt
31) Stessa cosa di 30, ma contando i caratteri.
  wc -c <p.txt
32) Stessa cosa di 30, ma contando le parole.
   wc -w <p.txt
33) Usando il comando wc su un file di nome pippo (che non esista) e ridirigendo lo standard error su /dev/null,verificare il valore di ritorno del comando.
  wc fiore 2> /dev/null
  
  PIPING
34) Utilizzando il comando ps in piping con tee temp e in piping con wc –l verificare: a) il numero visualizzato; 
  ps|tee temp|wc -l(mi da 5)
  b) il contenuto del file di nome temp creato dal filtro tee.
  cat tee temp
  
HEAD e TAIL
35) Usando la ridirezione dello standard input e il comando-filtro head, selezionare le prime 10 linee del file p.txt
(vedi esercizio 11).
  head <p.txt
36) Stessa cosa di 35, ma selezionando la prima linea.
  head -1 <p.txt
37) Stessa cosa di 35, ma selezionando le prime 3 linee.
  head -3 <p.txt
38) Usando la ridirezione dello standard input e il comando-filtro tail, selezionare le ultime 10 linee del file p.txt.
  tail <p.txt
39) Stessa cosa di 38, ma selezionando l’ultima linea.
  tail -1 <p.txt
40) Stessa cosa di 38, ma selezionando le ultime 3 linee.
  tail -3 <p.txt
41) Utilizzando la soluzione di uno degli esercizi fra 35 e 40, ridirigere lo standard output in un file di nome provahead o prova-tail a seconda dei casi.
   tail -3 <p.txt >prova-tail
42) Utilizzando il piping dei comandi, isolare in un file di nome p.txt.terza la terza linea a partire dall’inizio del file p.txt.
  head -3 <p.txt | tail -1 | tee p.terza.txt
43) Utilizzando il piping dei comandi, isolare in un file di nome p.txt.terzultima la terza linea a partire dalla fine del file p.txt.
tail -3 <p.txt | head -1 | tee p.terzultima.txt
  
ESECUZIONE IN BACKGROUND
44) Mandare in esecuzione con le opportune ridirezioni di standard output e di standard error il comando ls -lR /usando l’esecuzione in background.
  ls -lR / >temp 2> temperror & 
45) Verificare i processi attivi nella sessione prima che finisca il comando lanciato in background.
  ps
DATE
46) Verificare la data (e l’ora corrente).
  date
DIFF
47) Creare con l’editor vi (oppure con la ridirezione dello standard output) un file che contenga almeno 5 o 6 linee;  crearne una copia e quindi modificare con l’editor vi alcune parti; quindi, verificare il funzionamento del comando diff utilizzando i due file prodotti.        
  cat >provadiff
  cp provadiff ./provadiffcp
  vi provadiff1
  diff provadiff provadiff1

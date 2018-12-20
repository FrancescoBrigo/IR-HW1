# REPERIMENTO DELL'INFORMAZIONE A.A. 2018/2019
# HOMEWORK 1: VALUTAZIONE
## DOCENTI: MARISTELLA AGOSTI E GIANMARIA SILVELLO

Homework per il corso di Reperimento dell'informazione, tenuto dall'Università degli Studi di Padova.
Il repository contiene:
- il notebook Evaluation, che elabora i file di valutazione ottenuti da Terrier e trec_eval al fine di fornire: 
  - MAP, RPrec e Precision at 10 di ogni run 
  - il top-group e la top-run fra quelle proposte sulla base dei test statistici ANOVA 1-way e Tukey HSD
- i file delle run, contenuti in run_files, identificate come segue:
  - __RUN#0__: run effettuata con stoplist e Porter stemmer, con il modello BM25
  - __RUN#1__: run effettuata con stoplist e Porter stemmer, con il modello TF*IDF
  - __RUN#2__: run effettuata senza stoplist ma con Porter Stemmer, con il modello BM25
  - __RUN#3__: run effettuata senza stoplist e stemmer, con il modello TF*IDF
- i file di valutazione, ottenute con trec_eval, ed identificate coerentemente con il nome della run corrispondente.

###### FUNZIONAMENTO DEL NOTEBOOK
Più in dettaglio il notebook effettua un parsing dei file di valutazione (con la possibilità di settare il path di riferimento), riempiendo 3 array specifici per ogni run:
- ap: contenente tutte le *Average Precision* per ogni topic;
- p10: contenente tutte le *Precision@10* per ogni topic;
- rprec: contenente tutte le *Precision at Recall base* per ogni topic.

Vengono inoltre riempiti 3 array comuni (maps,p10s,rprecs) in cui vengono inseriti i valori totali delle rispettive misure.
Una volta effettuata questa operazioni viene effettuato il test ANOVA 1-way per verificare la similarità fra le varie run.
Successivamente viene effettuato il test Tukey HSD per verificare le effettive differenze fra i gruppi e vengono mostrati graficamente i risultati.
Nell'ultima cella vengono mostrati i risultati totali e i plot delle AP delle singole run sui diversi topic.

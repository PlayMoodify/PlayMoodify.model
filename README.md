# PlayMoodify.model
**Mood Classification for Music Playlists using Machine Learning** 

PlayMoodify è un progetto di Machine Learning applicato alla musica che mira a classificare l’umore di un brano musicale a partire dai suoi metadati audio, fornendo agli utenti una nuova chiave di lettura emotiva delle proprie playlist.
A differenza dei classici sistemi di raccomandazione basati sui gusti, PlayMoodify assegna un significato emotivo alle playlist, aiutando l’utente a scegliere cosa ascoltare in base allo stato d’animo del momento.

Link al repository: [PlayMoodify/PlayMoodify.model](https://github.com/PlayMoodify/PlayMoodify.model)


## Obiettivo del progetto
L’obiettivo principale è costruire un sistema di classificazione in grado di:
- Analizzare le audio features di un brano
- Classificarne l’umore in una delle seguenti classi:
  - sad
  - calm
  - happy
  - energetic
- Supportare scenari reali come:
  - Analisi dell’umore di playlist
  - Raccomandazione di brani per stato emotivo

## Contenuto (panoramica)
- Notebook Colab per esplorazione dati, preprocessing, training e inference.
- Script di utilità per caricamento dati, metriche ed salvataggio del modello addestrato.

## Dataset
- Dataset composto da circa 278.000 brani musicali
- Ogni brano è descritto da audio features numeriche
- Ogni entry è associata a una label di umore

Il dataset è stato sottoposto a:
- Data cleaning
- Analisi delle distribuzioni
- Rimozione di entry non valide
- Studio della distribuzione delle classi

## Pipeline di Machine Learning
Il progetto prevede l’implementazione e il confronto di due pipeline distinte:

**1. Random Forest Classifier**
- Modello ensemble tree-based
- Non richiede feature scaling
- Gestione dello sbilanciamento tramite class_weight='balanced'
- Valutazione tramite:
  - Accuracy
  - Precision, Recall, F1-score
  - Confusion Matrix
  - OOB Score (Out-Of-Bag)

**2. Logistic Regression**
- Modello lineare discriminativo
- Richiede feature scaling
- Gestione dello sbilanciamento tramite SMOTE
- Maggiore interpretabilità dei coefficienti

## Fasi principali del progetto
**1.Data Understanding**
- Analisi delle distribuzioni delle feature
- Analisi della distribuzione delle classi
- Individuazione di outlier e anomalie

**2.Data Preprocessing**
- Pulizia dei dati
- Rimozione di feature non significative
- Analisi della collinearità (correlation matrix)

**3.Train-Test Split**
- Suddivisione 80/20
- Split stratificato sulle classi
- Garanzia di riproducibilità (random_state=42)
  
**4.Gestione dello sbilanciamento**
- Random Forest → class weights
- Logistic Regression → SMOTE (solo sul training set)
  
**5.Addestramento e Valutazione**
- Confronto delle metriche di performance
- Analisi delle confusion matrix
- Confronto diretto tra i modelli

## Risultati
- **Random Forest:**
  - Accuracy ≈ 92%
  - Migliori F1-score e recall per tutte le classi
  - Ottima capacità di generalizzazione
  
- **Logistic Regression:**
  - Accuracy ≈ 81%
  - Prestazioni inferiori, ma maggiore interpretabilità

Il modello Random Forest è stato scelto come modello finale per l’utilizzo reale.

## Utilizzo del modello
Modello alla base della piattaforma PlayMoodify

## Contatti
Per domande o dettagli sul modello:
- Repository: https://github.com/PlayMoodify/PlayMoodify.model
- Maintainer / organizzazione: PlayMoodify

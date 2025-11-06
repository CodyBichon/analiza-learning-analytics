# analiza-learning-analytics
Analiză predictivă și structurală a ecosistemului github: o abordare pyspark-ML

## 💡 overview

Acest proiect implementează o analiză aprofundată a unui set de date extins de metadate GitHub, utilizând instrumente de **Machine Learning (ML) scalabile** prin **PySpark**.

Obiectivul principal este dublu: **(1)** a valida potențialul predictiv al caracteristicilor structurale (mărime, adâncime, duplicare) pentru clasificarea fișierelor și **(2)** a descoperi tipologii de fișiere care să permită **optimizarea economică a costurilor de stocare** prin strategii de deduplicare și alocare eficientă a resurselor.

---

## 📂 structura repository-ului

* **`Learning_Analytics.ipynb`**: Notebook-ul Colab care conține codul sursă complet pentru:
    * Analiza Exploratorie a Datelor (**EDA**).
    * Clasificarea Supervizată (**Logistic Regression, Random Forest, Decision Tree**).
    * Clustering-ul Nesupervizat (**K-Means, Bisecting K-Means**).
* **`raport-analiza-finala.pdf`** (sau `.docx`): Documentul academic final de 5 pagini care sintetizează metodologia, rezultatele și implicațiile operaționale.

---

## 📊 rezultate cheie machine learning

### 1. clasificarea (predictibilitatea naturii fișierului: text vs. binar)

Modelul demonstrează o separare liniară cvasiprefectă a datelor, validând utilitatea caracteristicilor structurale simple.

| algoritm | auc (area under roc) | acuratețe | eficiență |
| :--- | :---: | :---: | :---: |
| **logistic regression (ales)** | **0.9918** | **0.9692** | cel mai rapid (12.55s) |
| random forest | 0.9894 | 0.9467 | 22.65s |

### 2. clustering (tipologii structurale și optimizarea stocării)

Clustering-ul (K-Means) a obținut un **Silhouette Score de 0.9962**, confirmând separarea clară a datelor în tipologii acționabile.

| tipologie descoperită | caracteristici principale | implicații pentru optimizarea stocării |
| :--- | :--- | :--- |
| **foarte duplicat** | size $\approx 25$ kb, copies $\approx 72$ | **țintă prioritară pentru deduplicare** (reducerea costurilor de redundanță). |
| **gigant, unic** | size $\approx 73$ mb, copies $\approx 1.0$ | **mutare pe Cold Storage** (reducerea costului per GB). |

---

## 🔑 concluzie și contribuție

Proiectul contribuie cu o metodologie bazată pe ML care transformă metadatele brute în **decizii operaționale directe**, demonstrând că este posibilă obținerea unei înțelegeri profunde a unui ecosistem de date la scară largă pentru **optimizarea economică a infrastructurii**.

# mapreduce-pyspark-sagemaker-projects
This repository contains three hands-on projects in distributed data processing and machine learning. It covers the implementation of the MapReduce paradigm using Python and PySpark, web scraping techniques, and the deployment of a credit scoring model using AWS SageMaker.

Ce projet est structuré autour de trois exercices principaux, chacun illustrant une application concrète des techniques de traitement de données à grande échelle :

Analyse des amis en commun sur un réseau social avec MapReduce (Python & PySpark).

Extraction d'informations web (emails & mots fréquents) avec scraping HTML et logique MapReduce.

Modélisation interprétable d’un score de crédit hypothécaire avec Amazon SageMaker.

Exercice 1 : Amis en Commun via MapReduce & PySpark

Objectif
Identifier les amis en commun entre chaque paire d’utilisateurs d’un réseau social à partir d’un fichier brut (amis.txt), en suivant le paradigme MapReduce.

Partie 1 : MapReduce en Python (séquentiel)
Lecture et parsing du fichier texte amis.txt.

Génération de couples utilisateurs (flatMap) et regroupement par paires (groupByKey).

Application de reduce par intersection des listes d’amis.

Partie 2 : Version distribuée avec PySpark
Création de SparkSession.

Traitement identique en RDD via flatMap, groupByKey, puis reduceByKey.

Affichage des résultats triés : nombre et noms des amis communs.

Exercice 2 : Extraction d’Informations Web (emails + mots fréquents)
Objectif
Extraire des emails et top mots fréquents depuis un ensemble de pages web, à partir d’un fichier URLs.txt.

Étapes
Collecte : Fichier URLs.txt contenant des liens de restaurants, salons et hôtels à Paris.

Scraping : Téléchargement du HTML via requests + nettoyage avec BeautifulSoup.

Extraction :

Emails avec regex.

Mots avec une version simulée de MapReduce :

map : (mot, 1)

group/shuffle : regroupement par mot

reduce : somme des occurrences

Résultats sauvegardés : Un fichier RESULTATS_<site>.txt par page web.

Exercice 3 : Score de Crédit Interprétable (Amazon SageMaker)
Objectif
Créer un modèle prédictif du risque de défaut de paiement à partir du dataset hmeq.csv, et le déployer sur AWS SageMaker avec un focus sur l’interprétabilité.

Étapes
Analyse exploratoire & traitement des valeurs manquantes.

Entraînement de 3 modèles locaux (Random Forest, Logistic Regression, etc.) et choix du meilleur.

Export et envoi vers Amazon S3.

Déploiement du modèle avec SageMaker.

Évaluation des performances + outils d’interprétabilité (SHAP, coefficients).

Résultats obtenus
Modèle sélectionné : Logistic Regression avec recall = 0.79 et précision = 0.72.

Déploiement réussi sur SageMaker.

Interprétation des coefficients : variables comme DEBTINC, DEROG, et CLAGE sont les plus influentes.

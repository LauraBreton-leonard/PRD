# Modèles simples et Multi Input Modèles (en cours de construction)

## Script  

importer le fichier "malaisianReceipts.hf" dans ':/content' dans google Colab

https://colab.research.google.com/drive/17bLMi7Qo4vloJxfuRFhKVNfDH08BXwwT?usp=sharing

## Desciption des données
Voici un apercu de la répartition du texte sur les tickets de caisse en fonction de leur label (bleu= date, rose= company, jaune= total, blanc= adresse...)  
<img src="https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/bbox.png" width="250" height="250"/>  
  
  
On remarque bien qu'il y a une correlation entre la position du texte est son label.  
D'ou la possiblienécéssité d'unmodel multi-Input (modèles 4 et 5)  

Une features d'entrée pourra donc être la position du texte.  
La deuxième feature d'entrée sera le texte en lui-même.  
Voici un apercu du dataFrame  
![alt text](https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/dataFrame.PNG?raw=true)

## Description des models
1) TFIDF +Logistic Regression  
- vectorization TFIDF avec keras puis Naive Bayes multinomial regression avec scikit-learn

2) Embedding layer +Bidirectional LSTM

3) Embedding layer + CNN + LSTM

4) Multi Input model avec 2)+ coordonees de position du texte

5) multi-input model avec 3)+ coordonees de position du texte

6) les modèles précédents avec une "pretrained embedding layer" (pas encore fait) 

modèle2:  

<img src="https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/model2.png" width="250" height="250"/>   

modèle3:  

<img src="https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/model3.png" width="250" height="250"/>     

modèle4:  

<img src="https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/model4.png" width="250" height="250"/>   
modèle5:  

<img src="https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/model5.png" width="250" height="250"/>   

## Résultats


## Conclusion et Problèmes rencontrés

Plusieurs models fonctionnels qui semblent donner de bons résultats (85% accuracy apres 2 epochs pour certains) sur le dataset "AG news classification dataset" (classement de titres d'articles selon quatre domaines : sport, business, world....)  

Problème: Pas de dataset correct pour tester les modèles sur notre type de donnés, à savoir les tickets de caisse.  

-On ne peut pas tester  
-on ne peut pas faire varier les parametres de nos modèles  qui sont liés au dataset utilisé pour l'entrainement final (nb couches, dimensions, fonctions d'activation...) 
-Il faudrait tester l'influence des pretrained embedding layers. Cette influence est étroitement liée au dataset: taille du dataset, type de language utilisé...  


## Améliorations possibles
1) Intégrer une instance d'un model Bert sur la branche NLP ou au moins la couche d'embedding de BERT pré-entrainé ou autre embedding pré entrainé   

2) Essayer SMOTE ou cost sensitive learning pour imbalanced multiclass classification problem

# Multi Input Model (en cours de construction)

## Script  

importer le fichier "allData.hf" dans ':/content' dans google Colab

https://colab.research.google.com/drive/17bLMi7Qo4vloJxfuRFhKVNfDH08BXwwT?usp=sharing

## Desciption des données
Voici un apercu de la répartition du texte sur les tickets de caisse en fonction de leur label (bleu= date, rose= company, jaune= total, blanc= adresse...)  
<img src="https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/bbox.png" width="250" height="250"/>  
  
  
On remarque bien qu'il y a une correlation entre la position du texte est son label.  
Une features d'entrée pourra donc être la position du texte.  
La deuxième feature d'entrée sera le texte en lui-même.  
Voici un apercu du dataFrame  
![alt text](https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/dataFrame.PNG?raw=true)

## Description du model

![alt text](https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/schemaModel.png?raw=true) ![alt text](https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/modelCouches.PNG?raw=true)  

## A Faire début de la semaine du 19/10

entrainer le modèle sur au mois 25 epoch (au moins 4-5h)
changer le parametre embedding dim ( passer de 16 à 128) 
etudier l'influence nb epoch et np embedding dim

Essayer avec les nouveaux dataset


## Améliorations possibles
1) Intégrer une instance d'un model Bert sur la branche NLP ou au moins la couche d'embedding de BERT pré-entrainé ou autre embedding pré entrainé

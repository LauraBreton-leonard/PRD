# Multi Input Model (en cours de construction)

# Script  
  
https://colab.research.google.com/drive/1WFEVNXoMhwNHlvrnhAK5EksVALUuH4bX#scrollTo=1WIgHrBHqVYB  

## Desciption des données
Voici un apercu de la répartition du texte sur les tickets de caisse en fonction de leur label (bleu= date, rose= company, jaune= total, blanc= adresse...)  
<img src="https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/bbox.png" width="250" height="250"/>  
  
  
On remarque bien qu'il y a une correlation entre la position du texte est son label.  
Une features d'entrée pourra donc être la position du texte.  
La deuxième feature d'entrée sera le texte en lui-même.  
Voici un apercu du dataFrame  
![alt text](https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/dataFrame.PNG?raw=true)

## Description du model

![alt text](https://github.com/LauraBreton-leonard/PRD/blob/main/NER/MULTI_INPUT_MODEL/IMAGES/schemaModel.png?raw=true)  

## Améliorations possibles
1) Intégrer une instance d'un model Bert sur la branche NLP ou au moins la couche d'embedding de BERT pré-entrainé ou autre embedding pré entrainé

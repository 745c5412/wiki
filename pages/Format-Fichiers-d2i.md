# Format de fichier d2i

Le format de fichier d2i est un format cr�er par Ankama pour qui � pour but de stocker des chaines de caract�res (nom des items, dialogues des pnjs, etc...) correspondant � des cl�s, ce sont les fichiers "langues" du client.

### La structure d�un fichier d2i :
* L'indexe des indexes (int)
* Les donn�es (chaines de caract�res pr�c�d� de leur longueur)
* La table des indexes
    * Le nombre d'indexes (int)  
    * [--R�p�tition des 4 prochains points jusqu'a la fin du fichier--]
    * La cl� (int)
    * Indicateur diacritique (bool)
    * Le pointeur (int)
    * Le pointeur diacritique (int) (non repr�sent� sur le schema)

note : dans la repr�sentation ci-dessous il est consid�r� qu'aucunes des donn�es ne comporte de chaines diacritiques
![structure](../resources/format-fichiers/d2i/d2i-structure.png)

### L'indexe des indexes :

Correspond � l'offset de la table des indexes

### Les donn�es :

Un short contenant la longueur de la chaine puis la chaine de caract�res

### La table des indexes :

Le nombre d'indexes puis les indexes

### Les indexes :

Les indexes sont compos� de 3 � 4 elements :

1. La cl� : Appel� par exemple dans les fichiers d2o, c'est le "num�ro d'identification" de la donn�e
2. Indicateur diacritique : Indique si il existe une donn�e diacritique pour cette cl�
3. Pointeur : Emplacement de la chaine
4. Pointeur diacritique : Emplacement de la chaine diacritique si existante

# Informations supl�mentaires
- [D�finition du terme : diacritique](https://fr.wikipedia.org/wiki/Diacritique)
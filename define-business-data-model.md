# D�finir le Mod�le de Donn�es M�tier (BDM)

La plateforme Bonita offre un moyen de d�finir, manipuler et stocker vos donn�es m�tier. Ce service de gestion des donn�es cr�e des objets Java pour autoriser la manipulation de donn�es, des tables de base de donn�es pour le stockage et toutes les op�rations requises pour int�grer les donn�es de votre processus dans la base de donn�es et vice versa.

La gestion de donn�es implique plusieurs �tapes :
- Cr�er le Mod�le de Donn�es M�tier (BDM). Il s'agit de la d�finition des types de donn�es que vous utiliserez dans vos processus et applications.
- D�clarer des variables m�tier dans la d�finition de processus. Les variables sont utilis�es pour �tablir le lien entre votre d�finition de processus et les donn�es dont elle a besoin pour cr�er, lire, mettre � jour et supprimer. Les donn�es peuvent �tre cr��es dans le cadre de l'ex�cution du processus (au d�marrage ou lors d'une t�che), mais les processus peuvent �galement lire et mettre � jour des donn�es cr��es par d'autres processus et bien s�r peuvent choisir de supprimer des donn�es.
- D�finir des contrats de processus et de t�che. Les contrats d�finissent les informations que le processus accepte de la part de l'utilisateur qui soumet le formulaire.

Dans ce chapitre, nous nous concentrerons uniquement sur la cr�ation du Mod�le de Donn�es M�tier (BDM). La d�claration des variables m�tier sera trait�e dans le chapitre suivant.

Dans Bonita Studio, cr�er un BDM :
1. Allez dans le menu **Development > Business Data Model > Define...**

  ![Define business data model menu](images/getting-started-tutorial/define-business-data-model/define-business-data-model-menu.png)<!--{.img-responsive .img-thumbnail}-->
  
1. Cliquez sur le bouton **Add**
1. Saisissez le nom d'objet _Claim_ (les noms d'objet doivent toujours commencer par une majuscule)
1. Dans l'onglet **Attributes**, cliquez sur le bouton **Add**
1. Ajoutez 3 attributs (les noms d'attribut doivent toujours commencer par une minuscule) :
  1. _description_ de type _STRING_ et _mandatory_ (cochez la case dans la colonne **mandatory**)
  1. _answer_ de type _STRING_, _optional_
  1. _satisfactionLevel_ de type _INTEGER_, _optional_
  
  ![Create business object with attributes](images/getting-started-tutorial/define-business-data-model/create-business-object-with-attributes.gif)<!--{.img-responsive .img-thumbnail}-->
  
1. Cliquez sur le bouton **Finish**

::: info
**Mandatory** pour l'attribut d'un objet signifie que l'objet ne peut pas �tre cr�� avec une valeur vide. Si l'option **mandatory** n'est pas coch�e, cela signifie qu'un objet peut �tre cr�� avec une valeur vide, pour l'attribut � not mandatory � (c'est-�-dire facultatif). Dans notre exemple, l'attribut _answer_ est facultatif, car, au d�marrage du processus, il sera vide. Plus loin dans l'ex�cution du processus, un employ� fournira une r�ponse qui sera donc obligatoire (mais cela ne sera pas impos� par la d�finition du BDM).
:::

::: warning
Lorsque vous modifiez le BDM dans Bonita Studio, il est toujours recommand� de r�initialiser la base de donn�es apr�s avoir apport� une modification au mod�le. Cochez la case � Reset BDM database �, affich�e dans la fen�tre contextuelle lorsque vos validez vos modifications.
:::

::: info
Lorsque vous cliquez sur le bouton � Finish �, trois op�rations diff�rentes sont ex�cut�es :
- La d�finition du BDM est enregistr�e dans votre projet (dans la cat�gorie **Business Data Model**)
- Les classes Java sont g�n�r�es, compil�es, int�gr�es et le fichier jar qui en r�sulte est ajout� � votre projet (dans la cat�gorie **Java dependencies**)
- Les tables sont cr��es dans la base de donn�es test int�gr�e de Bonita Studio

:::

::: info
Bonita Studio utilise h2 pour fournir la base de donn�es � des fins de test. (Vous pouvez utiliser d'autres types de bases de donn�es telles que Oracle, PostgreSQL, MySQL et SQL Server for production). Bonita Studio fournit deux sch�mas de base de donn�es : un pour le moteur Bonita et un d�di� au BDM. Vous pouvez afficher les tables cr��es dans la base de donn�es BDM h2 en cliquant dans le menu de Bonita Studio sur **Development > Business Data Model > Browse data (h2 console)...**. Dans la console h2 (une interface web), vous pouvez voir qu'une table nomm�e � CLAIM � a �t� cr��e. Vous pouvez ex�cuter une requ�te SQL telle que � SELECT * FROM CLAIM � qui doit retourner un r�sultat vide, car il n'y a aucune donn�e pour l'instant.
:::

Vous disposez maintenant d'un mod�le de gestion des donn�es m�tier enti�rement fonctionnel. Vous �tes pr�t(e) � passer au chapitre suivant et � [commencer � renseigner la base de donn�es avec les donn�es collect�es par le processus](declare-business-variables.md). 

# Créer des interfaces utilisateur web (formulaires)

L'utilisateur pilote généralement l'exécution du processus via des interfaces web. Bonita fournit une solution, l'éditeur d'interface utilisateur (UI Designer) pour créer facilement ces interfaces.

> ℹ info :  
> Le workflow standard consiste à :
> - Créer le Modèle de Données Métier
> - Ajouter des variables métier dans la définition du processus
> - Générer des contrats basés sur les variables métier
> - Générer des formulaires Bonita basés sur les contrats
>
> Étant donné que nous avons déjà réalisé les trois premières étapes, il est maintenant temps de créer les formulaires.

Commencer par le formulaire d'instanciation de processus :
1. Sélectionnez le pool de processus
1. Allez dans **Exécution > Formulaire d'instanciation**
1. Cliquez sur l'icône du crayon à côté de **Formulaire cible**. Un nouveau formulaire basé sur le contrat est créé (si le formulaire n'existe pas déjà) et l'UI Designer s'ouvre dans votre navigateur web
1. Renommez le formulaire _newForm_ en _submitClaimForm_
1. Cliquez sur le bouton **Enregistrer** pour enregistrer le formulaire sous son nouveau nom

   ![Création d'un formulaire d'instanciation basé sur la définition d'un contrat](images/getting-started-tutorial/create-web-user-interfaces/create-instantiation-form.gif)<!--{.img-responsive .img-thumbnail}-->

Vous pouvez personnaliser l'aspect du formulaire. Par exemple, vous pouvez passer d'un widget d'une ligne de texte à une zone de texte :
1. Sélectionnez le widget _Description_ en cliquant dessus
1. Dans la zone affichant les propriétés du widget, à droite de la fenêtre, cliquez sur l'icône **...** et sélectionnez **Remplacer...**
1. Dans la liste déroulante, sélectionnez **Text Area**
1. Cliquez sur le bouton **Afficher les propriétés**
1. Cliquez sur le bouton **Remplacer**
1. Cliquez sur le bouton **Enregistrer** pour enregistrer vos modifications

   ![Modification du type de widget](images/getting-started-tutorial/create-web-user-interfaces/switch-widget.gif)<!--{.img-responsive .img-thumbnail}-->

Vous pouvez maintenant retourner dans Bonita Studio et créer le formulaire pour la tâche utilisateur _Review and answer claim_ :
1. Sélectionnez la tâche
1. Allez dans **Exécution > Formulaire**
1. Cliquez sur l'icône du crayon à côté de **Formulaire cible**. Un nouveau formulaire basé sur le contrat est créé (si le formulaire n'existe pas déjà) et l'UI Designer s'ouvre dans votre navigateur web
1. Répondez **Oui** à la question. Vous incluez ainsi des widgets pour afficher tous les attributs de la variable métier dans le formulaire
1. Renommez le formulaire _newForm_ en _reviewAndAnswerForm_
1. Sélectionnez le widget _Satisfaction Level_ et utilisez la touche de suppression pour le supprimer, car nous n'en voulons pas dans ce formulaire
1. Cliquez sur le bouton **Enregistrer** pour enregistrer vos modifications

Effectuez les mêmes opérations avec le formulaire pour la tâche _Read the answer and rate it_ :
1. Définissez le nom du formulaire sur _readAnswerAndRateItForm_
1. Ne supprimez aucun widget, car nous souhaitons afficher la description de la réclamation et la réponse et permettre à l'utilisateur de donner un niveau de satisfaction

Vous pouvez maintenant exécuter cette nouvelle version du processus. Vous verrez que le formulaire vous offre toujours la possibilité de saisir les données requises par le contrat, mais affiche également les données fournies au début du processus ou dans les étapes précédentes.

Dans le [chapitre suivant](define-who-can-do-what.md), vous allez voir comment s'assurer que les tâches soient exécutables uniquement par les utilisateurs appropriés.

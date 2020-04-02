# Cr�er des interfaces utilisateur web (formulaires)

L'utilisateur pilote g�n�ralement l'ex�cution du processus via des interfaces web. Bonita fournit une solution, l'�diteur d'interface utilisateur (UI Designer) pour cr�er facilement ces interfaces.

::: info
Le workflow standard serait :
- De cr�er le Mod�le de Donn�es M�tier
- D'ajouter des variables m�tier dans la d�finition du processus
- De g�n�rer des contrats bas�s sur les variables m�tier
- De g�n�rer des formulaires Bonita bas�s sur les contrats

�tant donn� que nous avons d�j� ex�cut� les trois premi�res �tapes, il est maintenant temps de cr�er les formulaires.
:::



Commencer par le formulaire d'instanciation de processus :
1. S�lectionnez le pool de processus
1. Allez dans **Execution > Instantiation form**
1. Cliquez sur l'ic�ne du crayon � c�t� de **Target form**. Un nouveau formulaire bas� sur le contrat est cr�� (si le formulaire n'existe pas d�j�) et UI Designer s'ouvre dans votre navigateur web
1. Renommez le formulaire _newForm_ en _submitClaimForm_
1. Cliquez sur le bouton **Save** pour enregistrer le formulaire sous son nouveau nom

   ![Create process instantiation form based on contract definition](images/getting-started-tutorial/create-web-user-interfaces/create-instantiation-form.gif)<!--{.img-responsive .img-thumbnail}-->

Vous pouvez personnaliser l'aspect du formulaire. Par exemple, vous pouvez passer d'un widget d'une ligne de texte � une zone de texte :
1. S�lectionnez le widget _Description_ en cliquant dessus
1. Dans **Widget properties**, � droite de la fen�tre, cliquez sur l'ic�ne **...** et s�lectionnez **Switch...**
1. Dans la liste d�roulante, s�lectionnez **Text Area**
1. Cliquez sur le bouton **Show properties**
1. Cliquez sur le bouton **Switch**
1. Cliquez sur le bouton **Save** pour enregistrer vos modifications

   ![Switch to a different widget type](images/getting-started-tutorial/create-web-user-interfaces/switch-widget.gif)<!--{.img-responsive .img-thumbnail}-->

Vous pouvez maintenant retourner dans Bonita Studio et cr�er le formulaire pour la t�che utilisateur  _Review and answer claim_ :
1. S�lectionnez la t�che
1. Allez dans **Execution > Form**
1. Cliquez sur l'ic�ne du crayon � c�t� de **Target form**. Un nouveau formulaire bas� sur le contrat est cr�� (si le formulaire n'existe pas d�j�) et UI Designer s'ouvre dans votre navigateur web
1. R�pondez **Yes** � la question. Vous incluez ainsi des widgets pour afficher tous les attributs de la variable m�tier dans le formulaire
1. Renommez le formulaire _newForm_ en _reviewAndAnswerForm_
1. S�lectionnez le widget _Satisfaction Level_ et utilisez la touche de suppression pour le supprimer, car nous n'en voulons pas dans ce formulaire
1. Cliquez sur le bouton **Save** pour enregistrer vos modifications

Effectuez les m�ms op�rations avec le formulaire pour la t�che _Read the answer and rate it_ :
1. D�finissez le nom du formulaire sur _readAnswerAndRateItForm_
1. Ne supprimez aucun widget, car nous souhaitons afficher la description de la r�clamation et la r�ponse et permettre � l'utilisateur de donner un niveau de satisfaction

Vous pouvez maintenant ex�cuter cette nouvelle version du processus. Vous verrez que le formulaire vous offre toujours la possibilit� de saisir les donn�es requises par le contrat, mais affiche �galement les donn�es fournies au d�but du processus ou dans les �tapes pr�c�dentes.

Dans le [chapitre suivant](define-who-can-do-what.md), vous pouvez veiller � ce que les t�ches soient ex�cutables uniquement par les utilisateurs appropri�s.

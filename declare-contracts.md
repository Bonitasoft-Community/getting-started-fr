# D�clarer des contrats

Jusqu'ici, notre processus d�finit une s�quence d'�v�nements et de t�ches et d�clare une variable m�tier qu'il va instancier et mettre � jour une fois ex�cut�e. Nous souhaitons instancier notre variable m�tier � claim � en utilisant la description fournie par le client lorsqu'il lance le processus. Nous devons �galement mettre � jour la r�clamation avec la r�ponse fournie par l'employ� et avec la note de satisfaction donn�e par le client. Nous avons besoin d'un moyen de collecter des informations aupr�s de l'utilisateur et de les stocker dans la variable m�tier. Pour ce faire, nous utilisons les interfaces utilisateur (formulaires web par d�faut dans Bonita) ainsi qu'un autre concept : le contrat.

Un contrat d�finit les donn�es attendues de l'utilisateur pour d�marrer un processus (contrat d'instanciation) ou pour ex�cuter une t�che utilisateur (contrat de t�che). Par d�faut, Bonita offre une solution pour construire facilement des formulaires (consultez le chapitre suivant) permettant � l'utilisateur de visualiser et de fournir des donn�es. Lorsqu'ils sont soumis, les formulaires demandent au moteur Bonita de lancer un processus ou d'ex�cuter une t�che en utilisant les donn�es fournies qui doivent correspondre � ce qui est attendu par le contrat.

�tant donn� que nos informations relatives au contrat seront utilis�es pour d�finir les valeurs des variables m�tier, nous pouvons utiliser un assistant qui g�n�rera le contrat en se fondant sur la variable m�tier. Cet assistant d�finit la valeur par d�faut de la variable m�tier et g�n�re l'ex�cution de la t�che.

Cr�er le contrat pour l'instanciation de processus :
1. S�lectionnez le pool de processus
1. En bas de la fen�tre de Bonita Studio, allez dans l'onglet **Execution > Contract > Inputs**
1. Cliquez sur le bouton **Add from data...**
1. Laissez les options par d�faut coch�es (_Business variable_, _Instantiate_, _claim_, _claimInput_)
1. Cliquez sur le bouton **Next**
1. S�lectionnez uniquement la _description_ (d�cochez _answer_, _satisfactionLevel_)
1. Cliquez sur **Finish**
1. Vous pouvez ignorer le message d'information et cliquer sur le bouton **OK**

   ![Declare process instantiation contract](images/getting-started-tutorial/declare-contracts/declare-process-instantiation-contract.gif)<!--{.img-responsive .img-thumbnail}-->

::: info
Vous avez maintenant un contrat nomm� _claimedInput_ de type � COMPLEXE � avec un attribut, _description_ de type � TEXTE �. Comme la description est obligatoire, vous pouvez voir dans l'onglet **Execution > Contract > Constraints** qu'une r�gle de validation a �t� cr��e pour s'assurer d'obtenir une valeur pour la description. Enfin, si vous �ditez la variable m�tier _claim_, vous constatez qu'un script a �t� g�n�r� pour vous permettre de d�finir la valeur par d�faut de la variable. La d�finition de cette valeur d�clenchera une insertion dans la table � CLAIM � cr��e pour vous dans la base de donn�es des donn�es m�tier g�r�e par Bonita.
:::

� pr�sent, cr�ons le contrat pour la t�che utilisateur _Review and answer claim_ :
1. S�lectionnez la t�che _Review and answer claim_
1. En bas de la fen�tre de Bonita Studio, allez dans l'onglet **Execution > Contract > Inputs**
1. Cliquez sur le bouton **Add from data...**
1. S�lectionnez Data : _Business variable_, Action : _Edit_, et conservez les valeurs par d�faut des autres options
1. Cliquez sur le bouton **Next**
1. S�lectionnez uniquement _answer_ (d�cochez _description_, _satisfactionLevel_)
1. Cliquez sur le bouton **Finish**
1. Vous pouvez ignorer les messages d'information et d'avertissement et cliquer sur le bouton **OK**

   ![Declare user task contract](images/getting-started-tutorial/declare-contracts/declare-user-task-contract.gif)<!--{.img-responsive .img-thumbnail}-->

::: info
Nous avons maintenant un contrat pour l'�tape. Ce contrat ne cr�e pas de nouvelle r�clamation, mais met � jour un attribut de la r�clamation (la r�clamation est cr��e lorsque nous lan�ons le processus). La mise � jour de l'attribut est effectu�e par une op�ration (g�n�r�e pour vous) sur la t�che. S�lectionnez **Execution > Operations** pour afficher l'op�ration qui met � jour l'attribut _answer_.
:::

Cr�er le contrat pour la t�che _Read the answer and rate it_ :
1. Proc�dez exactement de la m�me mani�re que pour la t�che _Review and answer claim_ 
1. S�lectionnez _satisfactionLevel_ comme attribut � utiliser dans le contrat

� pr�sent, vous pouvez cliquer sur le bouton **Run** de Bonita Studio pour d�ployer et ex�cuter cette version mise � jour. Vous obtenez des formulaires g�n�r�s automatiquement fond�s sur le contrat. Dans le formulaire d'aper�u, vous verrez les donn�es stock�es dans la variable m�tier. Notez qu'un formulaire n'affichera pas les donn�es saisies pr�c�demment. Nous aborderons ce sujet dans le [chapitre suivant](create-web-user-interfaces.md).

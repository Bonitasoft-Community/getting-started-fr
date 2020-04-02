# D�clarer les variables m�tier 

Pour que votre processus puisse ex�cuter des op�rations sur les donn�es m�tier telles que les op�rations classiques cr�er, lire, mettre � jour et supprimer, vous devez inclure des variables m�tier dans votre d�finition de processus.

Dans notre processus, nous allons traiter un seul objet : une r�clamation. L'objet r�clamation stockera des informations sur la r�clamation elle-m�me (c'est-�-dire sa description), la r�ponse fournie et un niveau de satisfaction. Pour d�clarer une variable m�tier :
1. S�lectionnez le pool de processus, le rectangle qui inclut les �v�nements de d�but et les t�ches.

   ![Select the pool](images/getting-started-tutorial/declare-business-variable/select-process-pool.gif)<!--{.img-responsive .img-thumbnail}-->

1. En bas de l'�cran de Bonita Studio, allez dans **Data > Pool variables**
1. Cliquez sur le bouton **Add...** � c�t� de **Business variables**
1. Saisissez le nom de la variable m�tier : _claim_ (en minuscule)
1. S�lectionnez le **Business Object**: _com.company.model.Claim_
1. Cliquez sur le bouton **Finish**

   ![Declare business variable](images/getting-started-tutorial/declare-business-variable/declare-business-variable.gif)<!--{.img-responsive .img-thumbnail}-->

Maintenant qu'une variable m�tier est d�clar�e, nous pouvons l'utiliser dans notre d�finition de condition de transition :
1. S�lectionnez la transition connectant la porte _Satisfaction level_ avec _Deal with unsatisfied customer_
1. Allez dans l'onglet **General > General**
1. Dans **condition**, cliquez sur l'ic�ne du crayon
1. S�lectionnez **Script** dans **Expression type** � gauche de la fen�tre contextuelle
1. Saisissez le script Groovy : `claim.satisfactionLevel < 3`
1. Cliquez sur le bouton **OK**

   ![Define transition condition using business variable value](images/getting-started-tutorial/declare-business-variable/define-condition.gif)<!--{.img-responsive .img-thumbnail}-->

::: info
Le script configur� pour la condition de transition retournera � true � si le niveau de satisfaction donn� est inf�rieur � 3, comme la transition vers _Deal with unsatisfied customer_ sera activ�e.
:::

::: info
Notre variable m�tier n'est jamais initialis�e, donc elle restera vide. Il existe plusieurs options diff�rentes pour initialiser une variable m�tier :
- valeur par d�faut de la variable m�tier
- op�ration sur une t�che
- sortie de connecteur

Nous utiliserons la premi�re et deuxi�me option dans les chapitres suivants.
:::

� ce stade de la d�finition de processus, si vous essayez de l'ex�cuter, vous ne verrez aucune diff�rence dans le formulaire d'instanciation de processus et dans les formulaires des t�ches utilisateur. Seul le formulaire de l'aper�u du processus est diff�rent : il r�pertorie d�sormais la variable m�tier mais sans valeur associ�e.

Vous �tes maintenant pr�t(e) � passer au [chapitre suivant](declare-contracts.md) et � commencer � collecter des entr�es utilisateur � partir des formulaires. Elles passeront par les [contrats](declare-contracts.md) et pourront finalement �tre stock�es dans les variables m�tier.

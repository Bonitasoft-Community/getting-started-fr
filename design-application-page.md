# Concevoir une page d'application

Jusqu'ici, avec un processus, des donn�es, des formulaires et des connecteurs, nous avons construit une solution logicielle enti�rement fonctionnelle pour g�rer les r�clamations. Mais que se passe-t-il si nous souhaitons avoir un tableau de bord affichant toutes les r�clamations en cours ? Ce type de tableau de bord n'est pas un processus. Vous n'avez pas besoin de le � lancer � pour l'afficher. Une application Bonita apporte la solution. Et la premi�re �tape pour construire une application est de cr�er des pages.

::: info
Les pages dans Bonita ressemblent beaucoup � des formulaires. Elles sont cr��es � l'aide de l'�diteur d'interface utilisateur (UI Designer) avec les m�mes ensembles de widgets. La principale diff�rence est qu'elles ne sont pas li�es � une d�finition de processus (comme les formulaires d'instanciation et les formulaires de t�ches utilisateur). Une page d'application peut afficher les valeurs des donn�es m�tier, les graphiques et m�me permettre � l'utilisateur de lancer un processus ou d'ex�cuter une t�che en affichant le formulaire appropri�.
:::

Pour cet exemple, nous construirons une page de base qui affiche toutes les r�clamations soumises dans un tableau. Pour cr�er une nouvelle page :
1. Cliquez sur l'ic�ne **UI Designer** ![UI Designer icon](images/getting-started-tutorial/design-application-page/ui-designer.png) dans la barre d'outils de Studio
1. Ignorez la fen�tre contextuelle avec le message d'information
1. Cliquez sur le bouton **create**
1. V�rifiez que **Application page** est coch�
1. Saisissez le nom : _claimsList_
1. Cliquez sur le bouton **Create**

   ![Creation of an application page](images/getting-started-tutorial/design-application-page/creation-of-an-application-page.gif)<!--{.img-responsive .img-thumbnail}-->

Sur la nouvelle page, vous pouvez permettre � UI Designer de cr�er automatiquement des variables pour r�cup�rer les donn�es m�tier :
1. Dans l'angle sup�rieur gauche de UI Designer, cliquez sur le bouton **data model** ![Data model button](images/getting-started-tutorial/design-application-page/data-model.png)
1. Dans la liste des objets m�tier, s�lectionnez l'objet _Claim_ et glissez-d�posez-le dans l'espace vide sur la page
1. Dans la fen�tre contextuelle, modifiez **Variable name** de _claim_ en _claims_
1. Dans la section **Additionnal queries**, s�lectionnez _find_
1. Cliquez sur le bouton **Save**

   ![Declare claims page variable](images/getting-started-tutorial/design-application-page/declare-claims-page-variable.gif)<!--{.img-responsive .img-thumbnail}-->

Ajouter et configurer le widget table :
1. Depuis la palette des widgets � gauche, glissez-d�posez un widget **Table** sur le tableau blanc
1. Dans les propri�t�s du widget � droite :
   - D�finissez le nom **headers** sur : _Description, Answer, Satisfaction level_
   - Pour le **content**, cliquez sur le bouton **fx**
   - Saisissez la valeur _claims_
   - D�finissez **Column keys** sur : _description, answer, satisfactionLevel_
1. Cliquez sur le bouton **Save** de l'�diteur d'interface utilisateur
1. Cliquez sur le bouton **Preview** pour avoir un aper�u de votre page

   ![Add and configure table widget](images/getting-started-tutorial/design-application-page/add-and-configure-table-widget.gif)<!--{.img-responsive .img-thumbnail}-->

::: warning
Afin que l'aper�u acc�de aux donn�es, un utilisateur doit �tre connect� au Portail Bonita. Vous pouvez cliquer sur le bouton **Portal** dans la barre d'outils de Bonita Studio pour v�rifier qu'un utilisateur est connect�.
:::

Vous avez maintenant votre premi�re page d'application. Il est temps de passer au [chapitre suivant](create-application.md) et de cr�er l'[application](create-application.md) qui int�grera la page.

# D�finir qui peut faire quoi

Jusqu'ici, lorsque vous ex�cutiez le processus, vous agissiez en tant qu'utilisateur unique (nom d'utilisateur : _walter.bates_, mot de passe : _bpm_) pouvant ex�cuter toutes les t�ches utilisateur. Dans un sc�nario plus proche d'un cas d'utilisation r�el, il existe diff�rents types d'utilisateurs : des clients (pouvant soumettre des r�clamations), des employ�s (qui r�pondent aux r�clamations) et le responsable de l'utilisateur qui fournit la r�ponse (qui est n�cessaire pour interagir avec des clients m�contents).

La premi�re �tape de la configuration de � qui peut faire quoi � consiste � cr�er des lanes dans notre pool. Nous avons d�j� une lane par d�faut pour les employ�s. Ajoutons-en une autre pour le client et une pour le responsable :
1. Dans Bonita Studio, depuis la palette � gauche du diagramme, s�lectionnez l'ic�ne **lane**
1. Cliquez � l'int�rieur du pool de processus pour ajouter la lane. Faites-le deux fois pour avoir un total de trois lanes
1. S�lectionnez l'employee lane et cliquez sur l'ic�ne de la fl�che en bas pour la d�placer dans la lane centrale

   ![Add and organize lanes](images/getting-started-tutorial/define-who-can-do-what/add-and-organize-lanes.gif)<!--{.img-responsive .img-thumbnail}-->

1. S�lectionnez _Lane1_, allez dans l'onglet **General > Lane** et renommez-la _Customer lane_
1. S�lectionnez _Lane2_, allez dans l'onglet **General > Lane** et renommez-la _Manager lane_
1. S�lectionnez l'�v�nement de d�but _Submit claim_ et d�placez-le (par glisser-d�placer) vers la _Customer lane_. Effectuez la m�me op�ration pour la t�che _Read the answer and rate it_
1. S�lectionnez la t�che _Deal with unsatisfied customer_ et d�placez-la vers la _Manager lane_. Effectuez la m�me op�ration pour l'�v�nement de fin _End client unsatisfied_

   ![Diagrams with lanes](images/getting-started-tutorial/define-who-can-do-what/diagrams-with-lanes.png)<!--{.img-responsive .img-thumbnail}-->

::: info
Une lane est utilis�e pour regrouper les t�ches utilisateur qui doivent �tre effectu�es par le m�me ensemble d'utilisateurs.
:::

� pr�sent, nous devons d�finir des � acteurs �, un pour chaque lane, et les associer � la lane � laquelle ils appartiennent :
1. S�lectionnez le pool
1. Allez dans **General > Actors**
1. Cliquez sur le bouton **Add**
1. Cliquez sur le nom par d�faut de l'acteur (_Actor1_) et modifiez-le en : _Customer actor_
1. R�p�tez pour cr�er _Manager actor_
1. S�lectionnez le _Customer actor_ et cliquez sur le bouton **Set as initiator**. Un drapeau sera ajout� pour cet acteur afin de l'identifier comme celui qui d�marre le processus

   ![Add and rename actors, define initiator](images/getting-started-tutorial/define-who-can-do-what/add-rename-actors-set-initiator.gif)<!--{.img-responsive .img-thumbnail}-->

1. S�lectionnez _Customer lane_ (cliquez sur le nom de la lane)
1. Allez dans **General > Actors** et dans la liste d�roulante, s�lectionnez _Customer actor_
1. Effectuez la m�me op�ration pour la _Manager lane_ avec _Manager actor_

   ![Map actor to lane](images/getting-started-tutorial/define-who-can-do-what/map-actor-to-lane.gif)<!--{.img-responsive .img-thumbnail}-->

Les acteurs sont simplement des identifiants. Afin de d�finir l'utilisateur r�el, nous devons configurer les acteurs et les associer aux groupes, r�les, utilisateurs, etc. de l'organisation. Nous utiliserons l'organisation test Bonita Acme pour cet exemple :
1. Dans le menu Bonita Studio, cliquez sur **Server > Configure** ![Configure button icon](images/getting-started-tutorial/define-who-can-do-what/configure.png)
1. S�lectionnez _Employee actor_
1. Cliquez sur le bouton **Groups...**
1. D�cochez _/acme_
1. Cochez _/acme/production/services_. Nous utiliserons ce groupe d'utilisateurs pour jouer le r�le de l'�quipe de support charg�e de r�pondre aux r�clamations. Dans l'organisation test, deux utilisateurs appartiennent � ce groupe : _mauro.zetticci_ et _thomas.wallis_. Le responsable des deux utilisateurs est : _michael.morrison_
1. Cliquez sur le bouton **Finish**

   ![Configure actor mapping for customer actor](images/getting-started-tutorial/define-who-can-do-what/configure-actor-mapping.gif)<!--{.img-responsive .img-thumbnail}-->

1. S�lectionnez **Customer actor**
1. Cliquez sur le bouton **Groups...**
1. Cochez _/acme/hr_. Nous utiliserons ce groupe d'utilisateurs pour jouer le r�le des clients qui peuvent soumettre des r�clamations. Dans l'organisation test, trois utilisateurs appartiennent � ce groupe : _walter.bates_, _helen.kelly_ et _april.sanchez_
1. Cliquez sur le bouton **Finish**
1. S�lectionnez _Manager actor_
1. Cliquez sur le bouton **Roles...**
1. S�lectionnez le r�le _member_. Tous les utilisateurs de l'organisation test ont ce r�le. Mais, cela n'a pas vraiment d'importance, car cette association d'acteur sera annul�e plus tard dans notre configuration
1. Cliquez sur le bouton **Finish**
1. Cliquez sur le bouton **Finish** pour fermer la fen�tre de configuration

� ce stade, si vous essayez d'ex�cuter le processus, vous verrez que _walter.bates_ ne peut plus ex�cuter la t�che _Review and answer claim_. Vous devrez vous d�connecter du Portail Bonita (cliquez sur **Walter Bates** dans l'angle sup�rieur droit et s�lectionnez **Logout**) et vous connecter avec _mauro.zetticci_ ou _thomas.wallis_ (mot de passe : _bpm_) pour pouvoir afficher la t�che. Et vous devez vous reconnecter avec le compte _walter.bates_ pour pouvoir afficher la t�che qui vous permet de lire la r�ponse fournie.

Actuellement, la t�che _Read the answer and rate it_ est disponible pour tous les utilisateurs du groupe _/acme/hr_, mais elle devrait �tre disponible uniquement pour l'utilisateur qui a lanc� le processus (_walter.bates_). De m�me, la t�che _Deal with unsatisfied customer_ sera disponible pour tous alors qu'elle devrait �tre disponible uniquement pour le responsable de l'utilisateur qui a ex�cut� la t�che _Review and answer claim_. Pour r�pondre � ce probl�me, nous configurerons des filtres pour les acteurs :
1. S�lectionnez la _Customer lane_
1. Allez dans **General > Actors**
1. Cliquez sur le bouton **Set...** � c�t� de filtre acteur
1. Dans la liste, s�lectionnez _Initiator_
1. Cliquez sur le bouton **Next**
1. D�finissez le nom : _User who submit the claim_
1. Cliquez sur le bouton **Finish**

   ![Configure initiator actor filter on Customer lane](images/getting-started-tutorial/define-who-can-do-what/configure-initiator-actor-filter.gif)<!--{.img-responsive .img-thumbnail}-->

1. S�lectionnez la _Manager lane_
1. Suivez les m�mes �tapes, mais s�lectionnez le filtre acteur _user-manager_
1. D�finissez le nom : _Manager of the user who provided answer_
1. Cliquez sur le bouton **Next**
1. Cliquez l'ic�ne du crayon
1. S�lectionnez **Script** et collez le script Groovy suivant (il recherchera l'identifiant de l'utilisateur qui a ex�cut� la t�che _Review and answer claim_) :

   ``` groovy
   import org.bonitasoft.engine.bpm.flownode.ArchivedHumanTaskInstance
   import org.bonitasoft.engine.bpm.flownode.ArchivedHumanTaskInstanceSearchDescriptor
   import org.bonitasoft.engine.search.SearchOptionsBuilder
   import org.bonitasoft.engine.search.SearchResult

   def taskName = 'Review and answer claim'

   final SearchOptionsBuilder searchOptionsBuilder = new SearchOptionsBuilder(0, 1)
   .filter(ArchivedHumanTaskInstanceSearchDescriptor.PARENT_PROCESS_INSTANCE_ID, processInstanceId)
   .filter(ArchivedHumanTaskInstanceSearchDescriptor.NAME, taskName).filter(ArchivedHumanTaskInstanceSearchDescriptor.TERMINAL, true)

   SearchResult<ArchivedHumanTaskInstance> searchResult = apiAccessor.processAPI.searchArchivedHumanTasks(searchOptionsBuilder.done())

   final List<ArchivedHumanTaskInstance> tasks = searchResult.result

   tasks.first().executedBy
   ```

1. Cliquez sur **OK**
1. Cliquez sur **Finish**

   ![Configure user manager actor filter for manager lane](images/getting-started-tutorial/define-who-can-do-what/configure-user-manager-actor-filter.gif)<!--{.img-responsive .img-thumbnail}-->


Si vous ex�cutez � nouveau le processus, seul _walter.bates_ doit avoir acc�s � _Read the answer and rate it_ et seul _michael.morrison_ doit avoir acc�s � _Deal with unsatisfied customer_ (car il est le responsable des deux utilisateurs qui peuvent ex�cuter la t�che _Review and answer claim_).

Nous avons maintenant un processus enti�rement personnalis� qui traite les donn�es et attribue les t�ches aux utilisateurs appropri�s. L'[�tape suivante](configure-email-connector.md) consistera � permettre � ce processus d'interagir avec le monde ext�rieur.

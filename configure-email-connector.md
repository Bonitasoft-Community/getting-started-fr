# Configurer un connecteur d'e-mail

Pour qu'un processus interagisse avec des syst�mes externes tels que la publication d'un document sur un CMS, l'appel d'un API REST ou l'envoi d'un e-mail, Bonita fournit des connecteurs. Dans notre exemple, nous allons configurer un connecteur d'e-mail pour informer le responsable qu'une t�che _Deal with unsatisfied customer_ requiert son attention.

::: info
Un connecteur est un morceau de code ex�cut� au d�but ou � la fin d'un processus ou d'une t�che. Il traite les donn�es d'entr�e (par exemple, les valeurs des variables m�tier) et g�n�re (en option) certaines sorties. Le code du connecteur peut uniquement transformer des entr�es, mais peut �galement ex�cuter une interaction avec des syst�mes externes.
:::

Afin d'�viter les param�tres qui sont sp�cifiques au vrai fournisseur d'e-mail, nous allons utiliser un outil pour un faux serveur d'e-mail � FakeSMTP � :
1. T�l�chargez FakeSMTP � partir de ce lien : [http://nilhcem.github.com/FakeSMTP/downloads/fakeSMTP-latest.zip](http://nilhcem.github.com/FakeSMTP/downloads/fakeSMTP-latest.zip)
1. D�compressez le fichier
1. Ex�cutez FakeSMTP en double-cliquant sur le fichier JAR ou en ex�cutant cette commande shell : � java -jar fakeSMTP-2.0.jar �
1. Lorsque l'interface utilisateur s'affiche, param�trez le**listening port** sur _2525_
1. Cliquez sur le bouton **Start server**.

   ![FakeSMTP configured and listening](images/getting-started-tutorial/configure-email-connector/fakesmtp-configured-and-listening.png)<!--{.img-responsive .img-thumbnail}-->

Maintenant que nous avons ex�cut� un faux serveur, configurons le connecteur d'e-mail sur la t�che _Deal with unsatisfied customer_ :
1. S�lectionnez la t�che _Deal with unsatisfied customer_
1. Allez dans **Execution > Connectors in**
1. Cliquez sur le bouton **Add...**
1. S�lectionnez le connecteur _Email (SMTP)_
1. Cliquez sur le bouton **Next**
1. Nommez la configuration du connecteur _Send notification_
1. Cliquez sur le bouton **Next**
1. D�finissez les valeurs des param�tres suivantes :
   - SMTP host : _localhost_
   - SMTP port : _2525_ (le num�ro de port sp�cifi� dans FakeSMTP)
   - SSL (dans la section **Security**) : _unchecked_
1. Cliquez sur le bouton **Next**
1. Saisissez _no-reply@acme.com_ dans le champ **From** 
1. Utilisez l'ic�ne ![ic�ne du crayon](images/getting-started-tutorial/configure-email-connector/pencil.png) pour modifier l'expression du champ **To** 
1. D�finissez **Expression type** sur **Script**
1. Collez le script Groovy suivant dans la zone de modification du code : `BonitaUsers.getUserProfessionalContactInfo(apiAccessor,taskAssigneeId).email`
1. Cliquez sur le bouton **OK**
1. Cliquez sur le bouton **Next**
1. D�finissez _You have a pending task_ comme objet
1. Cliquez sur **Finish**

   ![Email connector configuration](images/getting-started-tutorial/configure-email-connector/configure-email-connector.gif)<!--{.img-responsive .img-thumbnail}-->

Si vous ex�cutez le processus avec le connecteur configur�, vous devez voir un nouvel e-mail entrant dans l'interface utilisateur FakeSMTP lorsque la t�che _Deal with unsatisfied customer_ est disponible.

Vous avez maintenant une d�finition de processus qui utilise une large palette de fonctionnalit�s de Bonita. Dans les [chapitres suivants](design-application-page.md), nous allons cr�er une application sur ce processus.

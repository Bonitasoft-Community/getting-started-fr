# Configurer un connecteur e-mail

Pour qu'un processus interagisse avec des systèmes externes tels que la publication d'un document sur un CMS, l'appel d'une API REST ou l'envoi d'un mail, Bonita fournit des connecteurs. Dans notre exemple, nous allons configurer un connecteur e-mail pour informer le responsable qu'une tâche _Deal with unsatisfied customer_ requiert son attention.

> ℹ info :  
> Un connecteur est un morceau de code exécuté au début ou à la fin d'un processus ou d'une tâche. Il traite les données d'entrée (par exemple, les valeurs des variables métier) et génère (en option) certaines sorties. Le code du connecteur peut uniquement transformer des entrées, mais peut également exécuter une interaction avec des systèmes externes.

Afin d'éviter les paramètres qui sont spécifiques au fournisseur du service mail, nous allons utiliser un outil permettant de disposer d'un serveur mail local « FakeSMTP » :
1. Téléchargez FakeSMTP à partir de ce lien : [http://nilhcem.github.com/FakeSMTP/downloads/fakeSMTP-latest.zip](http://nilhcem.github.com/FakeSMTP/downloads/fakeSMTP-latest.zip)
1. Décompressez le fichier
1. Exécutez FakeSMTP en double-cliquant sur le fichier JAR ou en exécutant cette commande shell : `java -jar fakeSMTP-2.0.jar`
1. Lorsque l'interface utilisateur s'affiche, paramétrez le **Port d'écoute** sur _2525_
1. Cliquez sur le bouton **Démarrer le serveur**.

   ![FakeSMTP configuré et en écoute sur le port 2525](images/getting-started-tutorial/configure-email-connector/fakesmtp-configured-and-listening.png)<!--{.img-responsive .img-thumbnail}-->

Maintenant que le serveur est démarré, configurons le connecteur mail sur la tâche _Deal with unsatisfied customer_ :
1. Sélectionnez la tâche _Deal with unsatisfied customer_
1. Allez dans **Exécution > Connecteurs en entrée**
1. Cliquez sur le bouton **Ajouter...**
1. Sélectionnez le connecteur _Courriel_
1. Cliquez sur le bouton **Suivant**
1. Nommez la configuration du connecteur _Send notification_
1. Cliquez sur le bouton **Suivant**
1. Définissez les valeurs des paramètres suivantes :
   - Hôte SMTP : _localhost_
   - Port SMTP : _2525_ (le numéro de port spécifié dans FakeSMTP)
   - SSL (dans la section **Sécurité**) : _décochée_
1. Cliquez sur le bouton **Suivant**
1. Saisissez _no-reply@acme.com_ dans le champ **De** 
1. Utilisez l'icône ![icône du crayon](images/getting-started-tutorial/configure-email-connector/pencil.png) pour modifier l'expression du champ **À** 
1. Définissez **Type d'expression** sur **Script**
1. Collez le script Groovy suivant dans la zone de modification du code : `BonitaUsers.getUserProfessionalContactInfo(apiAccessor,taskAssigneeId).email`
1. Cliquez sur le bouton **OK**
1. Cliquez sur le bouton **Suivant**
1. Définissez _You have a pending task_ comme objet
1. Cliquez sur **Terminer**

   ![Configuration du connecteur courriel](images/getting-started-tutorial/configure-email-connector/configure-email-connector.gif)<!--{.img-responsive .img-thumbnail}-->

Si vous exécutez le processus avec le connecteur configuré, vous devez voir un nouvel e-mail entrant dans l'interface utilisateur FakeSMTP lorsque la tâche _Deal with unsatisfied customer_ est disponible.

Vous avez maintenant une définition de processus qui utilise une large palette de fonctionnalités de Bonita. Dans les [chapitres suivants](design-application-page.md), nous allons créer une application s'appuyant sur ce processus.

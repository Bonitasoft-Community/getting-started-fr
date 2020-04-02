# Créer une application

La création de l'application est l'étape finale de ce tutoriel.

Mais avant de créer réellement l'application, nous devons déployer notre page d'application dans le Portail Bonita :
1. Dans le menu Bonita Studio, cliquez sur **Fichier > Déployer...**
1. Cliquez sur le bouton **Tout sélectionner** pour être certain(e) de tout déployer : organisation de test, modèle de données métier, définition de processus, page d'application
1. Vérifiez que la case **Vider la base de données métier avant le déploiement** n'est pas cochée, car nous souhaitons conserver nos données pour le test
1. Cliquez sur le bouton **Déployer**
1. Dans la fenêtre contextuelle **Statut du déploiement**, cliquez sur le bouton **Fermer**

   ![Déploiement d'un projet](images/getting-started-tutorial/create-application/project-deployment.gif)<!--{.img-responsive .img-thumbnail}-->

À présent, nous sommes prêts à créer réellement l'application. Dans la Bonita Community Edition, le moyen le plus simple de créer une application est d'utiliser le Portail Bonita :
1. Cliquez sur l'icône du Portail ![Icône du portail](images/getting-started-tutorial/create-application/portal-icon.png) dans la barre d'outils de Bonita Studio
1. Dans l'angle supérieur droit de la fenêtre, cliquez sur le menu déroulant **Utilisateur**
1. Sélectionnez **Administrateur**
1. Cliquez sur l'onglet **Applications**
1. Cliquez sur le bouton **Nouveau**
1. Configurez l'application :
   - Nom affiché : _Claims_
   - URL : _claims_
   - Version : _1.0_
   - Profils : _User_
   - Description : _Claims management application_
1. Cliquez sur le bouton **Créer**

   ![Création d'une application](images/getting-started-tutorial/create-application/create-application.gif)<!--{.img-responsive .img-thumbnail}-->

Vous devez maintenant modifier l'application pour ajouter la page d'application créée précédemment :
1. Cliquez sur l'icône **...** dans la colonne **Actions** 
1. Dans la section **Pages**, cliquez sur le bouton **Ajouter**
1. Dans la liste déroulante, sélectionnez _custompage_claimsList - claimsList_
1. Dans **URL** saisissez : _claims-list_
1. Cliquez sur le bouton **Ajouter**
1. Dans la liste des pages, cliquez sur l'**icône maison** pour définir claims-list comme page d'accueil et supprimer l'accueil par défaut
1. Nous avons créé une application très simple, avec une seule page, nous n'avons donc pas besoin de définir un menu de navigation

   ![Ajout d'une page à l'application](images/getting-started-tutorial/create-application/add-page-to-application.gif)<!--{.img-responsive .img-thumbnail}-->

Vous pouvez maintenant cliquer sur l'URL de l'application et vous verrez la page d'application s'afficher (elle utilise le layout et le thème par défaut).

Félicitations ! Vous avez créé avec succès votre premier processus et votre première application avec Bonita.

Si vous souhaitez en savoir plus sur les composants et les concepts de Bonita, nous vous recommandons le [Tutoriel Bonita Camp](https://www.youtube.com/playlist?list=PLvvoQatxaHOPSATzZe-zPh-LrSNGfpQEf). Bien sûr la [documentation officielle](https://documentation.bonitasoft.com) est également l'outil idéal pour en apprendre plus sur Bonita. Si vous préférez apprendre à l'aide d'exemples, vous en trouverez plusieurs sur le [site web de la communauté](https://community.bonitasoft.com/project?title=&field_type_tid=3869). Et enfin, n'oubliez pas que vous pouvez toujours demander de l'aide et [poser des questions à la communauté Bonita](https://community.bonitasoft.com/questions-and-answers/).

# Cr�er une application

La cr�ation de l'application est l'�tape finale de ce tutoriel de d�marrage.

Mais avant de cr�er r�ellement l'application, nous devons d�ployer notre page d'application dans le Portail Bonita :
1. Dans le menu Bonita Studio, cliquez sur **File > Deploy**
1. Cliquez sur le bouton **Select all** pour �tre certain(e) de tout d�ployer : organisation test, mod�le de donn�es m�tier, d�finition de processus, page d'application
1. V�rifiez que la case **Clean BDM database before deployment** n'est pas coch�e, car nous souhaitons conserver nos donn�es pour le test
1. Cliquez sur le bouton **Deploy**
1. Dans la fen�tre contextuelle **Deploy status**, cliquez sur le bouton **Close**

   ![Project deployment](images/getting-started-tutorial/create-application/project-deployment.gif)<!--{.img-responsive .img-thumbnail}-->

� pr�sent, nous sommes pr�ts � cr�er r�ellement l'application. Dans la Bonita Community Edition, le moyen le plus simple de cr�er une application est d'utiliser le Portail Bonita :
1. Cliquez sur l'ic�ne du Portail ![Portal icon](images/getting-started-tutorial/create-application/portal-icon.png) dans la barre d'outils de Bonita Studio
1. Dans l'angle sup�rieur droit de la fen�tre, cliquez sur le menu d�roulant **User**
1. S�lectionnez **Administrator**
1. Cliquez sur l'onglet **Applications**
1. Cliquez sur le bouton **New**
1. Configurez l'application :
   - Display name : _Claims_
   - URL : _claims_
   - Version : _1.0_
   - Profile : _User_
   - Description : _Claims management application_
1. Cliquez sur le bouton **Create**

   ![Create an application](images/getting-started-tutorial/create-application/create-application.gif)<!--{.img-responsive .img-thumbnail}-->

Vous devez maintenant modifier l'application pour ajouter la page d'application cr��e pr�c�demment :
1. Cliquez sur l'ic�ne **...** dans la colonne **Actions** 
1. Dans la section **Pages**, cliquez sur le bouton **Add**
1. Dans la liste d�roulante, s�lectionnez _custompage_claimsList - claimsList_
1. Dans **URL** saisissez : _claims-list_
1. Cliquez sur le bouton **Add**
1. Dans la liste des pages, cliquez sur **home icon** pour d�finir claims-list comme page d'accueil et supprimer l'accueil par d�faut
1. Nous avons cr�� une application tr�s simple, avec une seule page, nous n'avons donc pas besoin de d�finir un menu de navigation

   ![Add page to application](images/getting-started-tutorial/create-application/add-page-to-application.gif)<!--{.img-responsive .img-thumbnail}-->

Vous pouvez maintenant cliquer sur l'URL de l'application et vous verrez la page d'application s'afficher dans le format d'application par d�faut.

F�licitations ! Vous avez cr�� avec succ�s votre premier processus et votre premi�re application avec Bonita.

Si vous souhaitez en savoir plus sur les composants et les concepts de Bonita, nous vous recommandons le [Tutoriel Bonita Camp](https://www.youtube.com/playlist?list=PLvvoQatxaHOMHRiP7hFayNXTJNdxIEiYp). Bien s�r la [documentation officielle](https://documentation.bonitasoft.com) est �galement l'outil id�al pour en apprendre plus sur Bonita. Si vous pr�f�rez apprendre � l'aide d'exemples, vous en trouverez plusieurs sur le [site web de la communaut�](https://community.bonitasoft.com/project?title=&field_type_tid=3869). Et enfin, n'oubliez pas que vous pouvez toujours demander de l'aide et [poser des questions � la communaut� Bonita](https://community.bonitasoft.com/questions-and-answers/).

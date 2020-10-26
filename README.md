# Getting started: workspace et fichier .bos

## Description
Ce répertoire fournit les ressources pour Bonita Getting Started en français.
Le Getting Started tutorial en anglais est disponible dans la [documentation](https://documentation.bonitasoft.com/bonita//_getting-started-tutorial).

## Compatibilité
Cet exemple a été réalisé avec Bonita 7.10.3 Community Edition.

Il est compatible avec toutes les éditions de Bonita, Community et Enterprise et devrait être compatible avec les versions futures de la solution.

## Artifacts fournis
Vous pouvez récupérer le fichier .bos depuis la [section de release du Getting started tutorial sur GitHub](https://github.com/Bonitasoft-Community/getting-started-tutorial/releases/latest). Ce fichier .bos inclut :
* Le diagramme du processus avec la définition de processus
* Le modèle de données métier (BDM)
* Les formulaires d'instantiation et de tâches
* La page d'application

**Note :** ce fichier est en version anglaise.
{: .note}


## Importer la solution dans Bonita Studio
Pour importer la solution dans Bonita Studio
* Allez à **Fichier > Importer > Archive BOS...** dans le menu du Studio 
* Cliquez sur le bouton **Parcourir...** et sélectionnez le fichier _claims-management.bos_ file
* Cliquez sur **Importer**

<div class="panel panel-warning">
**Warning**
{: .panel-heading}
  <div class="panel-body">

ATTENTION: A l'import de _claims-management.bos_ dans votre Studio, si des artéfacts (BDM, diagrammes, ...) avec des noms identiques existent déjà, le Studio vous demandera si vous voulez les écraser. 
C'est pourquoi avec l'Edition Community il est préférable de faire cet import dans une installation différente du Studio Bonita. Avec l'Edition Enterprise nous vous recommandons d'importer l'archive BOS dans un nouveau projet.

  </div>
</div>

**Note :** vous pouvez également cloner le répertoire dans l'Edition Bonita Enterprise avec l'intégration Git.
{: .note}

## Déploiement
Cliquez sur **Fichier > Déployer** dans le menu Bonita Studio pour déployer tous les artéfacts et ouvrir l'application ou la page d'accueil du Portail Bonita. 

## Contenu du répertoire Git et résultat
En suivant le [Bonita getting started](https://github.com/Bonitasoft-Community/getting-started-fr/blob/master/index.md) de ce répertoire, vous devriez être capable de créer une application correspondant au workspace proposé dans le contenu du répertoire Git contenant la solution.

## Suivi des problèmes
Utilisez l'issue tracker de GitHub [GitHub issue tracker](https://github.com/Bonitasoft-Community/getting-started-fr/issues) pour remonter des problèmes sur ce Getting Started Tutoriel.



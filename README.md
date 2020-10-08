# Getting started: workspace et fichier .bos

## Description
Ce répertoire fournit les ressources pour Bonita Getting Started en français.
Le Getting Started tutorial en anglais est disponible dans la [documentation](https://documentation.bonitasoft.com/bonita//_getting-started-tutorial).

## Compatibilité
Cet exemple a été réalisé avec Bonita 7.10.3 Community Edition.

Il est compatible avec toutes les éditions de Bonita, Community et Enterprise et devrait être compatible avec les versions futures de la solution.

## Artifacts fournis
Vous pouvez récupérer le fichier .bos depuis la [section de release du Getting started tutorial  on GitHub](https://github.com/Bonitasoft-Community/getting-started-tutorial/releases/latest). Ce fichier .bos inclut :
* Le diagramme du processus avec la définition de processus
* Le modèle de données métier (BDM)
* Les formulaires d'instantiation et de tâches
* La page d'application

## Importing the solution in Studio
To import the solution in Bonita Studio:
* Go to **File > Import > BOS archive...** Studio menu
* Click on **Browse...** button and select _claims-management.bos_ file
* Click on **Import** button

WARNING: When you import _claims-management.bos_ in your Studio, if some artifacts (BDM, diagrams...) with identical names already exsit, Studio will ask you if you want to override them. On Community Edition you might want to do that in a separated installation of Bonita Studio. With Enterprise Edition you probably want to import the bos file content to a new project.

Note: alternatively you can clone this repository in Enterprise Edition using Git integration.

## Deployment
Click on **File > Deploy** Bonita Studio menu to deploy all artifacts and open the application or the Portal homepage. For more details refer to [Bonita getting started](https://documentation.bonitasoft.com/bonita//_getting-started-tutorial).

## Issues tracker
Use [GitHub issue tracker](https://github.com/Bonitasoft-Community/getting-started-turorial/issues) to report issues.

## Content of the Git repository
If you follow the [Bonita getting started](https://documentation.bonitasoft.com/bonita//_getting-started-tutorial) you should end up with a workspace just like the content of this Git repository.


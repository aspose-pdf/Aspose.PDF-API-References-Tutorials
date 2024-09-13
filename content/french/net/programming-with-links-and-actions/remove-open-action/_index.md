---
title: Supprimer l'action ouverte
linktitle: Supprimer l'action ouverte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Supprimez facilement les actions ouvertes des PDF à l'aide d'Aspose.PDF pour .NET ! Un tutoriel simple avec des instructions étape par étape pour une gestion efficace des PDF.
type: docs
weight: 80
url: /fr/net/programming-with-links-and-actions/remove-open-action/
---
## Introduction

Dans ce didacticiel, nous allons parcourir les étapes simples nécessaires pour supprimer une action d'ouverture d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous serez surpris de la simplicité de cette procédure et, à la fin, vous vous sentirez comme un pro du PDF ! Passons directement aux prérequis.

## Prérequis

Avant de commencer, vous aurez besoin de quelques éléments en place :

1. Compréhension de base de C# : la familiarité avec le langage de programmation C# vous aidera à naviguer facilement dans les extraits de code.
2. Visual Studio : assurez-vous d'avoir installé Visual Studio. Il s'agit de l'IDE le plus courant pour le développement .NET.
3.  Aspose.PDF pour .NET : vous aurez besoin de cette bibliothèque à portée de main. Vous pouvez la télécharger[ici](https://releases.aspose.com/pdf/net/). 
4. .NET Framework : assurez-vous d’avoir configuré votre projet pour utiliser .NET Framework (la version 4.0 ou ultérieure est recommandée).
5. Un fichier PDF avec des actions ouvertes : c'est le document sur lequel nous allons travailler. Vous pouvez en créer un ou télécharger un exemple pour vous entraîner.

Une fois ces bases posées, vous êtes prêt à vous lancer ! Importons maintenant les packages nécessaires pour commencer à coder.

## Paquets d'importation

Pour commencer à coder, vous devrez inclure certains packages essentiels dans votre projet. C'est ainsi que vous posez les bases des opérations que vous effectuerez sur les fichiers PDF. Voici ce que vous devez faire :

### Ouvrez votre projet

Ouvrez votre projet .NET dans Visual Studio où vous souhaitez effectuer les opérations.

### Ajouter la bibliothèque Aspose.PDF

Vous devrez ajouter la bibliothèque Aspose.PDF à votre projet. Vous pouvez le faire facilement via le gestionnaire de packages NuGet. Recherchez simplement Aspose.PDF et installez la dernière version stable.

### Inclure les espaces de noms nécessaires

En haut de votre fichier C#, vous devez importer l'espace de noms Aspose.PDF. Cela permet à votre code de savoir que vous allez travailler avec les fonctionnalités PDF offertes par Aspose. Voici ce que vous devez ajouter :

```csharp
using System.IO;
using Aspose.Pdf;
using System;
```

Maintenant que vous êtes prêt et configuré, passons aux choses sérieuses : supprimer les actions ouvertes d'un document PDF.

## Étape 1 : Définir le répertoire des documents

Tout d'abord, vous devez spécifier l'emplacement de votre fichier PDF. Considérez cela comme la configuration de votre espace de travail. Voici comment procéder :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où votre PDF est stocké. Par exemple :

```csharp
string dataDir = "C:\\Documents\\";
```

Ceci prépare le terrain pour les prochaines étapes. 

## Étape 2 : Ouvrir le document PDF

Ensuite, chargeons le document PDF dans votre application. C'est là que la magie commence à opérer ! Utilisez le code suivant :

```csharp
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

 Dans cette étape, nous demandons à notre application de créer un nouveau`Document` objet qui représente le fichier PDF nommé « RemoveOpenAction.pdf ». Assurez-vous que ce fichier existe dans votre répertoire spécifié !

## Étape 3 : Supprimer l'action ouverte

Vient maintenant la partie intéressante : supprimer l'action d'ouverture de votre document. Vous pouvez le faire en une seule ligne de code. Voici comment procéder :

```csharp
document.OpenAction = null;
```

Cette ligne indique essentiellement au document qu'il n'y a plus d'action ouverte définie. C'est comme si vous donniez un nouveau départ à votre PDF juste avant de l'enregistrer !

## Étape 4 : Enregistrer le document mis à jour

Après avoir supprimé l'action d'ouverture, vous souhaiterez enregistrer vos modifications. Voici comment enregistrer le document mis à jour dans votre répertoire :

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document.Save(dataDir);
```

Ce code va enregistrer le document modifié sous le nom « RemoveOpenAction_out.pdf » dans le même répertoire. Vous avez en fait créé une nouvelle version de votre PDF exempte d'actions indésirables !

## Étape 5 : Confirmer le succès

Pour faire savoir à tout le monde que l'opération a réussi, vous pouvez imprimer un message de confirmation sur la console. Ajoutez simplement la ligne suivante pour bien conclure :

```csharp
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir);
```

Cette étape n'est pas strictement nécessaire, mais il est agréable d'avoir une clôture après avoir exécuté vos opérations. Vous l'avez fait ! Vous avez supprimé avec succès l'action d'ouverture d'un document PDF.

## Conclusion

Et voilà ! Avec seulement quelques lignes de code C# et la puissance d'Aspose.PDF pour .NET, vous avez simplifié votre PDF en supprimant une action d'ouverture. La gestion des documents n'est pas aussi compliquée qu'elle le paraît. En maîtrisant des outils comme Aspose, vous pouvez prendre en charge vos fichiers PDF et les faire travailler plus efficacement pour vous, et non l'inverse.

## FAQ

### Quelles sont les actions ouvertes dans les fichiers PDF ?
Les actions d'ouverture sont des commandes exécutées lors de l'ouverture d'un PDF, comme la lecture d'un son ou la navigation vers une page Web.

### Dois-je payer pour Aspose.PDF pour .NET ?
 Aspose propose un essai gratuit. Vous pouvez le télécharger[ici](https://releases.aspose.com/).

### Puis-je supprimer plusieurs actions d’ouverture d’un PDF ?
 Oui, vous pouvez définir le`OpenAction` propriété à`null` pour supprimer toutes les actions ouvertes.

### Comment tester si la suppression de l'action d'ouverture a fonctionné ?
Ouvrez le fichier PDF enregistré et vérifiez si des actions précédemment définies se produisent. Si ce n'est pas le cas, vous avez réussi !

### Où puis-je trouver de l’aide si je rencontre un problème ?
 Visitez le forum Aspose pour obtenir de l'aide sur les problèmes liés au PDF[ici](https://forum.aspose.com/c/pdf/10).
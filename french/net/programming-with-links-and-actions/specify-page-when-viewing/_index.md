---
title: Spécifier la page lors de la visualisation
linktitle: Spécifier la page lors de la visualisation
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à spécifier une page lors de la visualisation d'un PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-links-and-actions/specify-page-when-viewing/
---

Apprenez à spécifier une page lors de l'affichage d'un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.

## Étape 1 : Configurer l'environnement

Assurez-vous d'avoir configuré votre environnement de développement avec un projet C# et les références Aspose.PDF appropriées.

## Étape 2 : Chargement du fichier PDF

Définissez le chemin du répertoire de vos documents et téléchargez le fichier PDF à l'aide du code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le fichier PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
```

## Étape 3 : Spécifier la page cible

Obtenez l'instance de page cible à l'aide du code suivant :

```csharp
Page page2 = doc.Pages[2];
```

 Vous pouvez régler l'indice`[2]` pour sélectionner la page souhaitée.

## Étape 4 : configuration du paramètre de zoom

Créez une variable pour définir le facteur de zoom de la page cible :

```csharp
double zoom = 1;
```

Vous pouvez ajuster la valeur du zoom en fonction de vos besoins.

## Étape 5 : Créer l'action de navigation

Créez une instance de l'action de navigation à l'aide de la page cible spécifiée :

```csharp
GoToAction action = new GoToAction(doc.Pages[2]);
```

## Étape 6 : Définition de la destination

Définissez la destination pour accéder à la page cible à l'aide des coordonnées et du zoom :

```csharp
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
```

## Étape 7 : Configuration de l'action d'ouverture de document

Définissez l'action d'ouverture de document avec l'action de navigation créée :

```csharp
doc. OpenAction = action;
```

## Étape 8 : Enregistrer le document mis à jour

 Enregistrez le document mis à jour à l'aide de la`Save` méthode:

```csharp
doc.Save(dataDir + "goto2page_out.pdf");
```

### Exemple de code source pour Spécifier la page lors de l'affichage à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le fichier PDF
Document doc = new Document(dataDir + "SpecifyPageWhenViewing.pdf");
// Obtenir l'instance de la deuxième page du document
Page page2 = doc.Pages[2];
// Créez la variable pour définir le facteur de zoom de la page cible
double zoom = 1;
// Créer une instance GoToAction
GoToAction action = new GoToAction(doc.Pages[2]);
// Aller à la page 2
action.Destination = new XYZExplicitDestination(page2, 0, page2.Rect.Height, zoom);
// Définir l'action d'ouverture du document
doc.OpenAction = action;
// Enregistrer le document mis à jour
doc.Save(dataDir + "goto2page_out.pdf");
```

## Conclusion

Félicitation ! Vous savez maintenant comment spécifier une page lors de l'affichage d'un PDF à l'aide d'Aspose.PDF pour .NET. Utilisez ces connaissances pour personnaliser l'expérience de visualisation de l'utilisateur dans vos documents PDF.

Maintenant que vous avez terminé ce guide, vous pouvez appliquer ces concepts à vos propres projets et explorer davantage les fonctionnalités offertes par Aspose.PDF pour .NET.
---
title: Hériter du zoom
linktitle: Hériter du zoom
second_title: Référence de l'API Aspose.PDF pour .NET
description: Bénéficiez facilement du zoom des signets dans vos fichiers PDF avec Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-bookmarks/inherit-zoom/
---

L'héritage du zoom dans un document PDF vous permet de spécifier un niveau de zoom par défaut pour les signets. Avec Aspose.PDF pour .NET, vous pouvez facilement hériter du zoom en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF dont vous souhaitez hériter du zoom. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF sur lequel nous voulons hériter du zoom à l'aide du code suivant :

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 4 : Obtenir la collection de signets

 Dans cette étape, nous obtiendrons la collection de signets ou de repères du document en utilisant le`Outlines` propriété de la`doc` objet. Voici le code correspondant :

```csharp
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
```

## Étape 5 : Définir le niveau de zoom

 Nous allons maintenant régler le niveau de zoom en créant un`XYZExplicitDestination` objet avec les coordonnées x, y et z spécifiées. Ici on utilise les coordonnées (100, 100, 0) avec un zoom de 2. Voici le code correspondant :

```csharp
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
```

## Étape 6 : Ajouter un niveau de zoom aux signets

 Dans cette étape, nous ajoutons le`XYZExplicitDestination` objet en tant qu'action aux signets du`item` collection. Voici le code correspondant :

```csharp
item. Action = new GoToAction(dest);
```

## Étape 7 : Ajouter les signets mis à jour au document

 Enfin, nous ajoutons les signets mis à jour à la collection de signets du document à l'aide de la commande`Add` méthode de la`doc.Outlines` objet. Voici le code correspondant :

```csharp
doc. Outlines. Add(item);
```

## Étape 8 : Enregistrer le fichier mis à jour

Maintenant, enregistrons le fichier PDF mis à jour en utilisant le`Save` méthode de la`doc` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "InheritZoom_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour Inherit Zoom à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document doc = new Document(dataDir + "input.pdf");
// Obtenir la collection de contours / signets du fichier PDF
OutlineItemCollection item = new OutlineItemCollection(doc.Outlines);
// Définir le niveau de zoom sur 0
XYZExplicitDestination dest = new XYZExplicitDestination(2, 100, 100, 0);
// Ajouter XYZExplicitDestination en tant qu'action aux contours de la collection de PDF
item.Action = new GoToAction(dest);
// Ajouter un élément à la collection de contours du fichier PDF
doc.Outlines.Add(item);
dataDir = dataDir + "InheritZoom_out.pdf";
// Enregistrer la sortie
doc.Save(dataDir);
Console.WriteLine("\nBookmarks updated successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez maintenant un guide étape par étape pour hériter du zoom avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour spécifier un niveau de zoom par défaut pour les signets dans vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation des signets.
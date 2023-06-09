---
title: Développer les signets
linktitle: Développer les signets
second_title: Référence de l'API Aspose.PDF pour .NET
description: Développez facilement les signets de vos fichiers PDF pour une navigation améliorée avec Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-bookmarks/expand-bookmarks/
---

L'expansion des signets dans un document PDF affichera tous les signets ouverts par défaut. Avec Aspose.PDF pour .NET, vous pouvez facilement étendre les signets en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF dont vous souhaitez développer les signets. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF dont nous voulons développer les signets en utilisant le code suivant :

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 4 : Définir le mode d'affichage de la page

 Dans cette étape, nous allons définir le mode d'affichage de la page pour afficher les signets par défaut. Nous utilisons le`PageMode` propriété de la`doc`objet pour définir le mode de page souhaité. Voici le code correspondant :

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## Étape 5 : Parcourir les signets et les développer

 Nous allons maintenant parcourir chaque élément de signet dans la collection de signets du document et définir l'état ouvert de chaque élément sur`true` pour les développer par défaut. Voici le code correspondant :

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## Étape 6 : Enregistrer le fichier mis à jour

 Enfin, nous enregistrons le fichier PDF mis à jour à l'aide de la`Save` méthode de la`doc` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour Expand Bookmarks à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document doc = new Document(dataDir + "input.pdf");
// Définir le mode d'affichage de la page, c'est-à-dire afficher les vignettes, le plein écran, afficher le panneau de pièces jointes
doc.PageMode = PageMode.UseOutlines;
// Parcourez chaque élément Ouline dans la collection de contours du fichier PDF
foreach (OutlineItemCollection item in doc.Outlines)
{
	// Définir le statut d'ouverture pour l'élément de plan
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// Enregistrer la sortie
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous disposez maintenant d'un guide étape par étape pour développer des signets avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour afficher tous les signets par défaut dans vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation des signets.
---
title: Ajouter un marque-page
linktitle: Ajouter un marque-page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Ajoutez facilement des signets à vos fichiers PDF pour une navigation améliorée avec Aspose.PDF pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/add-bookmark/
---

L'ajout de signets dans un document PDF permet une navigation facile et rapide. Avec Aspose.PDF pour .NET, vous pouvez facilement ajouter un signet en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF auquel vous souhaitez ajouter un signet. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF auquel nous voulons ajouter un signet en utilisant le code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## Étape 4 : Créer un objet de signet

 Dans cette étape, nous allons créer un objet signet en utilisant`OutlineItemCollection` class et définissez ses propriétés telles que le titre, l'attribut italique, l'attribut gras et l'action à exécuter lorsque vous cliquez dessus. Voici le code correspondant :

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## Étape 5 : Ajouter un signet au document

 Enfin, nous ajoutons le signet créé à la collection de signets du document à l'aide de la`Add` méthode de la`Outlines` propriété. Voici le code correspondant :

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Exemple de code source pour Ajouter un signet à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// Créer un objet signet
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// Définir le numéro de la page de destination
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// Ajoutez un signet dans la collection de plans du document.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// Enregistrer la sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez maintenant un guide étape par étape pour ajouter un signet en utilisant Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour améliorer la navigation dans vos documents PDF en ajoutant des signets personnalisés.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation des signets.
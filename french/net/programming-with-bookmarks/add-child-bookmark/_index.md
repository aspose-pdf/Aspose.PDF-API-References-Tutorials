---
title: Ajouter un signet enfant
linktitle: Ajouter un signet enfant
second_title: Référence de l'API Aspose.PDF pour .NET
description: Ajoutez facilement un signet enfant à vos fichiers PDF pour une navigation plus organisée avec Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-bookmarks/add-child-bookmark/
---

L'ajout de signets enfants à un document PDF permet une organisation et une navigation plus structurées. Avec Aspose.PDF pour .NET, vous pouvez facilement ajouter un sous-signet en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF auquel vous souhaitez ajouter un sous-signet. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF auquel nous voulons ajouter un sous-signet en utilisant le code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Étape 4 : Créer un objet de signet parent

 Dans cette étape, nous allons créer un objet de signet parent en utilisant le`OutlineItemCollection` classe et définissez ses propriétés telles que le titre, l'attribut italique et l'attribut gras. Voici le code correspondant :

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Étape 5 : créer un objet de signet enfant

Dans cette étape, nous allons recréer un objet sous-signet en utilisant le`OutlineItemCollection` classe et définissez ses propriétés. Voici le code correspondant :

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Étape 6 : Ajoutez le sous-favori au favori parent

 Enfin, nous ajoutons le sous-signet créé à la collection de sous-signets du signet parent à l'aide de la`Add` méthode de l'objet parent. Voici le code correspondant :

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Étape 7 : Ajouter le signet parent à la collection de signets du document

 Enfin, nous ajoutons le signet parent à la collection de signets du document à l'aide de la`Add` méthode de la`Outlines` propriété. Voici le code correspondant :

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Exemple de code source pour Ajouter un signet enfant à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Créer un objet de signet parent
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Créer un objet signet enfant
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Ajouter un signet enfant dans la collection du signet parent
pdfOutline.Add(pdfChildOutline);
// Ajoutez un signet parent dans la collection de plans du document.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Enregistrer la sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez maintenant un guide étape par étape pour ajouter un sous-signet avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour organiser et structurer vos signets dans vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation des signets.
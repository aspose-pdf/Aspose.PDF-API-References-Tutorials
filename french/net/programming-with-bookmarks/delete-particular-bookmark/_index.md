---
title: Supprimer un signet particulier
linktitle: Supprimer un signet particulier
second_title: Référence de l'API Aspose.PDF pour .NET
description: Supprimez facilement un signet particulier de vos fichiers PDF avec Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-bookmarks/delete-particular-bookmark/
---

Il peut être nécessaire de supprimer un signet particulier d'un document PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement supprimer un signet particulier en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF à partir duquel vous souhaitez supprimer un signet particulier. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF dont nous souhaitons supprimer un marque-page à l'aide du code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
```

## Étape 4 : Supprimer un marque-page particulier

 Dans cette étape, nous supprimons un signet particulier à l'aide de la`Delete` méthode de la`Outlines` propriété. Nous précisons le titre du signet à supprimer. Voici le code correspondant :

```csharp
pdfDocument.Outlines.Delete("Child Outline");
```

## Étape 5 : Enregistrez le fichier mis à jour

 Enfin, nous enregistrons le fichier PDF mis à jour à l'aide de la`Save` méthode de la`pdfDocument` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour supprimer un signet particulier à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
// Supprimer un plan particulier par titre
pdfDocument.Outlines.Delete("Child Outline");
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
// Enregistrer le fichier mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular bookmark deleted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez maintenant un guide étape par étape pour supprimer un signet particulier avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour cibler et supprimer des signets spécifiques de vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation des signets.
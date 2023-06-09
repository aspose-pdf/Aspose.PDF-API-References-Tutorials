---
title: Supprimer tous les signets
linktitle: Supprimer tous les signets
second_title: Référence de l'API Aspose.PDF pour .NET
description: Supprimez facilement tous les signets de vos fichiers PDF avec Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-bookmarks/delete-all-bookmarks/
---

# Supprimer tous les signets avec Aspose.PDF pour .NET

La suppression des signets d'un document PDF peut être nécessaire dans certains cas. Avec Aspose.PDF pour .NET, vous pouvez facilement supprimer tous les signets en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF dont vous souhaitez supprimer les signets. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF dont nous voulons supprimer les marque-pages en utilisant le code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## Étape 4 : Supprimer tous les signets

 Dans cette étape, nous supprimons tous les signets du document à l'aide de la`Delete` méthode de la`Outlines` propriété. Voici le code correspondant :

```csharp
pdfDocument.Outlines.Delete();
```

## Étape 5 : Enregistrez le fichier mis à jour

 Enfin, nous enregistrons le fichier PDF mis à jour à l'aide de la`Save` méthode de la`pdfDocument` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour supprimer tous les signets à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Supprimer tous les signets
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Enregistrer le fichier mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez maintenant un guide étape par étape pour supprimer tous les signets avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour nettoyer vos documents PDF en supprimant tous les signets existants.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation des signets.
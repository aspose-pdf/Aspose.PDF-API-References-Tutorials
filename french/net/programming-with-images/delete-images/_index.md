---
title: Supprimer des images
linktitle: Supprimer des images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Supprimez facilement des images d'un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-images/delete-images/
---

Ce guide vous expliquera étape par étape comment supprimer des images d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le répertoire correct pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## Étape 3 : Supprimer une image spécifique

 Dans cette étape, nous allons supprimer une image spécifique d'une page particulière. Utilisez le`Delete` méthode de la ressource de la page`Images` objet pour supprimer l'image. Dans l'exemple ci-dessous, nous supprimons l'image avec l'index 1 de la première page.

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## Étape 4 : Enregistrer le fichier PDF mis à jour

 Enregistrez le fichier PDF mis à jour à l'aide de`Save` méthode de la`pdfDocument` objet. Spécifiez le chemin de sortie du fichier PDF.

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour supprimer des images à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
//Supprimer une image particulière
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// Enregistrer le fichier PDF mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Félicitation ! Vous avez supprimé avec succès des images d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le fichier PDF mis à jour est enregistré dans le répertoire spécifié. Vous pouvez maintenant utiliser ce fichier PDF sans les images supprimées.
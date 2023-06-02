---
title: Supprimer une annotation particulière
linktitle: Supprimer une annotation particulière
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à supprimer une annotation particulière d'un document PDF en utilisant Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 50
url: /fr/net/annotations/deleteparticularannotation/
---
Dans ce didacticiel, nous allons vous montrer comment utiliser Aspose.PDF pour .NET pour supprimer une annotation particulière d'un fichier PDF à l'aide de C#.

Suivez les étapes ci-dessous pour montrer comment supprimer une annotation particulière avec Aspose.PDF pour .NET

## Étape 1 : Définissez le chemin du répertoire

Déclarez une variable pour contenir le chemin d'accès au fichier PDF contenant l'annotation à supprimer. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF

 Ouvrez le fichier PDF à l'aide de la`Document` classe dans Aspose.PDF pour .NET.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");
```

## Étape 3 : Obtenir la page pour supprimer l'annotation particulière

Supprimez l'annotation particulière en spécifiant son index et l'index de la page à laquelle elle appartient. Dans ce didacticiel, nous supprimons l'annotation située à l'index 1 sur la deuxième page du fichier PDF.

```csharp
pdfDocument.Pages[1].Annotations.Delete(1);
```
## Étape 4 : Enregistrer le document PDF mis à jour

Enregistrez le fichier PDF mis à jour dans un nouveau fichier avec un nom différent.

```csharp
dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```

## Étape 5 : Afficher un message pour supprimer une annotation particulière

Imprimez un message indiquant que l'annotation particulière a été supprimée et que le fichier PDF mis à jour a été enregistré.

```csharp
Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour supprimer une annotation particulière à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "DeleteParticularAnnotation.pdf");

// Supprimer une annotation particulière
pdfDocument.Pages[1].Annotations.Delete(1);

dataDir = dataDir + "DeleteParticularAnnotation_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);

Console.WriteLine("\nParticular annotation deleted successfully.\nFile saved at " + dataDir);
```

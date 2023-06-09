---
title: Image CGM en PDF
linktitle: Image CGM en PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez facilement une image CGM en PDF avec Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-images/cgm-image-to-pdf/
---

Ce guide étape par étape explique comment convertir une image CGM en PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le répertoire correct pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre fichier CGM.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Définir le fichier d'entrée et de sortie

 Définissez le nom du fichier d'entrée CGM et le nom du fichier de sortie PDF. Remplacer`"corvette.cgm"` avec le nom de votre fichier CGM, et mettez à jour`dataDir`avec le répertoire de sortie souhaité et le nom du fichier PDF.

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## Étape 3 : Convertir l'image CGM en PDF

 Utilisez le`Produce` méthode de`PdfProducer` pour convertir le fichier CGM au format PDF en utilisant`ImportFormat.Cgm`. Spécifiez le fichier d'entrée CGM et le fichier de sortie PDF.

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### Exemple de code source pour CGMImage au format PDF en utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
// Enregistrer le CGM au format PDF
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Félicitation ! Vous avez converti avec succès un fichier CGM en PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant utiliser le fichier PDF généré dans vos projets ou applications.
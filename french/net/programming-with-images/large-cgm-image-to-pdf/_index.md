---
title: Grande image CGM au format PDF
linktitle: Grande image CGM en PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Convertissez facilement une grande image CGM en PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 190
url: /fr/net/programming-with-images/large-cgm-image-to-pdf/
---

Dans ce didacticiel, nous allons parcourir un guide étape par étape sur la façon de convertir une grande image CGM en un fichier PDF à l'aide de la bibliothèque Aspose.PDF dans .NET. Le code source C# fourni illustre le processus de conversion d'un fichier CGM au format PDF, en spécifiant la taille de la page et en enregistrant le fichier de sortie. Nous vous expliquerons chaque étape en détail pour vous aider à bien comprendre le processus.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :
- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée dans votre projet.
- Un fichier image CGM que vous souhaitez convertir en PDF.

## Etape 1 : Mise en place du projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF dans votre projet.

## Étape 2 : Importer les espaces de noms nécessaires
Au début de votre fichier C#, importez les espaces de noms requis pour accéder aux classes et méthodes Aspose.PDF. Voici un exemple :
```csharp
using System;
using Aspose.Pdf;
using System.Drawing;
```

## Étape 3 : Initialisation des variables et des chemins
Avant d'effectuer la conversion, nous devons configurer les variables et les chemins nécessaires.
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
```
 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : Conversion de CGM en PDF
Pour convertir l'image CGM au format PDF, procédez comme suit :
1.  Créer une instance de`CgmImportOptions` classe.
```csharp
CgmImportOptions options = new CgmImportOptions();
```
2. Spécifiez les dimensions pour l'importation de la taille de la page.
```csharp
options. PageSize = new SizeF(1000, 1000);
```
Ici, nous définissons la taille de la page sur 1000x1000 pixels. Vous pouvez ajuster les dimensions selon vos besoins.
 3. Utilisez le`PdfProducer.Produce` méthode pour convertir le fichier CGM au format PDF.
```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```
4. Affichez un message de réussite avec le chemin où le fichier PDF est enregistré.
```csharp
Console.WriteLine("\nLarge CGM file converted to PDF successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour Large CGMImage au format PDF à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "LargeCGMImageToPDF_out.pdf";
// Créer une instance de CgmImportOptions
CgmImportOptions options = new CgmImportOptions();
// Spécifiez les dimensions pour l'importation de la taille de la page
options.PageSize = new SizeF(1000, 1000);
// Enregistrer le CGM au format PDF
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nLarge CGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## Conclusion
En suivant ce guide étape par étape, vous avez appris à convertir une grande image CGM en fichier PDF à l'aide de la bibliothèque Aspose.PDF dans .NET. Ce processus implique la configuration du projet, l'importation des espaces de noms nécessaires, l'initialisation des variables et des chemins et l'exécution de la conversion. Vous pouvez maintenant intégrer ce code dans vos propres projets et le modifier selon vos besoins spécifiques.
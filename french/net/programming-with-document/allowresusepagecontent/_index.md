---
title: Autoriser la réutilisation du contenu de la page
linktitle: Autoriser la réutilisation du contenu de la page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à optimiser les PDF en activant la fonctionnalité "Autoriser la réutilisation du contenu de la page" à l'aide d'Aspose.PDF pour .NET. Réduisez la taille des fichiers et améliorez les performances.
type: docs
weight: 50
url: /fr/net/programming-with-document/allowresusepagecontent/
---

Dans ce didacticiel, nous expliquerons comment activer la fonctionnalité "Autoriser la réutilisation du contenu de la page" à l'aide d'Aspose.PDF pour .NET. Cette fonction optimise le document PDF en réutilisant le contenu de la page, en réduisant la taille du fichier et en améliorant les performances. Suivez le guide étape par étape ci-dessous :

## Étape 1 : Chargez le document PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Étape 2 : Définissez l'option AllowReusePageContent

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## Étape 3 : Optimisez le document PDF

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Étape 4 : Enregistrer le document mis à jour

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## Étape 5 : Vérifiez la réduction de la taille du fichier

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

Toutes nos félicitations! Vous avez autorisé avec succès la réutilisation du contenu de la page dans votre document PDF.

### Exemple de code source pour Autoriser la réutilisation du contenu de la page à l'aide d'Aspose.PDF pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

// Définir l'option AllowReusePageContent
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};

Console.WriteLine("Start");

// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);

// Enregistrer le document mis à jour
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");

Console.WriteLine("Finished");

var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

Vous pouvez désormais optimiser efficacement vos documents PDF en autorisant la réutilisation du contenu des pages.

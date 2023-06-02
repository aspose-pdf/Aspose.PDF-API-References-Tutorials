---
title: Supprimer les flux inutilisés
linktitle: Supprimer les flux inutilisés
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à supprimer les flux inutilisés des fichiers PDF à l'aide d'Aspose.PDF pour .NET. Notre guide étape par étape.
type: docs
weight: 270
url: /fr/net/programming-with-document/removeunusedstreams/
---
Dans cet exemple, nous expliquerons comment supprimer les flux inutilisés des documents PDF à l'aide d'Aspose.PDF pour .NET. Nous fournirons un guide étape par étape sur la façon de procéder, y compris le code source complet avec des explications.

## Étape 1 : Le chemin d'accès au répertoire des documents

La première ligne du code définit le chemin d'accès au répertoire où se trouve votre document PDF. Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document

La ligne de code suivante ouvre le document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Étape 3 : Définir l'option RemoveUnusedStreams

L'étape suivante consiste à définir l'option RemoveUnusedStreams sur true. Cela supprimera tous les flux inutilisés du document PDF.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## Étape 4 : Optimisez le document PDF à l'aide d'OptimizationOptions

Maintenant que nous avons défini les options d'optimisation, nous pouvons optimiser le document PDF à l'aide de la ligne de code suivante.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Étape 5 : Enregistrer le document mis à jour

Enfin, nous pouvons enregistrer le document mis à jour en utilisant la méthode Save de la classe Document.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour supprimer les flux inutilisés à l'aide d'Aspose.PDF pour .NET

Vous trouverez ci-dessous l'exemple de code source permettant de supprimer les flux inutilisés à l'aide d'Aspose.PDF pour .NET.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Définir l'option RemoveUsedStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
```

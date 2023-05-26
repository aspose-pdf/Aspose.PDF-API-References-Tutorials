---
title: Réduire les documents
linktitle: Réduire les documents
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour réduire les documents PDF avec ce guide étape par étape.
type: docs
weight: 350
url: /fr/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et optimiser des documents PDF à l'aide de C#. Dans ce didacticiel, nous allons parcourir un exemple d'utilisation de Aspose.PDF pour réduire un document PDF.

## Étape 1 : Chargement du document PDF

 Pour réduire un document PDF, nous devons d'abord le charger dans notre application C# en utilisant Aspose.PDF. Dans le code ci-dessous, nous spécifions le chemin d'accès à notre document PDF et créons une nouvelle instance du`Document` classe.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## Étape 2 : Réduire le document PDF

 Une fois que nous avons chargé le document PDF, nous pouvons utiliser le`OptimizeResources` méthode de la`Document`classe pour optimiser le document et potentiellement réduire sa taille. Notez que cette méthode ne garantit pas la réduction du document, car certains documents PDF peuvent déjà être hautement optimisés.

```csharp
// Optimiser le document PDF. Notez, cependant, que cette méthode ne peut pas garantir la réduction du document
pdfDocument.OptimizeResources();
```

## Étape 3 : Enregistrer le document PDF mis à jour

 Après avoir optimisé le document PDF, nous pouvons enregistrer la version mise à jour dans un nouveau fichier à l'aide de la`Save` méthode de la`Document` classe. Dans le code ci-dessous, nous spécifions le chemin et le nom du fichier de sortie.

```csharp
// Spécifiez le chemin du fichier de sortie
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(outputFilePath);
```

### Exemple de code source pour réduire les documents à l'aide d'Aspose.PDF pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ouvrir le document
	Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
	// Optimiser le document PDF. Notez, cependant, que cette méthode ne peut pas garantir la réduction du document
	pdfDocument.OptimizeResources();
	dataDir = dataDir + "ShrinkDocument_out.pdf";
	// Enregistrer le document mis à jour
	pdfDocument.Save(dataDir);
	
```

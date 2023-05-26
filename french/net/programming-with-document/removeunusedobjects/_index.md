---
title: Supprimer les objets inutilisés
linktitle: Supprimer les objets inutilisés
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour supprimer les objets inutilisés des documents PDF avec ce guide étape par étape.
type: docs
weight: 260
url: /fr/net/programming-with-document/removeunusedobjects/
---
Si vous cherchez un moyen de supprimer les objets inutilisés dans vos documents PDF en utilisant Aspose.PDF pour .NET, vous êtes au bon endroit. Ce guide étape par étape vous montrera comment utiliser le code source C# fourni pour accomplir cette tâche.

## Étape 1 : Définissez le chemin du répertoire

Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents en remplaçant "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF

Ensuite, vous devez ouvrir le document PDF que vous souhaitez optimiser en utilisant le code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Étape 3 : Définir l'option RemoveUnusedObjects

Pour supprimer les objets inutilisés de votre document PDF, vous devez définir l'option RemoveUnusedObjects sur "true" comme suit :

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## Étape 4 : Optimisez le document PDF à l'aide d'OptimizationOptions

Maintenant, vous pouvez optimiser votre document PDF en utilisant la méthode OptimizeResources avec les options d'optimisation que vous venez de définir :

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Étape 5 : Enregistrer le document mis à jour

Enfin, vous pouvez enregistrer le document mis à jour avec le code suivant :

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

C'est ça! Vous avez supprimé avec succès les objets inutilisés de votre document PDF à l'aide d'Aspose.PDF pour .NET.

### Exemple de code source pour supprimer les objets inutilisés à l'aide d'Aspose.PDF pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ouvrir le document
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Définir l'option RemoveUsedObject
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedObjects = true
	};
	// Optimiser le document PDF à l'aide d'OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Enregistrer le document mis à jour
	pdfDocument.Save(dataDir);

```

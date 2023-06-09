---
title: Compter les artefacts
linktitle: Compter les artefacts
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à compter facilement les filigranes dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-stamps-and-watermarks/counting-artifacts/
---

Dans ce didacticiel, nous vous expliquerons étape par étape comment compter les artefacts dans un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour compter le nombre d'artefacts de "filigrane" sur une page spécifique du document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Chargement du document PDF

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : compter les artefacts

Maintenant que vous avez chargé le document PDF, vous pouvez compter les artefacts de type "filigrane" sur une page spécifique du document. Voici comment:

```csharp
// Initialiser le compteur
int count = 0;

// Parcourez tous les artefacts de la première page
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     // Si le sous-type d'artefact est "filigrane", incrémentez le compteur
     if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark)
         count++;
}

// Afficher le nombre d'artefacts de type "filigrane"
Console.WriteLine("The page contains " + count + " watermarks");
```

Le code ci-dessus parcourt tous les artefacts de la première page du document PDF et incrémente le compteur pour chaque artefact de type "filigrane" rencontré.

### Exemple de code source pour le comptage des artefacts à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

int count = 0;
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	// Si le type d'artefact est un filigrane, incréez le compteur
	if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark) count++;
}
Console.WriteLine("Page contains " + count + " watermarks");

```

## Conclusion

Félicitation ! Vous avez appris à compter les artefacts de "filigrane" dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour effectuer une analyse et un traitement spécifiques sur les artefacts de vos documents PDF.

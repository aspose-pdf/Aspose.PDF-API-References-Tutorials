---
title: Obtenir un filigrane
linktitle: Obtenir un filigrane
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire des filigranes de vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-stamps-and-watermarks/get-watermark/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment obtenir un filigrane à partir d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour parcourir les artefacts d'une page spécifique et obtenir le type, le texte et l'emplacement du filigrane.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Chargement du document PDF

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document PDF
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : Obtenir le filigrane

Maintenant que vous avez chargé le document PDF, vous pouvez parcourir les artefacts de page spécifiques pour obtenir les informations de filigrane. Voici comment:

```csharp
// Parcourez les artefacts et obtenez le sous-type, le texte et l'emplacement du filigrane
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Le code ci-dessus parcourt tous les artefacts de la première page du document PDF et affiche le sous-type, le texte et le rectangle (emplacement) de chaque filigrane rencontré.

### Exemple de code source pour Get Watermark en utilisant Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Parcourez et obtenez le type de baignoire, le texte et l'emplacement de l'artefact
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Conclusion

Félicitation ! Vous avez appris comment obtenir des informations de filigrane à partir d'un document PDF en utilisant Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour analyser et traiter les filigranes dans vos documents PDF.

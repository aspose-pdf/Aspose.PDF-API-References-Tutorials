---
title: Ajouter un tampon de page PDF
linktitle: Ajouter un tampon de page PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter facilement un tampon de page PDF à vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-stamps-and-watermarks/add-pdf-page-stamp/
---

Dans ce didacticiel, nous vous expliquerons étape par étape comment ajouter un tampon de page PDF à un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour ajouter un tampon personnalisé à une page spécifique du document PDF.

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
Document pdfDocument = new Document(dataDir + "PDFPageStamp.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : création du tampon de page

Maintenant que vous avez téléchargé le document PDF, vous pouvez créer le tampon de page à ajouter. Voici comment procéder :

```csharp
// Créer le tampon de page
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
```

Le code ci-dessus crée un nouveau tampon de page en utilisant la première page du document PDF.

## Étape 4 : Configuration des propriétés du tampon de page

Avant d'ajouter le tampon de page au document PDF, vous pouvez configurer diverses propriétés du tampon, telles que l'arrière-plan, la position, la rotation, etc. Voici comment :

```csharp
// Configurer les propriétés du tampon de page
pageStamp. Background = true;
pageStamp. XIndent = 100;
pageStamp. YIndent = 100;
pageStamp.Rotate = Rotate.on180;
```

Vous pouvez ajuster ces propriétés en fonction de vos besoins.

## Étape 5 : Ajouter le tampon de page au PDF

Maintenant que le tampon de page est prêt, vous pouvez l'ajouter à une page spécifique du document PDF. Voici comment:

```csharp
// Ajouter un tampon de page à une page spécifique
pdfDocument.Pages[1].AddStamp(pageStamp);
```

Le code ci-dessus ajoute le tampon de page à la première page du document PDF. Vous pouvez spécifier une autre page si nécessaire.

## Étape 6 : Enregistrer le document de sortie

Une fois que vous avez ajouté le tampon de page, vous pouvez enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
```

### Exemple de code source pour Ajouter un tampon PDFPage à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "PDFPageStamp.pdf");

// Créer un tampon de page
PdfPageStamp pageStamp = new PdfPageStamp(pdfDocument.Pages[1]);
pageStamp.Background = true;
pageStamp.XIndent = 100;
pageStamp.YIndent = 100;
pageStamp.Rotate = Rotation.on180;

// Ajouter un tampon à une page particulière
pdfDocument.Pages[1].AddStamp(pageStamp);
dataDir = dataDir + "PDFPageStamp_out.pdf";

// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nPdf page stamp added successfully.\nFile saved at " + dataDir);

```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

## Conclusion

Félicitation ! Vous avez appris à ajouter un tampon de page PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances à vos propres projets pour ajouter des tampons personnalisés à des pages spécifiques de vos documents PDF.

---
title: Créer un PDF avec une image balisée
linktitle: Créer un PDF avec une image balisée
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour créer un PDF avec une image balisée à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
Dans ce didacticiel, nous vous fournirons un guide étape par étape sur la façon de créer un document PDF avec une image balisée à l'aide d'Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de créer, manipuler et convertir des documents PDF par programme. En utilisant les fonctionnalités de structure de contenu balisé d'Aspose.PDF, vous pouvez ajouter des images balisées à votre document PDF.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont en place :

1. Visual Studio installé avec le framework .NET.
2. La bibliothèque Aspose.PDF pour .NET.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet dans Visual Studio et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Vous pouvez télécharger la bibliothèque depuis le site officiel d'Aspose et l'installer sur votre machine.

## Étape 2 : Importez les espaces de noms nécessaires

Dans votre fichier de code C#, importez les espaces de noms requis pour accéder aux classes et méthodes fournies par Aspose.PDF :

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Étape 3 : Création du document PDF avec une image balisée

Utilisez le code suivant pour créer un document PDF avec une image balisée :

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

Ce code crée un document PDF vide et ajoute une image balisée en utilisant les méthodes fournies par Aspose.PDF. L'image est spécifiée avec un texte alternatif, un titre et une balise.

## Étape 4 : Enregistrer le document PDF

Utilisez le code suivant pour enregistrer le document PDF :

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

Ce code enregistre le document PDF avec l'image balisée dans un fichier spécifié.

### Exemple de code source pour créer un PDF avec une image balisée à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// Ajouter une image avec une résolution de 300 DPI (par défaut)
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// Enregistrer le document PDF
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## Conclusion

Dans ce didacticiel, vous avez appris à créer un document PDF avec une image balisée à l'aide d'Aspose.PDF pour .NET. Les images balisées ajoutent des informations structurées supplémentaires à votre document PDF.

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

### FAQ

#### Q : Quel est l'objectif de créer un document PDF avec une image balisée à l'aide d'Aspose.PDF pour .NET ?

R : La création d'un document PDF avec une image balisée à l'aide d'Aspose.PDF pour .NET vous permet d'ajouter des images balisées au contenu du document. Les images balisées fournissent des informations structurées, telles que le texte alternatif et les titres, améliorant l'accessibilité et l'organisation.

#### Q : Comment la bibliothèque Aspose.PDF aide-t-elle à créer un document PDF avec une image balisée ?

: Aspose.PDF pour .NET est une bibliothèque robuste qui fournit des fonctionnalités pour créer, manipuler et convertir des documents PDF par programmation. Dans ce didacticiel, les fonctionnalités de structure de contenu balisé de la bibliothèque sont utilisées pour ajouter une image balisée au document PDF.

#### Q : Quelles sont les conditions préalables à la création d'un document PDF avec une image balisée à l'aide d'Aspose.PDF pour .NET ?

R : Avant de commencer, assurez-vous que Visual Studio est installé avec le framework .NET et que la bibliothèque Aspose.PDF pour .NET est référencée dans votre projet.

#### Q : Comment le code C# fourni crée-t-il un document PDF avec une image balisée ?

R : Le code montre comment créer un document PDF, définir un élément d'image balisé et l'ajouter au contenu du document. L'image balisée comprend un texte alternatif, un titre et une balise à l'aide des méthodes fournies par Aspose.PDF.

#### Q : Puis-je utiliser différents formats d'image pour l'image taguée ?

R : Oui, vous pouvez utiliser différents formats d'image pour l'image balisée, tels que JPEG, PNG, GIF, etc. L'exemple de code fourni dans le didacticiel utilise une image JPEG, mais vous pouvez la remplacer par le chemin d'accès à un fichier image dans votre format préféré.

#### Q : Comment le texte alternatif (texte alternatif) est-il utilisé dans les images balisées ?

 R : Le texte alternatif fournit une description textuelle de l'image, qui est lue à haute voix par les lecteurs d'écran pour les utilisateurs malvoyants. Dans le code fourni, le texte alternatif est défini à l'aide de la`AlternativeText` propriété de la`IllustrationElement` représentant l'image taguée.

####  Q : Comment fonctionne le`SetTitle` method contribute to the PDF document's tagged image?

 R : Le`SetTitle` La méthode définit le titre du contenu balisé du document PDF, fournissant un contexte supplémentaire pour l'image balisée. Ce titre peut aider à identifier le but ou le sujet du contenu balisé.

#### Q : Puis-je personnaliser le tag et le titre de l'image taguée ?

 R : Oui, vous pouvez personnaliser le tag et le titre de l'image taguée à l'aide de la`SetTag` et`Title` méthodes de la`IllustrationElement`. L'exemple de code montre comment définir la balise sur "Fig" et le titre sur "Image 1".

#### Q : Comment puis-je m'assurer que l'image taguée est accessible et conforme aux normes d'accessibilité ?

R : En utilisant les fonctionnalités de structure de contenu balisé d'Aspose.PDF et en fournissant un texte alternatif et d'autres informations pertinentes, vous contribuez à l'accessibilité de l'image balisée. Assurer la conformité aux normes d'accessibilité implique de suivre les meilleures pratiques pour le texte alternatif et la structure du document.

#### Q : Est-il possible d'ajouter plusieurs images balisées au même document PDF en utilisant des techniques similaires ?

 R : Oui, vous pouvez ajouter plusieurs images balisées au même document PDF en utilisant des techniques similaires. Vous créeriez des`IllustrationElement` instances pour chaque image taguée et personnalisez leurs propriétés selon vos besoins.
---
title: Incorporer la police lors de la création de documents
linktitle: Incorporer la police lors de la création de documents
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à incorporer une police lors de la création d'un document PDF à l'aide d'Aspose.PDF pour .NET. Assurez un affichage correct sur différents appareils.
type: docs
weight: 140
url: /fr/net/programming-with-document/embedfontwhiledoccreation/
---

Dans ce didacticiel, nous expliquerons comment incorporer une police lors de la création d'un document PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, modifier et manipuler des documents PDF par programmation. Cette bibliothèque fournit un large éventail de fonctionnalités pour travailler avec des documents PDF, y compris l'ajout de texte, d'images, de tableaux et bien plus encore. L'incorporation de polices lors de la création d'un document PDF est une exigence courante pour les développeurs qui souhaitent s'assurer que le document PDF s'affiche correctement sur différents appareils, que les polices requises soient installées ou non sur ces appareils.

## Étape 1 : Créer une nouvelle application de console C#
Pour commencer, créez une nouvelle application console C# dans Visual Studio. Vous pouvez le nommer comme bon vous semble. Une fois le projet créé, vous devez ajouter une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer l'espace de noms Aspose.PDF
Ajoutez la ligne de code suivante en haut de votre fichier C# pour importer l'espace de noms Aspose.PDF :

```csharp
using Aspose.Pdf;
```

## Étape 3 : instancier un objet PDF
Instanciez un objet Pdf en appelant son constructeur vide :

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Étape 4 : créer une section dans l'objet PDF
Créez une section dans l'objet Pdf :

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Étape 5 : Ajouter du texte à la section
Ajoutez du texte à la section :

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## Étape 6 : Définissez la police et intégrez-la
Définissez la police et intégrez-la :

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## Étape 7 : Enregistrez le document PDF
Une fois que vous avez intégré la police lors de la création du document PDF, vous devez enregistrer le document :

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);
```

### Exemple de code source pour intégrer une police lors de la création d'un document à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciez l'objet Pdf en appelant son constructeur vide
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Créer une section dans l'objet Pdf
Aspose.Pdf.Page page = doc.Pages.Add();

Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);

dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);
```

## Conclusion
Dans ce didacticiel, nous avons expliqué comment incorporer une police lors de la création d'un document PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF pour .NET fournit une API simple et facile à utiliser pour travailler avec des documents PDF, y compris l'ajout et l'incorporation de polices. L'intégration de polices lors de la création d'un document PDF est une étape importante pour garantir que le document s'affiche correctement sur différents appareils, que les polices requises soient installées ou non sur ces appareils.


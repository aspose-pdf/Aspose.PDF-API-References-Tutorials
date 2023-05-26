---
title: Créer une première approche de PDF multicouche
linktitle: Créer une première approche de PDF multicouche
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à créer des documents PDF multicouches à l'aide de la première approche avec Aspose.PDF pour .NET. Ajoutez du texte, des images et plus encore pour améliorer vos PDF.
type: docs
weight: 70
url: /fr/net/programming-with-document/createmultilayerpdffirstapproach/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de création d'un PDF multicouche en utilisant la première approche avec Aspose.PDF pour .NET. Cette approche vous permet d'ajouter plusieurs couches à votre document PDF. Suivez le guide étape par étape ci-dessous :

## Étape 1 : Initialiser le document PDF

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## Étape 2 : Ajouter une nouvelle page au document

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## Étape 3 : Ajouter un fragment de texte à la page

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## Étape 4 : Personnalisez le fragment de texte

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## Étape 5 : Ajouter une image à la page

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## Étape 6 : Ajouter une boîte flottante à la page

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## Étape 7 : Enregistrez le document PDF résultant

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Toutes nos félicitations! Vous avez créé avec succès un document PDF multicouche en utilisant la première approche avec Aspose.PDF pour .NET.

Exemple de code source pour la première approche de création de PDF multicouche à l'aide d'Aspose.PDF pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

Vous pouvez désormais créer des documents PDF multicouches en utilisant la première approche avec Aspose.PDF pour .NET.

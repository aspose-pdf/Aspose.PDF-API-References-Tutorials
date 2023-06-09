---
title: Image et numéro de page dans la section d'en-tête de pied de page en ligne
linktitle: Image et numéro de page dans la section d'en-tête de pied de page en ligne
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter une image et un numéro de page dans l'en-tête et le pied de page à l'aide de paragraphes en ligne avec Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment ajouter une image et un numéro de page dans la section d'en-tête et de pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous utiliserons le code source C # fourni pour créer une page, définir l'en-tête et le pied de page, ajouter une image et du texte à l'aide de paragraphes en ligne dans l'en-tête du document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Création du document PDF et de la page

La première étape consiste à créer un nouvel objet Document et une page dans le document PDF. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer un nouvel objet Document
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Créer une page dans le document
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Le code ci-dessus crée un nouvel objet Document et une page vide dans le document PDF.

## Étape 3 : Ajouter l'en-tête avec une image et du texte en ligne

Maintenant que la page est créée, nous pouvons ajouter une section d'en-tête avec une image et du texte à l'aide de paragraphes en ligne. Voici comment:

```csharp
// Créer une section d'en-tête
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Définir l'en-tête de la page
page. Header = header;

// Créer un objet TextFragment pour le premier texte en ligne
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Spécifiez la couleur du texte
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

//Créer un objet Image pour l'image
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Définir le chemin de l'image
image1.File = dataDir + "aspose-logo.jpg";

// Définir les dimensions de l'image
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indique que le premier texte en ligne est une image
image1.IsInLineParagraph = true;

// Créer un deuxième texte en ligne
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// Ajouter des éléments à l'en-tête
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

Le code ci-dessus crée une section d'en-tête, définit l'en-tête de page avec cette section, ajoute un TextFragment avec du texte en ligne et un objet Image en ligne.

## Étape 4 : Enregistrer le document PDF modifié

Une fois l'en-tête avec l'image et le texte en ligne ajoutés, nous pouvons enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrez le document PDF modifié
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour l'image et le numéro de page dans la section d'en-tête de pied de page en ligne à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciez un objet Document en appelant son constructeur vide
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Créer une page dans l'objet Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Créer une section d'en-tête du document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Définir l'en-tête du fichier PDF
page.Header = header;

// Créer un objet texte
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// Spécifiez la couleur
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Créer un objet image dans la section
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Définir le chemin du fichier image
image1.File = dataDir + "aspose-logo.jpg";

// Définir la largeur de l'image
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indiquez que le paragraphe InlineParagraph de seg1 est une image.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Enregistrer le PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusion

Félicitation ! Vous avez appris à ajouter une image et un numéro de page dans la section d'en-tête et de pied de page d'un document PDF à l'aide de paragraphes en ligne avec Aspose.PDF pour .NET. Vous pouvez désormais personnaliser l'en-tête et le pied de page de vos documents PDF de manière flexible.

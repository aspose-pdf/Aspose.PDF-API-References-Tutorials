---
title: Image et numéro de page dans la section d'en-tête de pied de page
linktitle: Image et numéro de page dans la section d'en-tête de pied de page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter une image et un numéro de page dans l'en-tête et le pied de page d'un document PDF avec Aspose.
type: docs
weight: 110
url: /fr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment ajouter une image et un numéro de page dans la section d'en-tête et de pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C # fourni pour créer une page, définir l'en-tête et le pied de page, ajouter une image à l'en-tête et du texte avec le numéro de page au pied de page du document PDF.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Créer une page dans le document
Aspose.Pdf.Page page = doc.Pages.Add();
```

Le code ci-dessus crée un nouvel objet Document et une page vide dans le document PDF.

## Étape 3 : Ajouter l'en-tête avec une image

Maintenant que la page est créée, nous pouvons ajouter une section d'en-tête avec une image. Voici comment:

```csharp
// Créer une section d'en-tête
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Définir l'en-tête de la page
page. Header = header;

// Créer un objet Image
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Définir le chemin de l'image
image1.File = dataDir + "aspose-logo.jpg";

// Ajouter l'image à l'en-tête de page du document PDF
header.Paragraphs.Add(image1);
```

Le code ci-dessus crée une section d'en-tête, définit l'en-tête de page avec cette section et ajoute une image à l'en-tête.

## Étape 4 : Ajouter le pied de page avec le numéro de page

Maintenant que l'en-tête est ajouté, nous pouvons ajouter une section de pied de page avec un numéro de page. Voici comment:

```csharp
// Créer une section de pied de page
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Définir le pied de page du document PDF
page. Footer = footer;

// Créer un objet TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Ajouter le texte avec le numéro de page au pied de page du document PDF
footer.Paragraphs.Add(txt);
```

Le code ci-dessus crée une section de pied de page, définit le pied de page de la page avec cette section et ajoute un TextFragment contenant le texte "Page : ($p of $P )"

  qui affiche le numéro de page.

## Étape 5 : Enregistrer le document PDF modifié

Une fois l'en-tête et le pied de page ajoutés, nous pouvons enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrez le document PDF modifié
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour la section Image et numéro de page dans l'en-tête de pied de page à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Créer une page dans l'objet document
Aspose.Pdf.Page page = doc.Pages.Add();

// Créer une section d'en-tête du document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Définir l'en-tête du fichier PDF
page.Header = header;

// Créer un objet image dans la page
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Définir le chemin du fichier image
image1.File = dataDir + "aspose-logo.jpg";

// Ajouter une image à la page d'en-tête du fichier Pdf
header.Paragraphs.Add(image1);

// Créer une section de pied de page du document
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Définir le pied de page du fichier PDF
page.Footer = footer;

// Créer un objet texte
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Ajouter du texte à la section En-tête du fichier Pdf
footer.Paragraphs.Add(txt);

// Enregistrez le fichier Pdf
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Conclusion

Félicitation ! Vous avez appris à ajouter une image et un numéro de page dans la section d'en-tête et de pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant utiliser cette méthode pour personnaliser l'en-tête et le pied de page de vos documents PDF.

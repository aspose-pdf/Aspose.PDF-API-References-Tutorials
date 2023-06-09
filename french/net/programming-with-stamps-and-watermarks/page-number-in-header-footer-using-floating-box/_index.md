---
title: Numéro de page dans l'en-tête pied de page à l'aide d'une zone flottante
linktitle: Numéro de page dans l'en-tête pied de page à l'aide d'une zone flottante
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter le numéro de page dans l'en-tête et le pied de page d'un document PDF avec Aspose.PDF pour .NET.
type: docs
weight: 150
url: /fr/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment ajouter un numéro de page dans l'en-tête et le pied de page d'un document PDF à l'aide de FloatingBox avec Aspose.PDF pour .NET. Nous allons utiliser le code source C# fourni pour créer un document PDF, ajouter une page, créer une FloatingBox, définir sa position et y ajouter le numéro de page, puis enregistrer le document PDF modifié.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Création du document PDF et ajout d'une page

La première étape consiste à créer une instance du document PDF et à y ajouter une page. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instancier le document PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Ajouter une page au document PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire dans lequel vous souhaitez enregistrer le document PDF.

## Étape 3 : Création de la FloatingBox et ajout du numéro de page

Maintenant que la page est ajoutée au document PDF, nous pouvons créer une FloatingBox, définir sa position et y ajouter le numéro de page. Voici comment:

```csharp
// Créer une FloatingBox avec une largeur de 140 et une hauteur de 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Définir la position à gauche du paragraphe
box1. Left = 2;

// Définir la position supérieure du paragraphe
box1. Top = 10;

// Ajouter le numéro de page à la FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Ajouter la FloatingBox à la page
page.Paragraphs.Add(box1);
```

Le code ci-dessus crée un FloatingBox avec une largeur de 140 et une hauteur de 80. Ensuite, nous définissons sa position en spécifiant les valeurs left et top. Enfin, on ajoute le numéro de page à la FloatingBox à l'aide d'un TextFragment contenant la syntaxe "($p/ $P )" qui sera remplacé par le numéro de page courant et le nombre total de pages.

## Étape 4 : Enregistrer le document PDF modifié

Une fois le numéro de page ajouté à l'en-tête ou au pied de page à l'aide de la FloatingBox, nous pouvons enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrez le document PDF modifié
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour le numéro de page dans l'en-tête de pied de page à l'aide d'une boîte flottante à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'instance de document
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Ajouter une page dans le document pdf
Aspose.Pdf.Page page = pdf.Pages.Add();

// Initialise une nouvelle instance de la classe FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Valeur flottante qui indique la position à gauche du paragraphe
box1.Left = 2;

// Valeur flottante indiquant la position supérieure du paragraphe
box1.Top = 10;

// Ajouter les macros à la collection de paragraphes de la FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Ajouter une FloatingBox à la page
page.Paragraphs.Add(box1);

// Enregistrer le document
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusion

Félicitation ! Vous avez appris à ajouter un numéro de page dans l'en-tête et le pied de page d'un document PDF à l'aide de FloatingBox avec Aspose.PDF pour .NET. Vous pouvez maintenant personnaliser vos en-têtes et pieds de page en ajoutant des informations dynamiques telles que le numéro de page.

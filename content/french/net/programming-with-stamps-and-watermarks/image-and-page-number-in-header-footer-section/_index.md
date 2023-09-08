---
title: Image et numéro de page dans la section En-tête et Pied de page
linktitle: Image et numéro de page dans la section En-tête et Pied de page
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter une image et un numéro de page dans l'en-tête et le pied de page d'un document PDF avec Aspose.
type: docs
weight: 110
url: /fr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
Dans ce didacticiel, nous vous guiderons étape par étape sur la façon d'ajouter une image et un numéro de page dans la section d'en-tête et de pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous allons vous montrer comment utiliser le code source C# fourni pour créer une page, définir l'en-tête et le pied de page, ajouter une image à l'en-tête et du texte avec le numéro de page au pied de page du document PDF.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Création du document PDF et de la page

La première étape consiste à créer un nouvel objet Document et une page dans le document PDF. Voici comment:

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer un nouvel objet Document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Créer une page dans le document
Aspose.Pdf.Page page = doc.Pages.Add();
```

Le code ci-dessus crée un nouvel objet Document et une page vide dans le document PDF.

## Étape 3 : Ajout de l'en-tête avec une image

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

## Étape 4 : Ajout du pied de page avec le numéro de page

Maintenant que l'en-tête est ajouté, nous pouvons ajouter une section de pied de page avec un numéro de page. Voici comment:

```csharp
// Créer une section de pied de page
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Définir le pied de page du document PDF
page. Footer = footer;

// Créer un objet TextFragment
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// Ajoutez le texte avec le numéro de page au pied de page du document PDF
footer.Paragraphs.Add(txt);
```

Le code ci-dessus crée une section de pied de page, définit le pied de page de la page avec cette section et ajoute un TextFragment contenant le texte "Page : ($p of $P )"

  qui affiche le numéro de page.

## Étape 5 : Sauvegarde du document PDF modifié

Une fois l'en-tête et le pied de page ajoutés, nous pouvons enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrez le document PDF modifié
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour l'image et le numéro de page dans la section de pied de page d'en-tête à l'aide d'Aspose.PDF pour .NET 
```csharp

// Le chemin d'accès au répertoire des documents.
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

// Ajouter une image à la page d'en-tête du fichier PDF
header.Paragraphs.Add(image1);

//Créer une section de pied de page du document
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// Définir le pied de page du fichier PDF
page.Footer = footer;

// Créer un objet Texte
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// Ajouter du texte à la section d'en-tête du fichier PDF
footer.Paragraphs.Add(txt);

// Enregistrez le fichier PDF
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## Conclusion

Félicitation ! Vous avez appris à ajouter une image et un numéro de page dans la section d'en-tête et de pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser cette méthode pour personnaliser l'en-tête et le pied de page de vos documents PDF.

### FAQ

#### Q : A quoi sert l'ajout d'une image et d'un numéro de page dans la section d'en-tête et de pied de page d'un document PDF ?

R : L'ajout d'une image et d'un numéro de page dans les sections d'en-tête et de pied de page d'un document PDF peut améliorer son attrait visuel, son image de marque et ses éléments de navigation. Une image peut représenter un logo, un filigrane ou tout autre élément graphique, tandis qu'un numéro de page aide les utilisateurs à suivre leur progression et à localiser des pages spécifiques.

#### Q : Comment le code source C# fourni aide-t-il à ajouter une image et un numéro de page à l'en-tête et au pied de page d'un document PDF ?

R : Le code fourni montre comment créer un document PDF, ajouter une page, puis personnaliser les sections d'en-tête et de pied de page. Il montre comment ajouter une image à l'en-tête et un fragment de texte avec une numérotation de page au pied de page.

#### Q : Puis-je utiliser n’importe quel format d’image pour l’en-tête et comment spécifier son chemin ?

 R : Oui, vous pouvez utiliser différents formats d'image (tels que JPEG, PNG, GIF, etc.) pour l'image d'en-tête. Le chemin de l'image est spécifié à l'aide du`File` propriété du`Aspose.Pdf.Image` objet.

#### Q : Comment personnaliser l'apparence et le positionnement de l'image dans la section d'en-tête ?

 R : Vous pouvez personnaliser l'apparence et le positionnement de l'image en ajustant les propriétés du`Aspose.Pdf.Image` objet avant de l’ajouter à la section d’en-tête. Par exemple, vous pouvez définir les dimensions, l'alignement, la rotation, l'opacité de l'image, etc.

####  Q : Quel est le but du`TextFragment` object used for the footer?

 R : Le`TextFragment` L'objet est utilisé pour créer et formater le texte qui sera affiché dans la section de pied de page. Dans le code fourni, il est utilisé pour afficher le numéro de page et le nombre total de pages.

#### Q : Puis-je modifier le texte du pied de page pour inclure des informations ou un formatage supplémentaires ?

 R : Oui, vous pouvez modifier le texte du pied de page en modifiant le contenu du`TextFragment` objet. Vous pouvez ajouter du texte supplémentaire, modifier les polices, les couleurs et le formatage selon vos besoins.

#### Q : Puis-je appliquer différents contenus d’en-tête et de pied de page à différentes pages du document PDF ?

 R : Oui, vous pouvez appliquer différents contenus d'en-tête et de pied de page à différentes pages en créant des`HeaderFooter` objets et en les attribuant à des pages spécifiques à l'aide du`Header` et`Footer` propriétés du`Aspose.Pdf.Page` objet.

#### Q : Comment puis-je personnaliser davantage l'en-tête et le pied de page, par exemple en modifiant les styles de police ou en ajoutant des éléments supplémentaires ?

R : Vous pouvez personnaliser l'en-tête et le pied de page en utilisant diverses classes et propriétés fournies par Aspose.PDF pour .NET. Par exemple, vous pouvez utiliser différentes options de formatage de texte, ajouter plus de paragraphes, d'images ou même de tableaux aux sections d'en-tête et de pied de page.

#### Q : Puis-je supprimer ou effacer les sections d’en-tête et de pied de page si nécessaire ?

R : Oui, vous pouvez supprimer ou effacer les sections d'en-tête et de pied de page en définissant l'option`Header` et`Footer` propriétés du`Aspose.Pdf.Page` s'opposer à`null`.

#### Q : Comment puis-je m'assurer que l'image ajoutée et le numéro de page restent cohérents sur les différents appareils et lecteurs ?

R : Aspose.PDF pour .NET fournit des fonctionnalités permettant de créer des documents PDF standardisés et cohérents, garantissant que l'image ajoutée et le numéro de page apparaîtront de manière cohérente sur les différents appareils et visualiseurs PDF.
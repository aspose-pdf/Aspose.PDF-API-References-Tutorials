---
title: Image et numéro de page dans la section en-tête et pied de page en ligne
linktitle: Image et numéro de page dans la section en-tête et pied de page en ligne
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter une image et un numéro de page dans l'en-tête et le pied de page à l'aide de paragraphes en ligne avec Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
Dans ce tutoriel, nous vous expliquerons étape par étape comment ajouter une image et un numéro de page dans la section d'en-tête et de pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous utiliserons le code source C# fourni pour créer une page, définir l'en-tête et le pied de page, ajouter une image et du texte à l'aide de paragraphes en ligne dans l'en-tête du document PDF.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous de disposer des éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Création du document et de la page PDF

La première étape consiste à créer un nouvel objet Document et une page dans le document PDF. Voici comment procéder :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer un nouvel objet Document
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Créer une page dans le document
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

Le code ci-dessus crée un nouvel objet Document et une page vide dans le document PDF.

## Étape 3 : Ajout de l'en-tête avec une image et du texte en ligne

Maintenant que la page est créée, nous pouvons ajouter une section d'en-tête avec une image et du texte à l'aide de paragraphes en ligne. Voici comment procéder :

```csharp
// Créer une section d'en-tête
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Définir l'en-tête de la page
page. Header = header;

// Créez un objet TextFragment pour le premier texte en ligne
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// Spécifier la couleur du texte
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// Créer un objet Image pour l'image
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// Définir le chemin de l'image
image1.File = dataDir + "aspose-logo.jpg";

// Définir les dimensions de l'image
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indiquer que le premier texte en ligne est une image
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

Le code ci-dessus crée une section d'en-tête, définit l'en-tête de la page avec cette section, ajoute un TextFragment avec du texte en ligne et un objet Image en ligne.

## Étape 4 : enregistrement du document PDF modifié

Une fois l'en-tête avec l'image et le texte en ligne ajoutés, nous pouvons enregistrer le document PDF modifié. Voici comment procéder :

```csharp
// Enregistrer le document PDF modifié
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour l'image et le numéro de page dans la section En-tête/Pied de page en ligne à l'aide d'Aspose.PDF pour .NET 
```csharp

// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier un objet Document en appelant son constructeur vide
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// Créer une page dans l'objet Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();

// Créer la section d'en-tête du document
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

//Définir la largeur de l'image Informations
image1.FixWidth = 50;
image1.FixHeight = 20;

// Indique que le paragraphe en ligne de seg1 est une image.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// Sauvegarder le PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## Conclusion

Félicitations ! Vous avez appris à ajouter une image et un numéro de page dans la section en-tête et pied de page d'un document PDF à l'aide de paragraphes en ligne avec Aspose.PDF pour .NET. Vous pouvez désormais personnaliser l'en-tête et le pied de page de vos documents PDF de manière flexible.

### FAQ

#### Q : Quel est l’avantage d’utiliser des paragraphes en ligne pour ajouter une image et du texte à l’en-tête d’un document PDF ?

R : L'utilisation de paragraphes en ligne vous permet d'intégrer de manière transparente des images et du texte au sein d'un même paragraphe, offrant ainsi un contrôle précis sur leur placement et leur formatage. Cette méthode est particulièrement utile pour créer des en-têtes personnalisés avec des éléments visuels.

#### Q : Comment le code source C# fourni permet-il d’obtenir des paragraphes en ligne pour l’en-tête d’un document PDF ?

R : Le code fourni montre comment créer un document PDF, ajouter une page et personnaliser l'en-tête à l'aide de paragraphes en ligne. Il ajoute un TextFragment avec du texte en ligne, une image en ligne et un autre TextFragment en ligne.

#### Q : Comment spécifier la couleur du texte en ligne dans l’en-tête ?

 A : La couleur du texte en ligne est spécifiée à l'aide de la`ForegroundColor` propriété de la`TextState` de la`TextFragment` objet.

#### Q : Puis-je ajuster les dimensions de l’image en ligne dans l’en-tête ?

 R : Oui, vous pouvez ajuster les dimensions de l'image en ligne à l'aide du`FixWidth` et`FixHeight` propriétés de la`Image` objet. Cela vous permet de contrôler la largeur et la hauteur de l'image dans l'en-tête.

#### Q : Puis-je inclure des éléments supplémentaires en ligne, tels que des hyperliens ou des styles de police différents, dans l'en-tête ?

 R : Oui, vous pouvez inclure des éléments en ligne supplémentaires dans l'en-tête en créant plus`TextFragment` ou`Image` objets avec les propriétés souhaitées. Cela vous permet de personnaliser davantage l'en-tête, y compris des liens hypertexte, des styles de police différents ou d'autres éléments visuels.

#### Q : Comment puis-je garantir que l’image et le texte en ligne restent correctement alignés et formatés sur différents appareils et spectateurs ?

R : Aspose.PDF pour .NET garantit que les images et le texte en ligne sont correctement alignés et formatés, ce qui permet une apparence cohérente sur différents appareils et visionneuses PDF.

#### Q : Puis-je également appliquer des paragraphes en ligne à la section de pied de page ?

 R : Oui, vous pouvez appliquer la même technique d'utilisation de paragraphes en ligne à la section de pied de page en créant un`Footer` objet et y ajouter des éléments en ligne tels que du texte et des images.

#### Q : Est-il possible de combiner des paragraphes en ligne avec d’autres méthodes de personnalisation d’en-tête ou de pied de page ?

R : Oui, vous pouvez combiner des paragraphes en ligne avec d’autres méthodes de personnalisation d’en-tête ou de pied de page fournies par Aspose.PDF pour .NET pour créer des conceptions d’en-tête ou de pied de page plus complexes et personnalisées.

#### Q : Puis-je supprimer ou effacer les éléments en ligne de l’en-tête si nécessaire ?

 R : Oui, vous pouvez supprimer ou effacer les éléments en ligne en modifiant le contenu du`HeaderFooter`objet et en supprimant les paragraphes en ligne respectifs.

#### Q : Comment puis-je appliquer des paragraphes en ligne à des pages spécifiques du document PDF ?

 R : Pour appliquer des paragraphes en ligne à des pages spécifiques, vous pouvez créer des paragraphes distincts.`HeaderFooter` objets pour chaque page et les affecter à l'aide de la`Header` propriété du respectif`Aspose.Pdf.Page` objets.
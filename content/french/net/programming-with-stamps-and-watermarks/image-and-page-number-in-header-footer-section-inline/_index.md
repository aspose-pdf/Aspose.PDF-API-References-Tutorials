---
title: Image et numéro de page dans la section en-tête et pied de page en ligne
linktitle: Image et numéro de page dans la section en-tête et pied de page en ligne
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter une image et un numéro de page en ligne dans la section d'en-tête d'un PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 120
url: /fr/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## Introduction

Aspose.PDF pour .NET est un outil puissant qui offre des fonctionnalités étendues pour manipuler et générer des fichiers PDF. Que vous ayez besoin d'ajouter des images, de personnaliser des en-têtes et des pieds de page ou de gérer du texte, Aspose.PDF est là pour vous. Dans ce didacticiel, nous verrons comment ajouter une image et un numéro de page en ligne dans l'en-tête ou le pied de page d'un document PDF. Plongeons-nous directement dans le processus et décomposons-le étape par étape.

## Prérequis

Avant de passer au code, assurons-nous que vous avez tout en place pour suivre :

-  Aspose.PDF pour .NET : Téléchargez la dernière version à partir du[Page de téléchargement du PDF Aspose](https://releases.aspose.com/pdf/net/).
- Environnement de développement : vous aurez besoin d'un IDE C# tel que Visual Studio.
-  Licence : Si vous n'avez pas encore de licence, vous pouvez en obtenir une[licence temporaire ici](https://purchase.aspose.com/temporary-license/) ou achetez-en un complet auprès de[Magasin Aspose](https://purchase.aspose.com/buy).

Maintenant que vous avez les prérequis prêts, commençons.

## Paquets d'importation

Avant de commencer à coder, assurez-vous d'importer les espaces de noms nécessaires :

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ces packages vous permettent de travailler avec des fichiers PDF et de manipuler du texte.

## Étape 1 : Configurer le répertoire de documents

La première chose à faire est de définir le chemin d'accès au répertoire où notre fichier PDF sera enregistré. Ce chemin peut être personnalisé en fonction du dossier de votre projet ou de n'importe quel emplacement sur votre machine.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Cette variable contient l'emplacement où votre document sera stocké. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel.

## Étape 2 : instancier le document PDF

 Dans cette étape, nous créons une nouvelle instance de`Aspose.Pdf.Document` objet. Cet objet servira d'épine dorsale à votre fichier PDF.

```csharp
// Instancier un objet Document en appelant son constructeur vide
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

Ici, nous créons un fichier PDF vierge que nous pourrons ensuite remplir avec du contenu.

## Étape 3 : Ajouter une page au PDF

Votre PDF doit comporter au moins une page sur laquelle vous pouvez ajouter des en-têtes, des pieds de page et du contenu. Ajoutons une page vierge à notre document.

```csharp
// Créer une page dans l'objet Pdf
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 En appelant`pdf1.Pages.Add()`une nouvelle page est ajoutée au document, prête pour la personnalisation de l'en-tête et du pied de page.

## Étape 4 : Créer et définir l’en-tête

Il est maintenant temps de créer l'en-tête du document. C'est ici que nous ajouterons le texte, l'image et le numéro de page.

```csharp
// Créer la section d'en-tête du document
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// Définir l'en-tête du fichier PDF
page.Header = header;
```

 Nous créons un`HeaderFooter` objet et l'assigner à la`Header` propriété de la page, garantissant que tout ce que nous ajoutons à l'en-tête apparaîtra en haut de la page.

## Étape 5 : ajouter du texte en ligne à l'en-tête

 Ajouter du texte est aussi simple que créer un`TextFragment` et en spécifiant ses propriétés. Ajoutons du texte coloré à notre en-tête.

```csharp
// Créer un objet texte
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// Spécifiez la couleur
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 Dans cette étape, nous créons un`TextFragment` avec le contenu « Aspose.Pdf est un composant robuste par » et définissez sa couleur sur bleu.`IsInLineParagraph` La propriété garantit que le texte est en ligne, ce qui signifie qu'il apparaîtra sur la même ligne que les autres éléments (comme l'image et le texte supplémentaire).

## Étape 6 : insérer une image en ligne dans l'en-tête

Pour rendre votre en-tête visuellement attrayant, vous pouvez ajouter une image en ligne avec le texte. Il peut s'agir du logo de votre entreprise ou de tout autre élément graphique.

```csharp
// Créer un objet image dans la section
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// Définir le chemin du fichier image
image1.File = dataDir + "aspose-logo.jpg";
// Définir la largeur de l'image Informations
image1.FixWidth = 50;
image1.FixHeight = 20;
// Indique que le paragraphe en ligne de seg1 est une image.
image1.IsInLineParagraph = true;
```

 Ici, nous ajoutons une image à l'en-tête en créant un`Image` objet, en définissant son chemin et en ajustant la largeur et la hauteur.`IsInLineParagraph` garantit que l'image est alignée avec le texte.

## Étape 7 : Ajoutez du texte supplémentaire en ligne pour compléter l'en-tête

Ajoutons un peu de texte supplémentaire pour compléter l'en-tête en ligne.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 Dans cette partie, nous créons un autre`TextFragment` avec le contenu « Pty Ltd. » et définissez sa couleur sur marron. Les fragments de texte et l'image sont ajoutés à l'en-tête.

## Étape 8 : Enregistrez le PDF

Une fois l'en-tête configuré, il est temps d'enregistrer le PDF.

```csharp
// Sauvegarder le PDF
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 Le`Save` la méthode écrit le fichier PDF final à l'emplacement spécifié.

## Conclusion

Félicitations ! Vous avez ajouté avec succès une image et du texte à l'en-tête d'un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel vous a présenté les étapes essentielles, notamment la création d'un document, l'ajout de pages, l'insertion d'en-têtes et le placement de contenu en ligne comme du texte et des images. Aspose.PDF vous offre une flexibilité incroyable pour gérer vos PDF, qu'il s'agisse de manipuler des en-têtes, des pieds de page ou du contenu complexe. 

## FAQ

### Puis-je également ajouter un numéro de page à l’en-tête ?
 Oui ! Vous pouvez facilement ajouter un numéro de page en utilisant le`TextFragment` classe et la formater selon les besoins. Il suffit de l'insérer dans la section d'en-tête en tant que contenu en ligne.

### Comment définir une image d'arrière-plan dans l'en-tête ?
 Vous pouvez utiliser le`BackgroundImage` propriété de la`HeaderFooter` classe pour définir une image d'arrière-plan. Cependant, ce n'est pas un contenu en ligne et il couvrira toute la zone d'en-tête.

### Est-il possible d'utiliser d'autres formats d'image en plus du JPEG ?
Absolument ! Aspose.PDF prend en charge différents formats d'image tels que PNG, BMP et GIF.

### Puis-je personnaliser la police du texte dans l'en-tête ?
 Oui, vous pouvez utiliser le`TextState`objet permettant de modifier la police, la taille et le style du texte.

### Ai-je besoin d'une licence pour utiliser Aspose.PDF pour .NET ?
 Oui, Aspose.PDF nécessite une licence pour une utilisation en production, mais vous pouvez commencer avec une[essai gratuit ici](https://releases.aspose.com/).
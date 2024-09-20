---
title: Placer du texte autour d'une image dans un fichier PDF
linktitle: Placer du texte autour d'une image dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment placer du texte autour des images dans des fichiers PDF à l'aide d'Aspose.PDF pour .NET. Suivez notre guide étape par étape pour créer des fichiers PDF professionnels avec des images et du texte côte à côte.
type: docs
weight: 260
url: /fr/net/programming-with-text/placing-text-around-image/
---
## Introduction

Avez-vous déjà essayé de placer du texte autour d'une image dans un fichier PDF, mais vous avez trouvé cela difficile ? Si tel est le cas, vous êtes au bon endroit ! Aspose.PDF pour .NET simplifie ce processus, en vous permettant de placer du texte à côté d'images avec seulement quelques lignes de code. Que vous créiez des rapports, des documents ou des présentations, cette fonctionnalité est un moyen fantastique d'améliorer la mise en page de votre contenu et de le rendre plus attrayant visuellement. Aujourd'hui, nous allons vous expliquer comment utiliser Aspose.PDF pour .NET pour placer du texte autour d'images dans un document PDF.

## Prérequis

Avant de passer au code, assurons-nous que tout est configuré. Voici ce dont vous aurez besoin :

-  Aspose.PDF pour .NET : Vous pouvez le télécharger à partir de[ici](https://releases.aspose.com/pdf/net/).
- Visual Studio : assurez-vous d’avoir installé la dernière version pour pouvoir suivre l’opération en douceur.
- .NET Framework : cet exemple utilise .NET, assurez-vous donc que votre environnement est configuré pour le développement .NET.
-  Une licence temporaire : Vous pouvez demander une licence temporaire[ici](https://purchase.aspose.com/temporary-license/) si vous évaluez le produit.

Si vous n'avez pas encore configuré Aspose.PDF pour .NET, suivez les instructions d'installation dans le[documentation](https://reference.aspose.com/pdf/net/).

## Importer des espaces de noms

Avant de commencer à coder, nous devons importer les espaces de noms nécessaires. Voici l'extrait de code pour le faire :

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 Ces espaces de noms sont essentiels car ils donnent accès à des classes telles que`Document`, `Page`, `Image` , et`HtmlFragment`, que nous utiliserons pour créer et manipuler le PDF.

Maintenant que nous avons préparé le terrain, décrivons comment placer du texte autour d'une image dans votre fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous vous guiderons étape par étape.

## Étape 1 : instancier l'objet document

 Tout d'abord, vous devez créer un document PDF. Dans Aspose.PDF, cela se fait en instanciant un`Document` objet. Cet objet servira de base à tout le contenu que nous ajouterons.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

Ici, nous avons créé un document PDF vide. Il ne contient pas encore de pages, mais ne vous inquiétez pas, nous en ajouterons une à l'étape suivante.

## Étape 2 : Ajouter une page au document

Maintenant que nous avons notre document, il est temps d'ajouter une page. Considérez cela comme la création d'une feuille de papier vierge sur laquelle vous ajouterez votre contenu.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

Ce code ajoute une nouvelle page au document. Par défaut, la page est vierge, mais nous sommes sur le point de changer cela.

## Étape 3 : Créer un tableau pour organiser le contenu

Pour que notre image et notre texte soient correctement alignés, nous allons utiliser un tableau. Les tableaux dans les PDF peuvent aider à structurer votre mise en page, tout comme dans les documents Word ou HTML.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

Cet extrait crée un tableau et l'ajoute à la page. Considérez le tableau comme le cadre permettant d'aligner votre image et votre texte.

## Étape 4 : définir la largeur des colonnes du tableau

Maintenant que nous avons ajouté un tableau, nous devons définir la largeur des colonnes. Cela garantit que l'image et le texte sont dimensionnés de manière appropriée sur la page.

```csharp
table1.ColumnWidths = "120 270";
```

Cette ligne définit la largeur de deux colonnes : une pour l'image et une pour le texte. Ajustez ces valeurs si votre image ou votre texte nécessite plus ou moins d'espace.

## Étape 5 : définir les marges et le remplissage

Pour nous assurer que tout semble bien net, ajoutons des marges et du remplissage au tableau.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

Ces paramètres garantissent que votre tableau dispose d'un espacement cohérent, ce qui rend le contenu visuellement attrayant.

## Étape 6 : Insérer une image dans le tableau

Passons maintenant à la partie amusante : ajouter une image. Dans ce cas, nous ajouterons le logo Aspose, mais n'hésitez pas à utiliser l'image de votre choix.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

Voici ce qui se passe :
- Nous chargeons l'image à partir de votre répertoire spécifié.
- Nous définissons la hauteur et la largeur de l'image.
- Enfin, nous ajoutons l’image à la première cellule du tableau.

## Étape 7 : ajouter du texte à côté de l’image

Maintenant que l'image est en place, ajoutons du texte à côté. Pour cet exemple, nous utiliserons du texte au format HTML pour styliser le contenu.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

Ce bloc ajoute un titre et une description stylisés dans la cellule à côté de l'image. Vous pouvez formater le texte à l'aide de balises HTML pour plus de personnalisation.

## Étape 8 : Ajuster l’alignement vertical

Par défaut, le contenu des cellules d'un tableau peut ne pas s'aligner comme vous le souhaitez. Dans ce cas, nous souhaitons nous assurer que le texte est aligné en haut de la cellule.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

Cela garantit que le texte se trouve en haut de la cellule, gardant ainsi la mise en page propre et professionnelle.

## Étape 9 : Ajoutez plus de texte sous l'image et la description

Vous souhaiterez peut-être inclure davantage de contenu sous l'image et le texte. Ajoutons une autre ligne au tableau à cet effet.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

Ici, nous avons ajouté une autre ligne avec du texte supplémentaire, couvrant les deux colonnes pour maintenir l'équilibre dans la mise en page.

## Étape 10 : Enregistrer le document PDF

Enfin, nous devons enregistrer le document afin que vous puissiez visualiser les modifications.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

Cela enregistre le PDF avec l'image et le texte formatés exactement comme nous le souhaitons.

## Conclusion

Placer du texte autour des images dans un PDF peut sembler une tâche ardue, mais Aspose.PDF pour .NET simplifie le processus. En tirant parti des tableaux, des images et du texte stylisé, vous pouvez créer des PDF d'aspect professionnel avec un minimum d'effort. Avec seulement quelques lignes de code, vous pouvez positionner le contenu exactement où vous le souhaitez, donnant à vos documents une apparence soignée et bien organisée.

## FAQ

### Puis-je utiliser cette méthode pour placer plusieurs images avec du texte ?
Oui, ajoutez simplement plus de lignes et de cellules à votre tableau pour inclure des images et du texte supplémentaires.

### Puis-je modifier l'alignement de l'image ?
Absolument ! Vous pouvez modifier l'alignement de l'image en ajustant les propriétés d'alignement de la cellule.

### Comment puis-je styliser davantage le texte ?
 Vous pouvez utiliser des balises HTML dans le`HtmlFragment` objet permettant d'appliquer différents styles comme le gras, l'italique ou des polices différentes.

### Puis-je contrôler l’espacement entre le texte et l’image ?
 Oui, en utilisant le`MarginInfo` L'objet vous permet de contrôler le remplissage et les marges entre les éléments.

### Est-il possible d'ajouter des liens au texte ?
 Absolument ! Vous pouvez intégrer des hyperliens dans le texte au format HTML à l'aide de`<a>` étiqueter.
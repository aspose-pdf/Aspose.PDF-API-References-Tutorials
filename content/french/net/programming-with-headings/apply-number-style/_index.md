---
title: Appliquer le style de numéro dans le fichier PDF
linktitle: Appliquer le style de numéro dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment appliquer différents styles de nombres (chiffres romains, alphabétiques) aux en-têtes d'un PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-headings/apply-number-style/
---
## Introduction

Avez-vous déjà eu besoin d'ajouter des listes joliment numérotées à vos documents PDF ? Que vous mettiez en forme des documents juridiques, des rapports ou des présentations, des styles de numérotation appropriés sont essentiels pour organiser les informations. Avec Aspose.PDF pour .NET, vous pouvez appliquer différents styles de numérotation aux titres de votre fichier PDF, créant ainsi des documents bien structurés et professionnels. 

## Prérequis

Avant de plonger dans le codage, passons en revue ce dont vous aurez besoin :

1. Aspose.PDF pour .NET : Téléchargez la dernière version d'Aspose.PDF depuis[ici](https://releases.aspose.com/pdf/net/).
2. Environnement de développement : assurez-vous de disposer de Visual Studio ou de tout autre IDE compatible .NET.
3. .NET Framework : assurez-vous que .NET Framework 4.0 ou supérieur est installé.
4.  Licence : Vous pouvez utiliser une licence temporaire à partir de[ici](https://purchase.aspose.com/temporary-license/) ou explorez le[essai gratuit](https://releases.aspose.com/) options.

## Paquets d'importation

Pour commencer, assurez-vous que les espaces de noms suivants sont importés dans votre projet :

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 1 : Configuration du document

Commençons par créer un nouveau document PDF et configurer ses paramètres de page. Nous allons définir la taille de la page et les marges pour contrôler la mise en page de notre contenu.

Explication : Dans cette étape, nous configurons la structure de base du PDF, qui comprend la définition de la taille de la page, de la hauteur et des marges pour une mise en forme cohérente.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();

// Définir les dimensions et les marges de la page
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

En procédant ainsi, votre document aura une taille de page standard, équivalente à une page de 8,5 x 11 pouces, et une marge de 72 points (ou 1 pouce) sur tous les côtés.

## Étape 2 : Ajout d'une page au PDF

Ensuite, nous ajouterons une nouvelle page au document PDF où nous appliquerons plus tard les styles de numérotation.

Explication : Chaque PDF nécessite des pages ! Cette étape ajoute une page vierge au PDF et définit ses marges pour correspondre aux paramètres au niveau du document.

```csharp
// Ajouter une nouvelle page au document PDF
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
```

## Étape 3 : Créer une boîte flottante

Une FloatingBox vous permet de placer du contenu (comme du texte ou des titres) à l'intérieur d'une boîte qui se comporte indépendamment du flux de la page. Cela est utile lorsque vous souhaitez avoir un contrôle total sur la mise en page de votre contenu.

Explication : Ici, nous configurons une FloatingBox pour contenir les titres auxquels seront appliqués des styles de numérotation.

```csharp
// Créer une FloatingBox pour le contenu structuré
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

## Étape 4 : ajoutez le premier titre avec des chiffres romains

Vient maintenant la partie passionnante ! Ajoutons le premier titre avec une numérotation en chiffres romains minuscules.

Explication : Nous appliquons le style NumberingStyle.NumeralsRomanLowercase au titre, qui affichera la numérotation en chiffres romains (i, ii, iii, etc.).

```csharp
// Créer le premier titre avec des chiffres romains
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
```

## Étape 5 : ajouter un deuxième en-tête en chiffres romains

À des fins de démonstration, ajoutons un deuxième en-tête en chiffres romains, mais cette fois nous commencerons à partir de 13.

Explication : La propriété StartNumber vous permet de commencer la numérotation à partir d’un numéro personnalisé. Dans ce cas, nous commençons à partir de 13.

```csharp
// Créez un deuxième titre commençant par le chiffre romain 13
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
```

## Étape 6 : ajouter un titre avec numérotation alphabétique

Pour varier, ajoutons un troisième titre, mais cette fois nous utiliserons une numérotation alphabétique en minuscules (a, b, c, etc.).

Explication : Changer le style de numérotation en Lettres minuscules nous permet d'appliquer une numérotation alphabétique à nos titres.

```csharp
// Créer un titre avec numérotation alphabétique
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan on account of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

## Étape 7 : Enregistrer le PDF

Enfin, après avoir appliqué tous les styles de titres et de numéros, enregistrons le fichier PDF dans le répertoire souhaité.

Explication : Cette étape enregistre le fichier PDF contenant tous les titres formatés avec les styles de numérotation appliqués.

```csharp
// Enregistrer le document PDF
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);
```

## Conclusion

Et voilà ! Vous avez appliqué avec succès des styles de numérotation (chiffres romains et alphabétiques) aux titres d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. La flexibilité offerte par Aspose.PDF pour contrôler la mise en page, les styles de numérotation et le positionnement du contenu vous offre un ensemble d'outils puissants pour créer des documents PDF professionnels et bien organisés.

## FAQ

### Puis-je appliquer différents styles de numérotation au même document PDF ?  
Oui, Aspose.PDF pour .NET vous permet de mélanger différents styles de numérotation tels que les chiffres romains, les chiffres arabes et la numérotation alphabétique dans le même document.

### Comment puis-je personnaliser le numéro de départ des titres ?  
 Vous pouvez définir le numéro de départ de n'importe quel titre en utilisant le`StartNumber` propriété.

### Existe-t-il un moyen de réinitialiser la séquence de numérotation ?  
Oui, vous pouvez réinitialiser la numérotation en ajustant le`StartNumber` propriété pour chaque rubrique.

### Puis-je appliquer un style gras ou italique aux titres en plus de la numérotation ?  
 Absolument ! Vous pouvez personnaliser les styles de titre en modifiant des propriétés telles que la police, la taille, le gras et l'italique à l'aide de l'`TextState` objet.

### Comment obtenir une licence temporaire pour Aspose.PDF ?  
 Vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/) pour tester Aspose.PDF sans restrictions.
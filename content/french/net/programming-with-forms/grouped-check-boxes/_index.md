---
title: Cases à cocher groupées dans un document PDF
linktitle: Cases à cocher groupées dans un document PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment créer des cases à cocher groupées (boutons radio) dans un document PDF à l'aide d'Aspose.PDF pour .NET avec ce didacticiel étape par étape.
type: docs
weight: 170
url: /fr/net/programming-with-forms/grouped-check-boxes/
---
## Introduction

Créer des PDF interactifs n'est pas aussi difficile qu'il n'y paraît, surtout lorsque vous disposez d'outils puissants comme Aspose.PDF pour .NET. L'un des éléments interactifs que vous devrez peut-être ajouter à vos documents PDF est celui des cases à cocher groupées, ou plus précisément des boutons radio qui permettent aux utilisateurs de sélectionner une option parmi un ensemble. Ce didacticiel vous guidera tout au long du processus d'ajout de cases à cocher groupées (boutons radio) à un document PDF à l'aide d'Aspose.PDF pour .NET. Que vous soyez un développeur débutant ou expérimenté, vous trouverez ce guide intéressant, détaillé et facile à suivre.

## Prérequis

Avant de plonger dans le guide étape par étape, examinons quelques prérequis essentiels :

1.  Aspose.PDF pour .NET : assurez-vous que la bibliothèque Aspose.PDF est installée. Sinon, vous pouvez[téléchargez-le ici](https://releases.aspose.com/pdf/net/).
2. IDE : vous devez disposer d’un environnement de développement configuré, tel que Visual Studio.
3. .NET Framework : Le projet doit cibler une version du .NET Framework compatible avec Aspose.PDF.
4. Connaissances de base en C# : une familiarité avec C# et la manipulation PDF est requise pour suivre en douceur.
5.  Licence : Aspose.PDF nécessite une licence pour bénéficier de toutes ses fonctionnalités. Vous pouvez[obtenir un permis temporaire](https://purchase.aspose.com/temporary-license/) si besoin.

## Paquets d'importation

Avant de commencer, assurez-vous d’avoir importé les espaces de noms nécessaires dans votre projet :

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Forms;
```

Ces packages vous donneront accès à toutes les classes et méthodes nécessaires pour manipuler les documents PDF, y compris la création de boutons radio et la définition de leurs propriétés.

Dans cette section, nous allons décomposer le processus de création de cases à cocher groupées (boutons radio) en étapes claires et faciles à suivre.

## Étape 1 : Créer un nouveau document PDF

 La première étape consiste à créer une instance de`Document` objet qui représentera votre fichier PDF. Ajoutez ensuite une page vierge à votre document où vous placerez vos cases à cocher groupées.

```csharp
// Instancier l'objet Document
Document pdfDocument = new Document();

// Ajouter une page au fichier PDF
Page page = pdfDocument.Pages.Add();
```

Cela établit la base pour l’ajout d’éléments, tels que des boutons radio, au PDF.

## Étape 2 : Initialiser le champ du bouton radio

Ensuite, nous devons créer un`RadioButtonField` objet qui contiendra les cases à cocher groupées (boutons radio). Ce champ est ajouté à la page spécifique où les cases à cocher apparaîtront.

```csharp
// Instanciez l'objet RadioButtonField et attribuez-le à la première page
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

Considérez cela comme le conteneur qui regroupera les options de bouton radio individuelles.

## Étape 3 : ajouter des options de bouton radio

 Ajoutons maintenant les options de bouton radio individuelles au champ. Dans cet exemple, nous allons ajouter deux boutons radio et spécifier leurs positions à l'aide de la commande`Rectangle` objet.

```csharp
// Ajoutez la première option de bouton radio et spécifiez sa position à l'aide de Rectangle
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));

// Définir les noms des options pour l'identification
opt1.OptionName = "Option1";
opt2.OptionName = "Option2";
```

 Ici, le`Rectangle` L'objet définit les coordonnées et la taille de chaque bouton radio sur la page.

## Étape 4 : Personnaliser le style des boutons radio

 Vous pouvez personnaliser l'apparence des boutons radio en définissant leur`Style` propriété. Par exemple, vous pourriez vouloir des cases à cocher de forme carrée ou en forme de croix.

```csharp
// Définir le style des boutons radio
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Cross;
```

Cela vous permet de contrôler l'apparence des cases à cocher, les rendant plus conviviales et visuellement attrayantes.

## Étape 5 : Configurer les propriétés de bordure

Les bordures jouent un rôle essentiel pour rendre les cases à cocher facilement identifiables. Ici, nous allons ajouter des bordures pleines autour de chaque option de bouton radio et définir leur largeur et leur couleur.

```csharp
// Configurer la bordure du premier bouton radio
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt1.Characteristics.Border = Color.Black;

// Configurer la bordure du deuxième bouton radio
opt2.Border = new Border(opt2);
opt2.Border.Style = BorderStyle.Solid;
opt2.Border.Width = 1;
opt2.Characteristics.Border = Color.Black;
```

Cette étape garantit que chaque bouton radio dispose d'une bordure bien définie, améliorant ainsi la lisibilité du document.

## Étape 6 : ajouter des options de bouton radio au formulaire

Nous allons maintenant ajouter les boutons radio au formulaire du document. Il s'agit de l'étape finale du regroupement des cases à cocher sous un seul champ.

```csharp
// Ajouter un champ de bouton radio à l'objet de formulaire du document
pdfDocument.Form.Add(radio);
```

L'objet de formulaire agit comme un conteneur pour tous les éléments interactifs, y compris nos cases à cocher groupées.

## Étape 7 : Enregistrer le document PDF

Enfin, une fois que tout est configuré, vous pouvez enregistrer le document PDF à l’emplacement souhaité.

```csharp
// Définir le chemin du fichier de sortie
string dataDir = "YOUR DOCUMENT DIRECTORY" + "GroupedCheckBoxes_out.pdf";

// Enregistrer le document PDF
pdfDocument.Save(dataDir);

// Confirmer la création réussie
Console.WriteLine("Grouped checkboxes added successfully. File saved at " + dataDir);
```

Et voilà ! Vous avez réussi à créer un PDF avec des cases à cocher groupées à l'aide d'Aspose.PDF pour .NET.

## Conclusion

L'ajout d'éléments interactifs tels que des cases à cocher groupées à des documents PDF peut sembler compliqué au début, mais avec Aspose.PDF pour .NET, cela devient un jeu d'enfant. En suivant ce guide étape par étape, vous avez appris à configurer un document PDF de base, à ajouter des boutons radio groupés, à personnaliser leur apparence et à enregistrer le résultat final. Que vous créiez des formulaires, des enquêtes ou tout autre type de PDF interactif, ce guide vous offre une base solide pour commencer.

## FAQ

### Puis-je ajouter plus de deux boutons radio à un groupe ?
 Absolument ! Il suffit d'instancier des éléments supplémentaires`RadioButtonOptionField` objets et les ajouter à la`RadioButtonField` comme indiqué dans le tutoriel.

### Comment gérer plusieurs groupes de cases à cocher dans un document ?
Pour créer plusieurs groupes, instanciez des groupes distincts`RadioButtonField` objets pour chaque groupe.

### Y a-t-il une limite au nombre de cases à cocher que je peux ajouter ?
Non, Aspose.PDF pour .NET n'impose aucune limite au nombre de cases à cocher que vous pouvez ajouter à un PDF.

### Puis-je modifier l’apparence des cases à cocher après leur ajout ?
Oui, vous pouvez modifier les propriétés telles que le style de bordure, la largeur et la couleur après avoir ajouté les cases à cocher.

### Est-il possible d’utiliser des images comme boutons radio ?
 Oui, Aspose.PDF vous permet d'utiliser des images personnalisées comme boutons radio en définissant le`Appearance` propriété de chaque option de bouton radio.
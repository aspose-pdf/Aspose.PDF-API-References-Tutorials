---
title: Faire pivoter le texte à l'aide d'un fragment de texte dans un fichier PDF
linktitle: Faire pivoter le texte à l'aide d'un fragment de texte dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment faire pivoter du texte dans des fichiers PDF à l'aide d'Aspose.PDF pour .NET grâce à un guide étape par étape. Découvrez les techniques de manipulation de texte, du positionnement à la rotation.
type: docs
weight: 390
url: /fr/net/programming-with-text/rotate-text-using-text-fragment/
---
## Introduction

Créer des PDF est une chose, mais les manipuler pour répondre à des exigences spécifiques ? C'est là que la vraie magie opère ! Vous êtes-vous déjà demandé comment faire pivoter du texte dans un PDF ? Que vous génériez des rapports ou créiez un document avec une conception personnalisée, la rotation de fragments de texte peut rendre vos PDF plus attrayants visuellement. Dans ce didacticiel, nous allons découvrir comment faire pivoter du texte à l'aide d'Aspose.PDF pour .NET, une bibliothèque puissante qui permet une manipulation transparente des documents PDF.

## Prérequis

Avant de passer au code, passons rapidement en revue les outils et les configurations dont vous aurez besoin. Vous voulez que tout soit prêt pour pouvoir suivre le processus sans effort.

### Bibliothèque Aspose.PDF pour .NET
Tout d'abord, vous devez installer Aspose.PDF pour .NET dans votre projet. Cette bibliothèque regorge de fonctionnalités pour vous aider à créer, modifier et gérer des fichiers PDF par programmation. Si vous ne l'avez pas encore téléchargé, voici où l'obtenir :
- [Télécharger Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/)

Pour ce tutoriel, assurez-vous que vous utilisez la dernière version de la bibliothèque.

### Environnement de développement
Vous aurez également besoin d'un environnement de développement .NET comme Visual Studio. Il s'agit de l'IDE de référence pour le développement C#, et il rendra votre expérience de codage fluide et efficace.

### Licence temporaire ou complète
Bien que vous puissiez commencer avec une version d'essai gratuite d'Aspose.PDF, si vous souhaitez éviter toute limitation, il est préférable d'utiliser une licence temporaire ou complète. Voici comment vous pouvez en obtenir une :
- [Essai gratuit](https://releases.aspose.com/)
- [Licence temporaire](https://purchase.aspose.com/temporary-license/)
- [Acheter la licence complète](https://purchase.aspose.com/buy)

Une fois que vous avez défini tous ces éléments essentiels, passons à autre chose !

## Paquets d'importation

Avant de commencer à coder, vous devez importer les espaces de noms nécessaires fournis avec Aspose.PDF. Cela est essentiel pour travailler avec des documents, des pages, des fragments de texte, etc. Ajoutez le code suivant au début de votre fichier C# :

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

Maintenant, décomposons l’exemple de code étape par étape afin que vous puissiez faire pivoter le texte comme un pro !

## Étape 1 : Initialiser l’objet Document

Chaque manipulation PDF commence par la création ou le chargement d'un document PDF. Ici, nous allons initialiser un nouveau document PDF à partir de zéro en utilisant Aspose.PDF.

 Nous créons un nouveau`Document` objet qui représente le fichier PDF. Initialement, ce document est vide.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialiser l'objet document
Document pdfDocument = new Document();
```

Explication:  
- `dataDir`:Il s'agit du répertoire dans lequel votre PDF final sera enregistré.
- `Document pdfDocument = new Document();`: Ceci initialise un nouveau document PDF vide. 

## Étape 2 : Ajouter une page au document

Ensuite, nous devons ajouter une page au document. Un PDF est essentiellement un ensemble de pages, et vous avez besoin d'au moins une page pour ajouter votre contenu.

```csharp
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

Sans ajouter de page, il n'y a pas de toile sur laquelle dessiner ou placer votre texte !

## Étape 3 : Créer le premier fragment de texte

Vient maintenant la partie intéressante ! Ajoutons un fragment de texte au PDF. Un fragment de texte est un morceau de texte doté de propriétés spécifiques telles que la police, la taille et la position.

```csharp
// Créer un fragment de texte
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```

- TextFragment("texte principal") : Cela crée un nouveau fragment de texte avec le contenu « texte principal ».
- Position(100, 600) : définit la position du texte sur la page. Le premier nombre est la coordonnée x et le second est la coordonnée y.
- TextState.FontSize : définit la taille de police du texte.
- FontRepository.FindFont : recherche la police spécifiée à appliquer au texte.

## Étape 4 : Créer les fragments de texte pivotés

Ajoutons plus de fragments de texte, mais cette fois nous allons les faire pivoter sous différents angles !

### Rotation d'un fragment de texte à 45 degrés

```csharp
// Créer un fragment de texte pivoté
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
```

Ici, le changement clé est :
- TextState.Rotation : cette propriété définit l'angle de rotation du fragment de texte et, dans ce cas, il est de 45 degrés.

### Rotation d'un fragment de texte à 90 degrés

```csharp
// Créer un fragment de texte pivoté
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

Dans ce cas, la rotation est de 90 degrés.

## Étape 5 : ajouter des fragments de texte à la page PDF

Maintenant que tous nos fragments de texte sont prêts, il est temps de les ajouter à la page PDF à l'aide de la classe TextBuilder.

```csharp
// créer un objet TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Ajouter le fragment de texte à la page PDF
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

La classe TextBuilder permet d'ajouter plusieurs fragments de texte à une seule page, vous offrant ainsi la possibilité de les manipuler individuellement.

## Étape 6 : Enregistrer le document PDF

Enfin, enregistrez le document dans le répertoire spécifié. Sans cette étape, tout votre travail acharné s'évanouira !

```csharp
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

Vous avez réussi à faire pivoter du texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant ouvrir le PDF pour afficher les fragments de texte pivotés !

## Conclusion

La rotation du texte dans un PDF peut ajouter une touche professionnelle à vos documents, les rendant visuellement attrayants et uniques. Avec Aspose.PDF pour .NET, il est incroyablement facile de manipuler des fragments de texte, ce qui vous donne un contrôle total sur l'apparence de votre contenu. Maintenant que vous avez appris à faire pivoter du texte, vous pouvez expérimenter différents angles et mises en page pour répondre aux besoins de votre projet.

## FAQ

### Puis-je faire pivoter des fragments de texte sous n’importe quel angle ?
 Oui ! Vous pouvez définir le`TextState.Rotation` propriété à n'importe quel degré (même angles négatifs) pour faire pivoter le texte selon les besoins.

### Puis-je utiliser des polices différentes pour chaque fragment de texte ?
 Absolument. Vous pouvez personnaliser la police de chaque fragment de texte à l'aide de`FontRepository.FindFont` et transmettez la police que vous souhaitez appliquer.

### Aspose.PDF prend-il en charge les PDF multipages ?
Oui, vous pouvez ajouter plusieurs pages à votre document PDF et manipuler chaque page indépendamment.

### Y a-t-il une limite au nombre de fragments de texte que je peux ajouter ?
Non, vous pouvez ajouter autant de fragments de texte que nécessaire. Veillez simplement à ce qu'ils soient correctement positionnés sur la page.

### Puis-je modifier des fragments de texte après les avoir ajoutés ?
Oui, une fois qu'un fragment de texte est ajouté, vous pouvez toujours mettre à jour ses propriétés ou le supprimer de la page.
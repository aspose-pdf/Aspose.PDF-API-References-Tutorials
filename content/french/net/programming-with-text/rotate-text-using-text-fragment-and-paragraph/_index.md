---
title: Faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe
linktitle: Faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment faire pivoter du texte à l'aide d'un fragment de texte et d'un paragraphe dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 400
url: /fr/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
## Introduction

En matière de création de documents dynamiques, les PDF sont la référence absolue. Grâce à leur attrait universel et à leur professionnalisme attendu, les PDF sont couramment utilisés dans différents secteurs, notamment les environnements juridiques, éducatifs et professionnels. Dans cet article, nous allons examiner de plus près comment exploiter Aspose.PDF pour .NET pour créer un document PDF avec des fragments de texte pivotés, parfait pour ajouter du style à vos documents ou mettre en valeur des informations importantes. Commençons !

## Prérequis

Avant de plonger dans les détails techniques, assurez-vous d'avoir quelques éléments en place :

1. Compréhension de base de .NET Framework : une familiarité avec C# ou VB.NET sera bénéfique car Aspose.PDF fonctionne parfaitement avec les applications .NET.
  
2.  Bibliothèque Aspose.PDF pour .NET : vous aurez besoin de la bibliothèque Aspose.PDF. Ne vous inquiétez pas, elle est facile à télécharger ! Vous pouvez l'obtenir ici :[Télécharger Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/).

3. Environnement de développement : vous pouvez utiliser n’importe quel IDE prenant en charge le développement .NET, comme Visual Studio. Assurez-vous que votre IDE peut accéder à la bibliothèque Aspose.PDF téléchargée.

4.  Une licence temporaire (facultative) : bien que vous puissiez commencer avec l'essai gratuit, si vous devez créer une application de production, envisagez d'acquérir une[permis temporaire](https://purchase.aspose.com/temporary-license/) pour une fonctionnalité complète.

5. Connexion Internet : cela peut sembler évident, mais vous en aurez besoin pour accéder à la documentation en ligne pour obtenir des conseils supplémentaires et un dépannage.

Une fois vos prérequis réglés, il est temps de passer à l'action !

## Paquets d'importation

Avant de lancer la partie codage, nous devons nous assurer que nous importons les packages nécessaires dans notre projet .NET. 

Pour commencer, assurez-vous d’utiliser les espaces de noms suivants en haut de votre fichier C# :

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

Cela vous permettra d'accéder aux fonctionnalités de manipulation de documents PDF et aux fonctionnalités de texte fournies par la bibliothèque Aspose.PDF.

Maintenant, le plaisir commence ! Nous allons créer une application simple pour générer un document PDF contenant à la fois des fragments de texte standard et pivotés. Respirez profondément et parcourons-la étape par étape.

## Étape 1 : Initialiser l’objet Document

Dans cette étape, nous allons créer un nouveau document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialiser l'objet document
Document pdfDocument = new Document();
```

Cette ligne de code nous permet de créer un nouveau canevas pour notre contenu. C'est comme si vous versiez un nouveau lot de peinture sur votre toile. C'est passionnant !

## Étape 2 : Ajouter une page

Ensuite, nous devons ajouter une page à notre document. C'est là que la magie va opérer.

```csharp
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

Imaginez cette étape comme la pose des fondations de votre chef-d'œuvre. Sans page, rien ne peut être peint ou écrit !

## Étape 3 : Créez votre premier fragment de texte

Nous allons maintenant ajouter du texte à notre PDF. Commençons par un fragment de texte standard.

```csharp
// Créer un fragment de texte
TextFragment textFragment1 = new TextFragment("main text");
// Définir les propriétés du texte
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```

Ici, nous avons créé notre premier fragment de texte nommé`textFragment1`. Nous définissons également ses propriétés de police, vous savez, pour lui donner une belle apparence !

## Étape 4 : ajouter le premier fragment de texte à la page

Notre fragment de texte étant prêt, il est temps de le mettre sur la page.

```csharp
pdfPage.Paragraphs.Add(textFragment1);
```

Ce code place essentiellement votre texte standard sur la toile. C'est comme si vous posiez votre pinceau sur la toile pour créer la première ligne de votre œuvre !

## Étape 5 : Créer des fragments de texte pivotés

Ensuite, nous allons ajouter du texte pivoté pour attirer l'attention. Allons-y.

### Création du premier fragment de texte pivoté

```csharp
// Créer un fragment de texte
TextFragment textFragment2 = new TextFragment("rotated text");
// Définir les propriétés du texte
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment2.TextState.Rotation = 315;
```

 Dans cet extrait, nous avons créé un fragment de texte nommé`textFragment2`. Nous avons réglé sa rotation à 315 degrés, ce qui est bien incliné mais pas complètement à l'envers. Cela pourrait représenter un texte qui a besoin d'un peu de style !

### Ajout du fragment de texte pivoté à la page

Il est temps d’ajouter également ce texte accrocheur à la page !

```csharp
pdfPage.Paragraphs.Add(textFragment2);
```

Génial, non ? C'est comme ajouter une touche de couleur à votre toile pour vraiment faire ressortir les choses !

### Créer un autre fragment de texte pivoté

Ajoutons un autre fragment de texte pivoté pour faire bonne mesure.

```csharp
// Créer un fragment de texte
TextFragment textFragment3 = new TextFragment("another rotated text");
// Définir les propriétés du texte
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment3.TextState.Rotation = 270;
```

Comme précédemment, nous ajoutons un autre morceau de texte pivoté. Cette fois, il est tourné à 270 degrés, ce qui le rend presque à l'envers !

## Étape 6 : ajouter le deuxième fragment de texte pivoté à la page

Maintenant, ajoutons cette touche finale.

```csharp
pdfPage.Paragraphs.Add(textFragment3);
```

De cette façon, vous avez plusieurs fragments de texte pivotés fonctionnant ensemble sur la toile !

## Étape 7 : Enregistrer le document

Maintenant que nous avons un document rempli d'éléments fantastiques, terminons les choses en le sauvegardant.

```csharp
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

Et voilà, votre chef-d'œuvre créatif a été enregistré au format PDF. Vous pouvez le considérer comme une exposition de votre œuvre dans une galerie : elle est prête à être vue par le monde entier !

## Conclusion

Félicitations ! Vous venez de créer un document PDF dynamique avec des fragments de texte standard et pivotés à l'aide d'Aspose.PDF pour .NET. Cela ouvre un monde de possibilités quant à la façon dont vous pouvez présenter vos informations. Que vous ayez besoin de mettre en valeur les points clés d'un rapport ou que vous souhaitiez simplement ajouter une touche visuelle à vos documents, ces techniques vous aideront à atteindre vos objectifs.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?

Aspose.PDF pour .NET est une bibliothèque robuste qui permet aux développeurs de créer, manipuler et convertir des fichiers PDF à l'aide d'applications .NET.

### Puis-je utiliser Aspose.PDF dans une application Web ?

Absolument ! Aspose.PDF peut être intégré à n'importe quelle application .NET, y compris les applications Web, les applications de bureau et les services.

### Existe-t-il un essai gratuit disponible pour Aspose.PDF ?

 Oui, vous pouvez bénéficier d'un essai gratuit pour découvrir ses fonctionnalités avant de procéder à un achat. Découvrez-le sur[Essai gratuit d'Aspose](https://releases.aspose.com/).

### Comment puis-je faire pivoter du texte dans un PDF à l'aide d'Aspose.PDF ?

 Vous pouvez faire pivoter le texte en définissant le`Rotation` propriété d'un`TextFragment` objet, comme démontré dans ce tutoriel.

### Où puis-je trouver de l'aide pour Aspose.PDF ?

 Pour toute assistance ou question, vous pouvez visiter le[Forum d'assistance Aspose](https://forum.aspose.com/c/pdf/10).
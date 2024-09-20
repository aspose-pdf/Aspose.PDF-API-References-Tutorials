---
title: Ajouter un retrait aux lignes suivantes dans le fichier PDF
linktitle: Ajouter un retrait aux lignes suivantes dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter des retraits aux lignes suivantes des fichiers PDF à l'aide d'Aspose.PDF pour .NET. Suivez ce guide détaillé étape par étape pour une mise en forme professionnelle du texte.
type: docs
weight: 60
url: /fr/net/programming-with-text/add-subsequent-lines-indent/
---
## Introduction

Créer des PDF visuellement attrayants implique souvent plus que simplement placer du texte sur une page. Vous êtes-vous déjà demandé comment ajouter un retrait aux lignes suivantes d'un document PDF, pour lui donner un aspect plus professionnel ? Que vous créiez un rapport, un livre électronique ou tout autre document où la mise en page est importante, il est essentiel de pouvoir contrôler la façon dont le texte s'écoule. Aujourd'hui, nous allons découvrir comment ajouter un retrait aux lignes suivantes d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Cette fonctionnalité peut être particulièrement utile pour les paragraphes qui nécessitent un retrait suspendu, ce qui améliore la lisibilité et l'esthétique. Alors, passons directement à l'action !

## Prérequis

Avant de commencer, vous devez mettre en place quelques éléments :

-  Aspose.PDF pour .NET : vous devez avoir installé cette bibliothèque. Si ce n'est pas déjà fait, vous pouvez[téléchargez-le ici](https://releases.aspose.com/pdf/net/).
- Environnement de développement : une connaissance de base de C# et d'un IDE comme Visual Studio serait utile.
- .NET Framework : ce didacticiel suppose que vous travaillez dans un environnement .NET.
-  Licence temporaire : Si vous ne disposez pas d'une licence complète pour Aspose.PDF, vous pouvez demander une[permis temporaire](https://purchase.aspose.com/temporary-license/).

Maintenant que vous êtes prêt, passons à la section codage !

## Importation d'espaces de noms

Tout d'abord, vous devez importer les espaces de noms nécessaires pour rendre la bibliothèque Aspose.PDF disponible dans votre projet. Il s'agit d'une étape simple, mais essentielle pour faire avancer les choses.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Une fois ceux-ci importés, vous êtes prêt à travailler avec les puissants outils fournis par Aspose.PDF.

## Étape 1 : Configurez votre document et votre page

Avant de pouvoir ajouter une indentation, nous devons créer un nouveau document PDF et y ajouter une page. Ce sera la toile sur laquelle nous appliquerons notre mise en forme de texte.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un nouvel objet de document
Aspose.Pdf.Document document = new Aspose.Pdf.Document();

//Ajouter une nouvelle page au document
Aspose.Pdf.Page page = document.Pages.Add();
```

Ici, nous initialisons le document PDF et y ajoutons une page vierge. C'est assez simple jusqu'ici, n'est-ce pas ? Considérez cela comme une préparation avant d'ajouter votre contenu.

## Étape 2 : Créer le fragment de texte

 Ensuite, vous devez créer un`TextFragment` objet qui contiendra le texte que vous afficherez sur votre PDF. Ce texte sera ensuite formaté avec les indentations requises.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment(
    "A quick brown fox jumped over the lazy dog. " +
    "A quick brown fox jumped over the lazy dog. " +
    "A quick brown fox jumped over the lazy dog. " +
    "A quick brown fox jumped over the lazy dog. " +
    "A quick brown fox jumped over the lazy dog."
);
```

Il s'agit simplement d'un exemple de texte simple répété plusieurs fois pour remplir l'espace sur la page. Vous pouvez le remplacer par n'importe quel texte pertinent pour votre projet.

## Étape 3 : Initialiser les options de formatage du texte

 C'est ici que la magie opère ! Maintenant que vous avez votre`TextFragment` , vous devrez initialiser les options de formatage du texte pour spécifier le`SubsequentLinesIndent`Ce paramètre appliquera un retrait à toutes les lignes sauf la première.

```csharp
// Initialisez TextFormattingOptions pour le fragment de texte et spécifiez la valeur FollowingLinesIndent
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

Dans cet exemple, nous avons défini le retrait sur 20 unités. Cela signifie que chaque ligne après la première sera indentée de 20 unités, créant ainsi un retrait suspendu visuellement distinct.

## Étape 4 : Ajouter du texte à la page

 Maintenant que vous avez appliqué la mise en forme nécessaire, il est temps d'ajouter le texte à la page. Cela se fait en ajoutant le`TextFragment` à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(text);
```

À ce stade, la page contient le texte et les lignes suivantes sont en retrait. Mais pourquoi s'arrêter là ? Ajoutons des lignes supplémentaires pour que le document paraisse plus complet.

## Étape 5 : ajouter des fragments de texte supplémentaires

Pour illustrer comment plusieurs fragments de texte peuvent apparaître dans le même document, vous pouvez ajouter quelques lignes supplémentaires. Chacune de ces lignes peut être formatée indépendamment ou utiliser la même mise en forme que celle de l'étape précédente.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);

text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);

text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);

text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

À chaque nouveau fragment de texte ajouté à la page, votre document commence à prendre forme. Vous pouvez facilement imaginer comment vous pouvez utiliser cela dans différents scénarios, que vous créiez des documents longs ou du contenu court.

## Étape 6 : Enregistrer le document

Une fois que vous avez ajouté tout votre texte et appliqué la mise en forme souhaitée, il est temps d'enregistrer le document. La ligne de code suivante fait exactement cela, en enregistrant le fichier dans le répertoire spécifié.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

Et voilà ! Votre fichier PDF contient désormais du texte avec des lignes suivantes en retrait.

## Conclusion

Et voilà ! Vous venez d'apprendre à ajouter des retraits de ligne à votre PDF à l'aide d'Aspose.PDF pour .NET. Cette méthode est parfaite pour ajouter une touche professionnelle à vos documents, en vous offrant la possibilité de contrôler la manière dont le texte est affiché. Que vous prépariez des rapports commerciaux, des documents juridiques ou à peu près n'importe quel type de fichier PDF, l'indentation est un outil petit mais puissant pour améliorer la lisibilité. Si vous avez apprécié ce didacticiel, pourquoi ne pas découvrir les autres fonctionnalités qu'Aspose.PDF a à offrir ?

## FAQ

### Puis-je appliquer des retraits différents à différents paragraphes ?  
 Oui, vous pouvez appliquer différents paramètres d'indentation à chaque`TextFragment` en modifiant leur individu`TextState.FormattingOptions`.

###  Quelles unités sont utilisées pour le`SubsequentLinesIndent` property?  
Le retrait est mesuré en points, qui est l'unité de mesure standard dans les documents PDF.

### Puis-je appliquer cela à des PDF déjà existants ?  
Absolument ! Vous pouvez charger un PDF existant et lui appliquer ces modifications de la même manière que vous le feriez pour un nouveau document.

### Existe-t-il une limite à l'indentation que je peux appliquer aux lignes suivantes ?  
Il n'y a pas de limite stricte, mais pour des raisons de lisibilité, il est recommandé de conserver l'indentation dans des limites raisonnables.

### Puis-je combiner cela avec d’autres options de formatage de texte ?  
 Oui ! Vous pouvez combiner les`SubsequentLinesIndent` propriété avec d'autres options de formatage de texte telles que la taille de la police, la couleur et l'alignement pour personnaliser encore plus votre texte.
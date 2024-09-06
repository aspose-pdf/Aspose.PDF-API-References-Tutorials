---
title: Largeur de la ligne d'annotation lnk
linktitle: Largeur de la ligne d'annotation lnk
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment définir la largeur de la ligne d'annotation d'encre dans un PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel détaillé vous guide à travers chaque étape, garantissant une sortie de haute qualité.
type: docs
weight: 110
url: /fr/net/annotations/lnkannotationlinewidth/
---
## Introduction

Lorsque vous travaillez avec des documents PDF, l'ajout d'annotations peut être un moyen efficace de mettre en évidence des informations ou d'ajouter des éléments interactifs à vos fichiers. L'annotation à l'encre est l'une de ces annotations, qui vous permet de dessiner des lignes de forme libre sur votre PDF. Mais que faire si vous devez personnaliser l'apparence de ces lignes, en particulier la largeur de la ligne ? Dans ce didacticiel, nous vous expliquerons le processus de définition de la largeur de la ligne d'annotation à l'encre à l'aide d'Aspose.PDF pour .NET.

## Prérequis

Avant de plonger dans le code, assurons-nous que tout est configuré pour suivre ce tutoriel en douceur :

1.  Aspose.PDF pour .NET : Assurez-vous que la bibliothèque Aspose.PDF pour .NET est installée. Vous pouvez la télécharger à partir du[page de téléchargement](https://releases.aspose.com/pdf/net/) ou installez-le via NuGet Package Manager dans Visual Studio.
2. Environnement de développement : ce didacticiel suppose que vous travaillez dans un environnement de développement .NET tel que Visual Studio.
3. Connaissances de base de C# : une compréhension fondamentale de C# vous aidera à suivre les étapes de codage.
4. Document PDF : utilisez un document PDF existant ou créez-en un nouveau pour ce didacticiel.

## Importer les espaces de noms nécessaires

Avant de commencer à coder, assurez-vous d'importer les espaces de noms nécessaires dans votre projet :

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System;
using System.Collections;
using System.Collections.Generic;
```

Ces espaces de noms fournissent les classes et les méthodes nécessaires pour manipuler des documents PDF, travailler avec des annotations et gérer des éléments graphiques.

Maintenant que nos conditions préalables sont en place, décomposons le processus de définition de la largeur de la ligne d’annotation d’encre en étapes claires et gérables.

## Étape 1 : Initialiser le document PDF

Tout d'abord, nous devons créer ou ouvrir un document PDF. Pour ce tutoriel, nous allons créer un nouveau document PDF à partir de zéro.

```csharp
// Initialiser le document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Spécifiez votre répertoire de documents
Document doc = new Document();
doc.Pages.Add(); // Ajouter une page vierge au document
```

 Ici, nous initialisons un nouveau`Document` objet qui représente notre fichier PDF. Nous ajoutons ensuite une page vierge à ce document pour travailler dessus.

## Étape 2 : Créer l'annotation à l'encre

Ensuite, nous allons créer l'annotation à l'encre elle-même. Cela implique de définir les points qui composent les traits d'encre.

```csharp
// Créer l'annotation à l'encre
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = Color.Red;
lineInfo.LineWidth = 2;
```

 Dans cette étape, nous définissons le`LineInfo` objet, qui contient les coordonnées des traits d'encre, leur visibilité, leur couleur et la largeur initiale de la ligne.`VerticeCoordinate` le tableau contient les coordonnées X et Y de chaque point du trait.

## Étape 3 : Convertir les coordonnées en points

Maintenant, nous devons convertir ces coordonnées en points qui peuvent être utilisés par l’annotation Ink.

```csharp
// Convertir les coordonnées en points
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
```

 Cette boucle traite le tableau de coordonnées, convertissant chaque paire de coordonnées en un`Point` objet, qui est ensuite ajouté à notre`inkList`.

## Étape 4 : ajouter l'annotation à l'encre sur la page PDF

Avec les points prêts, nous pouvons maintenant créer l’annotation à l’encre et l’ajouter à la page PDF.

```csharp
// Ajoutez l'annotation à l'encre à la page PDF
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(Color.Green);
```

 Dans cette étape, nous initialisons un`InkAnnotation`objet, en spécifiant la page, un rectangle de délimitation et notre liste de points. Nous définissons également le sujet, le titre et la couleur de l'annotation.

## Étape 5 : Personnaliser la bordure de l'annotation

Pour personnaliser davantage l'apparence de notre annotation, nous allons modifier ses propriétés de bordure.

```csharp
// Personnaliser la bordure de l'annotation
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);
```

 Ici, nous créons un`Border` objet pour notre annotation, en définissant sa largeur, son effet, son motif de tiret et son style. Cette étape garantit que l'annotation se démarque visuellement sur la page PDF.

## Étape 6 : Enregistrer le document PDF

Enfin, après avoir effectué toutes les modifications nécessaires, il est temps d'enregistrer le document.

```csharp
// Enregistrer le document PDF
dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation line width setup successfully.\nFile saved at " + dataDir);
```

 Ce code enregistre le document PDF modifié avec l'annotation à l'encre dans le répertoire spécifié.`Console.WriteLine` l'instruction confirme l'exécution réussie du code.

## Conclusion

Félicitations ! Vous avez réussi à créer et personnaliser une annotation manuscrite dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel couvre l'intégralité du processus, de l'initialisation du document à l'enregistrement du fichier final. Grâce à ces connaissances, vous pouvez explorer davantage les vastes capacités d'Aspose.PDF pour .NET et appliquer des techniques similaires à d'autres types d'annotations ou de manipulations PDF.

## FAQ

### Puis-je utiliser différentes couleurs pour différentes parties de l’annotation à l’encre ?  
 Oui, vous pouvez créer plusieurs`InkAnnotation` objets de couleurs différentes et ajoutez-les à la même page ou à des pages différentes de votre PDF.

### Comment modifier la largeur de ligne de manière dynamique ?  
 Vous pouvez ajuster le`LineWidth` propriété de la`LineInfo` objet avant de convertir les coordonnées en points.

### Est-il possible de rendre l'annotation à l'encre transparente ?  
 Oui, vous pouvez modifier le`Opacity` propriété de la`InkAnnotation` objet pour le rendre transparent.

### Puis-je ajouter plusieurs annotations à l’encre sur la même page ?  
Absolument ! Vous pouvez ajouter autant d'annotations à l'encre que vous le souhaitez sur une seule page en répétant le processus.

### Comment supprimer une annotation à l’encre d’un PDF ?  
 Vous pouvez supprimer une annotation à l'aide de la`doc.Pages[1].Annotations.Delete(a1)` méthode, où`a1` est votre objet d'annotation.
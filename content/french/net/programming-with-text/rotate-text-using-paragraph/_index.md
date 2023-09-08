---
title: Faire pivoter le texte à l'aide d'un paragraphe dans un fichier PDF
linktitle: Faire pivoter le texte à l'aide d'un paragraphe dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment faire pivoter du texte à l'aide de paragraphes dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 380
url: /fr/net/programming-with-text/rotate-text-using-paragraph/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour faire pivoter du texte à l'aide de paragraphes. Le code source C# fourni illustre le processus étape par étape.

## Conditions préalables

Avant de poursuivre le didacticiel, assurez-vous d'avoir les éléments suivants :

- Connaissance de base du langage de programmation C#.
- Aspose.PDF pour la bibliothèque .NET installée. Vous pouvez l'obtenir sur le site Web Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Text.TextBuilder;
```

## Étape 3 : Créer le document PDF

 Initialisez le`Document` objet pour créer un nouveau document PDF :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Ajouter une page

 Obtenez une page particulière du document en utilisant le`Pages.Add()` méthode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Étape 5 : Créer le paragraphe de texte

 Créer un`TextParagraph` objet et définissez sa position sur la page :

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
```

Ajustez les valeurs de position selon vos besoins.

## Étape 6 : Créer et configurer des fragments de texte

 Créer plusieurs`TextFragment` objets et définir leur texte et leurs propriétés :

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45;

TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45;
```

Ajustez le texte et les autres propriétés comme vous le souhaitez.

## Étape 7 : Ajouter des fragments de texte au paragraphe

 Ajoutez les fragments de texte créés au paragraphe à l'aide du`AppendLine` méthode:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## Étape 8 : Créez un TextBuilder et ajoutez le paragraphe

 Créer un`TextBuilder` objet à l'aide du`pdfPage` et ajoutez le paragraphe de texte à la page PDF :

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
```

## Étape 9 : Enregistrez le document PDF

 Enregistrez le document PDF modifié dans un fichier à l'aide du`Save` méthode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```

 Assurez-vous de remplacer`"TextFragmentTests_Rotated2_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour faire pivoter le texte à l’aide d’un paragraphe à l’aide d’Aspose.PDF pour .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialiser l'objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600);
// Créer un fragment de texte
TextFragment textFragment1 = new TextFragment("rotated text");
// Définir les propriétés du texte
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment1.TextState.Rotation = 45;
// Créer un fragment de texte
TextFragment textFragment2 = new TextFragment("main text");
// Définir les propriétés du texte
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Créer un fragment de texte
TextFragment textFragment3 = new TextFragment("another rotated text");
// Définir les propriétés du texte
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment3.TextState.Rotation = -45;
// Ajouter les fragments de texte au paragraphe
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
// Créer un objet TextBuilder
TextBuilder textBuilder = new TextBuilder(pdfPage);
// Ajouter le paragraphe de texte à la page PDF
textBuilder.AppendParagraph(paragraph);
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```


## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment faire pivoter du texte à l'aide de paragraphes dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, depuis la création du document jusqu'à l'enregistrement de la version modifiée. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour manipuler la rotation du texte dans les fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Rotation du texte à l'aide d'un paragraphe » ?

: Le didacticiel « Faire pivoter le texte à l'aide d'un paragraphe » vise à vous guider tout au long du processus d'utilisation de la bibliothèque Aspose.PDF pour .NET afin de faire pivoter du texte à l'aide de paragraphes de texte dans un document PDF. Le didacticiel fournit des instructions étape par étape et un exemple de code pour réaliser cette fonctionnalité.

#### Q : Qu'entend-on par « rotation du texte à l'aide de paragraphes » ?

R : La rotation du texte à l'aide de paragraphes fait référence à la possibilité d'appliquer une rotation au texte d'un document PDF à l'aide de paragraphes de texte. Cette technique vous permet d'orienter le texte selon différents angles ou positions dans le contenu PDF.

#### Q : Pourquoi voudrais-je faire pivoter le texte dans un document PDF ?

R : La rotation du texte dans un document PDF peut être utile à diverses fins, telles que mettre en valeur un contenu spécifique, créer des conceptions artistiques ou améliorer la mise en page et la lisibilité.

#### Q : Comment puis-je créer un nouveau document PDF ?

 R : Pour créer un nouveau document PDF, initialisez un`Document`objet de la bibliothèque Aspose.PDF. Vous pouvez utiliser cet objet pour ajouter des pages et du contenu au PDF.

#### Q : Comment faire pivoter du texte à l’aide de paragraphes ?

R : Pour faire pivoter du texte à l’aide de paragraphes :

1.  Créer un`TextParagraph` objet.
2.  Créer`TextFragment` objets avec le texte et les angles de rotation souhaités.
3. Ajoutez les fragments de texte au paragraphe de texte.
4.  Créer un`TextBuilder` objet et ajoutez le paragraphe de texte à une page PDF spécifique.

#### Q : Puis-je contrôler l’angle de rotation de fragments de texte individuels ?

 R : Oui, vous pouvez contrôler l’angle de rotation de l’individu`TextFragment` objets en définissant le`TextState.Rotation` propriété. Les valeurs positives indiquent une rotation dans le sens des aiguilles d'une montre, tandis que les valeurs négatives indiquent une rotation dans le sens inverse des aiguilles d'une montre.

#### Q : Puis-je appliquer différents angles de rotation à différents fragments de texte dans le même paragraphe ?

 R : Oui, vous pouvez appliquer différents angles de rotation à différents`TextFragment` objets dans le même paragraphe en définissant le`TextState.Rotation` propriété de chaque fragment en conséquence.

#### Q : Comment puis-je enregistrer le document PDF pivoté ?

R : Pour enregistrer le document PDF pivoté, utilisez le`Save` méthode du`Document` objet et fournissez le chemin et le nom du fichier de sortie souhaité.
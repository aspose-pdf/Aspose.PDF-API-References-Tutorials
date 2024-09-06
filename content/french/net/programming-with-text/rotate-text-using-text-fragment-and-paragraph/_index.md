---
title: Faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe
linktitle: Faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment faire pivoter du texte à l'aide d'un fragment de texte et d'un paragraphe dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 400
url: /fr/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Ce tutoriel explique comment utiliser Aspose.PDF pour .NET pour faire pivoter du texte à l'aide d'un fragment de texte et d'un paragraphe. Le code source C# fourni illustre le processus étape par étape.

## Prérequis

Avant de poursuivre le didacticiel, assurez-vous de disposer des éléments suivants :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez l'obtenir sur le site Web d'Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Créer le document PDF

 Initialiser le`Document` objet pour créer un nouveau document PDF :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Ajouter une page

 Obtenir une page particulière du document à l'aide de la`Pages.Add()` méthode:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Étape 5 : Créer des fragments de texte

 Créer plusieurs`TextFragment` objets, définissez leur texte et leurs propriétés et spécifiez l'angle de rotation :

```csharp
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");

TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 315;

TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 270;
```

Ajustez le texte, l’angle de rotation et d’autres propriétés comme vous le souhaitez.

## Étape 6 : ajouter des fragments de texte à la page

 Ajoutez les fragments de texte créés à la page en les ajoutant au`Paragraphs` collection:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Étape 7 : Enregistrez le document PDF

 Enregistrez le document PDF modifié dans un fichier à l'aide de la commande`Save` méthode:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

 Assurez-vous de remplacer`"TextFragmentTests_Rotated3_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe à l'aide d'Aspose.PDF pour .NET 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Initialiser l'objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Créer un fragment de texte
TextFragment textFragment1 = new TextFragment("main text");
// Définir les propriétés du texte
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Créer un fragment de texte
TextFragment textFragment2 = new TextFragment("rotated text");
// Définir les propriétés du texte
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment2.TextState.Rotation = 315;
// Créer un fragment de texte
TextFragment textFragment3 = new TextFragment("rotated text");
// Définir les propriétés du texte
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
// Définir la rotation
textFragment3.TextState.Rotation = 270;
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
// Enregistrer le document
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated3_out.pdf");
```

## Conclusion

Félicitations ! Vous avez appris avec succès à faire pivoter du texte à l'aide de fragments de texte et de paragraphes dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, de la création du document à l'enregistrement de la version modifiée. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour manipuler la rotation du texte dans les fichiers PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Faire pivoter le texte à l’aide d’un fragment de texte et d’un paragraphe » ?

R : Le didacticiel « Faire pivoter du texte à l'aide d'un fragment de texte et d'un paragraphe » vise à vous guider dans le processus d'utilisation de la bibliothèque Aspose.PDF pour .NET pour faire pivoter du texte à l'aide de fragments de texte et de paragraphes dans un document PDF. Le didacticiel fournit des instructions étape par étape et un exemple de code pour réaliser cette fonctionnalité.

#### Q : En quoi ce tutoriel diffère-t-il des tutoriels précédents sur la rotation de texte ?

 : Ce didacticiel combine l'utilisation de fragments de texte et de paragraphes pour réaliser une rotation de texte dans un document PDF. Il montre comment faire pivoter des fragments de texte individuellement, puis les ajouter à la page d'une page.`Paragraphs` collection pour obtenir un effet de rotation de texte plus complet.

#### Q : Quels sont les avantages de l’utilisation de fragments de texte et de paragraphes pour la rotation de texte ?

R : L'utilisation conjointe de fragments de texte et de paragraphes permet une plus grande flexibilité dans la rotation du texte. Les fragments de texte permettent des paramètres de rotation et de formatage individuels, tandis que les paragraphes fournissent une structure pour organiser et positionner les fragments de texte dans une page.

#### Q : Puis-je appliquer différents angles de rotation à différents fragments de texte dans le même paragraphe ?

 R : Oui, vous pouvez appliquer différents angles de rotation à différents`TextFragment` objets dans le même paragraphe. Chaque fragment de texte peut avoir son propre angle de rotation spécifié à l'aide de la`TextState.Rotation` propriété.

#### Q : Est-il possible d’obtenir des effets de rotation de texte complexes en utilisant cette méthode ?

: Oui, en combinant des fragments de texte avec différents angles de rotation et en les organisant dans des paragraphes, vous pouvez obtenir des effets de rotation de texte complexes et personnalisés, améliorant ainsi l'attrait visuel de vos documents PDF.

#### Q : Quelles étapes sont impliquées dans la rotation de texte à l’aide de fragments de texte et de paragraphes ?

R : Les étapes comprennent :

1. Configuration du projet en créant un nouveau projet C# et en ajoutant une référence à la bibliothèque Aspose.PDF pour .NET.
2. Création du document PDF et ajout d'une page.
3. Création de fragments de texte, définition de leurs propriétés et spécification des angles de rotation.
4.  Ajout de fragments de texte à la page à l'aide de la`Paragraphs` collection.
5. Enregistrement du document PDF modifié.

#### Q : Puis-je appliquer une rotation à des paragraphes entiers ?

 R : Oui, vous pouvez appliquer une rotation à des paragraphes entiers en définissant le`TextState.Rotation` propriété du paragraphe lui-même. Cela fera pivoter tous les fragments de texte dans ce paragraphe.
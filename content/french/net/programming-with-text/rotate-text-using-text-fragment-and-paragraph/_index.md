---
title: Faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe
linktitle: Faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment faire pivoter du texte à l'aide d'un fragment de texte et d'un paragraphe dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 400
url: /fr/net/programming-with-text/rotate-text-using-text-fragment-and-paragraph/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour faire pivoter du texte à l'aide d'un fragment de texte et d'un paragraphe. Le code source C# fourni illustre le processus étape par étape.

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

## Étape 5 : Créer des fragments de texte

 Créer plusieurs`TextFragment` objets, définissez leur texte et leurs propriétés, et spécifiez l'angle de rotation :

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

Ajustez le texte, l'angle de rotation et d'autres propriétés comme vous le souhaitez.

## Étape 6 : Ajouter des fragments de texte à la page

 Ajoutez les fragments de texte créés à la page en les ajoutant au`Paragraphs` collection:

```csharp
pdfPage.Paragraphs.Add(textFragment1);
pdfPage.Paragraphs.Add(textFragment2);
pdfPage.Paragraphs.Add(textFragment3);
```

## Étape 7 : Enregistrez le document PDF

 Enregistrez le document PDF modifié dans un fichier à l'aide du`Save` méthode:

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

Toutes nos félicitations! Vous avez appris avec succès comment faire pivoter du texte à l'aide de fragments de texte et de paragraphes dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, depuis la création du document jusqu'à l'enregistrement de la version modifiée. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour manipuler la rotation du texte dans les fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Faire pivoter le texte à l'aide d'un fragment de texte et d'un paragraphe » ?

R : Le didacticiel « Faire pivoter le texte à l'aide de fragments de texte et de paragraphes » vise à vous guider tout au long du processus d'utilisation de la bibliothèque Aspose.PDF pour .NET afin de faire pivoter le texte à l'aide de fragments de texte et de paragraphes dans un document PDF. Le didacticiel fournit des instructions étape par étape et un exemple de code pour réaliser cette fonctionnalité.

#### Q : En quoi ce didacticiel diffère-t-il des didacticiels précédents sur la rotation de texte ?

R : Ce didacticiel combine l'utilisation de fragments de texte et de paragraphes pour réaliser la rotation du texte dans un document PDF. Il montre comment faire pivoter des fragments de texte individuellement, puis les ajouter au contenu d'une page.`Paragraphs` collection pour obtenir un effet de rotation de texte plus complet.

#### Q : Quels sont les avantages d’utiliser des fragments de texte et des paragraphes pour la rotation du texte ?

R : L’utilisation conjointe de fragments de texte et de paragraphes permet une plus grande flexibilité dans la rotation du texte. Les fragments de texte permettent des paramètres de rotation et de formatage individuels, tandis que les paragraphes fournissent une structure pour organiser et positionner les fragments de texte dans une page.

#### Q : Puis-je appliquer différents angles de rotation à différents fragments de texte dans le même paragraphe ?

 R : Oui, vous pouvez appliquer différents angles de rotation à différents`TextFragment` objets dans le même paragraphe. Chaque fragment de texte peut avoir son propre angle de rotation spécifié à l'aide du`TextState.Rotation` propriété.

#### Q : Est-il possible d’obtenir des effets de rotation de texte complexes en utilisant cette méthode ?

: Oui, en combinant des fragments de texte avec différents angles de rotation et en les organisant dans des paragraphes, vous pouvez obtenir des effets de rotation de texte complexes et personnalisés, améliorant ainsi l'attrait visuel de vos documents PDF.

#### Q : Quelles sont les étapes impliquées dans la rotation du texte à l'aide de fragments de texte et de paragraphes ?

R : Les étapes comprennent :

1. Configuration du projet en créant un nouveau projet C# et en ajoutant une référence à la bibliothèque Aspose.PDF pour .NET.
2. Création du document PDF et ajout d'une page.
3. Créer des fragments de texte, définir leurs propriétés et spécifier les angles de rotation.
4.  Ajout de fragments de texte à la page à l'aide de l'outil`Paragraphs` collection.
5. Enregistrement du document PDF modifié.

#### Q : Puis-je appliquer une rotation à des paragraphes entiers ?

 R : Oui, vous pouvez appliquer une rotation à des paragraphes entiers en définissant l'option`TextState.Rotation` propriété du paragraphe lui-même. Cela fera pivoter tous les fragments de texte de ce paragraphe.
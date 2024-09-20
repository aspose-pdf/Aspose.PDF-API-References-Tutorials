---
title: Rechercher du texte et dessiner un rectangle
linktitle: Rechercher du texte et dessiner un rectangle
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à rechercher du texte dans des fichiers PDF et à le mettre en surbrillance avec des rectangles à l'aide d'Aspose.PDF pour .NET ! Tutoriel étape par étape simple pour améliorer vos compétences en manipulation de PDF.
type: docs
weight: 460
url: /fr/net/programming-with-text/search-text-and-draw-rectangle/
---
## Introduction

Vous cherchez à améliorer vos compétences en manipulation de PDF ? Vous souhaitez apprendre à rechercher un texte spécifique dans des fichiers PDF et à le mettre en évidence avec un rectangle ? Vous êtes tombé sur le guide parfait ! Aujourd'hui, je vais vous expliquer comment utiliser Aspose.PDF pour .NET pour rechercher du texte dans un document PDF et dessiner des rectangles autour de celui-ci. Cet article fournira un didacticiel étape par étape conçu dans un souci de clarté et d'utilité, vous permettant de suivre et d'appliquer ces techniques à vos projets. 

## Prérequis

Avant de plonger dans le didacticiel, préparons ce dont vous avez besoin pour assurer un flux de travail fluide :

1. Compréhension de base de .NET : vous devez être familiarisé avec la programmation C# et le framework .NET pour suivre efficacement ce didacticiel.
   
2. Visual Studio installé : vous aurez besoin d'un environnement de développement intégré (IDE) pour écrire et tester votre code. Visual Studio Community est une excellente option, et elle est gratuite.
   
3. Aspose.PDF pour .NET : vous devez avoir installé la bibliothèque Aspose.PDF dans votre projet. Vous pouvez la télécharger[ici](https://releases.aspose.com/pdf/net/) ou envisagez un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour des fonctionnalités étendues.
   
4.  Exemple de document PDF : pour ce didacticiel, vous aurez besoin d'un exemple de fichier PDF nommé`SearchAndGetTextFromAll.pdf` stocké dans votre répertoire de projet. 

## Paquets d'importation

Pour commencer, vous devez d'abord importer les packages nécessaires dans votre projet .NET. Suivez ces étapes :

### Ouvrir Visual Studio

Lancez Visual Studio et créez une nouvelle application console ou utilisez-en une existante dans laquelle vous souhaitez implémenter les fonctionnalités PDF.

### Ajoutez Aspose.PDF à votre projet

1. Faites un clic droit sur votre projet dans l’Explorateur de solutions.
2. Sélectionnez « Gérer les packages NuGet ».
3.  Rechercher`Aspose.PDF` et installez la dernière version.

En faisant cela, vous posez les bases de toutes les manipulations PDF étonnantes que vous êtes sur le point d’effectuer.

## Importer des espaces de noms

En haut de votre fichier de programme, vous souhaiterez importer les espaces de noms pertinents de la bibliothèque Aspose :

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

Cela facilite l'accès aux classes et aux méthodes de la bibliothèque Aspose.PDF pour vos tâches.


Maintenant que vous avez tout configuré, décomposons le processus de recherche de texte dans un PDF et de dessin d'un rectangle autour de celui-ci en étapes gérables.

## Étape 1 : définissez le chemin d’accès de votre document

 Tout d'abord, définissez le chemin d'accès à votre fichier PDF. Assurez-vous de remplacer`YOUR DOCUMENT DIRECTORY` avec le chemin réel où votre`SearchAndGetTextFromAll.pdf` est stocké.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrir le document PDF

 Ensuite, créez une instance de`Document` classe pour charger votre PDF :

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

Cette ligne de code ouvre votre fichier PDF spécifié, vous permettant de le manipuler davantage.

## Étape 3 : Créer un absorbeur de texte

 Vous aurez maintenant besoin d'un moyen de rechercher du texte dans ce document. Pour cela, nous utilisons la fonction`TextFragmentAbsorber`:

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 L'expression régulière`@"[\S]+"` est conçu pour correspondre à n'importe quelle chaîne non blanche dans le PDF. 

## Étape 4 : Configurer les options de recherche de texte

Ensuite, vous devez configurer les options de recherche de texte :

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

 Ici, le`true` paramètre signifie que la recherche sera sensible à la casse. Vous pouvez le définir sur`false` si vous souhaitez une recherche insensible à la casse.

## Étape 5 : Accepter l'absorbeur de texte dans le document

 Avec votre`TextFragmentAbsorber` et les options de recherche prêtes, il est temps d'absorber le texte du document :

```csharp
document.Pages.Accept(textAbsorber);
```

Cette méthode examine chaque page de votre PDF pour trouver des fragments de texte correspondant au modèle spécifié.

## Étape 6 : Créer un éditeur de contenu PDF

 Pour dessiner des formes sur le document, vous aurez besoin de`PdfContentEditor`:

```csharp
var editor = new PdfContentEditor(document);
```

Cet éditeur vous permet de manipuler et d'éditer facilement le contenu PDF.

## Étape 7 : Parcourir les fragments de texte trouvés

Maintenant, vous voudrez parcourir les fragments de texte trouvés pour dessiner des rectangles autour d'eux :

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

 Cette boucle itère sur chaque fragment de texte et leurs segments, appelant un`DrawBox` méthode pour dessiner un rectangle.

## Étape 8 : définir la méthode DrawBox

 Vous devez définir le`DrawBox` méthode qui va gérer la logique de dessin du rectangle. Voici une implémentation simple :

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    // Calculer les dimensions du rectangle en fonction du segment de texte
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    // Dessinez un rectangle en utilisant les valeurs calculées
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

Cette méthode détermine la position et la taille du rectangle en fonction du rectangle de délimitation du segment et utilise l'éditeur pour le dessiner.

## Étape 9 : Enregistrer le document modifié

Après avoir dessiné les rectangles autour du texte trouvé, vous pouvez enregistrer le document modifié :

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

Assurez-vous que votre nouveau fichier est enregistré sous un nom distinct pour éviter d'écraser votre document d'origine.

## Étape 10 : Message de confirmation

Enfin, imprimez un message de confirmation sur la console pour vous informer que l'opération a réussi :

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

Et voilà ! Vous avez réussi à créer un script pour rechercher du texte dans un PDF et le mettre en évidence avec des rectangles.

## Conclusion

Félicitations ! Vous venez de débloquer une compétence puissante qui peut grandement améliorer vos capacités de manipulation de PDF à l'aide d'Aspose.PDF pour .NET. En quelques étapes simples, vous pouvez rechercher n'importe quel texte dans votre document et le mettre en surbrillance visuellement, ce qui rend vos documents PDF plus interactifs et plus faciles à gérer. N'hésitez pas à expérimenter différents modèles d'expressions régulières et options de couleur pour vraiment personnaliser cet outil !

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque qui fournit un moyen complet de créer, manipuler et convertir des documents PDF par programmation.

### Puis-je utiliser Aspose.PDF gratuitement ?
Oui, Aspose propose un essai gratuit que vous pouvez utiliser pour tester les fonctionnalités de la bibliothèque. Découvrez-le[ici](https://releases.aspose.com/).

### Quel langage de programmation dois-je utiliser avec Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est conçu pour être utilisé avec C# et d'autres langages .NET.

### Comment puis-je obtenir de l'aide avec Aspose.PDF ?
 Vous pouvez visiter le forum d'assistance Aspose pour obtenir de l'aide concernant tout problème ou toute question que vous pourriez avoir. Trouver de l'aide[ici](https://forum.aspose.com/c/pdf/10).

### Où puis-je télécharger Aspose.PDF pour .NET ?
 Vous pouvez télécharger la bibliothèque à partir du site Web d'Aspose,[ici](https://releases.aspose.com/pdf/net/).
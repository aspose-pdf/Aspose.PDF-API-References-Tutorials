---
title: Rechercher du texte et dessiner un rectangle
linktitle: Rechercher du texte et dessiner un rectangle
second_title: Aspose.PDF pour la référence de l'API .NET
description: Apprenez à rechercher du texte dans un PDF, à dessiner des rectangles autour du texte trouvé et à enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 460
url: /fr/net/programming-with-text/search-text-and-draw-rectangle/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, dessiner un rectangle autour du texte trouvé et enregistrer le document modifié. Le code source C# fourni illustre le processus étape par étape.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Étape 3 : Définir le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide du`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Charger le document PDF

 Chargez le document PDF à l'aide du`Document` classe:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Remplacer`"SearchAndGetTextFromAll.pdf"` avec le nom réel de votre fichier PDF.

## Étape 5 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche saisie :

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Remplacer`@"[\S]+"` avec le modèle d'expression régulière souhaité.

## Étape 6 : Activer la recherche d'expressions régulières

 Activez la recherche d'expressions régulières en définissant le`TextSearchOptions` propriété de l'absorbeur :

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Étape 7 : Rechercher sur toutes les pages

Acceptez l'absorbeur pour toutes les pages du document :

```csharp
document.Pages.Accept(textAbsorber);
```

## Étape 8 : Dessinez un rectangle autour du texte trouvé

 Créer un`PdfContentEditor` objet et parcourez les fragments de texte récupérés, en traçant un rectangle autour de chaque segment de texte :

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## Étape 9 : Enregistrez le document modifié

Enregistrez le document modifié :

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Assurez-vous de remplacer`"SearchTextAndDrawRectangle_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour rechercher du texte et dessiner un rectangle à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
// Créez un objet TextAbsorber pour trouver toutes les phrases correspondant à l'expression régulière
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès comment rechercher un texte spécifique dans un document PDF, dessiner un rectangle autour du texte trouvé et enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, depuis la configuration du projet jusqu'à l'exécution des actions requises. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour manipuler du texte et dessiner des rectangles dans des fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Rechercher du texte et dessiner un rectangle » ?

R : Le didacticiel « Rechercher du texte et dessiner un rectangle » vise à guider les utilisateurs tout au long du processus d'utilisation de la bibliothèque Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, dessiner des rectangles autour des segments de texte trouvés et enregistrer le texte modifié. document. Le didacticiel fournit des instructions détaillées et des exemples de code C# pour illustrer chaque étape du processus.

#### Q : Comment ce didacticiel aide-t-il à dessiner des rectangles autour d'un texte spécifique dans un document PDF ?

R : Ce didacticiel fournit un guide complet sur la façon de localiser et de dessiner des rectangles autour de segments de texte spécifiques dans un document PDF. Il montre le processus de configuration d'un projet, de chargement d'un document PDF, d'activation de la recherche d'expressions régulières, de dessin de rectangles autour des segments de texte trouvés et d'enregistrement du PDF modifié.

#### Q : Quels prérequis sont requis pour suivre ce tutoriel ?

R : Avant de commencer le didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web Aspose ou l'installer dans votre projet à l'aide de NuGet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré. Ensuite, ajoutez une référence à la bibliothèque Aspose.PDF pour .NET à votre projet. Cela vous permettra d'utiliser les fonctionnalités de la bibliothèque pour manipuler des documents PDF.

#### Q : Puis-je dessiner des rectangles autour d'un texte spécifique à l'aide de ce didacticiel ?

R : Oui, le didacticiel se concentre sur le dessin de rectangles autour de segments de texte spécifiques dans un document PDF. Il montre comment localiser le texte souhaité à l'aide d'expressions régulières, créer des rectangles autour des segments de texte identifiés et enregistrer le PDF modifié.

#### Q : Comment puis-je spécifier le texte que je souhaite rechercher et dessiner des rectangles autour ?

 R : Pour spécifier le texte que vous souhaitez rechercher et dessiner des rectangles autour, créez un`TextFragmentAbsorber` objet et définissez son motif à l'aide du`Text` paramètre. Remplacer le modèle par défaut`@"[\S]+"` dans le code du didacticiel avec le modèle d'expression régulière souhaité.

#### Q : Comment puis-je activer la recherche d'expressions régulières pour du texte ?

 R : La recherche d'expressions régulières est activée en créant un`TextSearchOptions` objet et en définissant sa valeur sur`true` . Attribuez cet objet au`TextSearchOptions` propriété du`TextFragmentAbsorber` exemple. Cela garantit que le modèle d'expression régulière est utilisé lors de la recherche de texte.

#### Q : Comment puis-je dessiner des rectangles autour du texte trouvé ?

 R : Après avoir identifié les segments de texte à l'aide du`TextFragmentAbsorber` , le didacticiel fournit une boucle pour parcourir ces segments. Pour chaque segment de texte, le didacticiel montre comment créer un rectangle autour de celui-ci à l'aide de la commande`DrawBox` et spécifiez l’apparence du rectangle.

#### Q : Quelles sont les étapes pour enregistrer le PDF modifié avec des rectangles dessinés ?

R : Après avoir dessiné des rectangles autour des segments de texte souhaités, utilisez le`Document` la classe`Save` méthode pour enregistrer le document modifié. L'exemple de code du didacticiel montre comment enregistrer le PDF modifié et afficher un message de réussite.

#### Q : Puis-je personnaliser l’apparence des rectangles dessinés ?

 R : Oui, vous pouvez personnaliser l’apparence des rectangles dessinés. Dans l'exemple de code du didacticiel, le`DrawBox` La méthode est utilisée pour créer des rectangles. Vous pouvez modifier des propriétés telles que la couleur, le style et l'épaisseur pour personnaliser l'apparence des rectangles dessinés.
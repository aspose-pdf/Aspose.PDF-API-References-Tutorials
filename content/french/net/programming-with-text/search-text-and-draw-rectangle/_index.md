---
title: Rechercher du texte et dessiner un rectangle
linktitle: Rechercher du texte et dessiner un rectangle
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher du texte dans un PDF, dessiner des rectangles autour du texte trouvé et enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 460
url: /fr/net/programming-with-text/search-text-and-draw-rectangle/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, dessiner un rectangle autour du texte trouvé et enregistrer le document modifié. Le code source C# fourni illustre le processus étape par étape.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
```

## Étape 3 : définir le chemin d’accès au répertoire du document

 Définissez le chemin d'accès à votre répertoire de documents à l'aide de l'`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Charger le document PDF

 Chargez le document PDF à l'aide de la`Document` classe:

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

 Remplacer`"SearchAndGetTextFromAll.pdf"` avec le nom réel de votre fichier PDF.

## Étape 5 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée :

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

 Remplacer`@"[\S]+"` avec le modèle d'expression régulière souhaité.

## Étape 6 : Activer la recherche par expression régulière

 Activez la recherche par expression régulière en définissant le`TextSearchOptions` propriété de l'absorbeur :

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## Étape 7 : Rechercher sur toutes les pages

Accepter l'absorbeur pour toutes les pages du document :

```csharp
document.Pages.Accept(textAbsorber);
```

## Étape 8 : Dessinez un rectangle autour du texte trouvé

 Créer un`PdfContentEditor` objet et parcourez les fragments de texte récupérés, en dessinant un rectangle autour de chaque segment de texte :

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

## Étape 9 : Enregistrer le document modifié

Enregistrer le document modifié :

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

 Assurez-vous de remplacer`"SearchTextAndDrawRectangle_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour la recherche de texte et le dessin d'un rectangle à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
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

Félicitations ! Vous avez appris avec succès à rechercher un texte spécifique dans un document PDF, à dessiner un rectangle autour du texte trouvé et à enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, de la configuration du projet à l'exécution des actions requises. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour manipuler du texte et dessiner des rectangles dans des fichiers PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Rechercher du texte et dessiner un rectangle » ?

R : Le didacticiel « Rechercher du texte et dessiner un rectangle » vise à guider les utilisateurs dans le processus d'utilisation de la bibliothèque Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, dessiner des rectangles autour des segments de texte trouvés et enregistrer le document modifié. Le didacticiel fournit des instructions détaillées et des exemples de code C# pour illustrer chaque étape du processus.

#### Q : Comment ce didacticiel aide-t-il à dessiner des rectangles autour d’un texte spécifique dans un document PDF ?

R : Ce didacticiel fournit un guide complet sur la manière de localiser et de dessiner des rectangles autour de segments de texte spécifiques dans un document PDF. Il présente le processus de configuration d'un projet, de chargement d'un document PDF, d'activation de la recherche par expression régulière, de dessin de rectangles autour des segments de texte trouvés et d'enregistrement du PDF modifié.

#### Q : Quels sont les prérequis nécessaires pour suivre ce tutoriel ?

R : Avant de commencer le didacticiel, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET. Vous pouvez l'obtenir sur le site Web d'Aspose ou l'installer dans votre projet à l'aide de NuGet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré. Ajoutez ensuite une référence à la bibliothèque Aspose.PDF pour .NET à votre projet. Cela vous permettra d'utiliser les fonctionnalités de la bibliothèque pour manipuler des documents PDF.

#### Q : Puis-je dessiner des rectangles autour d’un texte spécifique à l’aide de ce didacticiel ?

: Oui, le didacticiel se concentre sur le dessin de rectangles autour de segments de texte spécifiques dans un document PDF. Il montre comment localiser le texte souhaité à l'aide d'expressions régulières, créer des rectangles autour des segments de texte identifiés et enregistrer le PDF modifié.

#### Q : Comment puis-je spécifier le texte que je souhaite rechercher et dessiner des rectangles autour ?

 A : Pour spécifier le texte que vous souhaitez rechercher et dessiner des rectangles autour, créez un`TextFragmentAbsorber` objet et définir son modèle à l'aide de la`Text` paramètre. Remplacez le modèle par défaut`@"[\S]+"` dans le code du didacticiel avec le modèle d'expression régulière souhaité.

#### Q : Comment activer la recherche d’expression régulière pour du texte ?

 A : La recherche par expression régulière est activée en créant un`TextSearchOptions` objet et définir sa valeur sur`true` . Affectez cet objet à la`TextSearchOptions` propriété de la`TextFragmentAbsorber` exemple. Cela garantit que le modèle d'expression régulière est utilisé pendant la recherche de texte.

#### Q : Comment dessiner des rectangles autour du texte trouvé ?

 A : Après avoir identifié les segments de texte à l'aide de la`TextFragmentAbsorber` , le didacticiel fournit une boucle pour parcourir ces segments. Pour chaque segment de texte, le didacticiel montre comment créer un rectangle autour de celui-ci à l'aide de`DrawBox` méthode et spécifiez l'apparence du rectangle.

#### Q : Quelles sont les étapes à suivre pour enregistrer le PDF modifié avec les rectangles dessinés ?

 : Après avoir dessiné des rectangles autour des segments de texte souhaités, utilisez le`Document` classe`Save` méthode pour enregistrer le document modifié. L'exemple de code du didacticiel montre comment enregistrer le PDF modifié et afficher un message de réussite.

#### Q : Puis-je personnaliser l’apparence des rectangles dessinés ?

 R : Oui, vous pouvez personnaliser l'apparence des rectangles dessinés. Dans l'exemple de code du didacticiel, le`DrawBox` La méthode est utilisée pour créer des rectangles. Vous pouvez modifier des propriétés telles que la couleur, le style et l'épaisseur pour personnaliser l'apparence des rectangles dessinés.
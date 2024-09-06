---
title: Rechercher du texte et ajouter un lien hypertexte
linktitle: Rechercher du texte et ajouter un lien hypertexte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher du texte dans un PDF, ajouter des hyperliens au texte trouvé et enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 450
url: /fr/net/programming-with-text/search-text-and-add-hyperlink/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, ajouter un lien hypertexte au texte trouvé et enregistrer le document modifié. Le code source C# fourni illustre le processus étape par étape.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Étape 3 : définir le chemin d’accès au répertoire du document

 Définissez le chemin d'accès à votre répertoire de documents à l'aide de l'`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée :

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Remplacer`"\\d{4}-\\d{4}"` avec le modèle d'expression régulière souhaité.

## Étape 5 : Activer la recherche par expression régulière

 Activez la recherche par expression régulière en définissant le`TextSearchOptions` propriété de l'absorbeur :

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Étape 6 : Ouvrir et relier le document PDF

 Créer un`PdfContentEditor` objet et le lier au fichier PDF source :

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Remplacer`"SearchRegularExpressionPage.pdf"` avec le nom réel de votre fichier PDF.

## Étape 7 : Accepter l'absorbeur pour la page

Accepter l'absorbeur pour la page souhaitée du document :

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Remplacer`1` avec le numéro de page souhaité.

## Étape 8 : ajouter des hyperliens au texte trouvé

Parcourez les fragments de texte récupérés et ajoutez-leur des hyperliens :

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Créer un rectangle basé sur la position du fragment de texte
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Ajouter un lien Web au rectangle
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Remplacer`"http://www.aspose.com"` avec l'URL du lien hypertexte souhaité.

## Étape 9 : Enregistrez et fermez le document modifié

Enregistrez le document modifié et fermez l'éditeur :

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Assurez-vous de remplacer`"SearchTextAndAddHyperlink_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour la recherche de texte et l'ajout d'un lien hypertexte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un objet absorbeur pour rechercher toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Activer la recherche par expression régulière
absorber.TextSearchOptions = new TextSearchOptions(true);
// Ouvrir le document
PdfContentEditor editor = new PdfContentEditor();
// Lier le fichier PDF source
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Accepter l'absorbeur pour la page
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Boucle à travers les fragments
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http:// Www.aspose.com", 1, bleu, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusion

Félicitations ! Vous avez appris avec succès à rechercher un texte spécifique dans un document PDF, à ajouter des hyperliens au texte trouvé et à enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, de la configuration du projet à l'exécution des actions requises. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour manipuler du texte et ajouter des hyperliens dans des fichiers PDF.

### FAQ

#### Q : Quel est le but du didacticiel « Rechercher du texte et ajouter un lien hypertexte » ?

R : Le didacticiel « Rechercher du texte et ajouter un lien hypertexte » vise à montrer comment utiliser la bibliothèque Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, ajouter des liens hypertexte au texte trouvé, puis enregistrer le document modifié. Le didacticiel fournit un guide complet et des exemples de code C# pour illustrer le processus étape par étape.

#### Q : Comment ce didacticiel aide-t-il à ajouter des hyperliens vers un texte spécifique dans un document PDF ?

R : Ce didacticiel vous guide tout au long du processus d'utilisation de la bibliothèque Aspose.PDF pour localiser un texte spécifique dans un document PDF, appliquer un lien hypertexte au texte identifié et enregistrer le PDF modifié. Il couvre les étapes essentielles telles que la configuration du projet, le chargement du document, l'activation de la recherche par expression régulière et l'ajout de liens hypertexte au texte trouvé.

#### Q : Quels sont les prérequis nécessaires pour suivre ce tutoriel ?

: Avant de commencer, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez avoir installé la bibliothèque Aspose.PDF pour .NET, que vous pouvez obtenir sur le site Web d'Aspose ou installer à l'aide de NuGet dans votre projet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré. Ajoutez ensuite une référence à la bibliothèque Aspose.PDF pour .NET, ce qui vous permettra d'utiliser les fonctionnalités de la bibliothèque dans votre projet.

#### Q : Puis-je ajouter des hyperliens vers un texte spécifique à l’aide de ce didacticiel ?

R : Oui, ce didacticiel porte spécifiquement sur l'ajout d'hyperliens vers un texte spécifique dans un document PDF. Il montre comment rechercher et extraire le texte souhaité à l'aide d'expressions régulières, créer des hyperliens associés aux fragments de texte et enregistrer le PDF modifié.

#### Q : Comment définir le texte que je souhaite rechercher et auquel ajouter un lien hypertexte ?

 A : Pour spécifier le texte que vous souhaitez rechercher et auquel ajouter un lien hypertexte, créez un`TextFragmentAbsorber` objet et définir son modèle à l'aide de la`Text` paramètre. Remplacez le modèle par défaut`"\\d{4}-\\d{4}"` dans le code du didacticiel avec le modèle d'expression régulière souhaité.

#### Q : Comment puis-je activer la recherche d’expression régulière pour du texte ?

 A : La recherche par expression régulière est activée en créant un`TextSearchOptions` objet et définir sa valeur sur`true` . Affectez cet objet à la`TextSearchOptions` propriété de la`TextFragmentAbsorber` exemple. Cela garantit que le modèle d'expression régulière est appliqué pendant la recherche de texte.

#### Q : Comment ajouter des hyperliens au texte trouvé ?

 A : Après avoir identifié les fragments de texte à l'aide de la`TextFragmentAbsorber` , le didacticiel fournit une boucle pour parcourir ces fragments. Pour chaque fragment de texte, le didacticiel montre comment définir la couleur du texte sur bleu et créer un lien hypertexte à l'aide de`CreateWebLink` méthode.

#### Q : Quelles sont les étapes à suivre pour enregistrer le PDF modifié avec des hyperliens ?

 A : Après avoir ajouté des hyperliens vers les fragments de texte souhaités, utilisez le`PdfContentEditor` classe pour enregistrer le document modifié. L'exemple de code du didacticiel montre comment enregistrer le PDF modifié, fermer l'éditeur et afficher un message de réussite.
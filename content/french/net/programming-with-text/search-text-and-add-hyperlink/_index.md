---
title: Rechercher du texte et ajouter un lien hypertexte
linktitle: Rechercher du texte et ajouter un lien hypertexte
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment rechercher du texte dans un PDF, ajouter des hyperliens vers le texte trouvé et enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 450
url: /fr/net/programming-with-text/search-text-and-add-hyperlink/
---
Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, ajouter un lien hypertexte vers le texte trouvé et enregistrer le document modifié. Le code source C# fourni illustre le processus étape par étape.

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide du`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 4 : Créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche saisie :

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Remplacer`"\\d{4}-\\d{4}"` avec le modèle d'expression régulière souhaité.

## Étape 5 : Activer la recherche d'expressions régulières

 Activez la recherche d'expressions régulières en définissant le`TextSearchOptions` propriété de l'absorbeur :

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Étape 6 : Ouvrir et lier le document PDF

 Créer un`PdfContentEditor` objet et liez-le au fichier PDF source :

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Remplacer`"SearchRegularExpressionPage.pdf"` avec le nom réel de votre fichier PDF.

## Étape 7 : Acceptez l'absorbeur pour la page

Acceptez l'absorbeur pour la page souhaitée du document :

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Remplacer`1` avec le numéro de page souhaité.

## Étape 8 : Ajouter des hyperliens au texte trouvé

Parcourez les fragments de texte récupérés et ajoutez-y des hyperliens :

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Créez un rectangle basé sur la position du fragment de texte
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //Ajouter un lien web au rectangle
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

 Remplacer`"http://www.aspose.com"` avec l’URL du lien hypertexte souhaité.

## Étape 9 : Enregistrez et fermez le document modifié

Enregistrez le document modifié et fermez l'éditeur :

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

 Assurez-vous de remplacer`"SearchTextAndAddHyperlink_out.pdf"` avec le nom du fichier de sortie souhaité.

### Exemple de code source pour rechercher du texte et ajouter un lien hypertexte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créez un objet absorbeur pour trouver toutes les instances de la phrase de recherche saisie
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Activer la recherche d'expressions régulières
absorber.TextSearchOptions = new TextSearchOptions(true);
// Ouvrir le document
PdfContentEditor editor = new PdfContentEditor();
// Lier le fichier PDF source
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
// Acceptez l'absorbeur pour la page
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
// Parcourez les fragments
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

Toutes nos félicitations! Vous avez appris avec succès comment rechercher un texte spécifique dans un document PDF, ajouter des hyperliens vers le texte trouvé et enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit un guide étape par étape, depuis la configuration du projet jusqu'à l'exécution des actions requises. Vous pouvez désormais intégrer ce code dans vos propres projets C# pour manipuler du texte et ajouter des hyperliens dans les fichiers PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Rechercher du texte et ajouter un lien hypertexte » ?

R : Le didacticiel « Rechercher du texte et ajouter un lien hypertexte » vise à montrer comment utiliser la bibliothèque Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, ajouter des hyperliens au texte trouvé, puis enregistrer le document modifié. Le didacticiel fournit un guide complet et des exemples de code C# pour illustrer le processus étape par étape.

#### Q : Comment ce didacticiel aide-t-il à ajouter des hyperliens vers du texte spécifique dans un document PDF ?

R : Ce didacticiel vous guide tout au long du processus d'utilisation de la bibliothèque Aspose.PDF pour localiser un texte spécifique dans un document PDF, appliquer un lien hypertexte vers le texte identifié et enregistrer le PDF modifié. Il couvre les étapes essentielles telles que la configuration du projet, le chargement du document, l'activation de la recherche d'expressions régulières et l'ajout d'hyperliens vers le texte trouvé.

#### Q : Quels prérequis sont nécessaires pour suivre ce tutoriel ?

R : Avant de commencer, vous devez avoir une compréhension de base du langage de programmation C#. De plus, vous devez installer la bibliothèque Aspose.PDF pour .NET, qui peut être obtenue sur le site Web Aspose ou installée à l'aide de NuGet dans votre projet.

#### Q : Comment configurer mon projet pour suivre ce tutoriel ?

R : Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré. Ensuite, ajoutez une référence à la bibliothèque Aspose.PDF pour .NET, ce qui vous permettra d'utiliser les fonctionnalités de la bibliothèque dans votre projet.

#### Q : Puis-je ajouter des hyperliens vers un texte spécifique à l’aide de ce didacticiel ?

R : Oui, ce didacticiel se concentre spécifiquement sur l'ajout d'hyperliens vers un texte spécifique dans un document PDF. Il montre comment rechercher et extraire le texte souhaité à l'aide d'expressions régulières, créer des hyperliens associés aux fragments de texte et enregistrer le PDF modifié.

#### Q : Comment définir le texte que je souhaite rechercher et auquel ajouter un lien hypertexte ?

 R : Pour spécifier le texte que vous souhaitez rechercher et ajouter un lien hypertexte, créez un`TextFragmentAbsorber` objet et définissez son motif à l'aide du`Text` paramètre. Remplacer le modèle par défaut`"\\d{4}-\\d{4}"` dans le code du didacticiel avec le modèle d'expression régulière souhaité.

#### Q : Comment puis-je activer la recherche d'expressions régulières pour du texte ?

 R : La recherche d'expressions régulières est activée en créant un`TextSearchOptions` objet et en définissant sa valeur sur`true` . Attribuez cet objet au`TextSearchOptions` propriété du`TextFragmentAbsorber` exemple. Cela garantit que le modèle d'expression régulière est appliqué lors de la recherche de texte.

#### Q : Comment puis-je ajouter des hyperliens au texte trouvé ?

 R : Après avoir identifié les fragments de texte à l'aide du`TextFragmentAbsorber` , le didacticiel fournit une boucle pour parcourir ces fragments. Pour chaque fragment de texte, le didacticiel montre comment définir la couleur du texte sur bleu et créer un lien hypertexte à l'aide de l'option`CreateWebLink` méthode.

#### Q : Quelles sont les étapes pour enregistrer le PDF modifié avec des hyperliens ?

 R : Après avoir ajouté des hyperliens vers les fragments de texte souhaités, utilisez le`PdfContentEditor` classe pour enregistrer le document modifié. L'exemple de code du didacticiel montre comment enregistrer le PDF modifié, fermer l'éditeur et afficher un message de réussite.
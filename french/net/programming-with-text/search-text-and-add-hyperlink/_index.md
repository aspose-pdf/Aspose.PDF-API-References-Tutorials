---
title: Rechercher du texte et ajouter un lien hypertexte
linktitle: Rechercher du texte et ajouter un lien hypertexte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher du texte dans un PDF, ajouter des liens hypertexte au texte trouvé et enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 450
url: /fr/net/programming-with-text/search-text-and-add-hyperlink/
---

Ce didacticiel explique comment utiliser Aspose.PDF pour .NET pour rechercher un texte spécifique dans un document PDF, ajouter un lien hypertexte au texte trouvé et enregistrer le document modifié. Le code source C# fourni illustre le processus étape par étape.

## Conditions préalables

Avant de poursuivre le didacticiel, assurez-vous que vous disposez des éléments suivants :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez l'obtenir sur le site Web d'Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Commencez par créer un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## Étape 3 : Définissez le chemin d'accès au répertoire de documents

 Définissez le chemin d'accès à votre répertoire de documents à l'aide de la`dataDir` variable:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 4 : créer un TextFragmentAbsorber

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée :

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

 Remplacer`"\\d{4}-\\d{4}"` avec le modèle d'expression régulière souhaité.

## Étape 5 : Activer la recherche d'expressions régulières

Activez la recherche d'expressions régulières en définissant le`TextSearchOptions` propriété de l'absorbeur :

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## Étape 6 : Ouvrir et relier le document PDF

 Créer un`PdfContentEditor` objet et liez-le au fichier PDF source :

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Remplacer`"SearchRegularExpressionPage.pdf"` avec le nom réel de votre fichier PDF.

## Étape 7 : Acceptez l'absorbeur pour la page

Acceptez l'absorbeur pour la page souhaitée du document :

```csharp
editor.Document.Pages[1].Accept(absorber);
```

 Remplacer`1` avec le numéro de page souhaité.

## Étape 8 : Ajouter des hyperliens au texte trouvé

Parcourez les fragments de texte récupérés et ajoutez-y des hyperliens :

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    // Créer un rectangle basé sur la position du fragment de texte
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    // Ajouter un lien Web au rectangle
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

 Assurez-vous de remplacer`"SearchTextAndAddHyperlink_out.pdf"` avec le nom de fichier de sortie souhaité.

### Exemple de code source pour rechercher du texte et ajouter un lien hypertexte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un objet absorbeur pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
// Activer la recherche d'expressions régulières
absorber.TextSearchOptions = new TextSearchOptions(true);
// Ouvrir le document
PdfContentEditor editor = new PdfContentEditor();
//Lier le fichier PDF source
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

Toutes nos félicitations! Vous avez appris avec succès à rechercher un texte spécifique dans un document PDF, à ajouter des liens hypertexte au texte trouvé et à enregistrer le document modifié à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a fourni un guide étape par étape, de la configuration du projet à l'exécution des actions requises. Vous pouvez désormais incorporer ce code dans vos propres projets C# pour manipuler du texte et ajouter des hyperliens dans les fichiers PDF.
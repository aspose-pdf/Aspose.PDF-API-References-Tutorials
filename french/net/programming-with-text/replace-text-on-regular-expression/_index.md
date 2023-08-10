---
title: Remplacer le texte sur l'expression régulière
linktitle: Remplacer l'expression régulière Texton
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à remplacer du texte basé sur une expression régulière dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 360
url: /fr/net/programming-with-text/replace-text-on-regular-expression/
---

Dans ce didacticiel, nous expliquerons comment remplacer du texte basé sur une expression régulière dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous fournirons un guide étape par étape avec le code source C # nécessaire.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Bibliothèque Aspose.PDF pour .NET installée.
- Compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Définissez le chemin d'accès au répertoire dans lequel vous avez le fichier PDF d'entrée. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir`variable avec le chemin d'accès à votre fichier PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le document PDF

 Chargez le document PDF à l'aide du`Document` classe de la bibliothèque Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## Étape 3 : Rechercher et remplacer du texte à l'aide d'une expression régulière

 Créer un`TextFragmentAbsorber` objet et spécifiez le modèle d'expression régulière pour trouver toutes les phrases correspondant au modèle. Définissez l'option de recherche de texte pour activer l'utilisation des expressions régulières.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Comme 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## Étape 4 : Remplacer le texte

Parcourez les fragments de texte extraits et remplacez le texte si nécessaire. Mettez à jour le texte et d'autres propriétés telles que la police, la taille de la police, la couleur de premier plan et la couleur d'arrière-plan.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Étape 5 : Enregistrez le PDF modifié

Enregistrez le document PDF modifié dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### Exemple de code source pour Remplacer l'expression régulière de Texton à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
// Créez un objet TextAbsorber pour trouver toutes les phrases correspondant à l'expression régulière
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // Comme 1999-2000
// Définir l'option de recherche de texte pour spécifier l'utilisation des expressions régulières
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// Accepter l'absorbeur pour une seule page
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Boucle à travers les fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Mettre à jour le texte et d'autres propriétés
	textFragment.Text = "New Phrase";
	// Défini sur une instance d'un objet.
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, vous avez appris à remplacer du texte basé sur une expression régulière dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez charger un document PDF, rechercher du texte à l'aide d'une expression régulière, le remplacer et enregistrer le PDF modifié.
---
title: Remplacer tout le texte
linktitle: Remplacer tout le texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à remplacer tout le texte d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 350
url: /fr/net/programming-with-text/replace-text-all/
---

Dans ce didacticiel, nous expliquerons comment remplacer tout le texte d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous fournirons un guide étape par étape avec le code source C # nécessaire.

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
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## Étape 3 : Rechercher et remplacer du texte

 Créer un`TextFragmentAbsorber` objet pour trouver toutes les instances de la phrase de recherche d'entrée. Acceptez l'absorbeur pour toutes les pages du document PDF pour extraire les fragments de texte.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Étape 4 : Remplacer le texte

Parcourez les fragments de texte extraits et remplacez le texte si nécessaire. Mettez à jour le texte et d'autres propriétés telles que la police, la taille de la police, la couleur de premier plan et la couleur d'arrière-plan.

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## Étape 5 : Enregistrez le PDF modifié

Enregistrez le document PDF modifié dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour Remplacer tout le texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
//Créer un objet TextAbsorber pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accepter l'absorbeur pour toutes les pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// Boucle à travers les fragments
foreach (TextFragment textFragment in textFragmentCollection)
{
	// Mettre à jour le texte et d'autres propriétés
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
// Enregistrez le document PDF résultant.
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, vous avez appris à remplacer tout le texte d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez charger un document PDF, rechercher le texte souhaité, le remplacer et enregistrer le PDF modifié.
---
title: Remplacer la première occurrence
linktitle: Remplacer la première occurrence
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à remplacer la première occurrence de texte dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 330
url: /fr/net/programming-with-text/replace-first-occurrence/
---

Dans ce didacticiel, nous expliquerons comment remplacer la première occurrence d'un texte spécifique dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons passer par le processus étape par étape d'ouverture d'un document PDF, de recherche de la première occurrence de la phrase de recherche, de remplacement du texte, de mise à jour des propriétés et d'enregistrement du PDF modifié à l'aide du code source C# fourni.

## Conditions préalables

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire dans lequel vous avez le fichier PDF d'entrée. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès à votre fichier PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF

 Ensuite, nous ouvrons le document PDF en utilisant le`Document` classe de la bibliothèque Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Étape 3 : Trouver la première occurrence de la phrase de recherche

 Nous créons un`TextFragmentAbsorber`objet et acceptez-le pour toutes les pages du document PDF afin de trouver toutes les instances de la phrase de recherche.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## Étape 4 : Remplacez le texte

Si la phrase de recherche est trouvée dans le document PDF, nous récupérons la première occurrence du fragment de texte et mettons à jour ses propriétés avec le nouveau texte et la mise en forme.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
    TextFragment textFragment = textFragmentCollection[1];
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
}
```

## Étape 5 : Enregistrez le PDF modifié

Enfin, nous enregistrons le document PDF modifié dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour Remplacer la première occurrence à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
// Créer un objet TextAbsorber pour trouver toutes les instances de la phrase de recherche d'entrée
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// Accepter l'absorbeur pour toutes les pages
pdfDocument.Pages.Accept(textFragmentAbsorber);
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
if (textFragmentCollection.Count > 0)
{
	// Obtenir la première occurrence du texte et remplacer
	TextFragment textFragment = textFragmentCollection[1];
	// Mettre à jour le texte et d'autres propriétés
	textFragment.Text = "New Phrase";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	dataDir = dataDir + "ReplaceFirstOccurrence_out.pdf";
	pdfDocument.Save(dataDir);                 
	Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à remplacer la première occurrence d'un texte spécifique dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez ouvrir un document PDF, rechercher la première occurrence d'une expression de recherche, remplacer le texte, mettre à jour les propriétés et enregistrer le PDF modifié.
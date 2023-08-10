---
title: Remplacer les polices
linktitle: Remplacer les polices
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à remplacer les polices dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 340
url: /fr/net/programming-with-text/replace-fonts/
---

Dans ce didacticiel, nous expliquerons comment remplacer des polices spécifiques dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons passer par le processus étape par étape de chargement d'un document PDF, de recherche de fragments de texte, d'identification des polices à remplacer, de remplacement des polices et d'enregistrement du PDF modifié à l'aide du code source C# fourni.

## Conditions préalables

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire dans lequel vous avez le fichier PDF d'entrée. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir`variable avec le chemin d'accès à votre fichier PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le document PDF

 Ensuite, nous chargeons le document PDF en utilisant le`Document` classe de la bibliothèque Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Étape 3 : Rechercher et remplacer les polices

 Nous créons un`TextFragmentAbsorber` objet et définissez l'option d'édition pour supprimer les polices inutilisées. Ensuite, nous acceptons l'absorbeur pour toutes les pages du document PDF pour rechercher des fragments de texte.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Étape 4 : remplacer les polices

Nous parcourons tous les fragments de texte identifiés par l'absorbeur. Si le nom de la police d'un fragment de texte correspond à la police que vous souhaitez remplacer, nous la remplaçons par la nouvelle police.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Étape 5 : Enregistrez le PDF modifié

Enfin, nous enregistrons le document PDF modifié dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Exemple de code source pour remplacer les polices à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF source
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Rechercher des fragments de texte et définir l'option d'édition pour supprimer les polices inutilisées
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Accepter l'absorbeur pour toutes les pages
	pdfDocument.Pages.Accept(absorber);
	// Parcourez tous les TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		// Si le nom de la police est ArialMT, remplacez le nom de la police par Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	// Enregistrer le document mis à jour
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à remplacer des polices spécifiques dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez charger un document PDF, rechercher des fragments de texte, identifier et remplacer des polices spécifiques et enregistrer le PDF modifié.
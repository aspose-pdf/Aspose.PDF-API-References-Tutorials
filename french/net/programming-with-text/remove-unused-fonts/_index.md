---
title: Supprimer les polices inutilisées
linktitle: Supprimer les polices inutilisées
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à supprimer les polices inutilisées d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 300
url: /fr/net/programming-with-text/remove-unused-fonts/
---

Dans ce didacticiel, nous expliquerons comment supprimer les polices inutilisées d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons suivre le processus étape par étape de chargement d'un PDF, d'identification et de suppression des polices inutilisées, et d'enregistrement du PDF mis à jour à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire où se trouvent vos fichiers PDF. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès à vos fichiers PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le PDF source

 Ensuite, nous chargeons le document PDF source en utilisant le`Document` classe de la bibliothèque Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Étape 3 : identifier et supprimer les polices inutilisées

 Nous créons un`TextFragmentAbsorber` objet avec le`TextEditOptions` paramètre réglé sur`TextEditOptions.FontReplace.RemoveUnusedFonts` Cette option nous permet d'identifier et de supprimer les polices inutilisées dans le document PDF. Nous parcourons ensuite tous les`TextFragments` et définissez la police sur la police souhaitée.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Étape 4 : Enregistrez le PDF mis à jour

Enfin, nous enregistrons le document PDF mis à jour dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Exemple de code source pour supprimer les polices inutilisées à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF source
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Itérer à travers tous les TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	// Enregistrer le document mis à jour
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à supprimer les polices inutilisées d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez charger un PDF, identifier et supprimer les polices inutilisées et enregistrer le PDF mis à jour.
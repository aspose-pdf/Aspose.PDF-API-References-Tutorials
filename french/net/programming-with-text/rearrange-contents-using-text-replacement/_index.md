---
title: Réorganiser le contenu à l'aide du remplacement de texte
linktitle: Réorganiser le contenu à l'aide du remplacement de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à réorganiser le contenu d'un document PDF en utilisant le remplacement de texte avec Aspose.PDF pour .NET.
type: docs
weight: 270
url: /fr/net/programming-with-text/rearrange-contents-using-text-replacement/
---

Dans ce didacticiel, nous expliquerons comment réorganiser le contenu d'un document PDF en utilisant le remplacement de texte avec la bibliothèque Aspose.PDF pour .NET. Nous allons passer par le processus étape par étape de chargement d'un PDF, de recherche de fragments de texte spécifiques, de remplacement du texte et d'enregistrement du PDF modifié à l'aide du code source C# fourni.

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
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## Étape 3 : Rechercher et remplacer des fragments de texte

 Nous créons un`TextFragmentAbsorber` objet avec une expression régulière pour rechercher des fragments de texte spécifiques. Ensuite, nous parcourons les fragments de texte, personnalisons leur police, leur taille, leur couleur et remplaçons le texte.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## Étape 4 : Enregistrer le PDF modifié

Enfin, nous enregistrons le document PDF modifié dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### Exemple de code source pour réorganiser le contenu à l'aide du remplacement de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF source
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	//Créer un objet TextFragment Absorber avec une expression régulière
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	// Remplacer chaque TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		// Définir la police du fragment de texte à remplacer
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		// Définir la taille de la police
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		// Remplacez le texte par une chaîne plus grande que l'espace réservé
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	// Enregistrer le PDF résultant
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à réorganiser le contenu d'un document PDF en utilisant le remplacement de texte avec la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez rechercher des fragments de texte spécifiques, personnaliser leur apparence et remplacer le texte dans un document PDF.
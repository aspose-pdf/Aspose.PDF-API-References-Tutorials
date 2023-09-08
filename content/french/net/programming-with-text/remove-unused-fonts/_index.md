---
title: Supprimer les polices inutilisées dans un fichier PDF
linktitle: Supprimer les polices inutilisées dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment supprimer les polices inutilisées dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 300
url: /fr/net/programming-with-text/remove-unused-fonts/
---
Dans ce didacticiel, nous expliquerons comment supprimer les polices inutilisées dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous passerons en revue le processus étape par étape de chargement d'un PDF, d'identification et de suppression des polices inutilisées et d'enregistrement du PDF mis à jour à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : configurer le répertoire de documents

 Tout d’abord, vous devez définir le chemin d’accès au répertoire où se trouvent vos fichiers PDF. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès à vos fichiers PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le PDF source

 Ensuite, nous chargeons le document PDF source à l'aide du`Document` classe de la bibliothèque Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Étape 3 : identifier et supprimer les polices inutilisées

 Nous créons un`TextFragmentAbsorber` objet avec le`TextEditOptions` paramètre réglé sur`TextEditOptions.FontReplace.RemoveUnusedFonts` . Cette option nous permet d'identifier et de supprimer les polices inutilisées dans le document PDF. Nous parcourons ensuite tous les`TextFragments` et définissez la police sur la police souhaitée.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Étape 4 : Enregistrez le PDF mis à jour

Enfin, nous enregistrons le document PDF mis à jour dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### Exemple de code source pour supprimer les polices inutilisées à l’aide d’Aspose.PDF pour .NET 
```csharp
try
{
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF source
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Parcourez tous les TextFragments
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
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à supprimer les polices inutilisées d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez charger un PDF, identifier et supprimer les polices inutilisées et enregistrer le PDF mis à jour.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Supprimer les polices inutilisées dans un fichier PDF » ?

R : Le didacticiel « Supprimer les polices inutilisées dans un fichier PDF » explique comment utiliser la bibliothèque Aspose.PDF pour .NET pour supprimer les polices inutilisées d'un document PDF. Le didacticiel vous guide tout au long du processus de chargement d'un PDF, d'identification et de suppression des polices inutilisées et d'enregistrement du PDF mis à jour.

#### Q : Pourquoi voudrais-je supprimer les polices inutilisées d’un document PDF ?

R : La suppression des polices inutilisées d'un document PDF peut aider à réduire la taille du fichier et à optimiser le document pour de meilleures performances. Ceci est particulièrement utile lorsqu'il s'agit de fichiers PDF contenant des polices intégrées qui ne sont pas réellement utilisées dans le contenu du document.

#### Q : Comment configurer le répertoire de documents ?

R : Pour configurer le répertoire de documents :

1.  Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès au répertoire où se trouvent vos fichiers PDF.

#### : Comment supprimer les polices inutilisées d'un document PDF à l'aide de la bibliothèque Aspose.PDF ?

R : Le didacticiel vous guide étape par étape tout au long du processus :

1.  Ouvrez le document PDF à l'aide du`Document` classe.
2.  Créer un`TextFragmentAbsorber` objet avec`TextEditOptions` mis à`FontReplace.RemoveUnusedFonts`.
3. Acceptez le absorbeur pour identifier et supprimer les polices inutilisées du PDF.
4.  Parcourez tout`TextFragments` et définissez la police sur la police souhaitée.
5. Enregistrez le document PDF mis à jour.

####  Q : Quel est le but du`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 R : Le`TextEditOptions.FontReplace.RemoveUnusedFonts` Le paramètre indique au`TextFragmentAbsorber` pour identifier et supprimer les polices inutilisées du document PDF.

#### Q : Puis-je remplacer les polices inutilisées par une police de mon choix ?

R : Oui, vous pouvez modifier le code pour remplacer les polices inutilisées par une police de votre choix. Dans l’exemple de code fourni, la police « Arial, Bold » est utilisée en remplacement.

####  Q : Comment le`TextFragmentAbsorber` work to remove unused fonts?

 R : Le`TextFragmentAbsorber` est configuré avec le`TextEditOptions.FontReplace.RemoveUnusedFonts` paramètre, qui identifie les polices inutilisées dans les fragments de texte du PDF. Après absorption, vous pouvez parcourir le`TextFragments` et définissez leurs polices sur les polices de remplacement souhaitées.

#### Q : Quel est le résultat attendu de l’exécution du code fourni ?

R : En suivant le didacticiel et en exécutant le code C# fourni, vous supprimerez les polices inutilisées du document PDF d'entrée et enregistrerez la version mise à jour en tant que fichier PDF de sortie.

#### Q : Puis-je modifier le code pour supprimer les polices uniquement de pages ou de zones spécifiques ?

R : Le code fourni se concentre sur la suppression des polices inutilisées de l'ensemble du document PDF. Si vous souhaitez cibler des pages ou des régions spécifiques pour la suppression des polices, vous devrez modifier l'approche et utiliser une logique plus complexe pour identifier les polices inutilisées dans ces zones.
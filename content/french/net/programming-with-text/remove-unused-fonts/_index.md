---
title: Supprimer les polices inutilisées dans le fichier PDF
linktitle: Supprimer les polices inutilisées dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment supprimer les polices inutilisées dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 300
url: /fr/net/programming-with-text/remove-unused-fonts/
---
Dans ce tutoriel, nous expliquerons comment supprimer les polices inutilisées dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous passerons en revue le processus étape par étape de chargement d'un PDF, d'identification et de suppression des polices inutilisées et d'enregistrement du PDF mis à jour à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous de disposer des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire où se trouvent vos fichiers PDF. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin vers vos fichiers PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le PDF source

 Ensuite, nous chargeons le document PDF source à l’aide de la`Document` classe de la bibliothèque Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Étape 3 : identifier et supprimer les polices inutilisées

 Nous créons un`TextFragmentAbsorber` objet avec le`TextEditOptions` paramètre défini sur`TextEditOptions.FontReplace.RemoveUnusedFonts` . Cette option nous permet d'identifier et de supprimer les polices inutilisées dans le document PDF. Nous parcourons ensuite toutes les`TextFragments` et définissez la police sur la police souhaitée.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## Étape 4 : Enregistrer le PDF mis à jour

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
	// Le chemin vers le répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF source
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	// Parcourir tous les fragments de texte
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

#### Q : Quel est le but du didacticiel « Supprimer les polices inutilisées dans un fichier PDF » ?

R : Le didacticiel « Supprimer les polices inutilisées dans un fichier PDF » explique comment utiliser la bibliothèque Aspose.PDF pour .NET pour supprimer les polices inutilisées d'un document PDF. Le didacticiel vous guide tout au long du processus de chargement d'un PDF, d'identification et de suppression des polices inutilisées et d'enregistrement du PDF mis à jour.

#### Q : Pourquoi voudrais-je supprimer les polices inutilisées d’un document PDF ?

R : La suppression des polices inutilisées d'un document PDF peut contribuer à réduire la taille du fichier et à optimiser le document pour de meilleures performances. Cela est particulièrement utile lorsque vous travaillez avec des PDF contenant des polices intégrées qui ne sont pas réellement utilisées dans le contenu du document.

#### Q : Comment configurer le répertoire de documents ?

A : Pour configurer le répertoire de documents :

1.  Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin vers le répertoire où se trouvent vos fichiers PDF.

#### Q : Comment supprimer les polices inutilisées d'un document PDF à l'aide de la bibliothèque Aspose.PDF ?

R : Le tutoriel vous guide tout au long du processus étape par étape :

1.  Ouvrez le document PDF à l'aide du`Document` classe.
2.  Créer un`TextFragmentAbsorber` objet avec`TextEditOptions` régler sur`FontReplace.RemoveUnusedFonts`.
3. Acceptez l'absorbeur pour identifier et supprimer les polices inutilisées du PDF.
4.  Itérer à travers tout`TextFragments` et définissez la police sur la police souhaitée.
5. Enregistrez le document PDF mis à jour.

####  Q : Quel est le but de la`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

 A : Le`TextEditOptions.FontReplace.RemoveUnusedFonts` paramètre indique le`TextFragmentAbsorber`pour identifier et supprimer les polices inutilisées du document PDF.

#### Q : Puis-je remplacer les polices inutilisées par une police de mon choix ?

R : Oui, vous pouvez modifier le code pour remplacer les polices inutilisées par une police de votre choix. Dans l'exemple de code fourni, la police « Arial, Bold » est utilisée en remplacement.

####  : Comment fonctionne le`TextFragmentAbsorber` work to remove unused fonts?

 A : Le`TextFragmentAbsorber` est configuré avec le`TextEditOptions.FontReplace.RemoveUnusedFonts` paramètre, qui identifie les polices inutilisées dans les fragments de texte du PDF. Après absorption, vous pouvez parcourir le`TextFragments` et définissez leurs polices sur les polices de remplacement souhaitées.

#### Q : Quel est le résultat attendu de l’exécution du code fourni ?

R : En suivant le didacticiel et en exécutant le code C# fourni, vous supprimerez les polices inutilisées du document PDF d’entrée et enregistrerez la version mise à jour en tant que fichier PDF de sortie.

#### Q : Puis-je modifier le code pour supprimer les polices uniquement de pages ou de zones spécifiques ?

R : Le code fourni se concentre sur la suppression des polices inutilisées de l'ensemble du document PDF. Si vous souhaitez cibler des pages ou des zones spécifiques pour la suppression des polices, vous devez modifier l'approche et utiliser une logique plus complexe pour identifier les polices inutilisées dans ces zones.
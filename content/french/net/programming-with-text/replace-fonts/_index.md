---
title: Remplacer les polices dans un fichier PDF
linktitle: Remplacer les polices dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment remplacer les polices dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 340
url: /fr/net/programming-with-text/replace-fonts/
---
Dans ce didacticiel, nous expliquerons comment remplacer des polices spécifiques dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous passerons en revue le processus étape par étape de chargement d'un document PDF, de recherche de fragments de texte, d'identification des polices à remplacer, de remplacement des polices et d'enregistrement du PDF modifié à l'aide du code source C# fourni.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : configurer le répertoire de documents

 Tout d’abord, vous devez définir le chemin d’accès au répertoire dans lequel se trouve le fichier PDF d’entrée. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès à votre fichier PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document PDF

 Ensuite, nous chargeons le document PDF en utilisant le`Document` classe de la bibliothèque Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## Étape 3 : Rechercher et remplacer les polices

 Nous créons un`TextFragmentAbsorber`objet et définissez l’option d’édition pour supprimer les polices inutilisées. Ensuite, nous acceptons l'absorbeur de toutes les pages du document PDF pour rechercher des fragments de texte.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## Étape 4 : Remplacer les polices

Nous parcourons tous les fragments de texte identifiés par l’absorbeur. Si le nom de police d'un fragment de texte correspond à la police que vous souhaitez remplacer, nous le remplaçons par la nouvelle police.

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## Étape 5 : Enregistrez le PDF modifié

Enfin, nous enregistrons le document PDF modifié dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### Exemple de code source pour remplacer les polices à l’aide d’Aspose.PDF pour .NET 
```csharp
try
{
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF source
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	// Rechercher des fragments de texte et définir l'option d'édition pour supprimer les polices inutilisées
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	// Acceptez l'absorbeur pour toutes les pages
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
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à remplacer des polices spécifiques dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez charger un document PDF, rechercher des fragments de texte, identifier et remplacer des polices spécifiques et enregistrer le PDF modifié.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Remplacer les polices dans un fichier PDF » ?

: Le didacticiel « Remplacer les polices dans un fichier PDF » montre comment utiliser la bibliothèque Aspose.PDF pour .NET pour remplacer des polices spécifiques dans un document PDF. Il fournit un guide étape par étape sur la façon de charger un document PDF, de rechercher des fragments de texte, d'identifier les polices à remplacer, de remplacer les polices et d'enregistrer le PDF modifié.

#### Q : Pourquoi voudrais-je remplacer les polices dans un document PDF ?

R : Le remplacement des polices dans un document PDF peut être nécessaire lorsque vous souhaitez standardiser l'apparence du texte ou améliorer la compatibilité du document sur différents appareils et plates-formes. Il vous permet de garantir une typographie et un formatage cohérents.

#### Q : Comment configurer le répertoire de documents ?

R : Pour configurer le répertoire de documents :

1.  Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d’accès au répertoire où se trouve votre fichier PDF d’entrée.

#### Q : Comment remplacer des polices spécifiques dans un document PDF ?

R : Le didacticiel vous guide étape par étape tout au long du processus :

1.  Chargez le document PDF à l'aide du`Document` classe.
2.  Créer un`TextFragmentAbsorber` objet et définissez l’option d’édition pour supprimer les polices inutilisées. Acceptez l'absorbeur de toutes les pages pour rechercher des fragments de texte.
3. Parcourez les fragments de texte identifiés. Si le nom de police d'un fragment de texte correspond à la police que vous souhaitez remplacer, remplacez-le par la nouvelle police.

####  Q : Quel est le but de l'utilisation`TextFragmentAbsorber` with font replacement options?

 R : Le`TextFragmentAbsorber` avec les options de remplacement de police, vous permet de localiser des fragments de texte et de supprimer simultanément les polices inutilisées. Ceci est important pour garantir que les polices remplacées ne soient pas ajoutées en tant que ressources supplémentaires dans le PDF.

#### Q : Comment puis-je identifier les polices spécifiques à remplacer ?

R : En parcourant les fragments de texte identifiés par l'absorbeur, vous pouvez accéder aux informations de police pour chaque fragment de texte. Si le nom de la police correspond à la police que vous souhaitez remplacer, vous pouvez effectuer le remplacement.

#### Q : Que se passe-t-il si la police à remplacer n'est pas trouvée dans un fragment de texte ?

R : Si la police à remplacer n'est pas trouvée dans un fragment de texte, la police du fragment de texte reste inchangée. Le remplacement n'aura lieu que si le nom de la police correspond.

#### Q : Y a-t-il une limitation au remplacement des polices dans ce didacticiel ?

R : Ce didacticiel se concentre sur le remplacement de polices spécifiques dans des fragments de texte. Si vous devez remplacer des polices dans d'autres contextes, tels que des annotations ou des champs de formulaire, vous devrez étendre l'approche en conséquence.

#### Q : Quel est le résultat attendu de l’exécution du code fourni ?

R : En suivant le didacticiel et en exécutant le code C# fourni, vous remplacerez des polices spécifiques dans le document PDF. Les polices identifiées par les critères que vous avez définis seront remplacées par la nouvelle police que vous spécifiez.

#### Q : Puis-je utiliser cette approche pour remplacer les polices dans l’ensemble du document PDF ?

R : Oui, vous pouvez adapter le code pour remplacer les polices dans l'ensemble du document PDF en parcourant tous les fragments de texte et en appliquant la logique de remplacement des polices.
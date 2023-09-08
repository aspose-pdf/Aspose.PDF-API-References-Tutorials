---
title: Rayer les mots
linktitle: Rayer les mots
second_title: Aspose.PDF pour la référence de l'API .NET
description: Cet article fournit un guide étape par étape sur l'utilisation de la fonctionnalité Strike Out Words d'Aspose.PDF pour .NET, y compris un guide étape par étape et des explications.
type: docs
weight: 150
url: /fr/net/annotations/strikeoutwords/
---
Aspose.PDF pour .NET est une bibliothèque de manipulation et de traitement de documents PDF qui fournit diverses fonctionnalités pour créer, modifier et convertir des fichiers PDF. L'une des fonctionnalités utiles fournies par Aspose.PDF est la possibilité de supprimer des mots ou des expressions dans un document PDF à l'aide du code source C#. Dans cet article, nous fournirons un guide étape par étape sur la façon de barrer des mots à l'aide d'Aspose.PDF pour .NET.

## Étape 1 : Chargement du document PDF
La première étape consiste à charger le document PDF que vous souhaitez modifier. Dans ce tutoriel, nous allons charger un document PDF nommé « input.pdf » depuis le dossier « VOTRE RÉPERTOIRE DE DOCUMENTS ». 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## Étape 2 : Recherche de fragments de texte
Pour supprimer des mots ou des expressions spécifiques dans le document PDF, vous devez d'abord les rechercher. Aspose.PDF fournit une classe TextFragmentAbsorber qui peut être utilisée pour rechercher un fragment de texte spécifique dans le document PDF.

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

Dans le code ci-dessus, nous recherchons le fragment de texte « Estoque » dans le document PDF. Vous pouvez modifier cela pour rechercher tout autre mot ou expression que vous souhaitez supprimer.

## Étape 3 : Supprimer les fragments de texte
Après avoir trouvé les fragments de texte, l’étape suivante consiste à les supprimer. Aspose.PDF fournit une classe StrikeOutAnnotation qui peut être utilisée pour créer une annotation barrée pour le fragment de texte. 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

Dans le code ci-dessus, nous créons une annotation barrée pour chaque fragment de texte que nous avons trouvé. Nous définissons également l'opacité, la bordure et la couleur de l'annotation barrée.

## Étape 4 : Sauvegarde du document PDF modifié
Après avoir supprimé les fragments de texte, enregistrez le document modifié.

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### Exemple de code source pour les mots barrés à l'aide d'Aspose.PDF pour .NET


```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document document = new Document(dataDir + "input.pdf");

// Créer une instance TextFragment Absorber pour rechercher un fragment de texte particulier
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
// Parcourez les pages d'un document PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
	// Obtenir la première page du document PDF
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

// Créer une collection de texte absorbé
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//Itérer sur la collection ci-dessus
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	// Obtenir les dimensions rectangulaires de l'objet TextFragment
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	// Instancier une instance d'annotation StrikeOut
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	// Définir l'opacité pour l'annotation
	strikeOut.Opacity = .80f;
	// Définir la bordure de l'instance d'annotation
	strikeOut.Border = new Border(strikeOut);
	// Définir la couleur de l'annotation
	strikeOut.Color = Aspose.Pdf.Color.Red;
	// Ajouter une annotation à la collection d'annotations de TextFragment
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser Aspose.PDF pour .NET pour supprimer des mots spécifiques dans un document PDF. En suivant le guide étape par étape et en utilisant le code source C# fourni, vous pouvez facilement charger un document PDF, rechercher des fragments de texte spécifiques et créer des annotations barrées pour marquer et barrer visuellement ces mots. Aspose.PDF pour .NET fournit un moyen simple et efficace de manipuler des documents PDF par programmation, ce qui en fait un outil précieux pour les développeurs travaillant avec des fichiers PDF dans des applications .NET.

### FAQ

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

: Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, modifier et manipuler des documents PDF par programmation dans des applications .NET. Il offre un large éventail de fonctionnalités pour travailler avec des fichiers PDF, notamment l'extraction de texte, la gestion des annotations, le remplissage de formulaires et bien plus encore.

#### Q : Puis-je utiliser Aspose.PDF pour .NET pour supprimer des mots spécifiques dans un document PDF ?

R : Oui, Aspose.PDF pour .NET fournit une fonctionnalité permettant de rechercher des fragments de texte spécifiques dans un document PDF, puis de créer des annotations barrées pour marquer et barrer visuellement ces mots.

#### Q : Comment puis-je spécifier le texte que je souhaite barrer dans le document PDF ?

 R : Pour spécifier le texte que vous souhaitez barrer, vous pouvez utiliser le`TextFragmentAbsorber` classe fournie par Aspose.PDF pour .NET. Il vous permet de rechercher un fragment de texte spécifique dans le document PDF en fonction des critères souhaités.

#### Q : Puis-je personnaliser l'apparence de l'annotation barrée ?

: Oui, vous pouvez personnaliser diverses propriétés de l'annotation barrée, telles que l'opacité, le style de bordure et la couleur. Cela vous permet d'adapter l'apparence de l'annotation barrée à vos besoins spécifiques.
---
title: Masquer les numéros de page dans la table des matières
linktitle: Masquer les numéros de page dans la table des matières
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à masquer les numéros de page dans une table des matières en utilisant Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 220
url: /fr/net/programming-with-document/hidepagenumbersintoc/
---
Dans cet article, nous discuterons de l'implémentation de la fonction Masquer les numéros de page dans la table des matières d'Aspose.PDF pour .NET à l'aide de C#. Nous commencerons par une brève introduction à Aspose.PDF pour .NET, puis plongerons dans le guide étape par étape pour implémenter cette fonctionnalité. 

## Introduction à Aspose.PDF pour .NET

Aspose.PDF pour .NET est un puissant composant de manipulation PDF qui permet aux développeurs de créer, modifier et manipuler des fichiers PDF par programme. Il offre un large éventail de caractéristiques et de fonctionnalités qui facilitent le travail avec les documents PDF. Aspose.PDF pour .NET prend en charge les systèmes d'exploitation 32 bits et 64 bits et peut être utilisé avec les plates-formes .NET Framework, .NET Core et Xamarin. 

## Qu'est-ce que la fonction Masquer les numéros de page dans la table des matières ?

La table des matières (TOC) est une partie essentielle d'un document PDF qui fournit aux utilisateurs un aperçu rapide du contenu. Parfois, les utilisateurs peuvent souhaiter masquer les numéros de page dans la table des matières pour la rendre plus conviviale. Aspose.PDF pour .NET fournit une fonctionnalité intégrée pour masquer les numéros de page dans la table des matières. Cette fonctionnalité peut être utilisée pour créer des documents PDF plus conviviaux. 

## Conditions préalables

Pour suivre ce tutoriel, vous aurez besoin des éléments suivants :

- Visual Studio 2010 ou version ultérieure
- Aspose.PDF pour .NET installé sur votre système
- Connaissance de base du langage de programmation C#

## Guide étape par étape pour implémenter la fonction Masquer les numéros de page dans la table des matières

Suivez les étapes ci-dessous pour implémenter la fonctionnalité Masquer les numéros de page dans la table des matières à l'aide d'Aspose.PDF pour .NET :

## Étape 1 : Créer une nouvelle application de console C# dans Visual Studio

Ouvrez Visual Studio et créez une nouvelle application console C#.

## Étape 2 : Ajouter une référence à Aspose.PDF pour .NET

Cliquez avec le bouton droit sur le dossier Références de votre projet et sélectionnez Ajouter une référence. Accédez à l'emplacement où Aspose.PDF pour .NET est installé sur votre système et ajoutez-y une référence.

## Étape 1 : Créer un nouveau document PDF

Créez un nouveau document PDF en utilisant le code suivant :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
```

## Étape 2 : Créer une page de table des matières

Créez une nouvelle page pour la table des matières et ajoutez-la au document PDF à l'aide du code suivant :

```csharp
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
```

## Étape 3 : Ajouter une section de liste à la collection de sections du document PDF

Ajoutez la section de liste à la collection de sections du document PDF à l'aide du code suivant :

```csharp
tocPage.TocInfo = tocInfo;
```

## Etape 4 : Définir le format de la liste des quatre niveaux

Définissez le format de la liste des quatre niveaux en définissant les marges de gauche et les paramètres de format de texte de chaque niveau à l'aide du code suivant :

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
```

## Étape 5 : Ajoutez quatre titres dans la section

```csharp

for (int Level = 1; Level != 5; Level++)
{ 
	Heading heading2 = new Heading(Level); 
	TextSegment segment2 = new TextSegment(); 
	heading2.TocPage = tocPage; 
	heading2.Segments.Add(segment2); 
	heading2.IsAutoSequence = true; 
	segment2.Text = "this is heading of level " + Level; 
	heading2.IsInList = true; 
	page.Paragraphs.Add(heading2); 
}
doc.Save(outFile);

```

### Exemple de code source pour masquer les numéros de page dans la table des matières à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
//Ajouter la section de liste à la collection de sections du document Pdf
tocPage.TocInfo = tocInfo;
//Définissez le format de la liste des quatre niveaux en définissant les marges de gauche et
//paramètres de format de texte de chaque niveau

tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
Page page = doc.Pages.Add();
//Ajouter quatre titres dans la section
for (int Level = 1; Level != 5; Level++)
	{ 
		Heading heading2 = new Heading(Level); 
		TextSegment segment2 = new TextSegment(); 
		heading2.TocPage = tocPage; 
		heading2.Segments.Add(segment2); 
		heading2.IsAutoSequence = true; 
		segment2.Text = "this is heading of level " + Level; 
		heading2.IsInList = true; 
		page.Paragraphs.Add(heading2); 
	}
doc.Save(outFile);
```

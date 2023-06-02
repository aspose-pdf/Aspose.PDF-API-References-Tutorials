---
title: Ajouter une table des matières
linktitle: Ajouter une table des matières
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter une table des matières aux documents PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape avec exemple de code source. Boostez la navigation dans les documents !
type: docs
weight: 40
url: /fr/net/programming-with-document/addtoc/
---

Dans ce didacticiel, nous allons explorer comment utiliser la fonctionnalité Ajouter une table des matières (Add TOC) d'Aspose.PDF pour .NET pour ajouter une table des matières aux documents PDF. Nous fournirons un guide étape par étape et expliquerons le code source C # requis pour y parvenir. À la fin de ce didacticiel, vous serez en mesure de générer un document PDF avec une table des matières à l'aide d'Aspose.PDF pour .NET.


## Étape 1 : Chargez le fichier PDF existant

Pour commencer, nous devons charger un fichier PDF existant. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre fichier PDF :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## Étape 2 : Créer une nouvelle page pour la table des matières

Nous allons créer une nouvelle page pour contenir la table des matières. Le code suivant insère une nouvelle page à l'index 1 :

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## Étape 3 : Définir les informations de la table des matières

Ensuite, nous devons définir les informations de la table des matières. Nous allons définir le titre et les autres propriétés de la table des matières. Ajoutez le code suivant :

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## Étape 4 : créer des éléments de table des matières

Maintenant, nous allons créer les éléments de la table des matières. Dans ce tutoriel, nous allons créer quatre éléments TOC correspondant à différentes pages. Modifiez le code suivant selon vos besoins :

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## Étape 5 : Enregistrer le document mis à jour

 Enfin, nous devons enregistrer le document modifié avec la table des matières. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code ci-dessous avec le chemin du fichier de sortie souhaité :

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### Exemple de code source pour l'ajout de table des matières aux documents PDF à l'aide d'Aspose.PDF pour .NET

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Charger un fichier PDF existant
Document doc = new Document(dataDir + "AddTOC.pdf");

// Accéder à la première page du fichier PDF
Page tocPage = doc.Pages.Insert(1);

// Créer un objet pour représenter les informations TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

// Définir le titre de la table des matières
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

// Créer des objets de chaîne qui seront utilisés comme éléments TOC
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	// Créer un objet d'en-tête
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	// Spécifiez la page de destination pour l'objet d'en-tête
	heading2.DestinationPage = doc.Pages[i + 2];

	// Page de destination
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	// Coordonnée de destination
	segment2.Text = titles[i];

	// Ajouter un titre à la page contenant la table des matières
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
// Enregistrer le document mis à jour
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

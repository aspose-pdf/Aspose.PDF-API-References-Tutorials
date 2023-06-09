---
title: Personnaliser les numéros de page lors de l'ajout de la table des matières
linktitle: Personnaliser les numéros de page lors de l'ajout de la table des matières
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à personnaliser les numéros de page tout en ajoutant une table des matières (TOC) à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape et cet exemple de code.
type: docs
weight: 100
url: /fr/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---

Dans ce didacticiel, nous explorerons comment personnaliser les numéros de page tout en ajoutant une table des matières (TOC) à l'aide d'Aspose.PDF pour .NET. Nous vous fournirons des conseils étape par étape, ainsi qu'un exemple de code, pour vous aider à y parvenir.

## Étape 1 : Charger un fichier PDF existant

Tout d'abord, nous devons charger un fichier PDF existant. Pour ce tutoriel, nous utiliserons le fichier "42824.pdf" situé dans le répertoire "YOUR DOCUMENT DIRECTORY". Remplacez ce chemin de répertoire par le chemin réel vers votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Étape 2 : Ajouter une page de table des matières

 Ensuite, nous devons ajouter une nouvelle page au début du document pour servir de page TOC. Nous pouvons y parvenir en utilisant le`Insert()` méthode de la`Pages` collecte de la`Document` objet.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Étape 3 : Création d'un objet TOC

 Pour créer un objet TOC, nous devons d'abord créer un`TocInfo`objet et définissez ses propriétés. Dans ce didacticiel, nous allons définir le titre de la table des matières sur "Table des matières" et le préfixe du numéro de page sur "P".

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Étape 4 : Création d'entrées de table des matières

Pour créer des entrées de table des matières, nous devons parcourir toutes les pages du document, à l'exception de la page de table des matières, et créer un objet d'en-tête pour chaque page. Nous pouvons ensuite ajouter l'objet d'en-tête à la page TOC et spécifier sa page de destination.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Créer un objet d'en-tête
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Spécifiez la page de destination pour l'objet d'en-tête
    heading2.DestinationPage = doc.Pages[i + 1];
    // Page de destination
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Coordonnée de destination
    segment2.Text = "Page " + i.ToString();
    //Ajouter un titre à la page contenant la table des matières
    tocPage.Paragraphs.Add(heading2);
}
```

## Étape 5 : Enregistrer le document mis à jour

 Enfin, nous devons enregistrer le document mis à jour dans un nouveau fichier. Nous pouvons y parvenir en utilisant le`Save()` méthode de la`Document` objet.

```csharp
doc.Save(outFile);
```

### Exemple de code source pour personnaliser les numéros de page lors de l'ajout de la table des matières à l'aide d'Aspose.PDF pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Charger un fichier PDF existant
Document doc = new Document(inFile);
// Accéder à la première page du fichier PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Créer un objet pour représenter les informations TOC
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
// Définir le titre de la table des matières
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
for (int i = 1; i<doc.Pages.Count; i++)
{
	// Créer un objet d'en-tête
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Spécifiez la page de destination pour l'objet d'en-tête
	heading2.DestinationPage = doc.Pages[i + 1];
	// Page de destination
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Coordonnée de destination
	segment2.Text = "Page " + i.ToString();
	//Ajouter un titre à la page contenant la table des matières
	tocPage.Paragraphs.Add(heading2);
}

// Enregistrer le document mis à jour
doc.Save(outFile);
```

## Conclusion

Dans ce didacticiel, nous avons fourni des instructions étape par étape sur la façon de personnaliser les numéros de page tout en ajoutant une table des matières à l'aide d'Aspose.PDF pour .NET. Nous avons également fourni un exemple de code que vous pouvez utiliser comme référence lors de l'implémentation de cette fonctionnalité dans votre


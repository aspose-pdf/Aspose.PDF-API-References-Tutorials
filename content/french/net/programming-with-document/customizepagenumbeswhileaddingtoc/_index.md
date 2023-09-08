---
title: Personnaliser les numéros de page lors de l'ajout de la table des matières
linktitle: Personnaliser les numéros de page lors de l'ajout de la table des matières
second_title: Aspose.PDF pour la référence de l'API .NET
description: Apprenez à personnaliser les numéros de page tout en ajoutant une table des matières (TOC) à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape et cet exemple de code.
type: docs
weight: 100
url: /fr/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
Dans ce didacticiel, nous explorerons comment personnaliser les numéros de page tout en ajoutant une table des matières (TOC) à l'aide d'Aspose.PDF pour .NET. Nous vous fournirons des conseils étape par étape, ainsi qu'un exemple de code, pour vous aider à y parvenir.

## Étape 1 : Chargement d'un fichier PDF existant

Tout d’abord, nous devons charger un fichier PDF existant. Pour ce tutoriel, nous utiliserons le fichier « 42824.pdf » situé dans le répertoire « VOTRE RÉPERTOIRE DE DOCUMENTS ». Remplacez ce chemin de répertoire par le chemin réel de votre répertoire de documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## Étape 2 : Ajouter une page de table des matières

 Ensuite, nous devons ajouter une nouvelle page au début du document pour servir de page TOC. Nous pouvons y parvenir en utilisant le`Insert()` méthode du`Pages` collecte des`Document` objet.

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## Étape 3 : Création d'un objet TOC

 Pour créer un objet TOC, nous devons d'abord créer un`TocInfo` objet et définir ses propriétés. Dans ce didacticiel, nous définirons le titre de la table des matières sur « Table des matières » et le préfixe du numéro de page sur « P ».

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## Étape 4 : Création d'entrées de table des matières

Pour créer des entrées de table des matières, nous devons parcourir toutes les pages du document, à l'exception de la page de table des matières, et créer un objet de titre pour chaque page. Nous pouvons ensuite ajouter l'objet de titre à la page TOC et spécifier sa page de destination.

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    // Créer un objet de titre
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    // Spécifier la page de destination pour l'objet d'en-tête
    heading2.DestinationPage = doc.Pages[i + 1];
    // Page de destination
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    // Coordonnées de destination
    segment2.Text = "Page " + i.ToString();
    // Ajouter un en-tête à la page contenant la table des matières
    tocPage.Paragraphs.Add(heading2);
}
```

## Étape 5 : Sauvegarde du document mis à jour

Enfin, nous devons enregistrer le document mis à jour dans un nouveau fichier. Nous pouvons y parvenir en utilisant le`Save()` méthode du`Document` objet.

```csharp
doc.Save(outFile);
```

### Exemple de code source pour personnaliser les numéros de page lors de l'ajout d'une table des matières à l'aide d'Aspose.PDF pour .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
// Charger un fichier PDF existant
Document doc = new Document(inFile);
// Accédez à la première page du fichier PDF
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
// Créer un objet pour représenter les informations de la table des matières
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
	// Créer un objet de titre
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);
	// Spécifier la page de destination pour l'objet d'en-tête
	heading2.DestinationPage = doc.Pages[i + 1];
	// Page de destination
	heading2.Top = doc.Pages[i + 1].Rect.Height;
	// Coordonnées de destination
	segment2.Text = "Page " + i.ToString();
	// Ajouter un en-tête à la page contenant la table des matières
	tocPage.Paragraphs.Add(heading2);
}

// Enregistrez le document mis à jour
doc.Save(outFile);
```

## Conclusion

Dans ce didacticiel, nous avons fourni des conseils étape par étape sur la façon de personnaliser les numéros de page lors de l'ajout d'une table des matières à l'aide d'Aspose.PDF pour .NET. Nous avons également fourni un exemple de code que vous pouvez utiliser comme référence lors de l'implémentation de cette fonctionnalité dans votre

### FAQ

#### Q : Qu'est-ce qu'une table des matières (TOC) dans un document PDF ?

R : Une table des matières (TOC) dans un document PDF est une aide à la navigation qui fournit une liste organisée de sections ou de chapitres de document ainsi que leurs numéros de page correspondants. Il permet aux lecteurs de naviguer rapidement vers des sections spécifiques du document.

#### Q :Pourquoi voudrais-je personnaliser les numéros de page dans une table des matières ?

R : La personnalisation des numéros de page dans une table des matières peut être utile lorsque vous souhaitez utiliser un format de numérotation de page spécifique ou inclure des informations supplémentaires avec les numéros de page. Il vous permet de créer une table des matières plus personnalisée et informative.

#### Q : Puis-je inclure des hyperliens dans la table des matières pour créer des liens vers des sections ou des pages spécifiques du document PDF ?

R : Oui, Aspose.PDF pour .NET vous permet de créer des hyperliens dans la table des matières qui renvoient vers des sections ou des pages spécifiques du document PDF. Cela améliore l’interactivité et la navigation du document PDF.

#### Q : Aspose.PDF pour .NET est-il compatible avec les normes PDF/A ?

R : Oui, Aspose.PDF pour .NET prend en charge les normes PDF/A, notamment PDF/A-1, PDF/A-2 et PDF/A-3. Il vous permet de créer des documents PDF conformes aux exigences d'archivage et de conservation à long terme.

#### Q : Puis-je ajouter davantage de mise en forme aux entrées de la table des matières, comme des styles de police ou des couleurs ?

: Oui, vous pouvez ajouter une mise en forme supplémentaire aux entrées de la table des matières, comme des styles de police, des couleurs et des tailles de police, à l'aide d'Aspose.PDF pour .NET. Cela vous permet de personnaliser l'apparence de la table des matières selon vos besoins.

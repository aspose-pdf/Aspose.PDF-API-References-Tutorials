---
title: Rendu des symboles remplaçables
linktitle: Rendu des symboles remplaçables
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à rendre des symboles remplaçables dans un document PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 310
url: /fr/net/programming-with-text/rendering-replaceable-symbols/
---

Dans ce didacticiel, nous expliquerons comment rendre des symboles remplaçables dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons passer par le processus étape par étape de création d'un PDF, en ajoutant un fragment de texte avec des marqueurs de nouvelle ligne, en définissant les propriétés du texte, en positionnant le texte et en enregistrant le PDF à l'aide du code source C# fourni.

## Conditions préalables

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès au répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : créer un document PDF et une page

 Ensuite, nous créons un nouveau document PDF et y ajoutons une page en utilisant le`Document` classe et`Page` classe de la bibliothèque Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Étape 3 : Ajouter un fragment de texte avec des marqueurs de nouvelle ligne

 Nous créons un`TextFragment` objet et définissez son texte pour inclure des marqueurs de nouvelle ligne (`Environment.NewLine`) pour représenter plusieurs lignes de texte.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## Étape 4 : Définir les propriétés du fragment de texte

Nous pouvons définir diverses propriétés pour le fragment de texte si vous le souhaitez, telles que la taille de la police, la police, la couleur d'arrière-plan et la couleur de premier plan.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## Étape 5 : Créer un paragraphe de texte et sa position

 Nous créons un`TextParagraph` objet, ajoutez le fragment de texte au paragraphe et définissez la position du paragraphe sur la page.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Étape 6 : Ajouter un paragraphe de texte à la page

 Nous créons un`TextBuilder`objet avec la page et ajoutez le paragraphe de texte au générateur de texte.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Étape 7 : Enregistrez le document PDF

Enfin, nous enregistrons le document PDF dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Exemple de code source pour le rendu de symboles remplaçables à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Initialiser le nouveau TextFragment avec le texte contenant les marqueurs de nouvelle ligne requis
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Définissez les propriétés du fragment de texte si nécessaire
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Créer un objet TextParagraph
TextParagraph par = new TextParagraph();
// Ajouter un nouveau TextFragment au paragraphe
par.AppendLine(textFragment);
// Définir la position du paragraphe
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// Créer un objet TextBuilder
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// Ajouter le TextParagraph à l'aide de TextBuilder
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, vous avez appris à rendre des symboles remplaçables dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez créer un PDF, ajouter du texte avec des marqueurs de nouvelle ligne, définir les propriétés du texte, positionner le texte sur la page et enregistrer le PDF.
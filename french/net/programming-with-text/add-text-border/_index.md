---
title: Ajouter une bordure de texte
linktitle: Ajouter une bordure de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter une bordure de texte à un document PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-text/add-text-border/
---

Ce didacticiel vous guidera tout au long du processus d'ajout d'une bordure de texte à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez ajouter la bordure de texte, ajoutez la directive using suivante en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le répertoire de documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document pdfDocument = new Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document à l'aide de la`Add` méthode de la`Pages` collection. Dans le code fourni, la nouvelle page est affectée à la variable`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Étape 6 : créer un fragment de texte
 Créer un`TextFragment` objet et fournissez le texte souhaité. Définissez la position du fragment de texte à l'aide de la`Position` propriété. Dans le code fourni, le texte est défini sur "texte principal" et positionné à (100, 600) sur la page.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Étape 7 : Définir les propriétés du texte
Personnalisez les propriétés du texte telles que la taille de police, le type de police, la couleur d'arrière-plan, la couleur de premier plan, etc. Dans le code fourni, des propriétés telles que la taille de police, la police, la couleur d'arrière-plan, la couleur de premier plan et la couleur de trait sont définies pour le fragment de texte.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Étape 8 : Activer la bordure de texte
 Pour activer la bordure de texte, définissez le`DrawTextRectangleBorder` propriété du fragment de texte`TextState` pour`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Étape 9 : Ajouter le TextFragment à la page
 Utilisez le`TextBuilder` classe pour ajouter le`TextFragment` s'opposer à la page.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Étape 10 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide de`Save` méthode de la`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Exemple de code source pour Ajouter une bordure de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un nouvel objet document
Document pdfDocument = new Document();
// Obtenir une page particulière
Page pdfPage = (Page)pdfDocument.Pages.Add();
// Créer un fragment de texte
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// Définir les propriétés du texte
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// Définir la propriété StrokingColor pour dessiner la bordure (trait) autour du rectangle de texte
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Définissez la valeur de la propriété DrawTextRectangleBorder sur true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Enregistrer le document
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusion
Vous avez ajouté avec succès une bordure de texte à votre document PDF en utilisant Aspose.PDF pour .NET. Le fichier PDF résultant se trouve maintenant dans le chemin du fichier de sortie spécifié.
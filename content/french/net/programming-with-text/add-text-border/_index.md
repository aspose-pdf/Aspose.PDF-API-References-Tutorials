---
title: Ajouter une bordure de texte dans un fichier PDF
linktitle: Ajouter une bordure de texte dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter une bordure de texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-text/add-text-border/
---
Ce didacticiel vous guidera tout au long du processus d'ajout d'une bordure de texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous de disposer des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Bibliothèque Aspose.PDF pour .NET. Vous pouvez la télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de paquets comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez ajouter la bordure de texte, ajoutez la directive using suivante en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : définir le répertoire du document
 Dans le code, recherchez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin vers le répertoire où sont stockés vos documents.

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document pdfDocument = new Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document en utilisant le`Add` méthode de la`Pages` collection. Dans le code fourni, la nouvelle page est attribuée à la variable`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Étape 6 : Créer un fragment de texte
 Créer un`TextFragment`objet et fournissez le texte souhaité. Définissez la position du fragment de texte à l'aide de la`Position` propriété. Dans le code fourni, le texte est défini sur « texte principal » et positionné à (100, 600) sur la page.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Étape 7 : définir les propriétés du texte
Personnalisez les propriétés du texte telles que la taille de la police, le type de police, la couleur d'arrière-plan, la couleur de premier plan, etc. Dans le code fourni, des propriétés telles que la taille de la police, la police, la couleur d'arrière-plan, la couleur de premier plan et la couleur de trait sont définies pour le fragment de texte.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Étape 8 : Activer la bordure du texte
 Pour activer la bordure de texte, définissez le`DrawTextRectangleBorder` propriété du fragment de texte`TextState` à`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Étape 9 : ajouter le fragment de texte à la page
 Utilisez le`TextBuilder` classe pour ajouter le`TextFragment` objet à la page.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Étape 10 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide de la`Save` méthode de la`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Exemple de code source pour ajouter une bordure de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un nouvel objet de document
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
// Définir la propriété StrokingColor pour dessiner une bordure (trait) autour du rectangle de texte
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Définissez la valeur de la propriété DrawTextRectangleBorder sur true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Enregistrer le document
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusion
Vous avez ajouté avec succès une bordure de texte à votre document PDF à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant se trouve désormais dans le chemin de fichier de sortie spécifié.

### FAQ

#### Q : Quel est l’objectif principal de ce tutoriel ?

R : Ce didacticiel vous guide tout au long du processus d'ajout d'une bordure de texte à un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires pour y parvenir.

#### Q : Quels espaces de noms dois-je importer pour ce tutoriel ?

R : Dans le fichier de code dans lequel vous souhaitez ajouter la bordure de texte, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q : Comment spécifier le répertoire du document ?

 A : Dans le code, localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer un objet Document ?

 A : À l’étape 4, vous allez instancier un nouveau`Document` objet en utilisant la ligne de code suivante :

```csharp
Document pdfDocument = new Document();
```

#### Q : Comment ajouter une page au document ?

 A : À l'étape 5, vous ajouterez une nouvelle page au document à l'aide de l'`Add` méthode de la`Pages` collection:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Q : Comment créer un TextFragment et définir sa position ?

 A : À l'étape 6, vous allez créer un`TextFragment` objet et définir sa position sur la page à l'aide de la`Position` propriété:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Q : Comment puis-je personnaliser les propriétés du texte, y compris la bordure du texte ?

A : À l’étape 7, vous allez personnaliser diverses propriétés de texte telles que la taille de la police, le type de police, la couleur d’arrière-plan, la couleur de premier plan et la bordure du texte :

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Q : Comment ajouter le TextFragment au document PDF ?

 A : À l'étape 9, vous utiliserez le`TextBuilder` classe pour ajouter le`TextFragment` objet à la page :

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Q : Comment puis-je enregistrer le document PDF obtenu ?

 : Après avoir ajouté le texte avec une bordure, utilisez le`Save` méthode de la`Document` objet pour enregistrer le document PDF :

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Q : Quel est le principal point à retenir de ce tutoriel ?

R : En suivant ce didacticiel, vous avez appris à améliorer votre document PDF en ajoutant une bordure de texte à l'aide d'Aspose.PDF pour .NET. Cela peut être particulièrement utile pour mettre en valeur un contenu de texte spécifique dans vos fichiers PDF.
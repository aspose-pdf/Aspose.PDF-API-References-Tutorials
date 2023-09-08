---
title: Ajouter une bordure de texte dans un fichier PDF
linktitle: Ajouter une bordure de texte dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter une bordure de texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-text/add-text-border/
---
Ce didacticiel vous guidera tout au long du processus d'ajout d'une bordure de texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez ajouter la bordure de texte, ajoutez la directive using suivante en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## Étape 3 : Définir le répertoire des documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où sont stockés vos documents.

## Étape 4 : Créer un nouvel objet Document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document pdfDocument = new Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document en utilisant le`Add` méthode du`Pages`collection. Dans le code fourni, la nouvelle page est affectée à la variable`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## Étape 6 : Créer un TextFragment
 Créer un`TextFragment` objet et fournir le texte souhaité. Définissez la position du fragment de texte à l'aide du`Position` propriété. Dans le code fourni, le texte est défini sur "texte principal" et positionné en (100, 600) sur la page.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## Étape 7 : Définir les propriétés du texte
Personnalisez les propriétés du texte telles que la taille de la police, le type de police, la couleur d'arrière-plan, la couleur de premier plan, etc. Dans le code fourni, des propriétés telles que la taille de la police, la police, la couleur d'arrière-plan, la couleur de premier plan et la couleur de trait sont définies pour le fragment de texte.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## Étape 8 : Activer la bordure de texte
 Pour activer la bordure de texte, définissez le`DrawTextRectangleBorder`propriété du fragment de texte`TextState` à`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## Étape 9 : ajouter le TextFragment à la page
 Utilisez le`TextBuilder` classe pour ajouter le`TextFragment` s'opposer à la page.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## Étape 10 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide du`Save` méthode du`Document` objet. Spécifiez le chemin du fichier de sortie que vous avez défini à l'étape 3.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### Exemple de code source pour Ajouter une bordure de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
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
// Définir la propriété StrokingColor pour dessiner une bordure (en caressant) autour du rectangle de texte
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// Définir la valeur de la propriété DrawTextRectangleBorder sur true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// Enregistrez le document
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## Conclusion
Vous avez réussi à ajouter une bordure de texte à votre document PDF à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant peut maintenant être trouvé au chemin du fichier de sortie spécifié.

### FAQ

#### Q : Quel est l’objectif principal de ce didacticiel ?

R : Ce didacticiel vous guide tout au long du processus d'ajout d'une bordure de texte à un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires pour y parvenir.

#### Q : Quels espaces de noms dois-je importer pour ce didacticiel ?

R : Dans le fichier de code dans lequel vous souhaitez ajouter la bordure de texte, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q : Comment spécifier le répertoire des documents ?

 R : Dans le code, localisez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer un objet Document ?

 R : À l'étape 4, vous allez instancier un nouveau`Document` objet en utilisant la ligne de code suivante :

```csharp
Document pdfDocument = new Document();
```

#### Q : Comment ajouter une page au document ?

 R : À l'étape 5, vous ajouterez une nouvelle page au document à l'aide de l'outil`Add` méthode du`Pages` collection:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Q : Comment créer un TextFragment et définir sa position ?

 R : À l'étape 6, vous allez créer un`TextFragment`objet et définissez sa position sur la page à l'aide du`Position` propriété:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Q : Comment puis-je personnaliser les propriétés du texte, y compris la bordure du texte ?

R : À l'étape 7, vous personnaliserez diverses propriétés de texte telles que la taille de la police, le type de police, la couleur d'arrière-plan, la couleur de premier plan et la bordure du texte :

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Q : Comment ajouter le TextFragment au document PDF ?

 R : À l'étape 9, vous utiliserez le`TextBuilder` classe pour ajouter le`TextFragment` s'opposer à la page :

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Q : Comment puis-je enregistrer le document PDF obtenu ?

 R : Après avoir ajouté le texte avec une bordure, utilisez le`Save` méthode du`Document` objet pour enregistrer le document PDF :

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Q : Quel est le principal point à retenir de ce didacticiel ?

R : En suivant ce didacticiel, vous avez appris avec succès comment améliorer votre document PDF en ajoutant une bordure de texte à l'aide d'Aspose.PDF pour .NET. Cela peut être particulièrement utile pour mettre en valeur un contenu textuel spécifique dans vos fichiers PDF.
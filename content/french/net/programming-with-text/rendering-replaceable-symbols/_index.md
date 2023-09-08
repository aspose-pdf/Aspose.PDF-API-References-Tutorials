---
title: Rendu des symboles remplaçables dans un fichier PDF
linktitle: Rendu des symboles remplaçables dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment restituer des symboles remplaçables dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 310
url: /fr/net/programming-with-text/rendering-replaceable-symbols/
---
Dans ce didacticiel, nous expliquerons comment restituer des symboles remplaçables dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous passerons en revue le processus étape par étape de création d'un PDF, d'ajout d'un fragment de texte avec des marqueurs de nouvelle ligne, de définition des propriétés du texte, de positionnement du texte et d'enregistrement du PDF à l'aide du code source C# fourni.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir`variable avec le chemin d'accès au répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document et une page PDF

 Ensuite, nous créons un nouveau document PDF et y ajoutons une page à l'aide du`Document` classe et`Page` classe de la bibliothèque Aspose.PDF.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## Étape 3 : ajouter un fragment de texte avec des marqueurs de nouvelle ligne

 Nous créons un`TextFragment`objet et définissez son texte pour inclure des marqueurs de nouvelle ligne (`Environment.NewLine`) pour représenter plusieurs lignes de texte.

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

## Étape 5 : Créer un paragraphe de texte et une position

 Nous créons un`TextParagraph` objet, ajoutez le fragment de texte au paragraphe et définissez la position du paragraphe sur la page.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## Étape 6 : ajouter un paragraphe de texte à la page

 Nous créons un`TextBuilder` objet avec la page et ajoutez le paragraphe de texte au générateur de texte.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## Étape 7 : Enregistrez le document PDF

Enfin, nous enregistrons le document PDF dans le fichier de sortie spécifié.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### Exemple de code source pour le rendu de symboles remplaçables à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// Initialisez le nouveau TextFragment avec le texte contenant les marqueurs de nouvelle ligne requis
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// Définir les propriétés du fragment de texte si nécessaire
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

Dans ce didacticiel, vous avez appris à restituer des symboles remplaçables dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez créer un PDF, ajouter du texte avec des marqueurs de nouvelle ligne, définir les propriétés du texte, positionner le texte sur la page et enregistrer le PDF.

### FAQ

#### Q : Quel est l'objectif du didacticiel « Rendu de symboles remplaçables dans un fichier PDF » ?

R : Le didacticiel « Rendu des symboles remplaçables dans un fichier PDF » montre comment utiliser la bibliothèque Aspose.PDF pour .NET pour créer un document PDF comprenant des symboles remplaçables. Ces symboles sont représentés sous forme de fragments de texte avec des marqueurs de nouvelle ligne pour créer un contenu multiligne.

#### Q : Pourquoi voudrais-je afficher des symboles remplaçables dans un document PDF ?

R : Le rendu des symboles remplaçables est utile lorsque vous devez générer dynamiquement du contenu PDF comprenant des informations variables ou spécifiques à l'utilisateur. Ces symboles agissent comme des espaces réservés qui peuvent être remplacés par des données réelles pendant l'exécution, telles que des valeurs de champs de formulaire ou des détails personnalisés.

#### Q : Comment configurer le répertoire de documents ?

R : Pour configurer le répertoire de documents :

1.  Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès au répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré.

#### Q : Comment puis-je restituer les symboles remplaçables dans un document PDF à l'aide de la bibliothèque Aspose.PDF ?

R : Le didacticiel vous guide étape par étape tout au long du processus :

1.  Créez un nouveau document PDF à l'aide du`Document` classe.
2.  Ajoutez une page au document à l'aide du`Page` classe.
3.  Créer un`TextFragment` objet avec des marqueurs de nouvelle ligne (`Environment.NewLine`) pour représenter un contenu multiligne.
4. Personnalisez les propriétés du fragment de texte telles que la taille de la police, la police, la couleur d'arrière-plan et la couleur de premier plan.
5.  Créer un`TextParagraph` objet, ajoutez-y le fragment de texte et définissez la position du paragraphe sur la page.
6.  Créer un`TextBuilder` objet avec la page et ajoutez-y le paragraphe de texte.
7. Enregistrez le document PDF.

#### Q : A quoi sert l’utilisation de marqueurs de nouvelle ligne (`Environment.NewLine`) in the text fragment?

 R : Les marqueurs de nouvelle ligne sont utilisés pour créer du contenu multiligne dans un seul fragment de texte. En utilisant`Environment.NewLine`, vous pouvez indiquer où les sauts de ligne doivent apparaître dans le texte.

#### Q : Puis-je personnaliser l’apparence des symboles remplaçables ?

R : Oui, vous pouvez personnaliser diverses propriétés du fragment de texte, telles que la taille de la police, la police, la couleur d'arrière-plan et la couleur de premier plan. Ces propriétés déterminent l'apparence visuelle des symboles remplaçables dans le document PDF.

#### Q : Comment puis-je spécifier la position du texte sur la page ?

 R : Vous pouvez définir la position du texte en créant un`TextParagraph` objet et en utilisant le`Position` propriété pour spécifier les coordonnées X et Y sur la page où le paragraphe doit être positionné.

#### Q : Quel est le résultat attendu de l’exécution du code fourni ?

R : En suivant le didacticiel et en exécutant le code C# fourni, vous créerez un document PDF comprenant des symboles remplaçables. Les symboles remplaçables seront représentés sous forme de fragments de texte avec des marqueurs de nouvelle ligne et des propriétés personnalisées.

#### Q : Puis-je utiliser cette approche pour générer dynamiquement des documents PDF personnalisés ?

: Oui, cette approche convient à la génération dynamique de documents PDF contenant des informations personnalisées. En remplaçant les symboles remplaçables par des données réelles, vous pouvez créer un contenu PDF personnalisé pour chaque utilisateur ou scénario.
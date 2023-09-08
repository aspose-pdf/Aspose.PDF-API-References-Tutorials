---
title: Créer un PDF multi-colonnes
linktitle: Créer un PDF multi-colonnes
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment créer un PDF multi-colonnes à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-text/create-multi-column-pdf/
---
Ce didacticiel vous guidera tout au long du processus de création d'un PDF multi-colonnes à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger depuis le site officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code dans lequel vous souhaitez créer un PDF multi-colonnes, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Étape 3 : Définir le répertoire des documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où sont stockés vos documents.

## Étape 4 : Créer une nouvelle instance de document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document doc = new Document();
```

## Étape 5 : Définir les marges de la page
 Spécifiez les informations sur les marges gauche et droite du fichier PDF à l'aide de l'option`PageInfo.Margin` propriété du`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## Étape 6 : Ajouter une page au document
 Ajoutez une nouvelle page au document à l'aide du`Add` méthode du`Pages`collection. Dans le code fourni, la nouvelle page est affectée à la variable`page`.

```csharp
Page page = doc.Pages.Add();
```

## Étape 7 : Créez un objet graphique et ajoutez une ligne
 Créer un nouveau`Graph` objet avec des dimensions spécifiques et ajoutez-y une ligne. Ensuite, ajoutez le`Graph` s'opposer à la`Paragraphs` collection de la page.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## Étape 8 : Ajouter le texte du titre avec le formatage HTML
 Créé un`HtmlFragment` objet et définissez son contenu sur le texte HTML souhaité. Ensuite, ajoutez le fragment au`Paragraphs` collection de la page.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## Étape 9 : Créer une FloatingBox avec plusieurs colonnes
 Créer un`FloatingBox` objet et définissez le nombre de colonnes et l’espacement des colonnes. Ensuite, ajoutez des fragments de texte et une ligne au`Paragraphs` collecte des`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## Étape 10 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide du`Save` méthode du`Document` objet.

```csharp
doc.Save(dataDir);
```

### Exemple de code source pour créer un PDF multi-colonnes à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// Spécifiez les informations de la marge gauche du fichier PDF
doc.PageInfo.Margin.Left = 40;
//Spécifiez les informations de marge droite pour le fichier PDF
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// Ajouter la ligne à la collection de paragraphes de l'objet de section
page.Paragraphs.Add(graph1);
// Spécifiez les coordonnées de la ligne
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// Créer des variables de chaîne avec du texte contenant des balises HTML
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// Créer des paragraphes de texte contenant du texte HTML
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// Ajouter quatre colonnes dans la section
box.ColumnInfo.ColumnCount = 2;
// Définir l'espacement entre les colonnes
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// Créer un objet graphique pour tracer une ligne
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// Spécifiez les coordonnées de la ligne
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// Ajouter la ligne à la collection de paragraphes de l'objet de section
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## Conclusion
Vous avez créé avec succès un PDF multi-colonnes à l'aide d'Aspose.PDF pour .NET. Le fichier PDF résultant peut maintenant être trouvé au chemin du fichier de sortie spécifié.

### FAQ

#### Q : Quel est l'objet de ce didacticiel ?

Ce didacticiel a pour objectif de vous guider tout au long du processus de création d'un PDF multicolonne à l'aide de la bibliothèque Aspose.PDF pour .NET. Le code source C# fourni montre les étapes nécessaires pour y parvenir.

#### Q : Quels espaces de noms dois-je importer pour ce didacticiel ?

R : Dans le fichier de code dans lequel vous souhaitez créer un PDF multicolonne, importez les espaces de noms suivants au début du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Q : Comment spécifier le répertoire des documents ?

 R : Dans le code, recherchez la ligne`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

#### Q : Comment créer une nouvelle instance de document ?

 R : À l'étape 4, vous allez instancier un nouveau`Document` objet en utilisant le code fourni.

#### Q : Comment définir les marges de la page ?

 R : À l'étape 5, vous utiliserez le`PageInfo.Margin` propriété du`Document` pour spécifier les informations sur les marges gauche et droite du fichier PDF.

#### Q : Comment ajouter une page au document ?

 R : À l'étape 6, vous ajouterez une nouvelle page au document à l'aide de l'outil`Add` méthode du`Pages` collection.

#### Q : Comment créer un objet graphique et ajouter une ligne ?

 R : À l'étape 7, vous allez créer un nouveau`Graph` objet, ajoutez-y une ligne, puis ajoutez le`Graph` s'opposer à la`Paragraphs` collection de la page.

#### Q : Comment ajouter du texte de titre au format HTML ?

 R : À l'étape 8, vous allez créer un`HtmlFragment` objet et définissez son contenu sur le texte HTML souhaité, puis ajoutez le fragment au`Paragraphs` collection de la page.

#### Q : Comment créer une FloatingBox avec plusieurs colonnes ?

 R : À l'étape 9, vous allez créer un`FloatingBox` objet avec plusieurs colonnes et espacement des colonnes, puis ajoutez des fragments de texte et une ligne au`Paragraphs` collecte des`FloatingBox`.

#### Q : Comment puis-je enregistrer le document PDF ?

 R : À l'étape 10, vous enregistrerez le document PDF à l'aide du`Save` méthode du`Document` objet.

#### Q : Quel est le principal point à retenir de ce didacticiel ?

R : En suivant ce didacticiel, vous avez appris à créer un document PDF multicolonne à l'aide d'Aspose.PDF pour .NET. Cela peut être utile pour afficher du contenu dans une mise en page structurée et organisée.
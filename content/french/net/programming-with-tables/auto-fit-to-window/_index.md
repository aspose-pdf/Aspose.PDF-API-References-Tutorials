---
title: Ajustement automatique à la fenêtre
linktitle: Ajustement automatique à la fenêtre
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour utiliser Aspose.PDF pour .NET et obtenir un ajustement automatique à la fenêtre lors de la génération de PDF.
type: docs
weight: 50
url: /fr/net/programming-with-tables/auto-fit-to-window/
---
L'article suivant est un guide étape par étape sur la façon d'utiliser le code source C# fourni pour obtenir la fonctionnalité d'ajustement automatique à la fenêtre à l'aide de la bibliothèque Aspose.PDF pour .NET. La fonction d'ajustement automatique à la fenêtre vous permet de générer des fichiers PDF avec une mise en page adaptée à la fenêtre de visualisation. Cette fonctionnalité est particulièrement utile lorsque vous souhaitez que votre document PDF s'adapte automatiquement à la taille de la fenêtre de lecture PDF utilisée par l'utilisateur.

## Étape 1 : Configuration de l'environnement

Avant de commencer, vous devez installer la bibliothèque Aspose.PDF pour .NET sur votre machine. Assurez-vous également d'importer les espaces de noms nécessaires dans votre projet.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un document PDF

 Pour commencer, vous devez créer un`Document` objet en appelant son constructeur par défaut.

```csharp
Document doc = new Document();
```

 Ensuite, créez une section dans le`Pdf` objet.

```csharp
Page sec1 = doc.Pages.Add();
```

## Étape 3 : Ajout d’un tableau au document

 Dans cette étape, nous allons ajouter un tableau à notre document PDF. Créez d'abord un`Table` objet.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

Ensuite, ajoutez le tableau à la collection de paragraphes de la section.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  Étape 4 : Personnalisation de l’apparence du tableau

Vous pouvez personnaliser l'apparence du tableau en définissant des propriétés telles que les bordures des cellules et la marge.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  Étape 4 : Ajout de lignes et de cellules au tableau

Ajoutons maintenant des lignes et des cellules à notre tableau. Commencez par créer une ligne et ajoutez des cellules à cette ligne.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## Étape 5 : enregistrement du document

Enfin, spécifiez le chemin du fichier de sortie et enregistrez le document.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour l'ajustement automatique à la fenêtre à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Lancez l'objet Pdf en appelant son constructeur vide
Document doc = new Document();
// Créer la section dans l'objet Pdf
Page sec1 = doc.Pages.Add();

// Instancier un objet de table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Ajoutez le tableau dans la collection de paragraphes de la section souhaitée
sec1.Paragraphs.Add(tab1);

// Définir avec les largeurs de colonnes du tableau
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// Définir la bordure de cellule par défaut à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Définir la bordure du tableau à l’aide d’un autre objet BorderInfo personnalisé
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Créez un objet MarginInfo et définissez ses marges gauche, inférieure, droite et supérieure
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// Définir le remplissage de cellule par défaut sur l'objet MarginInfo
tab1.DefaultCellPadding = margin;

//Créez des lignes dans le tableau, puis des cellules dans les lignes
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// Enregistrer le document mis à jour contenant l'objet tableau
doc.Save(dataDir);
```

## Conclusion

Dans ce tutoriel, nous avons appris à utiliser Aspose.PDF pour .NET pour générer un fichier PDF avec la fonction d'ajustement automatique à la fenêtre. Cette fonction est extrêmement utile lorsque vous souhaitez que votre document PDF s'ajuste automatiquement à la taille de la fenêtre de visualisation. Aspose.PDF pour .NET offre de nombreuses autres fonctionnalités puissantes pour générer et manipuler des fichiers PDF. Je vous encourage à explorer davantage cette bibliothèque pour découvrir toutes ses fonctionnalités.

### FAQ

#### Q : Quel est le but de la fonction Ajuster automatiquement à la fenêtre dans la génération de PDF ?

R : La fonction d'ajustement automatique à la fenêtre dans la génération de PDF garantit que la mise en page du document PDF s'ajuste automatiquement à la taille de la fenêtre du lecteur PDF utilisée par l'utilisateur. Cela permet une meilleure visualisation et garantit que le contenu s'adapte parfaitement à la zone de visualisation disponible.

#### Q : Puis-je personnaliser l’apparence du tableau, comme la taille de la police et les couleurs ?

R : Oui, vous pouvez personnaliser l'apparence du tableau dans le document PDF à l'aide d'Aspose.PDF pour .NET. L'extrait de code fourni montre comment définir des propriétés telles que les bordures de cellule, les marges et la largeur des colonnes. Vous pouvez personnaliser davantage la taille de la police, les couleurs et d'autres aspects de style du tableau et de son contenu.

#### Q : Comment intégrer Aspose.PDF pour .NET dans mon projet C# ?

R : Pour utiliser Aspose.PDF pour .NET dans votre projet C#, vous devez d’abord installer la bibliothèque Aspose.PDF pour .NET sur votre machine. Ensuite, vous pouvez ajouter une référence à la bibliothèque dans votre projet C#. Enfin, importez les espaces de noms nécessaires pour accéder aux classes et méthodes fournies par Aspose.PDF pour .NET.

#### Q : Aspose.PDF pour .NET est-il compatible avec les applications .NET Core ?

R : Oui, Aspose.PDF pour .NET est compatible avec les applications .NET Core. Il prend en charge diverses plates-formes .NET, notamment .NET Framework, .NET Core et .NET 5.0+.

#### Q : Puis-je ajouter d’autres tableaux au document PDF ?

 : Oui, vous pouvez ajouter plusieurs tableaux à un document PDF en suivant des étapes similaires à celles illustrées dans l'extrait de code. Créez simplement de nouvelles instances du`Aspose.Pdf.Table` classe et les ajouter à différentes sections ou pages du document PDF.
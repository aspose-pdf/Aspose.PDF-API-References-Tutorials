---
title: Ajouter un objet SVG
linktitle: Ajouter un objet SVG
second_title: Référence de l'API Aspose.PDF pour .NET
description: Ajoutez facilement des objets SVG à vos fichiers PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-tables/add-svg-object/
---

Dans ce didacticiel, nous allons apprendre à ajouter un objet SVG à un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. SVG (Scalable Vector Graphics) est un format populaire pour les graphiques vectoriels qui peuvent être facilement mis à l'échelle sans perte de qualité. Avec Aspose.PDF, vous pouvez ajouter des objets SVG à vos documents PDF par programmation.

## Exigences

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio installé
- Bibliothèque Aspose.PDF pour .NET installée

## Étape 1 : Configurer l'environnement

Tout d'abord, configurons l'environnement en créant un nouveau projet C# dans Visual Studio. Ouvrez Visual Studio et suivez ces étapes :

1. Cliquez sur "Fichier" > "Nouveau" > "Projet" pour créer un nouveau projet.
2. Sélectionnez le modèle "Console App (.NET Framework)" ou "Console App (.NET Core)", selon votre configuration.
3. Choisissez un nom et un emplacement appropriés pour votre projet, puis cliquez sur "Créer".

## Étape 2 : créer des objets de document et d'image

Dans cette étape, nous allons créer les objets nécessaires pour notre document PDF et notre image SVG. Ouvrez le fichier C# de votre projet et ajoutez le code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objet Document instantané
Document doc = new Document();
// Créer une instance d'image
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Étape 3 : Définir les propriétés de l'image

Ensuite, nous allons définir les propriétés de notre image SVG. Nous spécifierons le type de fichier comme SVG, le chemin d'accès au fichier SVG et les dimensions de l'image. Ajoutez le code suivant après l'étape précédente :

```csharp
// Définir le type d'image comme SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Chemin du fichier source
img.File = dataDir + "SVGToPDF.svg";
// Définir la largeur de l'instance d'image
img. FixWidth = 50;
// Définir la hauteur de l'instance d'image
img.FixHeight = 50;
```

## Étape 4 : créer et configurer la table

Maintenant, créons un objet table et définissons les largeurs de colonne. Nous allons créer un tableau avec deux colonnes, chacune d'une largeur de 100 unités. Ajoutez le code suivant :

```csharp
// Créer une table d'instances
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Définir la largeur des cellules du tableau
table. ColumnWidths = "100 100";
```

## Étape 5 : Ajouter des cellules au tableau

Dans cette étape, nous allons ajouter une ligne et des cellules au tableau. Chaque ligne représente une ligne horizontale dans le tableau et des cellules sont ajoutées aux lignes. Ajoutez le code suivant :

```csharp
// Créer un objet de ligne et l'ajouter à l'instance de table
Aspose.Pdf.Row row = table.Rows.Add();
// Créer un objet cellule et l'ajouter à l'instance de ligne
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Étape 6 : Ajouter du texte et une image aux cellules

Ensuite, ajoutons du texte et l'image SVG aux cellules du tableau. Nous ajouterons le texte "Première cellule" à la première cellule et l'image SVG à la deuxième cellule. Ajoutez le code suivant :

```csharp
// Ajouter un fragment de texte à la collection de paragraphes de l'objet cellule
cell.Paragraphs.Add(new TextFragment("First cell"));
// Ajouter une autre cellule à l'objet ligne
cell = row. Cells. Add();
// Ajouter une image SVG à la collection de paragraphes de l'instance de cellule récemment ajoutée
cell.Paragraphs.Add(img);
```

## Étape 7 : créer et ajouter une page au document

Maintenant, créons un objet page et ajoutons-le au document. Le tableau sera ajouté à la collection de paragraphes de la page. Ajoutez le code suivant :

```csharp
// Créer un objet de page et l'ajouter à la collection de pages de l'instance de document
Page page = doc.Pages.Add();
// Ajouter un tableau à la collection de paragraphes de l'objet de page
page.Paragraphs.Add(table);
```

## Étape 8 : Enregistrez le fichier PDF

Enfin, nous enregistrerons le fichier PDF à l'emplacement spécifié. Ajoutez le code suivant :

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Exemple de code source pour ajouter un objet SVG à l'aide de Aspose.Words pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'objet Document
Document doc = new Document();
// Créer une instance d'image
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Définir le type d'image comme SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Chemin du fichier source
img.File = dataDir + "SVGToPDF.svg";
// Définir la largeur de l'instance d'image
img.FixWidth = 50;
// Définir la hauteur de l'instance d'image
img.FixHeight = 50;
// Créer une instance de table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Définir la largeur des cellules du tableau
table.ColumnWidths = "100 100";
// Créer un objet de ligne et l'ajouter à l'instance de table
Aspose.Pdf.Row row = table.Rows.Add();
// Créer un objet cellule et l'ajouter à l'instance de ligne
Aspose.Pdf.Cell cell = row.Cells.Add();
// Ajouter un fragment de texte à la collection de paragraphes de l'objet cellule
cell.Paragraphs.Add(new TextFragment("First cell"));
// Ajouter une autre cellule à l'objet ligne
cell = row.Cells.Add();
// Ajouter une image SVG à la collection de paragraphes de l'instance de cellule récemment ajoutée
cell.Paragraphs.Add(img);
// Créer un objet de page et l'ajouter à la collection de pages de l'instance de document
Page page = doc.Pages.Add();
// Ajouter un tableau à la collection de paragraphes de l'objet de page
page.Paragraphs.Add(table);

dataDir = dataDir + "AddSVGObject_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);            
```

## Conclusion

Dans ce didacticiel, nous avons appris à ajouter un objet SVG à un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous avons couvert le processus étape par étape de création d'un document, de configuration de l'environnement, d'ajout d'une image SVG à une cellule de tableau et d'enregistrement du fichier PDF. Vous pouvez désormais incorporer des objets SVG dans vos documents PDF par programmation.
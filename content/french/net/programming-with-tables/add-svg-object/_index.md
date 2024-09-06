---
title: Ajouter un objet SVG dans un fichier PDF
linktitle: Ajouter un objet SVG dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Ajoutez facilement des objets SVG dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-tables/add-svg-object/
---
Dans ce tutoriel, nous allons apprendre à ajouter un objet SVG dans un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. SVG (Scalable Vector Graphics) est un format populaire pour les graphiques vectoriels qui peuvent être facilement mis à l'échelle sans perte de qualité. Avec Aspose.PDF, vous pouvez ajouter des objets SVG à vos documents PDF par programmation.

## Exigences

Avant de commencer, assurez-vous de disposer des éléments suivants :

- Visual Studio installé
- Bibliothèque Aspose.PDF pour .NET installée

## Étape 1 : Configurer l’environnement

Commençons par configurer l'environnement en créant un nouveau projet C# dans Visual Studio. Ouvrez Visual Studio et suivez ces étapes :

1. Cliquez sur « Fichier » > « Nouveau » > « Projet » pour créer un nouveau projet.
2. Sélectionnez le modèle « Application console (.NET Framework) » ou « Application console (.NET Core) », selon votre configuration.
3. Choisissez un nom et un emplacement appropriés pour votre projet, puis cliquez sur « Créer ».

## Étape 2 : Créer des objets de document et d’image

Dans cette étape, nous allons créer les objets nécessaires à notre document PDF et à notre image SVG. Ouvrez le fichier C# de votre projet et ajoutez le code suivant :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Objet Document instantané
Document doc = new Document();
// Créer une instance d'image
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
```

## Étape 3 : définir les propriétés de l’image

Ensuite, nous allons définir les propriétés de notre image SVG. Nous allons spécifier le type de fichier SVG, le chemin d'accès au fichier SVG et les dimensions de l'image. Ajoutez le code suivant après l'étape précédente :

```csharp
// Définir le type d'image comme SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Chemin d'accès au fichier source
img.File = dataDir + "SVGToPDF.svg";
// Définir la largeur de l'instance d'image
img. FixWidth = 50;
// Définir la hauteur de l'instance d'image
img.FixHeight = 50;
```

## Étape 4 : Créer et configurer la table

Maintenant, créons un objet tableau et définissons la largeur des colonnes. Nous allons créer un tableau avec deux colonnes, chacune d'une largeur de 100 unités. Ajoutez le code suivant :

```csharp
// Créer une table d'instance
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Définir la largeur des cellules du tableau
table. ColumnWidths = "100 100";
```

## Étape 5 : ajouter des cellules au tableau

Dans cette étape, nous allons ajouter une ligne et des cellules au tableau. Chaque ligne représente une ligne horizontale dans le tableau et des cellules sont ajoutées aux lignes. Ajoutez le code suivant :

```csharp
//Créer un objet de ligne et l'ajouter à l'instance de table
Aspose.Pdf.Row row = table.Rows.Add();
// Créer un objet de cellule et l'ajouter à l'instance de ligne
Aspose.Pdf.Cell cell = row.Cells.Add();
```

## Étape 6 : ajouter du texte et une image aux cellules

Ensuite, ajoutons du texte et l'image SVG aux cellules du tableau. Nous ajouterons le texte « Première cellule » à la première cellule et l'image SVG à la deuxième cellule. Ajoutez le code suivant :

```csharp
// Ajouter un fragment de texte à la collection de paragraphes de l'objet cellule
cell.Paragraphs.Add(new TextFragment("First cell"));
// Ajouter une autre cellule à l'objet de ligne
cell = row. Cells. Add();
// Ajouter une image SVG à la collection de paragraphes de l'instance de cellule récemment ajoutée
cell.Paragraphs.Add(img);
```

## Étape 7 : Créer et ajouter une page au document

Maintenant, créons un objet page et ajoutons-le au document. Le tableau sera ajouté à la collection de paragraphes de la page. Ajoutez le code suivant :

```csharp
// Créer un objet de page et l'ajouter à la collection de pages de l'instance de document
Page page = doc.Pages.Add();
// Ajouter un tableau à la collection de paragraphes de l'objet de page
page.Paragraphs.Add(table);
```

## Étape 8 : Enregistrez le fichier PDF

Enfin, nous allons enregistrer le fichier PDF à l'emplacement spécifié. Ajoutez le code suivant :

```csharp
dataDir = dataDir + "AddSVGObject_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);

Console.WriteLine("\nSVG image added successfully inside a table cell.\nFile saved at " + dataDir);
```

### Exemple de code source pour ajouter un objet SVG à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'objet Document
Document doc = new Document();
// Créer une instance d'image
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// Définir le type d'image comme SVG
img.FileType = Aspose.Pdf.ImageFileType.Svg;
// Chemin d'accès au fichier source
img.File = dataDir + "SVGToPDF.svg";
// Définir la largeur de l'instance d'image
img.FixWidth = 50;
// Définir la hauteur de l'instance d'image
img.FixHeight = 50;
// Créer une instance de table
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// Définir la largeur des cellules du tableau
table.ColumnWidths = "100 100";
//Créer un objet de ligne et l'ajouter à l'instance de table
Aspose.Pdf.Row row = table.Rows.Add();
// Créer un objet de cellule et l'ajouter à l'instance de ligne
Aspose.Pdf.Cell cell = row.Cells.Add();
// Ajouter un fragment de texte à la collection de paragraphes de l'objet cellule
cell.Paragraphs.Add(new TextFragment("First cell"));
// Ajouter une autre cellule à l'objet de ligne
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

Dans ce didacticiel, nous avons appris à ajouter un objet SVG à un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous avons abordé le processus étape par étape de création d'un document, de configuration de l'environnement, d'ajout d'une image SVG à une cellule de tableau et d'enregistrement du fichier PDF. Vous pouvez désormais incorporer des objets SVG dans vos documents PDF par programmation.

### FAQ pour ajouter un objet SVG dans un fichier PDF

#### Q : Puis-je ajouter plusieurs objets SVG au document PDF ?

 R : Oui, vous pouvez ajouter plusieurs objets SVG au document PDF. Il vous suffit de créer et de configurer des objets supplémentaires.`Aspose.Pdf.Image` instances pour chaque image SVG que vous souhaitez ajouter, puis ajoutez-les aux cellules de tableau ou aux paragraphes souhaités dans le document PDF.

#### Q : Comment puis-je ajuster la taille et la position de l’image SVG dans la cellule du tableau ?

 A : Pour ajuster la taille et la position de l'image SVG dans la cellule du tableau, vous pouvez modifier le`FixWidth` et`FixHeight` propriétés de la`Aspose.Pdf.Image`exemple. Vous pouvez également utiliser d'autres propriétés comme`HorizontalAlignment` et`VerticalAlignment` de la cellule du tableau pour contrôler le positionnement.

#### Q : Est-il possible d’ajouter du texte à côté de l’image SVG dans la même cellule du tableau ?

 R : Oui, il est possible d'ajouter du texte à côté de l'image SVG dans la même cellule du tableau. Vous pouvez utiliser l'`cell.Paragraphs.Add(new TextFragment("Your Text Here"));` méthode pour ajouter du texte à la cellule avec l'image SVG.

#### Q : Puis-je ajouter des hyperliens à l’image SVG ?

 R : Oui, vous pouvez ajouter des hyperliens à l'image SVG en utilisant le`Hyperlink` propriété de la`Aspose.Pdf.Image` exemple. Définissez l'URL ou l'action du lien hypertexte pour rendre l'image cliquable.

#### Q : Aspose.PDF pour .NET est-il compatible avec .NET Core 3.1 ou les versions ultérieures ?

R : Oui, Aspose.PDF pour .NET est compatible avec .NET Core 3.1 et les versions ultérieures. Vous pouvez l'utiliser dans les applications .NET Framework et .NET Core.
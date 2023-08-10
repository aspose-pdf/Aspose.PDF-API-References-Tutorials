---
title: Tableau dans la section d'en-tête de pied de page
linktitle: Tableau dans la section d'en-tête de pied de page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter un tableau dans la section en-tête/pied de page d'un document PDF avec Aspose.PDF pour .NET.
type: docs
weight: 170
url: /fr/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
Dans ce didacticiel, nous vous guiderons étape par étape sur la façon d'ajouter un tableau dans la section d'en-tête ou de pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni vous montre comment créer un document PDF vide, ajouter une page, configurer la section d'en-tête, créer un tableau, ajouter des lignes et des cellules au tableau et enfin enregistrer le document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Création du document PDF et de la page

 La première étape consiste à créer une instance de`Document` classe et ajouter une page au document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instancier un objet Document
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// Créer une page dans le document PDF
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire dans lequel vous souhaitez enregistrer le document PDF.

## Étape 3 : Configurer la section d'en-tête

 Nous allons maintenant configurer la section d'en-tête du document PDF en créant une instance de`HeaderFooter` classe. Voici comment:

```csharp
// Créer une section d'en-tête pour le fichier PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Définir la section d'en-tête de la page
page. Header = header;

//Définir la marge supérieure de la section d'en-tête
header. Margin. Top = 20;
```

## Etape 4 : Création du tableau

 Nous allons maintenant créer une table en utilisant le`Table` class et ajoutez-le à la collection de paragraphes de la section d'en-tête. Voici comment:

```csharp
// Instancier un objet Table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Ajouter le tableau à la collection de paragraphes de la section d'en-tête
header.Paragraphs.Add(tab1);

// Définir les largeurs des colonnes du tableau
tab1.ColumnWidths = "60,300";
```

Le code ci-dessus crée une table avec deux colonnes de largeurs spécifiées.

## Étape 5 : Ajouter des lignes et des cellules au tableau

 Nous allons maintenant ajouter des lignes et des cellules au tableau à l'aide de la`Row` classe et la`Cell` classe. Voici comment:

```csharp
// Créer une ligne dans le tableau et ajouter des cellules
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// Fusionner la première cellule de la première ligne
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Créez une autre ligne dans le tableau et ajoutez une cellule avec une image
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Étape 6 : Enregistrer le document PDF

Une fois le tableau ajouté à la section d'en-tête, nous pouvons enregistrer le document PDF. Voici comment:

```csharp
//Enregistrez le fichier PDF
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire dans lequel vous souhaitez enregistrer le document PDF.

### Exemple de code source pour la section Table In Header Footer utilisant Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instanciez l'instance de document en appelant un constructeur vide
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

//Créer une page dans le document pdf
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// Créer une section d'en-tête du fichier PDF
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// Définir l'en-tête impair pour le fichier PDF
page.Header = header;

// Définir la marge supérieure de la section d'en-tête
header.Margin.Top = 20;

// Instancier un objet table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// Ajouter le tableau dans la collection de paragraphes de la section souhaitée
header.Paragraphs.Add(tab1);

// Définir la bordure de cellule par défaut à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// Définir avec les largeurs de colonne du tableau
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// Créer des lignes dans le tableau, puis des cellules dans les lignes
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// Définissez la valeur d'étendue de ligne pour la première ligne sur 2
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Créer des lignes dans le tableau, puis des cellules dans les lignes
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Définir la couleur d'arrière-plan pour Row2
row2.BackgroundColor = Color.White;

// Ajouter la cellule qui contient l'image
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// Réglez la largeur de l'image sur 60
img.FixWidth = 60;

// Ajouter l'image à la cellule du tableau
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// Définir l'alignement vertical du texte comme aligné au centre
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// Enregistrez le fichier Pdf
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## Conclusion

Félicitation ! Vous avez appris à ajouter un tableau dans la section d'en-tête ou de pied de page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais personnaliser vos en-têtes et pieds de page en ajoutant des tableaux pour afficher des informations supplémentaires dans vos documents PDF.

### FAQ pour le tableau dans la section d'en-tête et de pied de page

#### Q : À quoi sert l'ajout d'un tableau dans la section d'en-tête ou de pied de page d'un document PDF ?

R : L'ajout d'un tableau dans la section d'en-tête ou de pied de page d'un document PDF vous permet d'afficher des informations structurées et organisées telles que des titres, des sous-titres, des logos ou tout autre contenu que vous souhaitez voir apparaître de manière cohérente sur chaque page du document.

#### Q : Comment le code source C# fourni parvient-il à ajouter un tableau dans la section d'en-tête ou de pied de page d'un document PDF ?

R : Le code illustre le processus de création d'un document PDF vide, l'ajout d'une page, la configuration de la section d'en-tête, la création d'un tableau avec des lignes et des cellules, et enfin l'enregistrement du document PDF. Le résultat est un tableau affiché dans la section d'en-tête du document PDF.

#### Q : Puis-je personnaliser l'apparence des cellules du tableau, telles que les bordures, la couleur d'arrière-plan et le style de texte ?

R : Oui, vous pouvez personnaliser l'apparence des cellules du tableau en définissant des propriétés telles que les bordures de cellule, la couleur d'arrière-plan, le style de texte, la police, la taille de la police, etc.

#### Q : Comment le tableau est-il ajouté à la section d'en-tête du document PDF ?

R : Le code ajoute le tableau à la collection de paragraphes de la section d'en-tête, ce qui garantit que le tableau s'affiche dans l'en-tête de chaque page.

#### Q : Puis-je ajouter plus de lignes et de cellules au tableau si nécessaire ?

 A : Absolument, vous pouvez ajouter plus de lignes et de cellules au tableau en utilisant le`Rows.Add()` et`Cells.Add()` méthodes. Cela vous permet de structurer le contenu du tableau comme vous le souhaitez.

#### Q : Est-il possible d'ajuster la largeur des colonnes du tableau ?
 R : Oui, vous pouvez ajuster la largeur des colonnes du tableau à l'aide du bouton`ColumnWidths` propriété. Cela vous permet de contrôler la disposition du tableau.

#### Q : Comment puis-je répartir les cellules sur plusieurs colonnes ou lignes dans le tableau ?
 R : Pour répartir les cellules sur plusieurs colonnes, vous pouvez utiliser la`ColSpan`propriété de la cellule correspondante. De même, vous pouvez utiliser le`RowSpan` propriété pour étendre les cellules sur plusieurs lignes.

#### Q : Que se passe-t-il si je souhaite ajouter un tableau aux sections d'en-tête et de pied de page du document PDF ?

 R : Vous pouvez suivre une approche similaire pour les sections d'en-tête et de pied de page. Créez simplement un`HeaderFooter` instance pour le pied de page, configurez-le et ajoutez le tableau à sa collection de paragraphes.

#### Q : Puis-je utiliser des images dans les cellules du tableau, et comment y parvenir ?

 R : Oui, vous pouvez ajouter des images dans les cellules du tableau. L'exemple de code montre comment ajouter une image à une cellule en créant un`Image` objet, en définissant son chemin de fichier et ses dimensions, puis en l'ajoutant aux paragraphes d'une cellule.

#### Q : Comment puis-je m'assurer que le tableau apparaît de manière cohérente sur toutes les pages du document PDF ?

 R : Lorsque vous ajoutez le tableau à la section d'en-tête ou de pied de page à l'aide de la`HeaderFooter` Par exemple, Aspose.PDF garantit que le tableau apparaît de manière cohérente sur chaque page, offrant une mise en page uniforme.
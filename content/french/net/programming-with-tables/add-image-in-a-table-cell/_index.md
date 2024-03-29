---
title: Ajouter une image dans une cellule de tableau
linktitle: Ajouter une image dans une cellule de tableau
second_title: Aspose.PDF pour la référence de l'API .NET
description: Ajoutez une image dans une cellule de tableau avec Aspose.PDF pour .NET, un guide étape par étape pour une manipulation précise des images dans les documents PDF.
type: docs
weight: 10
url: /fr/net/programming-with-tables/add-image-in-a-table-cell/
---
Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout d'une image à une cellule de tableau à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni montre comment réaliser cette fonctionnalité. En suivant les étapes décrites ci-dessous, vous pourrez intégrer efficacement des images dans les cellules de votre tableau.

Avant de plonger dans le code, assurez-vous que la bibliothèque Aspose.PDF pour .NET est installée et référencée dans votre projet.

## Étape 1 : Configuration du document

 Pour commencer, nous devons créer une nouvelle instance du`Document` classe de l’espace de noms Aspose.Pdf. Cette classe représente un document PDF.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier un objet Document
Document pdfDocument = new Document();
```

## Étape 2 : Création d'une page

Ensuite, nous devons ajouter une page au document PDF. Une page sert de conteneur pour le tableau et d’autres éléments.

```csharp
// Créer une page dans le document pdf
Page sec1 = pdfDocument.Pages.Add();
```

## Étape 3 : Ajout d'un tableau

 Dans cette étape, nous allons créer une table en instanciant le`Table` classe de l’espace de noms Aspose.Pdf.

```csharp
// Instancier un objet table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## Étape 4 : Définition de la bordure de cellule par défaut

 Pour garantir la cohérence, nous pouvons définir une bordure de cellule par défaut à l'aide de l'option`DefaultCellBorder`propriété de la table`BorderInfo` objet.

```csharp
// Définir la bordure de cellule par défaut à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## Étape 5 : Définition des largeurs de colonnes

 Pour définir la largeur de chaque colonne du tableau, nous pouvons définir la`ColumnWidths` propriété. Spécifiez les largeurs sous forme de chaîne avec des valeurs séparées par des espaces.

```csharp
// Définir avec les largeurs de colonnes du tableau
tab1.ColumnWidths = "100 100 120";
```

## Étape 6 : Ajout d'une image à une cellule de tableau

Vient maintenant la partie la plus intéressante : ajouter une image à une cellule du tableau. Pour ce faire, nous suivrons ces sous-étapes :

## Étape 6.1 : Création d'un objet image

 Créez une instance du`Image` classe de l’espace de noms Aspose.Pdf. Met le`File` propriété au chemin du fichier image que vous souhaitez ajouter.

```csharp
// Créer un objet Image
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
```

## Étape 6.2 : Création d'une ligne et de cellules

Pour ajouter l'image au tableau, nous devons d'abord créer une ligne et les cellules nécessaires.

```csharp
// Créer une ligne dans le tableau
Aspose.Pdf.Row row1 = tab1.Rows.Add();

// Ajouter une cellule de texte à la ligne
row1.Cells.Add("Sample text in cell");

// Ajouter la cellule qui contient l'image
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
```

## Étape 6.3 : Ajout de l'image à la cellule du tableau

Enfin, nous pouvons ajouter l'image à la cellule du tableau en l'ajoutant sous forme de paragraphe dans la cellule.

```csharp
// Ajouter l'image à la cellule du tableau
cell2.Paragraphs.Add(img);
```

## Étape 6.4 : Ajout de cellules supplémentaires

Après avoir ajouté la cellule d'image, nous pouvons ajouter plus de cellules à la ligne si nécessaire.

```csharp
//Ajouter une autre cellule à la ligne
row1.Cells.Add("Previous cell with image");

// Ajustez l’alignement vertical de la troisième cellule
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
```

## Étape 7 : Sauvegarde du document

 Enfin, nous pouvons enregistrer le document modifié dans un emplacement spécifié en utilisant le`Save` méthode.

```csharp
// Enregistrez le document
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

Toutes nos félicitations! Vous avez appris avec succès comment ajouter une image à une cellule de tableau à l'aide d'Aspose.PDF pour .NET. N'hésitez pas à explorer d'autres options de personnalisation et à intégrer cette fonctionnalité dans vos projets.

### Exemple de code source pour ajouter une image dans une cellule de tableau à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier un objet Document
Document pdfDocument = new Document();
// Créer une page dans le document pdf
Page sec1 = pdfDocument.Pages.Add();
// Instancier un objet table
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// Ajouter le tableau dans la collection de paragraphes de la page souhaitée
sec1.Paragraphs.Add(tab1);
// Définir la bordure de cellule par défaut à l'aide de l'objet BorderInfo
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Définir avec les largeurs de colonnes du tableau
tab1.ColumnWidths = "100 100 120";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose.jpg";
// Créez des lignes dans le tableau puis des cellules dans les lignes
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Sample text in cell");
// Ajouter la cellule qui contient l'image
Aspose.Pdf.Cell cell2 = row1.Cells.Add();
// Ajouter l'image à la cellule du tableau
cell2.Paragraphs.Add(img);
row1.Cells.Add("Previous cell with image");
row1.Cells[2].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
// Enregistrez le document
pdfDocument.Save(dataDir + "AddImageInTableCell_out.pdf");
```

## Conclusion

Dans ce didacticiel, nous avons expliqué étape par étape comment ajouter une image à une cellule de tableau à l'aide d'Aspose.PDF pour .NET. Nous avons commencé par configurer le document, créer une page et ajouter un tableau. Ensuite, nous définissons la bordure de cellule et la largeur des colonnes par défaut. Nous avons montré comment ajouter une image à une cellule de tableau et ajuster l'alignement vertical de la cellule. Enfin, nous avons enregistré le document modifié. En suivant ces étapes, vous pouvez améliorer efficacement vos documents PDF avec des images dans les cellules du tableau.

### FAQ

#### Q : Puis-je ajouter plusieurs images à différentes cellules du même tableau à l’aide d’Aspose.PDF pour .NET ?

R : Oui, vous pouvez ajouter plusieurs images à différentes cellules du même tableau à l'aide d'Aspose.PDF pour .NET. Suivez simplement le même processus démontré dans le didacticiel pour chaque image que vous souhaitez ajouter au tableau.

#### Q : Puis-je personnaliser la taille et la position de l’image dans la cellule du tableau ?

 R : Oui, vous pouvez personnaliser la taille et la position de l'image dans la cellule du tableau en ajustant les propriétés du`Image`objet. Vous pouvez définir la largeur et la hauteur de l'image, ainsi que l'alignement dans la cellule.

#### Q : Puis-je ajouter des images à un tableau avec un nombre dynamique de lignes et de colonnes ?

R : Oui, vous pouvez ajouter des images à un tableau avec un nombre dynamique de lignes et de colonnes. Aspose.PDF pour .NET offre une flexibilité dans la création de tableaux de dimensions variables. Vous pouvez ajouter des lignes et des cellules selon vos besoins, puis ajouter des images à des cellules spécifiques en conséquence.

#### Q : Quels formats d'image sont pris en charge par Aspose.PDF pour .NET pour ajouter des images aux cellules d'un tableau ?

R : Aspose.PDF pour .NET prend en charge un large éventail de formats d'image, notamment JPEG, PNG, GIF, BMP et TIFF. Vous pouvez utiliser des images de n’importe lequel de ces formats pour les ajouter aux cellules du tableau.

#### Q : Puis-je ajouter des images aux tableaux d'un document PDF existant ?

R : Oui, vous pouvez ajouter des images aux tableaux d'un document PDF existant à l'aide d'Aspose.PDF pour .NET. Chargez simplement le document existant et suivez les mêmes étapes pour ajouter des images au tableau, comme illustré dans le didacticiel.
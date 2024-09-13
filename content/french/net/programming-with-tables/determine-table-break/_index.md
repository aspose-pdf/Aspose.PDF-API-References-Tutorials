---
title: Déterminer le saut de tableau dans un fichier PDF
linktitle: Déterminer le saut de tableau dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment déterminer les sauts de tableau dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-tables/determine-table-break/
---
Dans ce tutoriel, nous allons apprendre à déterminer les sauts de tableau dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source en C# étape par étape. À la fin de ce tutoriel, vous saurez comment déterminer si un tableau dépasse les marges de la page. Commençons !

## Étape 1 : Configuration de l'environnement
Tout d’abord, assurez-vous d’avoir configuré votre environnement de développement C# avec Aspose.PDF pour .NET. Ajoutez la référence à la bibliothèque et importez les espaces de noms nécessaires.

## Étape 2 : Création du document PDF
 Dans cette étape, nous créons un nouveau`Document` objet pour représenter le document PDF.

```csharp
pdf-Document = new Document();
```

Ce document servira à ajouter des sections et des tableaux.

## Étape 3 : Ajout d'une section et d'un tableau
Nous allons maintenant ajouter une section à notre document PDF et créer un tableau à l'intérieur de cette section.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

Nous spécifions également une marge supérieure de 300 points pour le tableau. Vous pouvez ajuster cette valeur selon vos besoins.

## Étape 4 : Installation de la table
Dans cette étape, nous configurons les propriétés du tableau, telles que la largeur des colonnes et les bordures.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

Ici, nous définissons la largeur des colonnes du tableau et les bordures des cellules. Vous pouvez ajuster ces valeurs selon vos préférences.

## Étape 5 : Ajouter des lignes et des cellules au tableau
Nous allons maintenant créer des lignes et des cellules dans le tableau à l’aide d’une boucle.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

Ici, nous créons 17 lignes dans le tableau et ajoutons trois cellules à chaque ligne. Vous pouvez ajuster la boucle selon vos besoins.

## Étape 6 : Déterminer les sauts de tableau
Nous allons maintenant déterminer si le tableau dépasse les marges de la page en comparant la hauteur de la page avec la hauteur totale des objets du tableau.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

Nous calculons la hauteur de la page et la hauteur totale des objets en tenant compte des marges. Si la différence est de 10 ou moins, le tableau dépasse les marges de la page.

## Étape 7 : Enregistrer le document PDF
Enfin, nous sauvegardons le document PDF avec les résultats.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

Assurez-vous de spécifier le bon répertoire de document. Le fichier PDF résultant sera enregistré avec les sauts de tableau déterminés.

### Exemple de code source pour déterminer le saut de tableau à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier une classe d'objet PDF
Document pdf = new Document();
// Ajoutez la section à la collection de sections du document PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
// Instancier un objet de table
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// Ajoutez le tableau dans la collection de paragraphes de la section souhaitée
page.Paragraphs.Add(table1);
// Définir avec les largeurs de colonnes du tableau
table1.ColumnWidths = "100 100 100";
// Définir la bordure de cellule par défaut à l'aide de l'objet BorderInfo
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// Définir la bordure du tableau à l’aide d’un autre objet BorderInfo personnalisé
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// Créez un objet MarginInfo et définissez ses marges gauche, inférieure, droite et supérieure
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// Définir le remplissage de cellule par défaut sur l'objet MarginInfo
table1.DefaultCellPadding = margin;
// Si vous augmentez le compteur à 17, la table se brisera
// Parce qu'il n'est plus possible de l'héberger sur cette page
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//Créez des lignes dans le tableau, puis des cellules dans les lignes
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// Obtenir les informations sur la hauteur de la page
float PageHeight = (float)pdf.PageInfo.Height;
// Obtenez les informations sur la hauteur totale des marges supérieure et inférieure de la page,
// Marge du plateau et hauteur de la table.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// Afficher la hauteur de la page, la hauteur du tableau, la marge supérieure du tableau et le haut de la page
// Et les informations sur la marge inférieure
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// Vérifiez si nous déduisons la somme de la marge supérieure de la page + la marge inférieure de la page
// + Marge supérieure du tableau et hauteur du tableau à partir de la hauteur de la page et de son moins
// Plus de 10 (une ligne moyenne peut être supérieure à 10)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// Si la valeur est inférieure à 10, affichez le message.
	//Ce qui montre qu'une autre ligne ne peut pas être placée et si nous en ajoutons une nouvelle
	// La ligne et le tableau seront cassés. Cela dépend de la valeur de la hauteur de la ligne.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// Enregistrer le document PDF
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## Conclusion
Dans ce didacticiel, nous avons appris à déterminer les sauts de tableau dans un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce guide étape par étape pour vérifier si un tableau dépasse les marges de page dans vos propres projets C#.

### FAQ pour déterminer le saut de tableau dans un fichier PDF

#### Q : Quel est le but de déterminer les sauts de tableau dans un document PDF ?

R : La détection des sauts de tableau dans un document PDF a pour but de vérifier si le tableau dépasse les marges de la page. Cela permet de garantir que le contenu du tableau s'affiche correctement dans l'espace disponible sur la page. En détectant les sauts de tableau, vous pouvez gérer le débordement du contenu et ajuster la mise en page du tableau en conséquence.

#### Q : Comment puis-je ajuster la marge supérieure du tableau ?

 R : Dans le code source C# fourni, vous pouvez ajuster la marge supérieure du tableau en modifiant la valeur de`table1.Margin.Top`propriété. Augmentez ou diminuez la valeur selon vos besoins pour définir la marge supérieure souhaitée pour le tableau.

#### Q : Puis-je personnaliser l’apparence du tableau, comme les couleurs des cellules et la taille de la police ?

R : Oui, vous pouvez personnaliser l'apparence du tableau et de ses cellules à l'aide de diverses propriétés et méthodes fournies par Aspose.PDF pour .NET. Par exemple, vous pouvez modifier les couleurs d'arrière-plan des cellules, la taille de la police, la famille de polices, l'alignement du texte, etc. Reportez-vous à la documentation officielle pour plus d'informations sur la personnalisation de l'apparence du tableau.

#### Q : Que se passe-t-il si le tableau dépasse les marges de la page ?

R : Si le tableau dépasse les marges de la page, le contenu peut être tronqué ou superposé, ce qui rend le document PDF moins lisible et moins organisé. En détectant les sauts de tableau et en gérant le dépassement, vous pouvez vous assurer que le contenu reste correctement affiché dans la zone de page disponible.

#### Q : Puis-je déterminer des sauts de tableau pour plusieurs tableaux dans le même document PDF ?

: Oui, vous pouvez définir des sauts de tableau pour plusieurs tableaux dans le même document PDF. Répétez simplement les étapes pour chaque tableau que vous souhaitez analyser et ajustez la disposition du tableau si nécessaire pour éviter tout débordement de contenu.
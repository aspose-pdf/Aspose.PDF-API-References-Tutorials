---
title: Ajouter une colonne répétitive dans un document PDF
linktitle: Ajouter une colonne répétitive dans un document PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter des colonnes répétitives à des documents PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape avec exemples et code. Idéal pour les développeurs.
type: docs
weight: 20
url: /fr/net/programming-with-tables/add-repeating-column/
---
## Introduction

Si vous travaillez avec des documents PDF et que vous devez ajouter des colonnes répétitives, vous êtes au bon endroit ! Grâce à Aspose.PDF pour .NET, vous pouvez facilement gérer les tableaux et le contenu d'un PDF. Que vous créiez des rapports dynamiques, des factures ou tout autre document structuré, les colonnes répétitives peuvent changer la donne dans l'organisation des données. Découvrons un guide étape par étape sur la façon d'ajouter des colonnes répétitives à un document PDF.

## Prérequis

Avant de passer au code, assurons-nous que tout est configuré :

- Aspose.PDF pour .NET : vous devez avoir la bibliothèque Aspose.PDF pour .NET installée dans votre projet.
- [Télécharger Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/)
- [Essai gratuit](https://releases.aspose.com/)
- Environnement de développement : assurez-vous d’avoir installé un IDE compatible .NET tel que Visual Studio.
- Compréhension de base de C# : nous allons tout détailler, mais une compréhension de base de C# vous aidera à suivre en douceur.
  
 Si vous n'avez pas encore Aspose.PDF pour .NET, vous pouvez obtenir un[permis temporaire](https://purchase.aspose.com/temporary-license/) pour commencer à explorer ses fonctionnalités.

## Paquets d'importation

Pour commencer, vous devez importer les espaces de noms nécessaires depuis Aspose.PDF pour .NET. Voici comment procéder :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ces packages fournissent les classes et méthodes essentielles nécessaires pour travailler avec des documents PDF et manipuler des tableaux.

Décomposons maintenant le processus en plusieurs étapes pour ajouter des colonnes répétitives à un document PDF. Suivez-moi !

## Étape 1 : définissez le chemin d’accès à votre répertoire de documents

Avant de créer ou de manipuler des fichiers, nous devons définir le chemin où le PDF généré sera enregistré. Dans votre projet C#, définissez le chemin du répertoire où seront situés vos fichiers :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

 Ce chemin pointe vers le répertoire où le PDF de sortie sera enregistré. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel sur votre machine.

## Étape 2 : Créer un nouveau document PDF

 Pour commencer, instanciez un nouveau`Document` objet. Il servira de conteneur pour toutes les pages et le contenu du PDF.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

 Ici, nous avons créé un nouveau document PDF et y avons ajouté une page vierge.`doc.Pages.Add()` la méthode insère une nouvelle page dans le document.

## Étape 3 : instancier la table externe

Ensuite, nous créons un tableau externe. Ce tableau s'étendra sur toute la largeur de la page et servira de conteneur pour d'autres tableaux, y compris celui qui contiendra les colonnes répétitives.

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

 Nous avons mis en place le`ColumnWidths` propriété à « 100 % », ce qui signifie que le tableau s'étendra sur toute la largeur de la page.

## Étape 4 : Créer la table interne

 Créons maintenant la table interne, qui comportera des colonnes répétitives. Les propriétés clés ici sont`Broken` , ce qui permet au tableau de continuer sur la même page, et`ColumnAdjustment`, qui ajuste automatiquement la largeur des colonnes pour s'adapter au contenu.

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

Cette table intérieure sera imbriquée dans la table extérieure.

## Étape 5 : Ajouter des tableaux à la page

Maintenant que les tableaux externes et internes sont prêts, ajoutons-les à la page. Cette étape garantit que les tableaux sont inclus dans la structure du document.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

 Ici, nous avons ajouté le`outerTable` à la page, puis dans la table externe, nous avons imbriqué le`mytable` . De plus, nous avons mis en place`RepeatingColumnsCount`à 5, spécifiant le nombre de colonnes à répéter lorsque des données sont ajoutées.

## Étape 6 : Ajouter une ligne d’en-tête

Il est maintenant temps d'ajouter les en-têtes au tableau. La ligne d'en-tête donne un contexte aux données et aide à structurer les colonnes. 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

Cet extrait de code ajoute la première ligne (que nous utiliserons comme en-têtes) et la remplit avec des cellules contenant du texte comme « en-tête 1 », « en-tête 2 », etc.

## Étape 7 : Ajouter des lignes de données

Enfin, nous pouvons ajouter des données au tableau. Cette boucle crée dynamiquement des lignes et remplit les cellules avec du contenu :

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

La boucle s'exécute six fois, ajoutant des lignes et remplissant chaque cellule avec les données de colonne correspondantes (par exemple, « col 1, 1 », « col 2, 2 », etc.).

## Étape 8 : Enregistrer le document

Une fois toutes les lignes et colonnes ajoutées, la dernière étape consiste à enregistrer le document dans le chemin de fichier spécifié.

```csharp
doc.Save(outFile);
```

Votre document est maintenant enregistré avec des colonnes répétitives !

## Conclusion

Et voilà ! Avec ces quelques étapes simples, vous pouvez créer un document PDF avec des colonnes répétitives à l'aide d'Aspose.PDF pour .NET. En tirant parti de la flexibilité des tableaux imbriqués, vous pouvez obtenir des mises en page complexes qui donnent à vos PDF un aspect professionnel et organisé. Essayez ceci pour votre prochain projet et explorez tout le potentiel d'Aspose.PDF pour répondre à vos besoins de génération de PDF.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, modifier et gérer des documents PDF par programmation.

### Puis-je ajuster le nombre de colonnes répétitives de manière dynamique ?
 Oui, vous pouvez modifier le nombre de colonnes répétitives en modifiant le`RepeatingColumnsCount` propriété.

### Comment puis-je appliquer une licence à Aspose.PDF pour .NET ?
 Vous pouvez appliquer une licence à partir d'un fichier ou d'un flux en suivant les[documentation](https://reference.aspose.com/pdf/net/).

### Est-il possible d'ajouter des images aux cellules du tableau ?
Oui, Aspose.PDF pour .NET prend en charge l’ajout de différents types de contenu, y compris des images, aux cellules du tableau.

### Puis-je personnaliser davantage la disposition du tableau ?
Absolument ! Aspose.PDF fournit de nombreuses fonctionnalités pour personnaliser les styles de tableau, notamment les bordures, le remplissage, l'alignement, etc.
---
title: Utiliser un script latex
linktitle: Utiliser un script latex
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser le script Latex pour ajouter des expressions mathématiques ou des formules dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 550
url: /fr/net/programming-with-text/use-latex-script/
---

Ce didacticiel explique comment utiliser le script Latex pour ajouter des expressions mathématiques ou des formules dans un document PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni montre les étapes pour créer un document, ajouter un tableau avec une cellule contenant le script LaTeX et enregistrer le document.

## Conditions préalables

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée. Vous pouvez l'obtenir sur le site Web d'Aspose ou utiliser NuGet pour l'installer dans votre projet.

## Étape 1 : Configurer le projet

Créez un nouveau projet C# dans votre environnement de développement intégré (IDE) préféré et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms nécessaires

Ajoutez les directives using suivantes au début de votre fichier C# pour importer les espaces de noms requis :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Tables;
using Aspose.Pdf.Text;
```

## Étape 3 : Créer et configurer le document

 Créer un nouveau`Document` objet et ajoutez-y une page :

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Étape 4 : Créer et configurer la table

Créez un tableau et ajoutez-y une ligne :

```csharp
Table table = new Table();
Row row = table.Rows.Add();
```

## Étape 5 : Ajouter une cellule avec le script LaTeX

 Créez une cellule et ajoutez un`LatexFragment` contenant le script Latex :

```csharp
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
```

 Notez que le`true` paramètre dans le`LatexFragment` Le constructeur élimine les retraits de paragraphe Latex.

## Étape 6 : Ajouter le tableau à la page

Ajoutez le tableau à la page :

```csharp
page.Paragraphs.Add(table);
```

## Étape 7 : Enregistrez le document

Enregistrez le document dans un fichier PDF :

```csharp
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

### Exemple de code source pour Utiliser le script Latex avec Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un nouvel objet document
Document doc = new Document();
//Ajouter une page dans la collection de pages
Page page = doc.Pages.Add();
// Créer un tableau
Table table = new Table();
// Ajouter une ligne dans le tableau
Row row = table.Rows.Add();
// Ajouter une cellule avec un script Latex pour ajouter des expressions/formules mathématiques
string latexText1 = "$123456789+\\sqrt{1}+\\int_a^b f(x)dx$";
Cell cell = row.Cells.Add();
cell.Margin = new MarginInfo { Left = 20, Right = 20, Top = 20, Bottom = 20 };
// Le deuxième paramètre booléen du constructeur LatexFragment fournit l'élimination des retraits de paragraphe LaTeX.
LatexFragment ltext1 = new LatexFragment(latexText1, true);
cell.Paragraphs.Add(ltext1);
// Ajouter un tableau à l'intérieur de la page
page.Paragraphs.Add(table);
// Enregistrer le document
doc.Save(dataDir + "LatextScriptInPdf_out.pdf");
```

## Conclusion

Toutes nos félicitations! Vous avez appris avec succès à utiliser le script Latex pour ajouter des expressions mathématiques ou des formules dans un document PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel fournit des instructions détaillées sur la création d'un document, l'ajout d'un tableau avec une cellule contenant un script LaTeX et l'enregistrement du document. Vous pouvez maintenant incorporer ce code dans vos propres projets C# pour générer des fichiers PDF avec un contenu mathématique.
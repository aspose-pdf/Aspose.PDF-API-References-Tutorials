---
title: Ligne de dessin
linktitle: Ligne de dessin
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à tracer une ligne sur une page en utilisant Aspose.PDF pour .NET. Guide étape par étape pour créer des lignes personnalisées.
type: docs
weight: 80
url: /fr/net/programming-with-graphs/drawing-line/
---

Dans ce didacticiel, nous vous guiderons pas à pas dans le code source C # suivant pour tracer une ligne à l'aide de Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

## Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création d'une instance de document et ajout d'une page

Nous créons une instance de la classe Document et ajoutons une page à ce document.

```csharp
Document pDoc = new Document();
Page pg = pDoc.Pages.Add();
```

## Étape 3 : Définition des marges de page

Nous définissons les marges de la page sur 0 de tous les côtés.

```csharp
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
```

## Étape 4 : Création d'un objet graphique et de la première ligne

Nous créons un objet Graph avec des dimensions égales à celles de la page et dessinons la première ligne allant du coin inférieur gauche au coin supérieur droit de la page.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width, (float)pg.PageInfo.Height);
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect. URY });
graph.Shapes.Add(line);
```

## Étape 5 : Dessiner la deuxième ligne

Nous traçons la deuxième ligne allant du coin supérieur gauche au coin inférieur droit de la page.

```csharp
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect. LLX });
graph.Shapes.Add(line2);
```

## Étape 6 : Ajout de l'objet graphique à la page

Nous ajoutons l'objet Graph à la collection de paragraphes de la page.

```csharp
pg.Paragraphs.Add(graph);
```

## Étape 7 : Enregistrer le fichier PDF résultant

Enfin, nous enregistrons le fichier PDF résultant sous le nom "DrawingLine_out.pdf" dans le répertoire spécifié.

```csharp
pDoc.Save(dataDir + "DrawingLine_out.pdf");
```

### Exemple de code source pour Drawing Line à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer une instance de document
Document pDoc = new Document();
// Ajouter une page à la collection de pages du document PDF
Page pg = pDoc.Pages.Add();
// Définir la marge de la page sur tous les côtés à 0
pg.PageInfo.Margin.Left = pg.PageInfo.Margin.Right = pg.PageInfo.Margin.Bottom = pg.PageInfo.Margin.Top = 0;
//Créer un objet graphique avec une largeur et une hauteur égales aux dimensions de la page
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph((float)pg.PageInfo.Width , (float)pg.PageInfo.Height);
// Créer un objet de première ligne en partant du coin inférieur gauche vers le coin supérieur droit de la page
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { (float)pg.Rect.LLX, 0, (float)pg.PageInfo.Width, (float)pg.Rect.URY });
// Ajouter une ligne à la collection de formes de l'objet Graph
graph.Shapes.Add(line);
// Tracez une ligne du coin supérieur gauche de la page au coin inférieur droit de la page
Aspose.Pdf.Drawing.Line line2 = new Aspose.Pdf.Drawing.Line(new float[] { 0, (float)pg.Rect.URY, (float)pg.PageInfo.Width, (float)pg.Rect.LLX });
// Ajouter une ligne à la collection de formes de l'objet Graph
graph.Shapes.Add(line2);
// Ajouter un objet Graph à la collection de paragraphes de la page
pg.Paragraphs.Add(graph);
dataDir = dataDir + "DrawingLine_out.pdf";
// Enregistrer le fichier PDF
pDoc.Save(dataDir);
Console.WriteLine("\nLine drawn successfully across the page.\nFile saved at " + dataDir);            

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment tracer une ligne à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour créer des formes géométriques avec des lignes personnalisées dans vos fichiers PDF.

---
title: Créer un rectangle rempli
linktitle: Créer un rectangle rempli
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à créer un rectangle plein avec Aspose.PDF pour .NET. Guide étape par étape pour personnaliser la couleur de remplissage.
type: docs
weight: 50
url: /fr/net/programming-with-graphs/create-filled-rectangle/
---
Dans ce didacticiel, nous vous guiderons pas à pas à travers le code source C # suivant pour créer un rectangle rempli à l'aide de Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

## Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création d'une instance de document et ajout d'une page

Nous créons une instance de la classe Document et ajoutons une page à ce document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Étape 3 : Créer un objet graphique et l'ajouter à la page

Nous créons un objet Graph avec des dimensions spécifiées et l'ajoutons à la collection de paragraphes de la page.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Étape 4 : créer un objet rectangle et l'ajouter au graphique

Nous créons un objet Rectangle avec les dimensions spécifiées et l'ajoutons à la collection de formes du graphique.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Étape 5 : Définition de la couleur de remplissage

Nous pouvons spécifier la couleur de remplissage du rectangle à l'aide de la propriété FillColor de l'objet GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Étape 6 : Enregistrer le fichier PDF résultant

Enfin, nous enregistrons le fichier PDF résultant sous le nom "CreateFilledRectangle_out.pdf" dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Exemple de code source pour créer un rectangle rempli à l'aide de Aspose.Words pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer une instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
Page page = doc.Pages.Add();
// Créer une instance de graphique
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Ajouter un objet graphique à la collection de paragraphes de l'instance de page
page.Paragraphs.Add(graph);
// Créer une instance Rectangle
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
// Spécifier la couleur de remplissage pour l'objet graphique
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
// Ajouter un objet rectangle à la collection de formes de l'objet Graph
graph.Shapes.Add(rect);
dataDir = dataDir + "CreateFilledRectangle_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);
Console.WriteLine("\nFilled rectangle object created successfully.\nFile saved at " + dataDir);            

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment créer un rectangle rempli à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour créer des formes géométriques avec des couleurs de remplissage personnalisées dans vos fichiers PDF.

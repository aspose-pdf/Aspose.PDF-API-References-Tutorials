---
title: Longueur du tiret
linktitle: Longueur du tiret
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir la longueur des tirets avec Aspose.PDF pour .NET. Guide étape par étape pour personnaliser les modèles de tirets.
type: docs
weight: 70
url: /fr/net/programming-with-graphs/dash-length/
---
Dans ce didacticiel, nous vous guiderons pas à pas dans le code source C # suivant pour définir la longueur des tirets à l'aide de Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

## Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : instanciation d'un objet document et ajout d'une page

Nous créons une instance de la classe Document et ajoutons une page à ce document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Étape 3 : Créer un objet graphique et l'ajouter à la page

Nous créons un objet Graph avec des dimensions spécifiées et l'ajoutons à la collection de paragraphes de la page.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Étape 4 : Création d'un objet de ligne et configuration

Nous créons un objet Line avec les coordonnées spécifiées et configurons la couleur et la longueur des tirets.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Étape 5 : Ajout de la ligne à l'objet graphique

Nous ajoutons la ligne à la collection de formes de l'objet Graph.

```csharp
canvas.Shapes.Add(line);
```

## Étape 6 : Enregistrer le fichier PDF résultant

Enfin, nous enregistrons le fichier PDF résultant sous le nom "DashLength_out.pdf" dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Exemple de code source pour Dash Length en utilisant Aspose.Words pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages de l'objet Document
Page page = doc.Pages.Add();
// Créer un objet de dessin avec certaines dimensions
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Ajouter un objet de dessin à la collection de paragraphes de l'instance de page
page.Paragraphs.Add(canvas);
// Créer un objet Ligne
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Définir la couleur de l'objet Ligne
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Spécifiez le tableau de tirets pour l'objet de ligne
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Définir la phase du tiret pour l'instance de ligne
line.GraphInfo.DashPhase = 1;
// Ajouter une ligne à la collection de formes de l'objet dessin
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment définir la longueur des tirets à l'aide de Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour créer des lignes avec des motifs de tirets personnalisés dans vos fichiers PDF.

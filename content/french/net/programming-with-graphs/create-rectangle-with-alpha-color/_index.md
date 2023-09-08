---
title: Créer un rectangle avec la couleur alpha
linktitle: Créer un rectangle avec la couleur alpha
second_title: Aspose.PDF pour la référence de l'API .NET
description: Apprenez à créer un rectangle de couleur transparente à l'aide d'Aspose.PDF pour .NET. Guide étape par étape pour personnaliser la transparence.
type: docs
weight: 60
url: /fr/net/programming-with-graphs/create-rectangle-with-alpha-color/
---
Dans ce didacticiel, nous vous guiderons pas à pas à travers le code source C# suivant pour créer un rectangle avec une couleur alpha à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Posséder également des connaissances de base en programmation C#.

## Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : instanciation d'un objet de document et ajout d'une page

Nous créons une instance de la classe Document et ajoutons une page à ce document.

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Étape 3 : Création d'un objet graphique et d'un rectangle

Nous créons un objet Graph avec des dimensions spécifiées et un rectangle avec des dimensions spécifiques.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
```

## Étape 4 : Configuration de la couleur alpha du rectangle

Nous pouvons spécifier une couleur alpha pour le rectangle en utilisant la méthode FromArgb de la classe System.Drawing.Color.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
```

## Étape 5 : Ajout du rectangle à l'objet graphique

Nous ajoutons le rectangle à la collection de formes de l'objet Graph.

```csharp
canvas.Shapes.Add(rect);
```

## Étape 6 : Création d'un deuxième rectangle avec une couleur alpha différente

Nous créons un deuxième rectangle avec des dimensions spécifiques et une autre couleur alpha.

```csharp
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
```

## Étape 7 : ajout de l'objet graphique à la page

Nous ajoutons l’objet Graph à la collection Paragraph de l’objet Page.

```csharp
page.Paragraphs.Add(canvas);
```

## Étape 8 : Enregistrement du fichier PDF résultant

Enfin, nous enregistrons le fichier PDF résultant sous le nom "CreateRectangleWithAlphaColor_out.pdf" dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");
```

### Exemple de code source pour créer un rectangle avec une couleur alpha à l'aide d'Aspose.PDF pour .NET 

```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier une instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Créer une instance de graphique
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Créer un objet rectangle avec des dimensions spécifiques
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 100);
//Définir la couleur de remplissage du graphique à partir de la structure System.Drawing.Color à partir d'une valeur ARGB 32 bits
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Ajouter un objet rectangle à la collection de formes de l'instance Graph
canvas.Shapes.Add(rect);
// Créer un deuxième objet rectangle
Aspose.Pdf.Drawing.Rectangle rect1 = new Aspose.Pdf.Drawing.Rectangle(200, 150, 200, 100);
rect1.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(16118015)));
canvas.Shapes.Add(rect1);
// Ajouter une instance de graphique à la collection de paragraphes de l'objet de page
page.Paragraphs.Add(canvas);
dataDir = dataDir + "CreateRectangleWithAlphaColor_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);
Console.WriteLine("\nRectangle object created successfully with alpha color.\nFile saved at " + dataDir);            

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment créer un rectangle avec une couleur alpha à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour créer des formes géométriques aux couleurs transparentes dans vos fichiers PDF.

## FAQ

#### Q : Quel est le but de ce tutoriel ?

R : Ce didacticiel vise à vous guider tout au long du processus de création d'un rectangle avec une couleur alpha à l'aide d'Aspose.PDF pour .NET. Vous apprendrez à ajouter des formes géométriques avec des couleurs transparentes à vos fichiers PDF.

#### Q : Quels sont les prérequis requis avant de commencer ?

R : Avant de commencer, assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement. De plus, il est recommandé d’avoir une compréhension de base de la programmation C#.

#### Q : Comment puis-je spécifier le répertoire d'enregistrement du fichier PDF ?

R : Dans le code source fourni, vous pouvez modifier la variable « dataDir » pour indiquer le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant.

#### Q : Quel est le but de l’objet Graph et du Rectangle ?

R : L'objet Graph agit comme un conteneur pour les éléments de dessin, tandis que le Rectangle représente la forme géométrique que vous allez ajouter au PDF.

#### Q : Comment puis-je définir une couleur alpha pour le rectangle ?

R : Vous pouvez spécifier une couleur alpha pour le rectangle à l'aide du`FillColor` propriété du`GraphInfo` l'objet et le`Color.FromRgb` méthode avec une valeur ARGB.

#### Q : Puis-je créer plusieurs rectangles avec différentes couleurs alpha ?

R : Oui, vous pouvez créer plusieurs rectangles avec différentes couleurs alpha en suivant les étapes similaires à celles illustrées dans le didacticiel.

#### Q : Comment puis-je enregistrer le fichier PDF obtenu après avoir créé des rectangles avec des couleurs alpha ?

 R : Après avoir créé les rectangles avec les couleurs alpha, vous pouvez enregistrer le fichier PDF résultant à l'aide du`doc.Save(dataDir + "CreateRectangleWithAlphaColor_out.pdf");` ligne dans le code source fourni.
---
title: Ajouter un dessin
linktitle: Ajouter un dessin
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter des dessins à l'aide d'Aspose.PDF pour .NET. Suivez ce guide étape par étape pour créer des documents PDF attrayants avec des fonctionnalités de dessin.
type: docs
weight: 10
url: /fr/net/programming-with-graphs/add-drawing/
---

Le développement d'applications nécessite souvent l'ajout de fonctionnalités telles que des dessins et des graphiques pour rendre les documents plus attrayants et informatifs. Dans cet article, nous vous guiderons étape par étape pour expliquer le code source C # pour ajouter le dessin à la programmation avec des graphiques à l'aide d'Aspose.PDF pour .NET.

Avant de commencer, assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement. Assurez-vous également d'avoir des connaissances de base en programmation C#.

## Étape 1 : Introduction à Aspose.PDF pour .NET et ses fonctionnalités

Aspose.PDF est une bibliothèque puissante et polyvalente pour créer, manipuler et convertir des fichiers PDF dans des applications .NET. Il offre un large éventail de fonctionnalités pour travailler avec des documents PDF, y compris l'ajout de dessins, de graphiques, de texte, etc.

## Étape 2 : Comprendre le code source pour ajouter des dessins à l'aide d'Aspose.PDF

Le code source fourni utilise la bibliothèque Aspose.PDF pour créer un dessin simple dans un document PDF. Nous allons maintenant examiner chaque étape du code en détail.

## Etape 3 : Configuration du répertoire des documents et initialisation des variables

Dans le code source, vous devez spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant. Vous pouvez modifier la variable "dataDir" pour indiquer le répertoire souhaité.

De plus, le code initialise les variables pour les composants de couleur alpha, rouge, vert et bleu.

## Étape 4 : Création d'un objet couleur avec Alpha RVB

La ligne de code suivante crée un objet Color à l'aide des valeurs alpha, rouge, vert et bleu spécifiées :

```csharp
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue);
```

Cela permet de définir une couleur avec un canal alpha, ce qui signifie que la couleur peut être partiellement transparente.

## Étape 5 : instanciation d'un objet document

Pour commencer à travailler avec Aspose.PDF, nous devons créer une instance de la classe Document. Ceci représente notre document PDF.

```csharp
Document document = new Document();
```

## Étape 6 : Ajouter une page au fichier PDF

Nous devons ajouter une page au fichier PDF où nous voulons afficher notre dessin.

```csharp
Page page = document.Pages.Add();
```

## Étape 7 : Création d'un objet graphique avec des dimensions

Dans cette étape, nous créons un objet Graph avec des dimensions spécifiées. Cet objet servira de contenant pour notre dessin.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
```

## Étape 8 : Définition de la bordure de l'objet Dessin

Nous pouvons définir la bordure de l'objet Drawing à l'aide de la classe BorderInfo.

```csharp
graph.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black);
```

Cela définira une bordure noire autour de notre dessin.

## Étape 9 : Ajout de l'objet graphique à la page

Nous ajoutons maintenant l'objet graph à la collection de paragraphes de l'instance de la classe Page.

```csharp
page.Paragraphs.Add(graph);
```

## Étape 10 : création d'un objet rectangle avec des dimensions

Nous créons un objet Rectangle avec des dimensions spécifiées. Ce rectangle sera ajouté à notre dessin.

```csharp
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
```

## Étape 11 : Création d'un objet GraphInfo pour l'instance Rectangle

Nous devons créer un objet GraphInfo pour l'instance Rectangle afin de configurer ses propriétés de graphique.

```csharp
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
```

## Étape 12 : configuration des informations de couleur pour l'objet GraphInfo

Nous pouvons configurer les informations de couleur pour l'objet GraphInfo à l'aide des propriétés Color et FillColor.

```csharp
graphInfo.Color = Aspose.Pdf.Color.Red;
graphInfo. FillColor = alphaColor;
```

Cela définira la couleur de la bordure du rectangle sur le rouge et la couleur de remplissage sur la couleur alpha spécifiée.

## Étape 13 : Ajout de la forme rectangulaire à l'objet graphique

Nous ajoutons maintenant la forme rectangulaire à la collection de formes de l'objet graphique.

```csharp
graph.Shapes.Add(rectangle);
```
## Étape 14 : Enregistrer le fichier PDF et afficher le message de réussite

Enfin, nous enregistrons le fichier PDF et affichons un message indiquant que le dessin a été ajouté avec succès.

```csharp
dataDir = dataDir + "AddDrawing_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nSuccessfully added drawing with transparent color.\nFile saved to location: " + dataDir);
```

### Exemple de code source pour Ajouter un dessin à l'aide d'Aspose.Words pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
// Créer un objet couleur à l'aide d'Alpha RVB
Aspose.Pdf.Color alphaColor = Aspose.Pdf.Color.FromArgb(alpha, red, green, blue); // Fournir un canal alpha
// Instancier l'objet Document
Document document = new Document();
// Ajouter une page à la collection de pages du fichier PDF
Page page = document.Pages.Add();
// Créer un objet graphique avec certaines dimensions
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(300, 400);
// Définir la bordure de l'objet Dessin
graph.Border = (new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Black));
// Ajouter un objet graphique à la collection de paragraphes de l'instance de page
page.Paragraphs.Add(graph);
// Créer un objet Rectangle avec certaines dimensions
Aspose.Pdf.Drawing.Rectangle rectangle = new Aspose.Pdf.Drawing.Rectangle(0, 0, 100, 50);
// Créer un objet graphInfo pour l'instance Rectangle
Aspose.Pdf.GraphInfo graphInfo = rectangle.GraphInfo;
// Définir les informations de couleur pour l'instance GraphInfo
graphInfo.Color = (Aspose.Pdf.Color.Red);
// Définir la couleur de remplissage pour GraphInfo
graphInfo.FillColor = (alphaColor);
// Ajouter une forme de rectangle à la collection de formes de l'objet graphique
graph.Shapes.Add(rectangle);
dataDir = dataDir + "AddDrawing_out.pdf";
// Enregistrer le fichier PDF
document.Save(dataDir);
Console.WriteLine("\nDrawing added successfully with transparent color.\nFile saved at " + dataDir);            

```

## Conclusion

Dans cet article, nous avons appris à ajouter du dessin à la programmation avec des graphiques à l'aide d'Aspose.PDF pour .NET. Nous avons suivi un guide étape par étape pour comprendre le code source et les différentes étapes impliquées dans l'ajout d'un dessin à un fichier PDF. En utilisant les fonctionnalités puissantes d'Aspose.PDF, vous pouvez créer des documents PDF attrayants et interactifs dans vos applications .NET.
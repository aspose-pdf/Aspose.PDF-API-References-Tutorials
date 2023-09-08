---
title: Ajouter un objet ligne dans un fichier PDF
linktitle: Ajouter un objet ligne dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter un objet ligne personnalisé dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-graphs/add-line-object/
---
Dans ce didacticiel, nous vous guiderons pas à pas à travers le code source C# suivant pour ajouter un objet ligne à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Posséder également des connaissances de base en programmation C#.

## Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : création d'une instance de document et ajout d'une page

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

## Étape 4 : Créer un objet linéaire et l'ajouter au graphique

Nous créons un objet Line avec les coordonnées spécifiées et l'ajoutons à la collection de formes du graphique.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
graph.Shapes.Add(line);
```

## Étape 5 : Configuration de la ligne

Nous pouvons spécifier des propriétés pour la ligne, telles que le type de tiret et la phase du tiret.

```csharp
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Étape 6 : Enregistrement du fichier PDF

Enfin, nous enregistrons le fichier PDF résultant sous le nom "AddLineObject_out.pdf" dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "AddLineObject_out.pdf");
```

### Exemple de code source pour Ajouter un objet de ligne à l'aide d'Aspose.PDF pour .NET 

```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer une instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
Page page = doc.Pages.Add();
// Créer une instance de graphique
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
// Ajouter un objet graphique à la collection de paragraphes de l'instance de page
page.Paragraphs.Add(graph);
// Créer une instance de rectangle
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Spécifier la couleur de remplissage pour l'objet graphique
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
// Ajouter un objet rectangle à la collection de formes de l'objet Graph
graph.Shapes.Add(line);
dataDir = dataDir + "AddLineObject_out.pdf";
// Enregistrer le fichier PDF
doc.Save(dataDir);
Console.WriteLine("\nLine object added successfully to pdf.\nFile saved at " + dataDir);            

```

## Conclusion

Dans ce didacticiel, nous avons expliqué étape par étape comment ajouter un objet ligne à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour créer des documents PDF avec des lignes personnalisées dans vos applications.

### FAQ pour ajouter un objet ligne dans un fichier PDF

#### Q : Quel est le but de ce tutoriel ?

R : Ce didacticiel vise à vous guider tout au long du processus d'ajout d'un objet ligne à l'aide d'Aspose.PDF for .NET afin d'améliorer vos documents PDF.

#### Q : Quels sont les prérequis requis avant de commencer ?

R : Avant de commencer, assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement. De plus, il est recommandé d’avoir une compréhension de base de la programmation C#.

#### Q : Comment puis-je spécifier le répertoire d'enregistrement du fichier PDF ?

R : Dans le code source fourni, vous pouvez modifier la variable « dataDir » pour indiquer le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant.

#### Q : Quel est le but de l’objet Graph ?

R : L'objet Graph sert de conteneur pour les éléments de dessin. Il est créé avec des dimensions spécifiées et ajouté à la collection de paragraphes de la page.

#### Q : Comment puis-je ajouter un objet ligne au document PDF ?

R : Pour ajouter un objet ligne, créez une instance de la classe Line avec les coordonnées spécifiées et ajoutez-la à la collection de formes du graphique.

#### Q : Puis-je personnaliser l’apparence de la ligne ?

: Oui, vous pouvez personnaliser l'apparence de la ligne en définissant des propriétés telles que le type de tiret et la phase du tiret à l'aide de la propriété GraphInfo de l'objet Line.

#### Q : A quoi sert de spécifier le tableau de bord et la phase du tableau de bord ?

R : Les propriétés de tableau de tirets et de phase de tiret vous permettent de créer des lignes pointillées ou pointillées avec des motifs spécifiques.

#### Q : Comment puis-je enregistrer le fichier PDF après avoir ajouté l'objet ligne ?

 R : Après avoir ajouté l'objet ligne, vous pouvez enregistrer le fichier PDF résultant à l'aide du`doc.Save(dataDir + "AddLineObject_out.pdf");` ligne dans le code source fourni.

#### Q : Existe-t-il un exemple de code source disponible ?

R : Oui, le didacticiel comprend un exemple de code source auquel vous pouvez vous référer pour mettre en œuvre les étapes décrites.
---
title: Créer un rectangle rempli
linktitle: Créer un rectangle rempli
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment créer un rectangle rempli avec Aspose.PDF pour .NET. Guide étape par étape pour personnaliser la couleur de remplissage.
type: docs
weight: 50
url: /fr/net/programming-with-graphs/create-filled-rectangle/
---
Dans ce didacticiel, nous vous guiderons pas à pas à travers le code source C# suivant pour créer un rectangle rempli à l'aide d'Aspose.PDF pour .NET.

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

## Étape 3 : création d'un objet graphique et ajout de celui-ci à la page

Nous créons un objet Graph avec des dimensions spécifiées et l'ajoutons à la collection de paragraphes de la page.

```csharp
Aspose.Pdf.Drawing.Graph graph = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(graph);
```

## Étape 4 : créer un objet rectangle et l'ajouter au graphique

Nous créons un objet Rectangle avec les dimensions spécifiées et l'ajoutons à la collection de formes du graphique.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 200, 120);
graph.Shapes.Add(rect);
```

## Étape 5 : Définition de la couleur de remplissage

Nous pouvons spécifier la couleur de remplissage du rectangle en utilisant la propriété FillColor de l'objet GraphInfo.

```csharp
rect.GraphInfo.FillColor = Aspose.Pdf.Color.Red;
```

## Étape 6 : Enregistrement du fichier PDF résultant

Enfin, nous enregistrons le fichier PDF résultant sous le nom "CreateFilledRectangle_out.pdf" dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "CreateFilledRectangle_out.pdf");
```

### Exemple de code source pour créer un rectangle rempli à l'aide d'Aspose.PDF pour .NET 

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

## FAQ

#### Q : Quel est le but de ce tutoriel ?

R : Le but de ce didacticiel est de vous guider tout au long du processus de création d'un rectangle rempli à l'aide d'Aspose.PDF pour .NET, vous permettant d'ajouter des formes géométriques personnalisées avec des couleurs de remplissage à vos fichiers PDF.

#### Q : Quels sont les prérequis requis avant de commencer ?

R : Avant de commencer, assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement. De plus, il est recommandé d’avoir une compréhension de base de la programmation C#.

#### Q : Comment puis-je spécifier le répertoire d'enregistrement du fichier PDF ?

R : Dans le code source fourni, vous pouvez modifier la variable « dataDir » pour indiquer le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant.

#### Q : Quel est le but de l’objet Graph ?

R : L'objet Graph agit comme un conteneur pour les éléments de dessin. Il est créé avec des dimensions spécifiées et ajouté à la collection de paragraphes de la page.

#### Q : Comment puis-je ajouter un rectangle rempli au document PDF ?

R : Pour ajouter un rectangle rempli, créez une instance de la classe Rectangle avec les dimensions et la couleur de remplissage spécifiées, puis ajoutez-la à la collection de formes du graphique.

#### Q : Puis-je personnaliser les dimensions et la couleur de remplissage du rectangle ?

 R : Oui, vous pouvez personnaliser les dimensions et la couleur de remplissage du rectangle en modifiant les paramètres passés au`Aspose.Pdf.Drawing.Rectangle` constructeur et définition de la propriété FillColor.

#### Q : Comment puis-je enregistrer le fichier PDF résultant après avoir créé le rectangle rempli ?

 R : Après avoir créé le rectangle rempli, vous pouvez enregistrer le fichier PDF résultant à l'aide du`doc.Save(dataDir + "CreateFilledRectangle_out.pdf");` ligne dans le code source fourni.
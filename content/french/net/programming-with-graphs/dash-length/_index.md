---
title: Longueur du tiret
linktitle: Longueur du tiret
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment définir la longueur des tirets avec Aspose.PDF pour .NET. Guide étape par étape pour personnaliser les modèles de tirets.
type: docs
weight: 70
url: /fr/net/programming-with-graphs/dash-length/
---
Dans ce didacticiel, nous vous guiderons étape par étape à travers le code source C# suivant pour définir la longueur des tirets à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Ayez également des connaissances de base en programmation C#.

## Étape 1 : Configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant. Modifiez la variable « dataDir » dans le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Instanciation d'un objet de document et ajout d'une page

Nous créons une instance de la classe Document et ajoutons une page à ce document.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## Étape 3 : Créer un objet graphique et l'ajouter à la page

Nous créons un objet Graph avec des dimensions spécifiées et l'ajoutons à la collection de paragraphes de la page.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
page.Paragraphs.Add(canvas);
```

## Étape 4 : Création d'un objet de ligne et configuration

Nous créons un objet Ligne avec les coordonnées spécifiées et configurons la couleur et la longueur des tirets.

```csharp
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
line.GraphInfo.DashPhase = 1;
```

## Étape 5 : Ajout de la ligne à l'objet graphique

Nous ajoutons la ligne à la collection de formes de l'objet Graph.

```csharp
canvas.Shapes.Add(line);
```

## Étape 6 : enregistrement du fichier PDF obtenu

Enfin, nous enregistrons le fichier PDF résultant avec le nom « DashLength_out.pdf » dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "DashLength_out.pdf");
```

### Exemple de code source pour Dash Length à l'aide d'Aspose.PDF pour .NET 

```csharp

// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages de l'objet Document
Page page = doc.Pages.Add();
// Créer un objet de dessin avec certaines dimensions
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Ajouter un objet de dessin à la collection de paragraphes de l'instance de page
page.Paragraphs.Add(canvas);
// Créer un objet de ligne
Aspose.Pdf.Drawing.Line line = new Aspose.Pdf.Drawing.Line(new float[] { 100, 100, 200, 100 });
// Définir la couleur de l'objet Ligne
line.GraphInfo.Color = Aspose.Pdf.Color.Red;
// Spécifier un tableau de tirets pour l'objet ligne
line.GraphInfo.DashArray = new int[] { 0, 1, 0 };
// Définir la phase de tiret pour l'instance de ligne
line.GraphInfo.DashPhase = 1;
// Ajouter une ligne à la collection de formes de l'objet de dessin
canvas.Shapes.Add(line);
dataDir = dataDir + "DashLength_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);
Console.WriteLine("\nLength dashed successfully in black and white.\nFile saved at " + dataDir);            

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment définir la longueur des tirets à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour créer des lignes avec des motifs de tirets personnalisés dans vos fichiers PDF.

## FAQ

#### Q : Quel est le but de ce tutoriel ?

R : L'objectif de ce didacticiel est de vous guider dans le processus de définition de la longueur des tirets des lignes à l'aide d'Aspose.PDF pour .NET. Vous apprendrez à créer des lignes avec des motifs de tirets personnalisés dans vos fichiers PDF.

#### Q : Quels sont les prérequis nécessaires avant de commencer ?

R : Avant de commencer, assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement. Une connaissance de base de la programmation C# est également recommandée.

#### Q : Comment spécifier le répertoire dans lequel enregistrer le fichier PDF ?

A : Modifiez la variable « dataDir » dans le code source fourni pour indiquer le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant.

#### Q : Comment créer une ligne avec des motifs de tirets personnalisés ?

 R : Le didacticiel montre comment créer un objet Line et configurer sa couleur, son tableau de tirets et sa phase de tirets à l'aide de l'`GraphInfo` objet. Modifiez ces paramètres pour obtenir le motif de tiret souhaité.

#### Q : Puis-je personnaliser la couleur de la ligne ?

 R : Oui, vous pouvez personnaliser la couleur de la ligne en définissant le`Color` propriété de la`GraphInfo` objet associé à la Ligne.

#### Q : Comment enregistrer le document PDF après avoir défini la longueur du tiret ?

 A : Après avoir configuré l'objet Ligne avec le motif de tirets souhaité, vous pouvez enregistrer le document PDF résultant à l'aide de l'`doc.Save(dataDir + "DashLength_out.pdf");` ligne dans le code source fourni.
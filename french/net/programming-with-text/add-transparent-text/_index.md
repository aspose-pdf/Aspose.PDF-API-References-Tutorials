---
title: Ajouter du texte transparent
linktitle: Ajouter du texte transparent
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter du texte transparent à un document PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-text/add-transparent-text/
---

Ce didacticiel vous guidera tout au long du processus d'ajout de texte transparent à un document PDF à l'aide d'Aspose.PDF pour .NET. Le code source C# fourni illustre les étapes nécessaires.

## Exigences
Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- Visual Studio ou tout autre compilateur C# installé sur votre machine.
- Aspose.PDF pour la bibliothèque .NET. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser un gestionnaire de packages comme NuGet pour l'installer.

## Étape 1 : Configurer le projet
1. Créez un nouveau projet C# dans votre environnement de développement préféré.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Importer les espaces de noms requis
Dans le fichier de code où vous souhaitez ajouter du texte transparent, ajoutez les directives using suivantes en haut du fichier :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## Étape 3 : Définir le répertoire de documents
 Dans le code, localisez la ligne qui dit`string dataDir = "YOUR DOCUMENT DIRECTORY";` et remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin du répertoire où sont stockés vos documents.

## Étape 4 : Créer une nouvelle instance de document
 Instancier un nouveau`Document` objet en ajoutant la ligne de code suivante :

```csharp
Document doc = new Document();
```

## Étape 5 : Ajouter une page au document
 Ajoutez une nouvelle page au document à l'aide de la`Add` méthode de la`Pages` collection. Dans le code fourni, la nouvelle page est affectée à la variable`page`.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Étape 6 : créer un objet Graph
 Créer un nouveau`Graph` objet avec une largeur et une hauteur spécifiques.

```csharp
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
```

## Étape 7 : Créer un rectangle avec transparence
Créez un rectangle avec des dimensions spécifiques et définissez sa couleur de remplissage sur une couleur transparente à l'aide de la`Color.FromRgb` méthode.

```csharp
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
canvas.Shapes.Add(rect);
```

## Étape 8 : Ajouter l'objet Graph à la page
 Ajouter le`Graph` objet à la collection de paragraphes de la page.

```csharp
page.Paragraphs.Add(canvas);
```

## Étape 9 : définir la position de l'objet graphique
 Met le`IsChangePosition` propriété de la`Graph` s'opposer à`false` pour l'empêcher de changer de position.

```csharp
canvas. IsChangePosition = false;
```

## Étape 10 : Créer un TextFragment avec transparence
 Créer un`TextFragment` objet et définissez son contenu sur le texte souhaité. Met le`ForegroundColor` propriété de la`TextState` à une couleur avec transparence à l'aide de`Color.FromArgb` méthode.

```csharp
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
text.TextState.ForegroundColor = color;
page.Paragraphs.Add(text);
```

## Étape 11 : Enregistrez le document PDF
 Enregistrez le document PDF à l'aide de`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "AddTransparentText_out.pdf");
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```

### Exemple de code source pour ajouter du texte transparent à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer une instance de document
Document doc = new Document();
// Créer une collection de pages à pages de fichiers PDF
Aspose.Pdf.Page page = doc.Pages.Add();
// Créer un objet graphique
Aspose.Pdf.Drawing.Graph canvas = new Aspose.Pdf.Drawing.Graph(100, 400);
// Créer une instance de rectangle avec certaines dimensions
Aspose.Pdf.Drawing.Rectangle rect = new Aspose.Pdf.Drawing.Rectangle(100, 100, 400, 400);
// Créer un objet de couleur à partir du canal de couleur Alpha
rect.GraphInfo.FillColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.FromArgb(128, System.Drawing.Color.FromArgb(12957183)));
// Ajouter un rectangle à la collection de formes de l'objet Graph
canvas.Shapes.Add(rect);
// Ajouter un objet graphique à la collection de paragraphes de l'objet page
page.Paragraphs.Add(canvas);
// Définir la valeur pour ne pas changer la position de l'objet graphique
canvas.IsChangePosition = false;
// Créer une instance TextFragment avec un exemple de valeur
TextFragment text = new TextFragment("transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text transparent text ");
// Créer un objet couleur à partir du canal Alpha
Aspose.Pdf.Color color = Aspose.Pdf.Color.FromArgb(30, 0, 255, 0);
//Définir les informations de couleur pour l'instance de texte
text.TextState.ForegroundColor = color;
// Ajouter du texte à la collection de paragraphes de l'instance de page
page.Paragraphs.Add(text);
dataDir = dataDir + "AddTransparentText_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTransparent text added successfully.\nFile saved at " + dataDir);
```


## Conclusion
Vous avez ajouté avec succès du texte transparent à votre document PDF en utilisant Aspose.PDF pour .NET. Le fichier PDF résultant se trouve maintenant dans le chemin du fichier de sortie spécifié.
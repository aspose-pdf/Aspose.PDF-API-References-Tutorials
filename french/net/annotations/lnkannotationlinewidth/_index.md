---
title: lnk Largeur de ligne d'annotation
linktitle: lnk Largeur de ligne d'annotation
second_title: Référence de l'API Aspose.PDF pour .NET
description: Cet article fournit un guide étape par étape pour définir la largeur de ligne de l'annotation lnk à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF est un outil puissant et largement utilisé pour travailler avec des fichiers PDF dans des applications .NET. Il fournit une variété de fonctionnalités pour créer, éditer et manipuler des fichiers PDF, y compris la possibilité d'ajouter des annotations aux pages. Dans ce didacticiel, nous expliquerons comment définir la largeur de ligne d'une annotation de lien à l'aide d'Aspose.PDF pour .NET.

Une fois que vous avez ces conditions préalables, créez un nouveau projet d'application console dans Visual Studio. Ensuite, ajoutez une référence à la bibliothèque Aspose.PDF pour .NET en cliquant avec le bouton droit sur le projet dans l'explorateur de solutions, en sélectionnant "Gérer les packages NuGet" et en recherchant "Aspose.PDF" dans le gestionnaire de packages NuGet.

Pour ajouter une annotation lnk à un document PDF, procédez comme suit :

##  Créer un nouveau`Document` object.
```csharp
Document doc = new Document();
```
## Ajouter une nouvelle page au document.
```csharp
doc.Pages.Add();
```
##  Créer une liste de`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Créer un nouveau`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Créer un nouveau`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Ajoutez le geste à la liste des gestes d'encre.
```csharp
inkList.Add(gesture);
```
##  Créer un nouveau`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Définissez l'objet et le titre de l'annotation.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Définissez la couleur de l'annotation.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Créer un nouveau`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Ajoutez l'annotation à la page.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Enregistrez le document dans un fichier.
```c// Save output file
doc.Save(dataDir);


```
### L'exemple montre lnk Annotation Line Width avec Aspose.PDF pour .NET

```csharp


// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
// Enregistrer le fichier de sortie
doc.Save(dataDir);


```

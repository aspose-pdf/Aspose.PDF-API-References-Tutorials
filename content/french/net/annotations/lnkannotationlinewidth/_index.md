---
title: Largeur de ligne d'annotation lnk
linktitle: Largeur de ligne d'annotation lnk
second_title: Aspose.PDF pour la référence de l'API .NET
description: Cet article fournit un guide étape par étape pour définir la largeur de ligne de l'annotation lnk à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF est un outil puissant et largement utilisé pour travailler avec des fichiers PDF dans des applications .NET. Il offre une variété de fonctionnalités pour créer, éditer et manipuler des fichiers PDF, notamment la possibilité d'ajouter des annotations aux pages. Dans ce didacticiel, nous expliquerons comment définir la largeur de ligne d'une annotation de lien à l'aide d'Aspose.PDF pour .NET.

Une fois que vous avez ces conditions préalables, créez un nouveau projet d’application console dans Visual Studio. Ensuite, ajoutez une référence à la bibliothèque Aspose.PDF pour .NET en cliquant avec le bouton droit sur le projet dans l'Explorateur de solutions, en sélectionnant « Gérer les packages NuGet » et en recherchant « Aspose.PDF » dans le gestionnaire de packages NuGet.

Pour ajouter une annotation lnk à un document PDF, procédez comme suit :

##  Étape 1 : Créer un nouveau`Document` object.
```csharp
Document doc = new Document();
```
## Étape 2 : Ajoutez une nouvelle page au document.
```csharp
doc.Pages.Add();
```
##  Étape 3 : Créez une liste de`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
##  Étape 4 : Créer un nouveau`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
##  Étape 5 : Créer un nouveau`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## Étape 6 : ajoutez le geste à la liste des gestes manuscrits.
```csharp
inkList.Add(gesture);
```
##  Étape 7 : Créer un nouveau`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## Étape 8 : Définissez le sujet et le titre de l'annotation.
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## Étape 9 : Définissez la couleur de l'annotation.
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
##  Étape 10 : Créer un nouveau`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## Étape 11 : Ajoutez l'annotation à la page.
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## Étape 12 : Enregistrez le document dans un fichier.
```csharp
// Enregistrer le fichier de sortie
doc.Save(dataDir);


```
### L'exemple montre la largeur de ligne d'annotation lnk avec Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
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

## Conclusion

Dans ce didacticiel, nous avons appris à définir la largeur de ligne d'une annotation de lien dans un document PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF pour .NET fournit une large gamme d'outils et de fonctionnalités pour travailler avec des documents PDF, notamment la possibilité de créer et de personnaliser des annotations de liens. En suivant le guide étape par étape et en utilisant le code source C# fourni, les développeurs peuvent facilement ajouter des liens interactifs à leurs documents PDF, améliorant ainsi l'expérience utilisateur et l'interactivité de leurs applications. Aspose.PDF pour .NET est une bibliothèque polyvalente qui permet aux développeurs .NET de travailler avec des fichiers PDF de manière efficace et efficiente.

### FAQ

#### Q : Qu'est-ce qu'une annotation de lien dans un document PDF ?

R : Une annotation de lien dans un document PDF est un élément interactif qui vous permet de créer des hyperliens ou des actions qui dirigent l'utilisateur vers un autre emplacement dans le même document, un site Web externe ou un autre document PDF.

#### Q : Comment puis-je définir la largeur de ligne d'une annotation de lien à l'aide d'Aspose.PDF pour .NET ?

R : Pour définir la largeur de ligne d'une annotation de lien à l'aide d'Aspose.PDF pour .NET, vous pouvez créer un`InkAnnotation` objet et spécifiez la propriété de largeur de ligne.

#### Q : Quelles propriétés peuvent être personnalisées pour une annotation de lien dans Aspose.PDF pour .NET ?

R : Vous pouvez personnaliser diverses propriétés d'une annotation de lien dans Aspose.PDF pour .NET, telles que son emplacement, sa taille, sa couleur, ses propriétés de bordure (largeur, style, motif de tiret et effet), son sujet, son titre et sa visibilité.

#### Q : Puis-je créer une annotation de lien contenant plusieurs gestes manuscrits ?

 R : Oui, vous pouvez créer une annotation de lien contenant plusieurs gestes manuscrits en ajoutant plusieurs`Point` tableaux au`InkAnnotation` objet.

#### Q : Comment puis-je ajouter une annotation de lien à une page spécifique du document PDF ?

 R : Pour ajouter une annotation de lien vers une page spécifique du document PDF, vous devez spécifier le numéro de page lors de la création du`InkAnnotation` objet. Par exemple,`new InkAnnotation(doc.Pages[1], ...)` ajoute l'annotation de lien à la première page.
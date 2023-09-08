---
title: Ajouter une annotation de lien
linktitle: Ajouter une annotation de lien
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter la fonctionnalité d'annotation manuscrite aux documents PDF en C# à l'aide d'Aspose.PDF pour .NET avec un guide étape par étape et un code source complet.
type: docs
weight: 20
url: /fr/net/annotations/addlnkannotation/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs d'effectuer diverses opérations PDF. L’une de ces opérations consiste à ajouter une annotation manuscrite aux documents PDF. Dans cet article, nous fournirons un guide étape par étape pour expliquer le code source C# pour l'ajout d'annotations manuscrites à l'aide d'Aspose.PDF pour .NET. Commençons!

## Comprendre la fonctionnalité d'annotation manuscrite d'Aspose.PDF pour .NET

Avant de plonger dans le code source C#, comprenons d'abord ce qu'est l'annotation Ink et ses utilisations.

L'annotation à l'encre est un moyen de dessiner des annotations à l'encre de forme libre sur des documents PDF. Il permet de créer des annotations avec un stylet ou une souris. Cette fonctionnalité est utile dans les situations où vous devez dessiner des diagrammes, des croquis ou d'autres types d'annotations.

## Étape 1 : Création d'un nouveau document

La première étape de l’ajout d’une annotation Ink à un document PDF consiste à créer une nouvelle instance de la classe Document. Ceci est réalisé à l'aide de l'extrait de code suivant :

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

Ici, nous créons une nouvelle instance de la classe Document et y ajoutons une nouvelle page.

## Étape 2 : Création d'une annotation manuscrite

L'étape suivante consiste à créer une instance de la classe InkAnnotation. Cela se fait à l'aide de l'extrait de code suivant :

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(AVC.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

Ici, nous créons d’abord un rectangle à l’aide de la classe System.Drawing.Rectangle et le convertissons en Aspose.Pdf.Rectangle à l’aide de la méthode FromRect. Nous créons ensuite une instance de la classe InkAnnotation en utilisant le rectangle, une liste de points et la page où l'annotation est ajoutée.

Nous définissons ensuite diverses propriétés de InkAnnotation, telles que le titre, la couleur, le style de majuscule, la bordure et l'opacité. Enfin, nous ajoutons l'annotation à la page à l'aide de la méthode Annotations.Add.

## Étape 3 : enregistrement du document

La dernière étape consiste à enregistrer le document PDF avec l'annotation à l'encre ajoutée. Ceci est réalisé à l'aide de l'extrait de code suivant :

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

Ici, nous concaténons le nom du fichier de sortie au répertoire de données et enregistrons le document à l'aide de la méthode Save.

### Exemple de code source pour l'ajout d'annotations manuscrites à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(AVC.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// Enregistrer le fichier de sortie
doc.Save(dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment ajouter des annotations manuscrites à un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant le guide étape par étape et le code source C# fournis, les développeurs peuvent facilement implémenter la fonctionnalité d'annotation manuscrite dans leurs applications de traitement PDF.

### FAQ

#### Q : Qu'est-ce qu'une annotation manuscrite dans un document PDF ?

R : Une annotation manuscrite dans un document PDF permet aux utilisateurs de dessiner des annotations manuscrites de forme libre à l'aide d'un stylet ou d'une souris. Il est couramment utilisé pour ajouter des croquis, des diagrammes ou d'autres annotations dessinées à la main à un PDF.

#### Q : Puis-je personnaliser l’apparence de l’annotation manuscrite ?

R : Oui, Aspose.PDF pour .NET fournit diverses propriétés pour personnaliser l'apparence de l'annotation manuscrite, telles que la couleur, l'opacité, le style de majuscule, la largeur de la bordure, etc. Les développeurs peuvent ajuster ces propriétés pour répondre à leurs besoins spécifiques.

#### Q : Est-il possible d'ajouter plusieurs annotations manuscrites à une seule page PDF ?

: Oui, vous pouvez ajouter plusieurs annotations manuscrites à une seule page PDF à l'aide d'Aspose.PDF pour .NET. Chaque annotation manuscrite peut avoir son propre ensemble de points et son apparence personnalisée.

#### Q : Puis-je ajouter des annotations manuscrites à des documents PDF existants ?

R : Oui, Aspose.PDF pour .NET vous permet d'ajouter des annotations manuscrites aux documents PDF nouvellement créés et aux fichiers PDF existants. Vous pouvez ouvrir un PDF existant, ajouter des annotations manuscrites et enregistrer le document mis à jour.

#### Q : Quels sont les cas d'utilisation courants des annotations manuscrites dans les documents PDF ?

R : Les annotations à l'encre sont utiles pour un large éventail d'applications, notamment l'ajout de signatures ou de notes manuscrites à des formulaires PDF, l'annotation de plans architecturaux ou de dessins techniques et le balisage de documents pour une révision collaborative.
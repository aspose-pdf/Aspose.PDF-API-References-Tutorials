---
title: Obtenir les propriétés PDF
linktitle: Obtenir les propriétés PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour obtenir les propriétés PDF telles que les dimensions et la rotation des boîtes à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-pdf-pages/get-properties/
---
Dans ce didacticiel, nous vous guiderons pas à pas tout au long du processus permettant d'obtenir les propriétés d'un PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. A la fin de ce tutoriel, vous saurez comment accéder aux différentes propriétés d'une page PDF telles que la zone d'art, la zone de recadrage, la zone de recadrage, etc., à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. Il s'agit de l'emplacement du fichier PDF dont vous souhaitez obtenir les propriétés. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF
 Ensuite, vous devez ouvrir le document PDF à l'aide du`Document` classe d’Aspose.PDF. Assurez-vous de spécifier le chemin correct vers le fichier PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Étape 3 : Accédez à la collection de pages
 Vous pouvez maintenant accéder à la collection de pages du document en utilisant le`Pages` propriété du`pdfDocument` objet.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Étape 4 : Accédez à une page spécifique
Ensuite, vous pouvez accéder à une page spécifique en utilisant l'index de la page de la collection. Dans l'exemple ci-dessous, nous accédons à la deuxième page (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Étape 5 : Obtenir les propriétés de la page
 Vous pouvez désormais obtenir les différentes propriétés de la page PDF, telles que la zone d'illustration, la zone de recadrage, la zone de recadrage, etc., en utilisant les propriétés correspondantes du`pdfPage` objet.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### Exemple de code source pour obtenir des propriétés à l'aide d'Aspose.PDF pour .NET 

```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// Obtenir la collection de pages
PageCollection pageCollection = pdfDocument.Pages;
// Obtenir une page particulière
Page pdfPage = pageCollection[1];
// Obtenir les propriétés de la page
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## Conclusion
Félicitation ! Vous avez obtenu avec succès les propriétés d'un PDF en utilisant Aspose.PDF pour .NET. Vous avez appris à ouvrir un document PDF, à accéder à une page spécifique et à obtenir diverses propriétés de page, telles que les zones de dimension et la rotation. Vous pouvez désormais utiliser ces informations pour personnaliser la gestion de vos fichiers PDF en fonction de leurs propriétés.

Assurez-vous de consulter la documentation officielle d'Aspose.PDF pour .NET pour plus d'informations sur les fonctionnalités avancées et les possibilités de personnalisation.

### FAQ

#### Q : Comment puis-je obtenir les propriétés d'un PDF à l'aide d'Aspose.PDF pour .NET ?

R : Pour obtenir les propriétés d'un PDF à l'aide d'Aspose.PDF pour .NET, vous pouvez suivre ces étapes :

1. Définissez le répertoire du document en spécifiant le chemin d'accès au fichier PDF dont vous souhaitez récupérer les propriétés.
2.  Ouvrez le document PDF à l'aide du`Document` classe d’Aspose.PDF, fournissant le chemin correct vers le fichier PDF.
3.  Accédez à la collection de pages du document à l'aide du`Pages` propriété du`pdfDocument` objet.
4. Accédez à une page spécifique en utilisant l'index de la page de la collection (l'indexation commence à partir de 1).
5.  Obtenez les différentes propriétés de la page PDF, telles que ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number et Rotation, en utilisant les propriétés correspondantes du fichier PDF.`pdfPage` objet.

#### Q : Quelles sont les différentes propriétés d'une page PDF que je peux récupérer à l'aide d'Aspose.PDF pour .NET ?

R : Vous pouvez récupérer diverses propriétés d'une page PDF à l'aide d'Aspose.PDF pour .NET, telles que :

- ArtBox : représente les dimensions de l'illustration de la page.
- BleedBox : représente les dimensions du fond perdu de la page.
- CropBox : représente les dimensions du contenu visible de la page après le recadrage.
- MediaBox : représente les dimensions du support physique de la page.
- TrimBox : représente les dimensions du contenu découpé de la page.
- Rect : représente les dimensions du cadre de délimitation de la page.
- Numéro de page : représente le numéro de page dans le document.
- Rotation : représente l'angle de rotation de la page.

#### Q : Comment accéder à une page spécifique du document PDF pour récupérer ses propriétés ?

 R : Pour accéder à une page spécifique du document PDF et récupérer ses propriétés, vous pouvez utiliser le`Pages` propriété du`pdfDocument` objet pour accéder à la collection de pages du document. Ensuite, vous pouvez utiliser l'index de la page de la collection pour accéder à la page souhaitée. Par exemple, pour accéder à la deuxième page, vous pouvez utiliser`pdfDocument.Pages[1]` (l'indexation commence à partir de 1).

#### Q : Puis-je effectuer des opérations sur les propriétés récupérées, telles que modifier ou redimensionner les zones de page ?

R : Oui, une fois que vous avez récupéré les propriétés d'une page PDF à l'aide d'Aspose.PDF pour .NET, vous pouvez y effectuer diverses opérations. Par exemple, vous pouvez modifier les dimensions des zones de page, faire pivoter la page ou utiliser les informations récupérées pour un traitement et une manipulation personnalisés du document PDF.

#### Q : Aspose.PDF pour .NET prend-il en charge l'extraction de propriétés à partir de fichiers PDF cryptés ou protégés par mot de passe ?

R : Oui, Aspose.PDF pour .NET prend en charge l'extraction de propriétés à partir de fichiers PDF cryptés ou protégés par mot de passe. Tant que vous fournissez le mot de passe correct pour ouvrir le document PDF, vous pouvez accéder et récupérer ses propriétés en utilisant la même approche démontrée dans le didacticiel.
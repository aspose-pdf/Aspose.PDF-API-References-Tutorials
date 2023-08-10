---
title: Obtenir les propriétés PDF
linktitle: Obtenir les propriétés PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour obtenir des propriétés PDF telles que les dimensions et la rotation de la boîte à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-pdf-pages/get-properties/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus d'obtention des propriétés d'un PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment accéder aux différentes propriétés d'une page PDF telles que la boîte d'art, la boîte de recadrage, la boîte de recadrage, etc., en utilisant Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire de documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement du fichier PDF dont vous souhaitez obtenir les propriétés. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF
 Ensuite, vous devez ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Assurez-vous de spécifier le chemin d'accès correct au fichier PDF.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## Étape 3 : Accéder à la collection de pages
 Vous pouvez maintenant accéder à la collection de pages du document à l'aide de la`Pages` propriété de la`pdfDocument` objet.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## Étape 4 : Accéder à une page spécifique
Ensuite, vous pouvez accéder à une page spécifique en utilisant l'index de la page dans la collection. Dans l'exemple ci-dessous, on accède à la deuxième page (index 1).

```csharp
Page pdfPage = pageCollection[1];
```

## Étape 5 : Obtenir les propriétés de la page
 Vous pouvez maintenant obtenir les différentes propriétés de la page PDF, telles que la zone d'art, la zone de recadrage, la zone de recadrage, etc., en utilisant les propriétés correspondantes du`pdfPage` objet.

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

// Chemin d'accès au répertoire des documents.
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
Félicitation ! Vous avez réussi à obtenir les propriétés d'un PDF en utilisant Aspose.PDF pour .NET. Vous avez appris à ouvrir un document PDF, à accéder à une page spécifique et à obtenir diverses propriétés de page, telles que les zones de dimension et la rotation. Vous pouvez maintenant utiliser ces informations pour personnaliser la gestion de vos fichiers PDF en fonction de leurs propriétés.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour .NET pour plus d'informations sur les fonctionnalités avancées et les possibilités de personnalisation.

### FAQ

#### : Comment puis-je obtenir les propriétés d'un PDF en utilisant Aspose.PDF pour .NET ?

R : Pour obtenir les propriétés d'un PDF à l'aide d'Aspose.PDF pour .NET, vous pouvez suivre ces étapes :

1. Définissez le répertoire du document en spécifiant le chemin d'accès au fichier PDF dont vous souhaitez récupérer les propriétés.
2.  Ouvrez le document PDF à l'aide de la`Document` classe de Aspose.PDF, fournissant le chemin d'accès correct au fichier PDF.
3.  Accéder à la collection de pages du document à l'aide de la`Pages` propriété de la`pdfDocument` objet.
4. Accéder à une page spécifique en utilisant l'index de la page dans la collection (l'indexation commence à partir de 1).
5.  Obtenez les différentes propriétés de la page PDF, telles que ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number et Rotation, en utilisant les propriétés correspondantes du`pdfPage` objet.

#### Q : Quelles sont les différentes propriétés d'une page PDF que je peux récupérer à l'aide d'Aspose.PDF pour .NET ?

R : Vous pouvez récupérer diverses propriétés d'une page PDF à l'aide d'Aspose.PDF pour .NET, telles que :

- ArtBox : représente les dimensions de l'illustration de la page.
- BleedBox : Représente les dimensions du fond perdu de la page.
- CropBox : Représente les dimensions du contenu visible de la page après le recadrage.
- MediaBox : Représente les dimensions du support physique de la page.
- TrimBox : représente les dimensions du contenu découpé de la page.
- Rect : Représente les dimensions du cadre de délimitation de la page.
- Numéro de page : Représente le numéro de page dans le document.
- Rotation : Représente l'angle de rotation de la page.

#### Q : Comment puis-je accéder à une page spécifique dans le document PDF pour récupérer ses propriétés ?

 R : Pour accéder à une page spécifique du document PDF et récupérer ses propriétés, vous pouvez utiliser le`Pages` propriété de la`pdfDocument` objet pour accéder à la collection de pages du document. Ensuite, vous pouvez utiliser l'index de la page dans la collection pour accéder à la page souhaitée. Par exemple, pour accéder à la deuxième page, vous pouvez utiliser`pdfDocument.Pages[1]` (l'indexation commence à partir de 1).

#### Q : Puis-je effectuer des opérations sur les propriétés récupérées, telles que la modification ou le redimensionnement des zones de page ?

R : Oui, une fois que vous avez récupéré les propriétés d'une page PDF à l'aide d'Aspose.PDF pour .NET, vous pouvez effectuer diverses opérations dessus. Par exemple, vous pouvez modifier les dimensions des zones de page, faire pivoter la page ou utiliser les informations récupérées pour le traitement personnalisé et la manipulation du document PDF.

#### Q : Aspose.PDF pour .NET prend-il en charge l'extraction de propriétés à partir de fichiers PDF cryptés ou protégés par mot de passe ?

R : Oui, Aspose.PDF pour .NET prend en charge l'extraction de propriétés à partir de fichiers PDF cryptés ou protégés par mot de passe. Tant que vous fournissez le mot de passe correct pour ouvrir le document PDF, vous pouvez accéder et récupérer ses propriétés en utilisant la même approche démontrée dans le didacticiel.
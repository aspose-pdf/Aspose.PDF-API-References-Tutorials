---
title: Obtenir les dimensions de la page PDF
linktitle: Obtenir les dimensions de la page PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Dans ce didacticiel, nous expliquons comment obtenir les dimensions d'une page PDF et effectuer des manipulations à l'aide d'Aspose.PDF pour .NET. Des étapes détaillées sont fournies pour vous guider tout au long du processus.
type: docs
weight: 60
url: /fr/net/programming-with-pdf-pages/get-dimensions/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus d'obtention des dimensions de page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. A la fin de ce tutoriel, vous saurez comment obtenir les dimensions d'une page dans un fichier PDF en utilisant Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où se trouve votre fichier PDF. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF
 Ensuite, vous pouvez ouvrir le fichier PDF en utilisant le`Document` classe de Aspose.PDF. Assurez-vous de spécifier le chemin d'accès correct au fichier PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Étape 3 : Ajoutez une page vierge (si nécessaire)
 Si le document PDF contient déjà des pages, vous pouvez accéder à une page existante à l'aide de l'index`1` (la première page a un index de 1). Sinon, vous pouvez ajouter une nouvelle page au document.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Étape 4 : Obtenir les dimensions de la page
 Vous pouvez maintenant obtenir les dimensions de la page en utilisant le`GetPageRect()` méthode de la`Page` objet. Cette méthode renvoie un`Rectangle` objet contenant les dimensions de la page. Vous pouvez accéder à la largeur et à la hauteur à l'aide de la`Width` et`Height` propriétés.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Étape 5 : Faire pivoter la page
 Si vous voulez faire pivoter la page, vous pouvez utiliser le`Rotate` propriété de la`Page`objet. Dans cet exemple, la page est pivotée de 90 degrés.

```csharp
page. Rotate = Rotate. on90;
```

## Étape 6 : Récupérez les dimensions de la page
 Après la rotation des pages, vous pouvez récupérer les dimensions de la page à l'aide de l'outil`GetPageRect()` méthode.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Exemple de code source pour Get Dimensions à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Ajoute une page vierge au document pdf
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Obtenir des informations sur la hauteur et la largeur de la page
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Faire pivoter la page à 90 degrés
page.Rotate = Rotation.on90;
// Obtenir des informations sur la hauteur et la largeur de la page
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusion
Dans ce didacticiel, nous avons appris à obtenir les dimensions d'une page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes fournies, vous pouvez facilement extraire les dimensions de la page et effectuer d'autres opérations de manipulation de PDF. Aspose.PDF pour .NET offre une grande flexibilité pour travailler avec des fichiers PDF et vous permet de développer des solutions puissantes et personnalisées.

N'hésitez pas à explorer davantage la documentation d'Aspose.PDF pour découvrir toutes les fonctionnalités offertes par cette bibliothèque.

### FAQ pour obtenir les dimensions de la page PDF

#### Q : Comment puis-je obtenir les dimensions d'une page spécifique dans un fichier PDF ?

 : Pour obtenir les dimensions d'une page spécifique dans un fichier PDF, vous pouvez utiliser le`GetPageRect()` méthode de la`Page` objet dans Aspose.PDF pour .NET. Cette méthode renvoie un`Rectangle` objet contenant les dimensions (largeur et hauteur) de la page.

####  Q : Qu'est-ce que le`GetPageRect(true)` method do in the provided C# source code?

 R : Le`GetPageRect(true)` La méthode dans le code source C# fourni renvoie les dimensions de la page après avoir appliqué des rotations. Si la page est pivotée, la méthode renvoie les dimensions de la page pivotée, qui peuvent être différentes des dimensions d'origine.

#### Q : Puis-je obtenir les dimensions de toutes les pages du document PDF à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, vous pouvez obtenir les dimensions de toutes les pages du document PDF en parcourant les`Pages` collecte de la`Document` objet et en utilisant le`GetPageRect(true)` méthode pour chaque page.

#### Q : Comment puis-je déterminer l'orientation d'une page (portrait ou paysage) en fonction de ses dimensions ?

R : Pour déterminer l'orientation d'une page en fonction de ses dimensions, vous pouvez comparer la largeur et la hauteur de la page. Si la largeur est supérieure à la hauteur, la page est en orientation paysage, et si la hauteur est supérieure à la largeur, la page est en orientation portrait.

#### Q : Puis-je modifier les dimensions d'une page à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, vous pouvez modifier les dimensions d'une page dans Aspose.PDF pour .NET. Après avoir obtenu le`Rectangle` objet représentant les dimensions de la page, vous pouvez ajuster la largeur et la hauteur selon vos besoins, puis appliquer les modifications à la page.
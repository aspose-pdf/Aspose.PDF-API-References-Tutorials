---
title: Obtenir les dimensions de la page PDF
linktitle: Obtenir les dimensions de la page PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Dans ce tutoriel, nous expliquons comment obtenir les dimensions d'une page PDF et effectuer des manipulations à l'aide d'Aspose.PDF pour .NET. Des étapes détaillées sont fournies pour vous guider tout au long du processus.
type: docs
weight: 60
url: /fr/net/programming-with-pdf-pages/get-dimensions/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus d'obtention des dimensions de page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment obtenir les dimensions d'une page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.

## Prérequis
Avant de commencer, assurez-vous de disposer des éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où se trouve votre fichier PDF. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Ouvrir le document PDF
 Vous pouvez ensuite ouvrir le fichier PDF à l'aide de la`Document` classe de Aspose.PDF. Assurez-vous de spécifier le chemin correct vers le fichier PDF.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## Étape 3 : Ajoutez une page vierge (si nécessaire)
 Si le document PDF contient déjà des pages, vous pouvez accéder à une page existante à l'aide de l'index`1` (la première page a un index de 1). Sinon, vous pouvez ajouter une nouvelle page au document.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## Étape 4 : Obtenir les dimensions de la page
 Vous pouvez maintenant obtenir les dimensions de la page en utilisant le`GetPageRect()` méthode de la`Page` objet. Cette méthode renvoie un`Rectangle` objet contenant les dimensions de la page. Vous pouvez accéder à la largeur et à la hauteur en utilisant le`Width` et`Height` propriétés.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## Étape 5 : Faire pivoter la page
 Si vous souhaitez faire pivoter la page, vous pouvez utiliser le`Rotate` propriété de la`Page`objet. Dans cet exemple, la page est tournée de 90 degrés.

```csharp
page. Rotate = Rotate. on90;
```

## Étape 6 : Récupérer à nouveau les dimensions de la page
 Après la rotation de la page, vous pouvez à nouveau obtenir les dimensions de la page en utilisant le`GetPageRect()` méthode.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### Exemple de code source pour obtenir des dimensions à l'aide d'Aspose.PDF pour .NET 

```csharp

// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// Ajoute une page vierge au document PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// Obtenir des informations sur la hauteur et la largeur de la page
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// Faire pivoter la page à un angle de 90 degrés
page.Rotate = Rotation.on90;
// Obtenir des informations sur la hauteur et la largeur de la page
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## Conclusion
Dans ce tutoriel, nous avons appris à obtenir les dimensions d'une page dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes fournies, vous pouvez facilement extraire les dimensions de la page et effectuer d'autres opérations de manipulation PDF. Aspose.PDF pour .NET offre une grande flexibilité pour travailler avec des fichiers PDF et vous permet de développer des solutions puissantes et personnalisées.

N'hésitez pas à explorer davantage la documentation d'Aspose.PDF pour découvrir toutes les fonctionnalités offertes par cette bibliothèque.

### FAQ pour obtenir les dimensions des pages PDF

#### Q : Comment puis-je obtenir les dimensions d’une page spécifique dans un fichier PDF ?

 : Pour obtenir les dimensions d'une page spécifique dans un fichier PDF, vous pouvez utiliser le`GetPageRect()` méthode de la`Page` objet dans Aspose.PDF pour .NET. Cette méthode renvoie un`Rectangle` objet contenant les dimensions (largeur et hauteur) de la page.

####  Q : Que signifie le`GetPageRect(true)` method do in the provided C# source code?

 A : Le`GetPageRect(true)` La méthode dans le code source C# fourni renvoie les dimensions de la page après avoir appliqué les rotations. Si la page est pivotée, la méthode renverra les dimensions de la page pivotée, qui peuvent être différentes des dimensions d'origine.

#### Q : Puis-je obtenir les dimensions de toutes les pages du document PDF à l’aide d’Aspose.PDF pour .NET ?

 R : Oui, vous pouvez obtenir les dimensions de toutes les pages du document PDF en parcourant le`Pages` collection de la`Document` objet et en utilisant le`GetPageRect(true)` méthode pour chaque page.

#### Q : Comment puis-je déterminer l'orientation d'une page (portrait ou paysage) en fonction de ses dimensions ?

: Pour déterminer l'orientation d'une page en fonction de ses dimensions, vous pouvez comparer la largeur et la hauteur de la page. Si la largeur est supérieure à la hauteur, la page est en orientation paysage, et si la hauteur est supérieure à la largeur, la page est en orientation portrait.

#### Q : Puis-je modifier les dimensions d’une page en utilisant Aspose.PDF pour .NET ?

 R : Oui, vous pouvez modifier les dimensions d'une page dans Aspose.PDF pour .NET. Après avoir obtenu le`Rectangle` objet représentant les dimensions de la page, vous pouvez ajuster la largeur et la hauteur selon vos besoins, puis appliquer les modifications à la page.
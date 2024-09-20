---
title: Rechercher et obtenir une page de texte dans un fichier PDF
linktitle: Rechercher et obtenir une page de texte dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher et obtenir du texte à partir d'une page spécifique dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 430
url: /fr/net/programming-with-text/search-and-get-text-page/
---
## Introduction

Avez-vous déjà eu besoin de rechercher un texte spécifique dans un document PDF et de l'extraire pour une utilisation ultérieure ? Peut-être créez-vous une application qui traite des documents et nécessite une extraction de données précise, ou peut-être avez-vous simplement besoin d'analyser efficacement des PDF. Quel que soit votre cas, vous êtes au bon endroit ! Dans ce tutoriel, nous allons découvrir comment rechercher et obtenir du texte à partir d'une page d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Que vous soyez un développeur débutant ou expérimenté, ce guide vous guidera à travers chaque étape de manière conversationnelle et engageante. Prêt à vous lancer ? Commençons !

## Prérequis

Avant de passer au codage, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1.  Bibliothèque Aspose.PDF pour .NET : vous pouvez la télécharger à partir de[ici](https://releases.aspose.com/pdf/net/) ou obtenez une version d'essai gratuite à partir du même lien. Pour acheter, rendez-vous sur le[Magasin Aspose](https://purchase.aspose.com/buy).
2. .NET Framework : vous aurez besoin d’un environnement de développement .NET fonctionnel tel que Visual Studio.
3. Un fichier PDF : vous aurez besoin d'un exemple de fichier PDF dans lequel nous pourrons rechercher et extraire le texte. Pour ce tutoriel, supposons que le fichier s'appelle`SearchAndGetTextPage.pdf`.

## Paquets d'importation

Tout d’abord, nous devons importer les espaces de noms nécessaires pour travailler avec Aspose.PDF pour .NET. Assurez-vous qu’ils sont inclus en haut de votre code.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System
```

Maintenant que nous avons couvert les prérequis, décomposons le code étape par étape. Chaque étape a été clairement décrite pour faciliter le suivi.

## Étape 1 : définissez le chemin d’accès à votre répertoire de documents

Avant d'interagir avec votre PDF, vous devez définir le chemin d'accès vers lequel votre document PDF est stocké. Cela garantit que le programme peut accéder au fichier.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir : il s'agit du chemin d'accès au dossier dans lequel sont stockés vos fichiers PDF. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où se trouve le PDF.

## Étape 2 : Charger le document PDF

L'étape suivante consiste à charger le document PDF en mémoire afin de pouvoir l'utiliser. Voici comment procéder :

```csharp
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

- Document : il s'agit de la classe Aspose.PDF qui charge le fichier PDF.
- pdfDocument : la variable dans laquelle votre fichier PDF est stocké après avoir été chargé.

## Étape 3 : Créer un objet absorbeur de texte

 Le`TextFragmentAbsorber`La classe vous permet de rechercher un texte spécifique dans le PDF. Créons une instance de cette classe pour trouver toutes les instances d'une phrase de recherche donnée.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

- TextFragmentAbsorber : cette classe est chargée de rechercher et d'extraire du texte du PDF.
- « Figure » : remplacez ceci par le texte que vous souhaitez rechercher dans le PDF.

## Étape 4 : appliquer Text Absorber à l'ensemble du PDF

Une fois l'absorbeur de texte configuré, vous devez indiquer au programme de rechercher dans toutes les pages du PDF.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

- Accept() : cette méthode applique l'absorbeur de texte au PDF, en analysant chaque page à la recherche du texte que vous avez spécifié.

## Étape 5 : Récupérer et parcourir le texte extrait

Maintenant que nous avons numérisé le PDF, il est temps de récupérer les résultats et de les afficher. Nous allons parcourir les fragments de texte extraits.

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- TextFragmentCollection : cette collection contient toutes les instances des fragments de texte trouvés par l'absorbeur de texte.

## Étape 6 : Parcourir chaque fragment et extraire les données

Nous allons maintenant parcourir le`textFragmentCollection` et extraire diverses propriétés de chaque segment de texte, telles que sa position, les détails de police et la couleur.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

- TextFragment : Chaque fragment contient des parties du texte trouvé.
- TextSegment : Chaque fragment peut avoir plusieurs segments, représentant différentes parties du texte.
- TextState : cela fournit des informations détaillées sur la police, la taille et la couleur du texte.

Dans cette boucle, nous imprimons les détails tels que le texte réel, sa position (coordonnées X et Y), la police, si la police est intégrée au PDF et la couleur de premier plan du texte.

## Conclusion

Et voilà ! Vous avez maintenant réussi à rechercher et à extraire du texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. C'est incroyable la flexibilité dont vous disposez avec cette bibliothèque. Que vous ayez besoin de rechercher un texte spécifique dans un document volumineux, de l'extraire ou d'analyser ses propriétés, Aspose.PDF vous facilite la tâche. De plus, avec le code que nous avons abordé, vous êtes bien équipé pour l'adapter à vos besoins. 

## FAQ

### Puis-je rechercher plusieurs phrases à la fois ?  
 Oui, vous pouvez modifier le code pour rechercher plusieurs phrases en créant plusieurs`TextFragmentAbsorber` objets.

### Comment puis-je extraire du texte d’une page spécifique ?  
 Vous pouvez cibler une page spécifique en appliquant le`TextFragmentAbsorber` sur une seule page au lieu du document entier. Par exemple :`pdfDocument.Pages[1].Accept(textFragmentAbsorber);`.

### Aspose.PDF pour .NET est-il gratuit ?  
 Aspose.PDF est un produit commercial, mais vous pouvez l'utiliser avec un[essai gratuit](https://releases.aspose.com/).

### Puis-je extraire des images du PDF à l'aide d'Aspose.PDF ?  
 Oui, Aspose.PDF vous permet d'extraire des images en plus du texte. Vérifiez le[documentation](https://reference.aspose.com/pdf/net/) pour plus de détails.

### Que faire si j’ai besoin de plus d’aide ou de soutien ?  
 Vous pouvez toujours obtenir de l'aide auprès du[Forum d'assistance Aspose](https://forum.aspose.com/c/pdf/10).
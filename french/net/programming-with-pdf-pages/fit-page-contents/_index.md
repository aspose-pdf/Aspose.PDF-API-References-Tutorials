---
title: Adapter le contenu de la page
linktitle: Adapter le contenu de la page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide détaillé étape par étape pour ajuster le contenu de la page PDF à l'aide d'Aspose.PDF pour .NET. Mise en œuvre facile et conclusion enrichissante.
type: docs
weight: 50
url: /fr/net/programming-with-pdf-pages/fit-page-contents/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus d'ajustement du contenu de la page PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment ajuster le contenu des pages PDF à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où se trouve votre fichier PDF d'entrée. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document PDF
 Ensuite, vous pouvez charger le document PDF en utilisant le`Document` classe de Aspose.PDF. Assurez-vous de spécifier le chemin d'accès correct au fichier PDF d'entrée.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 3 : Ajuster le contenu de la page
Vous pouvez maintenant parcourir toutes les pages du document et ajuster le contenu de chaque page en fonction de la taille de la boîte multimédia. Dans l'exemple fourni, on ajuste la largeur de la page pour la rendre en mode paysage (landscape) en gardant la même hauteur. La nouvelle largeur est calculée en fonction du format d'image de la boîte multimédia.

```csharp
foreach(Page page in doc.Pages)
{
     Rectangle r = page.MediaBox;
     double newHeight = r.Height;
     double newWidth = r.Height * r.Height / r.Width;
}
```

### Exemple de code source pour Fit Page Contents en utilisant Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Rectangle r = page.MediaBox;
	// Nouvelle hauteur identique
	double newHeight = r.Height;
	// La nouvelle largeur est agrandie proportionnellement pour rendre le paysage d'orientation
	// (nous supposons que l'orientation précédente est portrait)
	double newWidth = r.Height * r.Height / r.Width;
}          

```

## Conclusion
Dans ce didacticiel, nous avons appris à ajuster le contenu d'une page PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez facilement implémenter cette fonctionnalité dans vos propres projets. N'hésitez pas à explorer davantage la documentation Aspose.PDF pour découvrir d'autres fonctionnalités utiles pour travailler avec des fichiers PDF.

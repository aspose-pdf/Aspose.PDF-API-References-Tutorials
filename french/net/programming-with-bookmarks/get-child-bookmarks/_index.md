---
title: Obtenir des signets enfants
linktitle: Obtenir des signets enfants
second_title: Référence de l'API Aspose.PDF pour .NET
description: Obtenez facilement des signets enfants de vos fichiers PDF avec Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/programming-with-bookmarks/get-child-bookmarks/
---

Récupérer des signets enfants à partir d'un document PDF peut être utile pour explorer la structure hiérarchique des signets. Avec Aspose.PDF pour .NET, vous pouvez facilement obtenir les signets enfants en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF dont vous souhaitez extraire les signets. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF dont nous souhaitons extraire les marque-pages à l'aide du code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## Étape 4 : Parcourir les signets et les signets enfants

Dans cette étape, nous allons parcourir tous les signets du document à l'aide d'un`foreach`boucle. Pour chaque signet, nous afficherons les informations telles que le titre, le style italique, le style gras et la couleur. Si le signet a des signets enfants, nous les afficherons également. Voici le code correspondant :

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // Parcourir également les signets enfants
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### Exemple de code source pour Get Child Bookmarks à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// Parcourez tous les signets
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// Il y a des signets enfants, puis bouclez-les également
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## Conclusion

Félicitation ! Vous avez maintenant un guide étape par étape pour obtenir des signets enfants avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour explorer la structure hiérarchique des signets et obtenir des informations détaillées sur chaque signet et ses signets enfants dans vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation des signets.
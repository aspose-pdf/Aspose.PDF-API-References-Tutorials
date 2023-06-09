---
title: Obtenir le numéro de page du signet
linktitle: Obtenir le numéro de page du signet
second_title: Référence de l'API Aspose.PDF pour .NET
description: Obtenez facilement des numéros de page de signet à partir de vos fichiers PDF avec Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-bookmarks/get-bookmark-page-number/
---

Récupérer les numéros de page associés aux signets dans un document PDF peut être utile pour la navigation. Avec Aspose.PDF pour .NET, vous pouvez facilement obtenir le numéro de page des signets en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf.Facades;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF dont vous souhaitez extraire les numéros de page des signets. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Créer l'éditeur de favoris

 Nous allons maintenant créer un`PdfBookmarkEditor` objet pour manipuler les signets du document. Utilisez le code suivant :

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

## Étape 4 : Ouvrez le fichier PDF

 Dans cette étape, nous ouvrons le fichier PDF en utilisant le`BindPdf` méthode de l'éditeur de signets. Voici le code correspondant :

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

## Étape 5 : Extraire les signets

 Nous allons maintenant extraire les signets du document en utilisant le`ExtractBookmarks` méthode de l'éditeur de signets. Voici le code correspondant :

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

## Étape 6 : Parcourir les signets et obtenir les numéros de page

 Enfin, nous parcourons les signets extraits et obtenons les numéros de page associés à chaque signet à l'aide d'un`foreach` boucle. Voici le code correspondant :

```csharp
foreach (Bookmark bookmark in bookmarks)
{
     string strLevelSeprator = string.Empty;
     for (int i = 1; i < bookmark.Level; i++)
     {
         strLevelSeprator += "----";
     }
     Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
     Console.WriteLine("{0}Page number: {1}", strLevelSeprator, bookmark.PageNumber);
     Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

### Exemple de code source pour obtenir le numéro de page du signet à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer PdfBookmarkEditor
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
// Ouvrir le fichier PDF
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
// Extraire les signets
Aspose.Pdf.Facades.Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
foreach (Aspose.Pdf.Facades.Bookmark bookmark in bookmarks)
{
	string strLevelSeprator = string.Empty;
	for (int i = 1; i < bookmark.Level; i++)
	{
		strLevelSeprator += "----";
	}
	Console.WriteLine("{0}Title: {1}", strLevelSeprator, bookmark.Title);
	Console.WriteLine("{0}Page Number: {1}", strLevelSeprator, bookmark.PageNumber);
	Console.WriteLine("{0}Page Action: {1}", strLevelSeprator, bookmark.Action);
}
```

## Conclusion

Félicitation ! Vous avez maintenant un guide étape par étape pour obtenir des numéros de page de signet avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour récupérer les informations de navigation associées à chaque signet dans vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation des signets.
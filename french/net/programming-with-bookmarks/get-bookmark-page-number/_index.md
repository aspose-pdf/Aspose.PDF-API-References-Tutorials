---
title: Obtenir le numéro de page du signet dans le fichier PDF
linktitle: Obtenir le numéro de page du signet dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Obtenez facilement le numéro de page du signet dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-bookmarks/get-bookmark-page-number/
---
La récupération des numéros de page associés aux signets dans le fichier PDF peut être utile pour la navigation. Avec Aspose.PDF pour .NET, vous pouvez facilement obtenir le numéro de page des signets en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf.Facades;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF dont vous souhaitez extraire les numéros de page des signets. Remplacer`"YOUR DOCUMENT DIRECTORY"`dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

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

### FAQ pour obtenir le numéro de page du signet dans le fichier PDF

#### Q : Que sont les signets dans un fichier PDF ?

R : Les signets dans un fichier PDF sont des aides à la navigation qui permettent aux utilisateurs d'accéder rapidement à des sections ou pages spécifiques du document. Ils améliorent l'expérience utilisateur en fournissant des raccourcis vers le contenu pertinent.

#### Q : Pourquoi voudrais-je récupérer les numéros de page des signets d'un fichier PDF ?

R : La récupération des numéros de page des signets aide les utilisateurs à naviguer plus efficacement dans un document, en fournissant une indication claire de l'endroit où mène chaque signet. Ceci est particulièrement utile pour les documents plus longs avec plusieurs sections.

#### Q : Comment importer les bibliothèques nécessaires pour mon projet C# ?

R : Pour importer la bibliothèque requise pour votre projet C#, utilisez la directive d'importation suivante :

```csharp
using Aspose.Pdf.Facades;
```

Cette directive vous permet d'utiliser les classes et les méthodes fournies par Aspose.PDF pour .NET.

#### Q : Comment spécifier le chemin d'accès au dossier de documents ?

 R : Dans le code source fourni, remplacez`"YOUR DOCUMENT DIRECTORY"`par le chemin d'accès réel au dossier contenant le fichier PDF à partir duquel vous souhaitez extraire les numéros de page des signets. Cela garantit que le code peut localiser le fichier PDF cible.

#### Q : Comment créer un éditeur de signets ?

R : Pour créer un éditeur de favoris, utilisez le code suivant :

```csharp
PdfBookmarkEditor bookmarkEditor = new PdfBookmarkEditor();
```

#### Q : Comment puis-je ouvrir un fichier PDF pour la manipulation des signets ?

R : Pour ouvrir un fichier PDF afin d'extraire des informations sur les signets, utilisez le code suivant :

```csharp
bookmarkEditor.BindPdf(dataDir + "GetBookmarks.pdf");
```

 Remplacer`"GetBookmarks.pdf"` avec le vrai nom du fichier.

#### Q : Comment puis-je extraire des signets du fichier PDF ?

 R : Pour extraire les signets du fichier PDF, utilisez le`ExtractBookmarks` méthode de l'éditeur de signets :

```csharp
Bookmarks bookmarks = bookmarkEditor.ExtractBookmarks();
```

#### Q : Comment puis-je récupérer et afficher les numéros de page des signets ?

 R : Parcourez les signets extraits à l'aide d'un`foreach` boucle et accéder à la`PageNumber` propriété de chaque signet pour récupérer et afficher son numéro de page associé :

```csharp
foreach (Bookmark bookmark in bookmarks)
{
    Console.WriteLine("Title: " + bookmark.Title);
    Console.WriteLine("Page Number: " + bookmark.PageNumber);
    Console.WriteLine("Page Action: " + bookmark.Action);
}
```

#### Q : Puis-je modifier les propriétés des favoris en utilisant cette approche ?

 R : Bien que ce didacticiel se concentre sur la récupération des numéros de page de signet, vous pouvez modifier d'autres propriétés de signet en utilisant le même`Bookmark`objet et propriétés associées.

#### Q : Comment puis-je enregistrer le fichier PDF mis à jour après avoir extrait les informations sur les signets ?

R : L'extraction des signets ne modifie pas le fichier PDF d'origine. Si vous souhaitez enregistrer des modifications, vous pouvez le faire en utilisant d'autres méthodes fournies par Aspose.PDF pour .NET.
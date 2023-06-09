---
title: Obtenir le texte du lien hypertexte
linktitle: Obtenir le texte du lien hypertexte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire le texte d'un lien hypertexte à partir d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-links-and-actions/get-hyperlink-text/
---

Apprenez à extraire du texte à partir d'hyperliens dans un fichier PDF en utilisant Aspose.PDF pour .NET avec ce guide étape par étape.

## Étape 1 : Configurer l'environnement

Assurez-vous d'avoir configuré votre environnement de développement avec un projet C# et les références Aspose.PDF appropriées.

## Étape 2 : Chargement du fichier PDF

Définissez le chemin du répertoire de vos documents et téléchargez le fichier PDF à l'aide du code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le fichier PDF
Document document = new Document(dataDir + "input.pdf");
```

## Étape 3 : Naviguer dans les pages du document

 Parcourez chaque page du document à l'aide d'un`foreach` boucle:

```csharp
foreach(Page page in document.Pages)
{
     // Afficher les annotations des liens
     ShowLinkAnnotations(page);
}
```

## Étape 4 : Gestion des erreurs

Ajoutez la gestion des erreurs pour intercepter toute exception et afficher le message d'erreur correspondant :

```csharp
catch (Exception ex)
{
     Console.WriteLine(ex.Message);
}
```

### Exemple de code source pour Get Hyperlink Text à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF
	Document document = new Document(dataDir + "input.pdf");
	// Parcourir chaque page du PDF
	foreach (Page page in document.Pages)
	{
		// Afficher l'annotation du lien
		ShowLinkAnnotations(page);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Félicitation ! Vous savez maintenant comment extraire le texte d'un lien hypertexte à partir d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ces connaissances pour gérer les hyperliens dans vos projets et automatiser les tâches liées aux fichiers PDF.

Maintenant que vous avez terminé ce guide, vous pouvez appliquer ces concepts à vos propres projets et explorer davantage les fonctionnalités offertes par Aspose.PDF pour .NET.
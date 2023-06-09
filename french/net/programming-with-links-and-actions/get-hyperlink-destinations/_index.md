---
title: Obtenir des destinations de lien hypertexte
linktitle: Obtenir des destinations de lien hypertexte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire des destinations de liens hypertexte à partir d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-links-and-actions/get-hyperlink-destinations/
---

Aspose.PDF pour .NET est une bibliothèque puissante pour manipuler et extraire des informations à partir de fichiers PDF à l'aide du langage de programmation C#. Dans ce didacticiel, nous nous concentrerons sur l'extraction de destinations de liens hypertexte à partir d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement intégré (IDE) tel que Visual Studio.
- La bibliothèque Aspose.PDF pour .NET installée sur votre machine.

## Étape 1 : Configuration de l'environnement de développement

Avant de commencer à écrire du code, vous devez configurer votre environnement de développement en créant un nouveau projet C# dans votre IDE préféré.

## Étape 2 : Importer les références Aspose.PDF

Pour utiliser Aspose.PDF pour .NET, vous devez ajouter les références appropriées à votre projet. Suivez les étapes ci-dessous pour importer les références nécessaires :

1. Dans votre projet, faites un clic droit sur "Références" et sélectionnez "Ajouter une référence".
2. Dans la fenêtre "Ajouter une référence", recherchez et sélectionnez les fichiers DLL de Aspose.PDF pour .NET.
3. Cliquez sur "OK" pour importer les références dans votre projet.

## Étape 3 : Chargement du fichier PDF

Avant de pouvoir extraire les destinations des liens hypertexte, vous devez charger le fichier PDF dans votre application. Utilisez le code suivant pour charger le fichier PDF :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le fichier PDF
Document document = new Document(dataDir + "input.pdf");
```

Assurez-vous de spécifier le chemin correct vers votre répertoire de documents et le fichier PDF que vous souhaitez traiter.

## Étape 4 : Naviguer dans les pages du document

Maintenant que le fichier PDF est chargé, vous devez parcourir toutes les pages du document. Cela vous permettra d'obtenir

ir les annotations de lien hypertexte présentes sur chaque page. Utilisez le code suivant pour parcourir les pages du document :

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     // Obtenir les annotations de lien d'une page spécifique
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     // Créer une liste pour stocker tous les liens
     IList<Annotation> list = selector. Selected;
     // Parcourez chaque élément de la liste
     foreach(LinkAnnotation a in list)
     {
         // Imprimer l'URL de destination
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Ce code parcourt chaque page du document et sélectionne les annotations de lien hypertexte présentes sur chaque page. Ensuite, il stocke ces annotations dans une liste et imprime l'URL de destination pour chaque lien.

## Étape 5 : Obtention des destinations des liens hypertexte

La dernière étape consiste à extraire les destinations des liens hypertexte à partir des annotations de lien hypertexte. Le code suivant vous montre comment faire :

```csharp
foreach(Aspose.Pdf.Page page in document.Pages)
{
     AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
     page. Accept(selector);
     IList<Annotation> list = selector. Selected;
     foreach(LinkAnnotation a in list)
     {
         string destination = (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI;
         // Utilisez la destination comme vous le souhaitez
     }
}
```

Dans ce code, nous obtenons chaque destination de lien hypertexte à partir des annotations de lien et stockons la destination dans une variable. Vous pourrez ensuite utiliser cette destination comme bon vous semble dans votre application.

### Exemple de code source pour obtenir des destinations de lien hypertexte à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF
	Document document = new Document(dataDir + "input.pdf");
	// Parcourir toute la page du PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Obtenir les annotations de lien d'une page particulière
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Créer une liste contenant tous les liens
		IList<Annotation> list = selector.Selected;
		// Itérer à travers un élément individuel dans la liste
		foreach (LinkAnnotation a in list)
		{
			// Imprimer l'URL de destination
			Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```
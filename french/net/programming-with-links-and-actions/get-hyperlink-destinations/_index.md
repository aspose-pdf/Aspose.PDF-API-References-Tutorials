---
title: Obtenir des destinations de lien hypertexte dans un fichier PDF
linktitle: Obtenir des destinations de lien hypertexte dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire des destinations de liens hypertexte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF pour .NET est une bibliothèque puissante pour manipuler et extraire des informations dans un fichier PDF à l'aide du langage de programmation C#. Dans ce didacticiel, nous nous concentrerons sur l'extraction de destinations de liens hypertexte à partir d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.

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

### FAQ pour obtenir des destinations de lien hypertexte dans un fichier PDF

#### Q : Qu'est-ce qu'une destination de lien hypertexte dans un fichier PDF ?

: Une destination de lien hypertexte dans un fichier PDF est un emplacement ou une cible spécifique vers lequel pointe un lien hypertexte. Il peut s'agir d'une URL, d'une page dans le même document ou d'un document externe.

#### Q : Comment l'extraction de destinations de liens hypertexte peut-elle bénéficier à mon analyse de document PDF ?

R : L'extraction des destinations des liens hypertexte vous permet d'identifier et de cataloguer toutes les cibles vers lesquelles les liens hypertexte pointent dans un document PDF. Ces informations peuvent être utiles pour la validation du contenu, la vérification des liens et l'analyse des données.

#### Q : Comment Aspose.PDF pour .NET aide-t-il à extraire les destinations des liens hypertexte ?

R : Aspose.PDF pour .NET fournit des API puissantes pour extraire facilement des destinations de liens hypertexte. Ce didacticiel montre étape par étape comment extraire des destinations de lien hypertexte à l'aide de C#.

#### Q : Puis-je extraire de manière sélective des destinations de liens hypertexte en fonction de certains critères ?

R : Oui, vous pouvez extraire de manière sélective les destinations des liens hypertexte en parcourant les pages du document PDF et en filtrant les annotations de lien hypertexte souhaitées en fonction de vos critères.

#### Q : Est-il possible d'extraire des destinations de liens hypertexte à partir de documents PDF protégés par mot de passe ?

R : Aspose.PDF pour .NET peut extraire des destinations de liens hypertexte à partir de documents PDF protégés par mot de passe tant que vous fournissez les informations d'authentification nécessaires lors de l'ouverture du document.

#### Q : Comment puis-je utiliser les destinations de liens hypertexte extraites dans mon application ?

R : Une fois que vous avez extrait les destinations des liens hypertexte, vous pouvez les utiliser pour effectuer diverses actions, telles que la validation des URL des liens, la création de rapports ou la mise en œuvre d'une navigation personnalisée.

#### Q : Existe-t-il des limitations lors de l'extraction de destinations de liens hypertexte ?

R : Bien que l'extraction de la destination des liens hypertexte soit puissante, il est essentiel de tenir compte de la structure du document PDF. Les hyperliens intégrés dans des graphiques complexes ou du contenu multimédia peuvent nécessiter une manipulation supplémentaire.

#### Q : Puis-je extraire d'autres attributs d'hyperliens, tels que des types de liens ou des coordonnées ?

R : Le didacticiel se concentre sur l'extraction de destinations de liens hypertexte. Cependant, vous pouvez vous référer à la documentation officielle Aspose.PDF pour explorer les fonctionnalités avancées, y compris l'extraction des types de liens et des coordonnées.
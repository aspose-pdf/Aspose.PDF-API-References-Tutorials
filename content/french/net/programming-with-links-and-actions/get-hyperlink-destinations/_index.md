---
title: Obtenir les destinations des hyperliens dans un fichier PDF
linktitle: Obtenir les destinations des hyperliens dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire les destinations des hyperliens dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-links-and-actions/get-hyperlink-destinations/
---
Aspose.PDF pour .NET est une bibliothèque puissante permettant de manipuler et d'extraire des informations dans un fichier PDF à l'aide du langage de programmation C#. Dans ce didacticiel, nous nous concentrerons sur l'extraction de destinations d'hyperliens à partir d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.

## Prérequis

Avant de commencer, assurez-vous de disposer des éléments suivants :

- Un environnement de développement intégré (IDE) tel que Visual Studio.
- La bibliothèque Aspose.PDF pour .NET installée sur votre machine.

## Étape 1 : Configuration de l’environnement de développement

Avant de commencer à écrire du code, vous devez configurer votre environnement de développement en créant un nouveau projet C# dans votre IDE préféré.

## Étape 2 : Importer les références Aspose.PDF

Pour utiliser Aspose.PDF pour .NET, vous devez ajouter les références appropriées à votre projet. Suivez les étapes ci-dessous pour importer les références nécessaires :

1. Dans votre projet, faites un clic droit sur « Références » et sélectionnez « Ajouter une référence ».
2. Dans la fenêtre « Ajouter une référence », recherchez et sélectionnez les fichiers DLL d’Aspose.PDF pour .NET.
3. Cliquez sur « OK » pour importer les références dans votre projet.

## Étape 3 : Chargement du fichier PDF

Avant de pouvoir extraire les destinations des hyperliens, vous devez charger le fichier PDF dans votre application. Utilisez le code suivant pour charger le fichier PDF :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le fichier PDF
Document document = new Document(dataDir + "input.pdf");
```

Assurez-vous de spécifier le chemin correct vers votre répertoire de documents et le fichier PDF que vous souhaitez traiter.

## Étape 4 : Parcourir les pages du document

Maintenant que le fichier PDF est chargé, vous devez parcourir toutes les pages du document. Cela vous permettra d'obtenir

les annotations des hyperliens présentes sur chaque page. Utilisez le code suivant pour parcourir les pages du document :

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
         // URL de destination d'impression
         Console.WriteLine("\nDestination: " + (a.Action as Aspose.Pdf.Annotations.GoToURIAction).URI + "\n");
     }
}
```

Ce code parcourt chaque page du document et sélectionne les annotations d'hyperlien présentes sur chaque page. Il stocke ensuite ces annotations dans une liste et imprime l'URL de destination de chaque lien.

## Étape 5 : Obtenir les destinations des hyperliens

La dernière étape consiste à extraire les destinations des hyperliens à partir des annotations des hyperliens. Le code suivant vous montre comment procéder :

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

Dans ce code, nous récupérons chaque destination d'hyperlien à partir des annotations de lien et stockons la destination dans une variable. Vous pouvez ensuite utiliser cette destination comme vous le souhaitez dans votre application.

### Exemple de code source pour obtenir les destinations des hyperliens à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Le chemin vers le répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le fichier PDF
	Document document = new Document(dataDir + "input.pdf");
	// Parcourir toutes les pages du PDF
	foreach (Aspose.Pdf.Page page in document.Pages)
	{
		// Obtenir les annotations de lien d'une page particulière
		AnnotationSelector selector = new AnnotationSelector(new Aspose.Pdf.Annotations.LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
		page.Accept(selector);
		// Créer une liste contenant tous les liens
		IList<Annotation> list = selector.Selected;
		// Parcourir un élément individuel à l'intérieur d'une liste
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

### FAQ pour obtenir des destinations de liens hypertexte dans un fichier PDF

#### Q : Quelle est la destination d’un lien hypertexte dans un fichier PDF ?

R : Une destination d'hyperlien dans un fichier PDF est un emplacement ou une cible spécifique vers lequel pointe un hyperlien. Il peut s'agir d'une URL, d'une page au sein du même document ou d'un document externe.

#### Q : Comment l’extraction des destinations des hyperliens peut-elle bénéficier à l’analyse de mes documents PDF ?

R : L'extraction des destinations des hyperliens vous permet d'identifier et de cataloguer toutes les cibles vers lesquelles pointent les hyperliens dans un document PDF. Ces informations peuvent être utiles pour la validation du contenu, la vérification des liens et l'analyse des données.

#### Q : Comment Aspose.PDF pour .NET aide-t-il à extraire les destinations des hyperliens ?

R : Aspose.PDF pour .NET fournit des API puissantes pour extraire facilement les destinations des hyperliens. Ce didacticiel montre étape par étape comment extraire les destinations des hyperliens à l'aide de C#.

#### Q : Puis-je extraire de manière sélective des destinations d’hyperliens en fonction de certains critères ?

R : Oui, vous pouvez extraire de manière sélective les destinations des hyperliens en parcourant les pages du document PDF et en filtrant les annotations d’hyperliens souhaitées en fonction de vos critères.

#### Q : Est-il possible d’extraire les destinations des hyperliens à partir de documents PDF protégés par mot de passe ?

R : Aspose.PDF pour .NET peut extraire les destinations des hyperliens à partir de documents PDF protégés par mot de passe à condition que vous fournissiez les informations d’authentification nécessaires lors de l’ouverture du document.

#### Q : Comment puis-je utiliser les destinations d’hyperliens extraites dans mon application ?

R : Une fois que vous avez extrait les destinations des hyperliens, vous pouvez les utiliser pour effectuer diverses actions, telles que la validation des URL de liens, la création de rapports ou l'implémentation d'une navigation personnalisée.

#### Q : Existe-t-il des limitations lors de l’extraction des destinations des hyperliens ?

R : Bien que l'extraction de la destination des hyperliens soit puissante, il est essentiel de prendre en compte la structure du document PDF. Les hyperliens intégrés dans des graphiques complexes ou du contenu multimédia peuvent nécessiter une gestion supplémentaire.

#### Q : Puis-je extraire d’autres attributs d’hyperliens, tels que les types de liens ou les coordonnées ?

R : Le didacticiel se concentre sur l'extraction des destinations des hyperliens. Cependant, vous pouvez vous référer à la documentation officielle d'Aspose.PDF pour découvrir les fonctionnalités avancées, notamment l'extraction des types de liens et des coordonnées.
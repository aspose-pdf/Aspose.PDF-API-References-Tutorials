---
title: Extraire le texte en surbrillance
linktitle: Extraire le texte en surbrillance
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire le texte en surbrillance à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 60
url: /fr/net/annotations/extracthighlightedtext/
---
Pour extraire le texte en surbrillance d'un document PDF, vous pouvez utiliser l'API Aspose.PDF pour .NET. Cette API fournit un moyen simple de récupérer tout le texte mis en surbrillance dans un document.

## Étape 1 : Chargez le document PDF

 La première étape de l'extraction du texte en surbrillance d'un document PDF consiste à charger le document à l'aide de l'API Aspose.PDF pour .NET. Vous pouvez le faire en créant une nouvelle instance de`Document` class et en transmettant le chemin d'accès au document PDF en tant que paramètre. 

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## Étape 2 : Parcourez toutes les annotations

 L'étape suivante consiste à parcourir toutes les annotations du document PDF. Vous pouvez le faire en utilisant un`foreach` boucle, comme ceci :

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// Le code va ici
}
```

## Étape 3 : Filtrer les annotations de balisage de texte

 À l'intérieur de`foreach` boucle, vous devrez filtrer toutes les annotations qui ne sont pas des annotations de balisage de texte. Vous pouvez le faire en vérifiant si l'annotation est une instance de`TextMarkupAnnotation` classe.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// Le code va ici
}
```

## Étape 4 : Récupérer les fragments de texte en surbrillance

 Une fois que vous avez filtré toutes les annotations de balisage de texte, vous pouvez récupérer les fragments de texte en surbrillance pour chaque annotation. Vous pouvez le faire en appelant le`GetMarkedTextFragments()` méthode sur la`TextMarkupAnnotation` objet.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## Étape 5 : Afficher le texte en surbrillance

 Enfin, vous pouvez afficher le texte en surbrillance à l'utilisateur. Vous pouvez le faire en parcourant chaque`TextFragment` objet dans le`TextFragmentCollection` et appelant le`Text` propriété.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### Exemple de code source pour Extraire le texte en surbrillance à l'aide d'Aspose.PDF pour .NET

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir ="YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

	foreach (Annotation annotation in doc.Pages[1].Annotations)
	{
		if (annotation is TextMarkupAnnotation)
		{
			TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
			TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
			foreach (TextFragment tf in collection)
			{
				Console.WriteLine(tf.Text);
			}
		}
	}
```


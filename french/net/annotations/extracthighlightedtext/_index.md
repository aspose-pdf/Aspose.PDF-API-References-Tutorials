---
title: Extraire le texte en surbrillance dans un fichier PDF
linktitle: Extraire le texte en surbrillance dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à extraire le texte en surbrillance dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 60
url: /fr/net/annotations/extracthighlightedtext/
---
Pour extraire le texte en surbrillance dans un fichier PDF, vous pouvez utiliser l'API Aspose.PDF pour .NET. Cette API fournit un moyen simple de récupérer tout le texte mis en surbrillance dans un document.

## Étape 1 : Chargez le document PDF

 La première étape de l'extraction du texte en surbrillance dans un fichier PDF consiste à charger le document à l'aide de l'API Aspose.PDF pour .NET. Vous pouvez le faire en créant une nouvelle instance de`Document` class et en transmettant le chemin d'accès au document PDF en tant que paramètre. 

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

## Conclusion

Dans ce didacticiel, nous avons exploré comment extraire le texte en surbrillance d'un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant le guide étape par étape et en utilisant le code source C# fourni, les développeurs peuvent facilement extraire et gérer le texte en surbrillance dans leurs documents PDF.

### FAQ pour extraire le texte en surbrillance dans un fichier PDF

#### Q : Que sont les annotations de balisage de texte dans un document PDF ?

R : Les annotations de balisage de texte sont des annotations qui mettent en surbrillance ou marquent un texte spécifique dans un document PDF. Des exemples d'annotations de balisage de texte incluent les surlignages, les soulignements et les barrés.

#### Q : Puis-je extraire du texte d'autres types d'annotations à l'aide d'Aspose.PDF pour .NET ?

R : Oui, Aspose.PDF pour .NET fournit diverses méthodes pour extraire du texte à partir de différents types d'annotations, notamment des annotations de balisage de texte, des annotations de texte libre, etc.

#### Q : Aspose.PDF pour .NET prend-il en charge l'extraction de texte à partir de fichiers PDF protégés par mot de passe ?

 : Oui, Aspose.PDF pour .NET prend en charge l'extraction de texte à partir de fichiers PDF protégés par mot de passe. Vous devez fournir le mot de passe correct lors du chargement du document PDF à l'aide du`Document` classe.

#### Q : Puis-je filtrer le texte en surbrillance en fonction d'autres critères, tels que la couleur ou l'auteur ?

R : Oui, vous pouvez filtrer le texte en surbrillance en fonction d'autres critères, tels que la couleur, l'auteur ou la date de création. Aspose.PDF pour .NET fournit des méthodes pour accéder et filtrer les annotations en fonction de leurs propriétés.

#### Q : Est-il possible d'enregistrer le texte en surbrillance extrait dans un fichier séparé ?

R : Oui, vous pouvez enregistrer le texte en surbrillance extrait dans un fichier séparé ou le stocker dans une structure de données pour un traitement ou une analyse ultérieur(e).

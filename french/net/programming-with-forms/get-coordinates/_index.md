---
title: Obtenir les coordonnées
linktitle: Obtenir les coordonnées
second_title: Référence de l'API Aspose.PDF pour .NET
description: Obtenez facilement les coordonnées des champs de formulaire dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/programming-with-forms/get-coordinates/
---

Dans ce didacticiel, nous allons vous montrer comment obtenir les coordonnées d'un champ de formulaire à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et définissez le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le document de sortie

Chargez le document PDF de sortie :

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Étape 3 : Rechercher les champs ajoutés

Recherchez les champs de formulaire ajoutés (dans cet exemple, nous utilisons les champs "Item1", "Item2" et "Item3") :

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Étape 4 : Afficher les positions des sous-éléments pour chaque champ

Parcourez les options de chaque champ et affichez les coordonnées de chaque sous-élément :

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### Exemple de code source pour Get Coordinates en utilisant Aspose.Words pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Charger le document de sortie
	Document doc1 = new Document( dataDir + "input.pdf");
	// Rechercher des champs ajoutés
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	// Et affichez les positions des sous-éléments pour chacun d'eux.
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à obtenir les coordonnées d'un champ de formulaire à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement récupérer les coordonnées des sous-éléments de vos champs de formulaire dans vos documents PDF à l'aide d'Aspose.PDF.
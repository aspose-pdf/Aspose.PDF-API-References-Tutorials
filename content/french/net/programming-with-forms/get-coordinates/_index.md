---
title: Obtenir les coordonnées du champ du formulaire PDF
linktitle: Obtenir les coordonnées du champ du formulaire PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Obtenez facilement les coordonnées des champs de formulaire PDF dans vos documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/programming-with-forms/get-coordinates/
---
Dans ce tutoriel, nous vous montrerons comment obtenir les coordonnées des champs de formulaire PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# étape par étape pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et défini le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : charger le document de sortie

Charger le document PDF de sortie :

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## Étape 3 : Rechercher les champs ajoutés

Recherchez les champs de formulaire ajoutés (dans cet exemple, nous utilisons les champs « Article1 », « Article2 » et « Article3 ») :

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## Étape 4 : Afficher les positions des sous-éléments pour chaque champ

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

### Exemple de code source pour obtenir des coordonnées à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Le chemin vers le répertoire des documents.
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

Dans ce tutoriel, nous avons appris à obtenir les coordonnées des champs de formulaire à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement récupérer les coordonnées des sous-éléments de vos champs de formulaire dans vos documents PDF à l'aide d'Aspose.PDF.

### FAQ

#### Q : Puis-je utiliser cette méthode pour obtenir les coordonnées de n’importe quel type de champ de formulaire dans Aspose.PDF pour .NET ?

R : Oui, vous pouvez utiliser cette méthode pour obtenir les coordonnées de différents types de champs de formulaire dans Aspose.PDF pour .NET. Le code source C# fourni montre comment obtenir les coordonnées des champs RadioButton, mais vous pouvez adapter la même approche à d'autres types de champs de formulaire, tels que TextBox, CheckBox, ListBox, etc.

#### Q : Comment puis-je modifier ou ajuster les coordonnées du champ de formulaire ?

R : Les coordonnées du champ de formulaire sont basées sur le système de coordonnées du document PDF, où l'origine (0,0) est située dans le coin inférieur gauche de la page. Pour modifier ou ajuster les coordonnées du champ de formulaire, vous pouvez mettre à jour le`Rect` propriété du champ de formulaire respectif ou de ses sous-éléments, tels que RadioButtonOptionField.

#### Q : Puis-je obtenir les coordonnées des champs de formulaire ajoutés par programmation à un document PDF ?

R : Oui, vous pouvez obtenir les coordonnées des champs de formulaire qui ont été ajoutés par programmation à un document PDF. Aspose.PDF pour .NET vous permet d'ajouter des champs de formulaire de manière dynamique et, une fois ajoutés, vous pouvez récupérer leurs coordonnées à l'aide de l'approche présentée dans ce didacticiel.

#### Q : Quel est le but de la récupération des coordonnées des champs de formulaire ?

R : La récupération des coordonnées des champs de formulaire peut être utile lorsque vous devez effectuer des opérations spécifiques liées à la mise en page ou des validations sur les champs de formulaire dans un document PDF. Elle vous permet de positionner et d'aligner avec précision les champs de formulaire en fonction de leurs coordonnées, garantissant ainsi qu'ils s'affichent correctement dans le document et offrent une expérience utilisateur fluide.

#### Q : Les coordonnées du champ de formulaire sont-elles exprimées en points ou dans une autre unité ?

R : Les coordonnées des champs de formulaire dans Aspose.PDF pour .NET sont exprimées en points. Un point équivaut à 1/72 pouce, ce qui en fait une unité de mesure standard au format PDF.
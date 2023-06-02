---
title: Aplatir les formulaires
linktitle: Aplatir les formulaires
second_title: Référence de l'API Aspose.PDF pour .NET
description: Aplatissez facilement les formulaires dans vos documents PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-forms/flatten-forms/
---

Dans ce didacticiel, nous allons vous montrer comment aplatir des formulaires à l'aide d'Aspose.PDF pour .NET. Nous expliquerons étape par étape le code source C # pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'abord d'avoir importé les bibliothèques nécessaires et de définir le chemin d'accès au répertoire des documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Charger le formulaire PDF source

Chargez le formulaire PDF source :

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 3 : Aplatir les formulaires

Vérifiez d'abord s'il y a des champs de formulaire dans le document. Si tel est le cas, parcourez chaque champ et appliquez l'aplatissement :

```csharp
if (doc.Form.Fields.Count() > 0)
{
foreach (var item in doc.Form.Fields)
{
item. Flatten();
}
}
```

## Étape 4 : Enregistrer le document mis à jour

Enregistrez le document PDF mis à jour :

```csharp
dataDir = dataDir + "FlattenForms_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour Flatten Forms en utilisant Aspose.Words pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le formulaire PDF source
Document doc = new Document(dataDir + "input.pdf");
// Aplatir les formulaires
if (doc.Form.Fields.Count() > 0)
{
	foreach (var item in doc.Form.Fields)
	{
		item.Flatten();
	}
}
dataDir = dataDir + "FlattenForms_out.pdf";
// Enregistrer le document mis à jour
doc.Save(dataDir);
Console.WriteLine("\nForms flattened successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons appris à aplatir des formulaires à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement aplatir les formulaires de vos documents PDF, rendre les champs non modifiables et fusionner les annotations avec le contenu du document.
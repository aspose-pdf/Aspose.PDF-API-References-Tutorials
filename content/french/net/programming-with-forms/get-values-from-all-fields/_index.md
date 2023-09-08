---
title: Obtenir les valeurs de tous les champs du document PDF
linktitle: Obtenir les valeurs de tous les champs du document PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Obtenez facilement les valeurs de tous les champs de formulaire dans un document PDF avec Aspose.PDF pour .NET.
type: docs
weight: 150
url: /fr/net/programming-with-forms/get-values-from-all-fields/
---
Dans ce didacticiel, nous allons vous montrer comment obtenir les valeurs de tous les champs de formulaire d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# étape par étape pour vous guider tout au long de ce processus.

## Étape 1 : Préparation

Assurez-vous d'avoir importé les bibliothèques nécessaires et défini le chemin d'accès à votre répertoire de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : ouvrez le document

Ouvrez le document PDF :

```csharp
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
```

## Étape 3 : Obtenez les valeurs de tous les champs

Parcourez tous les champs de formulaire du document et obtenez leurs noms et valeurs :

```csharp
foreach(Field formField in pdfDocument.Form)
{
Console.WriteLine("Field name: {0} ", formField.PartialName);
Console.WriteLine("Value: {0}", formField.Value);
}
```

### Exemple de code source pour obtenir les valeurs de tous les champs à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetValuesFromAllFields.pdf");
// Obtenez les valeurs de tous les champs
foreach (Field formField in pdfDocument.Form)
{
	Console.WriteLine("Field Name : {0} ", formField.PartialName);
	Console.WriteLine("Value : {0} ", formField.Value);
}
```

## Conclusion

Dans ce didacticiel, nous avons appris comment obtenir les valeurs de tous les champs de formulaire d'un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ces étapes, vous pouvez facilement extraire les valeurs de tous les champs de formulaire de vos documents PDF à l'aide d'Aspose.PDF.

### FAQ

#### Q : Puis-je modifier les valeurs des champs de formulaire lors de leur récupération à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, vous pouvez modifier les valeurs des champs de formulaire tout en les récupérant à l'aide d'Aspose.PDF pour .NET. Une fois que vous avez le`Field` objet représentant un champ de formulaire, vous pouvez mettre à jour son`Value`propriété avec la valeur souhaitée. Après avoir apporté les modifications nécessaires, vous pouvez enregistrer le document PDF mis à jour pour refléter les modifications.

#### Q : Comment puis-je filtrer et récupérer des champs de formulaire spécifiques en fonction de leur type (par exemple, champs de texte, cases à cocher) ?

 R : Pour récupérer des champs de formulaire spécifiques en fonction de leurs types, vous pouvez utiliser des instructions conditionnelles ou des requêtes LINQ pour filtrer les champs qui vous intéressent. Vous pouvez vérifier le type de chaque champ du formulaire à l'aide du champ`FieldType` propriété, puis récupérez les valeurs en conséquence.

#### Q : Que se passe-t-il si le document PDF ne comporte aucun champ de formulaire ?

 R : Si le document PDF ne contient aucun champ de formulaire, le`pdfDocument.Form` la propriété renverra une collection vide. Dans de tels cas, la boucle de récupération des valeurs ne s'exécutera pas et aucune valeur ne sera affichée.

#### Q : Puis-je extraire les valeurs des champs du formulaire dans un ordre spécifique ou les trier par ordre alphabétique ?

: L'ordre dans lequel les champs du formulaire sont récupérés dépend de la structure sous-jacente du document PDF. Aspose.PDF pour .NET renvoie les champs du formulaire dans l'ordre dans lequel ils ont été ajoutés au document. Si vous souhaitez afficher ou traiter les champs du formulaire dans un ordre spécifique, vous pouvez implémenter une logique de tri personnalisée en fonction de vos besoins.

#### Q : Comment puis-je gérer des documents PDF cryptés avec des champs de formulaire protégés par mot de passe ?

 R : Aspose.PDF pour .NET fournit des fonctionnalités permettant de travailler avec des documents PDF cryptés et des champs de formulaire protégés par mot de passe. Avant de charger le document, vous pouvez définir le mot de passe à l'aide du`pdfDocument.Password` propriété pour accéder au document PDF sécurisé et à ses champs de formulaire.
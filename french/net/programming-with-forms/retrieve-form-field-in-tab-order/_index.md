---
title: Récupérer le champ du formulaire dans l'ordre des onglets
linktitle: Récupérer le champ du formulaire dans l'ordre des onglets
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à récupérer les champs de formulaire dans l'ordre de tabulation à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 240
url: /fr/net/programming-with-forms/retrieve-form-field-in-tab-order/
---

Lorsque vous travaillez avec des documents PDF en C# à l'aide d'Aspose.PDF pour .NET, vous pouvez rencontrer un scénario dans lequel vous devez récupérer des champs de formulaire dans un ordre de tabulation spécifique. Cela peut être utile lorsque vous souhaitez effectuer des opérations sur des champs de formulaire en fonction de leur séquence de tabulation. Dans ce didacticiel, nous vous guiderons étape par étape sur la façon de récupérer les champs de formulaire dans l'ordre de tabulation à l'aide d'Aspose.PDF pour .NET.

## Exigences

Avant de commencer, assurez-vous d'avoir les prérequis suivants :

- Visual Studio installé sur votre système
- Bibliothèque Aspose.PDF pour .NET installée

Passons maintenant aux étapes pour récupérer les champs de formulaire dans l'ordre de tabulation.

## Étape 1 : Définition du répertoire de documents

Pour commencer, vous devez définir le répertoire de documents où se trouve votre document PDF. Vous pouvez le faire en spécifiant le chemin d'accès au répertoire dans le`dataDir` variable.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 2 : Chargement du document PDF

 Dans cette étape, nous allons charger le document PDF en utilisant Aspose.PDF pour .NET. Le`Document` La classe offre la possibilité de charger et de manipuler des documents PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Ici,`"Test2.pdf"` est le nom du document PDF que vous souhaitez charger. Assurez-vous que le document est présent dans le répertoire de documents spécifié.

## Étape 3 : Récupération des champs de formulaire dans l'ordre de tabulation

 Pour récupérer les champs du formulaire dans l'ordre de tabulation, nous devons accéder au`FieldsInTabOrder` propriété de la`Page` classe. Cette propriété renvoie une liste de champs de formulaire triés par leur séquence de tabulation.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Dans l'extrait de code ci-dessus, nous récupérons les champs du formulaire de la deuxième page (`doc.Pages[1]` ) et parcourir chaque champ pour concaténer leurs noms partiels dans le`s` variable. Vous pouvez modifier cet extrait de code en fonction de vos besoins spécifiques.

## Étape 4 : Modification de l'ordre de tabulation

 Si vous souhaitez modifier l'ordre de tabulation des champs du formulaire, vous pouvez le faire en accédant au`TabOrder` propriété de chaque champ et en attribuant une nouvelle valeur d'ordre de tabulation. Voici un exemple :

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Dans l'extrait de code ci-dessus, nous attribuons de nouvelles valeurs d'ordre de tabulation à trois champs de formulaire (`doc.Form[3]`, `doc.Form[1]` , et`doc.Form[2]`). Ajustez les indices de champ et les valeurs d'ordre de tabulation en fonction de vos besoins spécifiques.

## Étape 5 : Enregistrer le document modifié

 Après avoir modifié l'ordre de tabulation des champs du formulaire, vous devez enregistrer le document modifié. Vous pouvez le faire en utilisant le`Save` méthode de la`Document` classe.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Ici,`"39522_out.pdf"` est le nom du fichier de sortie où sera enregistré le document modifié. Spécifiez le nom et l'emplacement souhaités pour le fichier de sortie.

### Exemple de code source pour Récupérer le champ de formulaire dans l'ordre de tabulation à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Test2.pdf");
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
	s += field.PartialName;
}
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
doc.Save(dataDir + "39522_out.pdf");
Document doc1 = new Document(dataDir + "39522_out.pdf");
s = "";
foreach (Field field in doc1.Pages[1].FieldsInTabOrder)
{
	s += field.PartialName;
}
string index = "";
foreach (Field field in doc1.Form)
{
	index += field.TabOrder;
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à récupérer les champs de formulaire dans l'ordre de tabulation à l'aide d'Aspose.PDF pour .NET. Nous avons couvert les étapes impliquées dans le chargement d'un document PDF, la récupération des champs de formulaire dans l'ordre de tabulation, la modification de l'ordre de tabulation et l'enregistrement du document modifié. En suivant ces étapes, vous pouvez travailler efficacement avec les champs de formulaire et personnaliser leur séquence d'onglets selon vos besoins.
---
title: Récupérer le champ du formulaire dans l'ordre de tabulation
linktitle: Récupérer le champ du formulaire dans l'ordre de tabulation
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment récupérer les champs de formulaire par ordre de tabulation à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 240
url: /fr/net/programming-with-forms/retrieve-form-field-in-tab-order/
---
Lorsque vous travaillez avec des documents PDF en C# à l'aide d'Aspose.PDF pour .NET, vous pouvez rencontrer un scénario dans lequel vous devez récupérer les champs de formulaire dans un ordre de tabulation spécifique. Cela peut être utile lorsque vous souhaitez effectuer des opérations sur des champs de formulaire en fonction de leur séquence de tabulations. Dans ce didacticiel, nous vous guiderons étape par étape sur la façon de récupérer les champs de formulaire par ordre de tabulation à l'aide d'Aspose.PDF pour .NET.

## Exigences

Avant de commencer, assurez-vous d'avoir les prérequis suivants :

- Visual Studio installé sur votre système
- Aspose.PDF pour la bibliothèque .NET installée

Passons maintenant aux étapes pour récupérer les champs du formulaire dans l'ordre de tabulation.

## Étape 1 : Définition du répertoire de documents

 Pour commencer, vous devez définir le répertoire de documents dans lequel se trouve votre document PDF. Vous pouvez le faire en spécifiant le chemin d'accès au répertoire dans le`dataDir` variable.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 2 : Chargement du document PDF

 Dans cette étape, nous chargerons le document PDF à l'aide d'Aspose.PDF pour .NET. Le`Document` La classe offre la possibilité de charger et de manipuler des documents PDF.

```csharp
Document doc = new Document(dataDir + "Test2.pdf");
```

 Ici,`"Test2.pdf"`est le nom du document PDF que vous souhaitez charger. Assurez-vous que le document est présent dans le répertoire de documents spécifié.

## Étape 3 : Récupération des champs de formulaire dans l'ordre de tabulation

 Pour récupérer les champs du formulaire dans l'ordre de tabulation, nous devons accéder au`FieldsInTabOrder` propriété du`Page` classe. Cette propriété renvoie une liste de champs de formulaire triés par leur séquence de tabulations.

```csharp
Page page = doc.Pages[1];
IList<Field> fields = page.FieldsInTabOrder;
string s = "";
foreach (Field field in fields)
{
     s += field. PartialName;
}
```

Dans l'extrait de code ci-dessus, nous récupérons les champs du formulaire de la deuxième page (`doc.Pages[1]` ) et parcourez chaque champ pour concaténer leurs noms partiels dans le`s` variable. Vous pouvez modifier cet extrait de code en fonction de vos besoins spécifiques.

## Étape 4 : Modification de l'ordre de tabulation

 Si vous souhaitez modifier l'ordre de tabulation des champs du formulaire, vous pouvez le faire en accédant à l'onglet`TabOrder` propriété de chaque champ et en attribuant une nouvelle valeur d’ordre de tabulation. Voici un exemple :

```csharp
(doc.Form[3] as Field).TabOrder = 1;
(doc.Form[1] as Field).TabOrder = 2;
(doc.Form[2] as Field).TabOrder = 3;
```

Dans l'extrait de code ci-dessus, nous attribuons de nouvelles valeurs d'ordre de tabulation à trois champs de formulaire (`doc.Form[3]`, `doc.Form[1]` , et`doc.Form[2]`). Ajustez les indices de champ et les valeurs d’ordre de tabulation en fonction de vos besoins spécifiques.

## Étape 5 : Enregistrement du document modifié

 Après avoir modifié l'ordre de tabulation des champs du formulaire, vous devez enregistrer le document modifié. Vous pouvez le faire en utilisant le`Save` méthode du`Document` classe.

```csharp
doc.Save(dataDir + "39522_out.pdf");
```

 Ici,`"39522_out.pdf"` est le nom du fichier de sortie dans lequel le document modifié sera enregistré. Spécifiez le nom et l'emplacement souhaités pour le fichier de sortie.

### Exemple de code source pour récupérer le champ de formulaire dans l'ordre de tabulation à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
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

Dans ce didacticiel, nous avons appris à récupérer les champs de formulaire par ordre de tabulation à l'aide d'Aspose.PDF pour .NET. Nous avons couvert les étapes impliquées dans le chargement d'un document PDF, la récupération des champs de formulaire dans l'ordre de tabulation, la modification de l'ordre de tabulation et l'enregistrement du document modifié. En suivant ces étapes, vous pouvez travailler efficacement avec les champs de formulaire et personnaliser leur séquence d'onglets selon vos besoins.


### FAQ

#### Q : Comment puis-je utiliser les champs de formulaire récupérés dans mon code C# pour un traitement ultérieur ?

 R : Vous pouvez utiliser les champs de formulaire récupérés dans votre code C# en accédant à leurs propriétés telles que`Value`, `Name`, `Rect`etc. Ces propriétés vous permettent de lire et de modifier les données du champ du formulaire selon vos besoins.

#### Q : Puis-je récupérer les champs de formulaire de toutes les pages du document PDF dans l'ordre de tabulation ?

 R : Oui, vous pouvez récupérer les champs de formulaire de toutes les pages du document PDF en parcourant chaque page et en accédant au`FieldsInTabOrder` propriété comme indiqué dans le didacticiel. Cela vous donnera des champs de formulaire triés par leur séquence de tabulations sur toutes les pages.

#### Q : Est-il possible de récupérer uniquement des types spécifiques de champs de formulaire, tels que des champs de texte ou des cases à cocher, par ordre de tabulation ?

R : Oui, vous pouvez filtrer les champs de formulaire en fonction de leurs types, tels que les champs de texte ou les cases à cocher, après les avoir récupérés dans l'ordre de tabulation. Vous pouvez utiliser des instructions conditionnelles pour vérifier le type de chaque champ de formulaire et les traiter en conséquence.

#### Q : Puis-je récupérer les champs du formulaire en fonction de leur nom plutôt que de l'ordre de tabulation ?

 R : Oui, vous pouvez récupérer les champs du formulaire en fonction de leurs noms en utilisant le`doc.Form` collection et en spécifiant le nom du champ comme index. Par exemple,`doc.Form["fieldName"]`récupérera le champ du formulaire avec le nom spécifié.

#### Q : Aspose.PDF pour .NET prend-il en charge l'utilisation de documents PDF cryptés ?

R : Oui, Aspose.PDF pour .NET prend en charge l'utilisation de documents PDF cryptés. Vous pouvez charger et manipuler des fichiers PDF cryptés à l'aide des paramètres de mot de passe appropriés.
---
title: Définir le script Java
linktitle: Définir le script Java
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour définir JavaScript dans les champs de formulaire des fichiers PDF.
type: docs
weight: 270
url: /fr/net/programming-with-forms/set-java-script/
---

Dans ce guide, nous allons expliquer étape par étape comment utiliser la bibliothèque Aspose.PDF pour .NET pour définir JavaScript dans un champ de formulaire d'un document PDF. Nous allons vous montrer comment configurer des actions JavaScript pour effectuer des opérations spécifiques sur le champ de texte.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé sur votre système.
- La bibliothèque Aspose.PDF pour .NET. Vous pouvez le télécharger sur le site officiel d'Aspose.

## Etape 1 : Configuration du répertoire de documents

 La première étape consiste à configurer le répertoire de documents dans lequel se trouve le fichier PDF sur lequel vous souhaitez travailler. Vous pouvez utiliser le`dataDir`variable pour spécifier le chemin du répertoire.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 2 : Chargement du fichier PDF d'entrée

 Dans cette étape, nous allons charger le fichier PDF d'entrée en utilisant le`Document` classe de Aspose.PDF.

```csharp
// Charger le fichier PDF d'entrée
Document doc = new Document(dataDir + "SetJavaScript.pdf");
```

Assurez-vous que le fichier PDF d'entrée est présent dans le répertoire de documents spécifié.

## Étape 3 : Accéder au champ TextBox

 Pour appliquer JavaScript à un champ de texte spécifique, nous devons d'abord accéder à ce champ. Dans cet exemple, nous supposons que le champ de texte s'appelle "textbox1". Utilisez le`doc.Form["textbox1"]` méthode pour obtenir la valeur correspondante`TextBoxField` objet.

```csharp
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
```

Assurez-vous que le champ de texte spécifié existe dans le fichier PDF d'entrée.

## Étape 4 : Configurer les actions JavaScript

 Maintenant que nous avons accédé au champ de texte, nous pouvons configurer les actions JavaScript associées à ce champ. Dans cet exemple, nous utiliserons deux actions :`OnModifyCharacter` et`OnFormat` . Ces actions seront définies à l'aide`JavascriptAction` objets.

```csharp
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
```

Assurez-vous de personnaliser les actions JavaScript en fonction de vos besoins.

## Étape 5 : Définition de la valeur initiale du champ

Avant d'enregistrer le PDF résultant, nous pouvons définir une valeur initiale pour le champ de texte. Dans cet exemple, nous allons définir la valeur "123" pour le champ.

```csharp
field.Value = "123";
```

Personnalisez cette valeur en fonction de vos besoins.

## Étape 6 : Enregistrer le PDF résultant

 Maintenant que nous avons fini de configurer le champ de texte et les actions JavaScript, nous pouvons enregistrer le PDF résultant en utilisant le`Save` méthode de la`Document` classe.

```csharp
dataDir = dataDir + "Restricted_out.pdf";
// Enregistrer le PDF résultant
doc.Save(dataDir);
```

Assurez-vous de spécifier le chemin d'accès complet et le nom de fichier du PDF résultant.


### Exemple de code source pour Set Java Script en utilisant Aspose.Words pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le fichier PDF d'entrée
Document doc = new Document(dataDir + "SetJavaScript.pdf");
TextBoxField field = (TextBoxField)doc.Form["textbox1"];
// 2 chiffres après le point
// Pas de séparateur
// Style négatif = moins
// Pas de devise
field.Actions.OnModifyCharacter = new JavascriptAction("AFNumber_Keystroke(2, 1, 1, 0, \"\", true)");
field.Actions.OnFormat = new JavascriptAction("AFNumber_Format(2, 1, 1, 0, \"\", true)");
// Définir la valeur initiale du champ
field.Value = "123";
dataDir = dataDir + "Restricted_out.pdf";
// Enregistrer le PDF résultant
doc.Save(dataDir);
Console.WriteLine("\nJavaScript on form field setup successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce guide, nous avons appris à utiliser la bibliothèque Aspose.PDF pour .NET afin de définir JavaScript dans un champ de formulaire d'un document PDF. En suivant les étapes décrites, vous pouvez personnaliser les actions JavaScript pour effectuer diverses opérations sur les champs de texte. N'hésitez pas à explorer davantage les fonctionnalités d'Aspose.PDF pour .NET afin d'élargir les possibilités de manipulation des fichiers PDF.
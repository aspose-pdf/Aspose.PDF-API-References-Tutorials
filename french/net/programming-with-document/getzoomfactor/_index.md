---
title: Obtenir le facteur de zoom
linktitle: Obtenir le facteur de zoom
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour obtenir le facteur de zoom d'un fichier PDF avec ce guide étape par étape.
type: docs
weight: 210
url: /fr/net/programming-with-document/getzoomfactor/
---
Aspose.PDF pour .NET est une bibliothèque de manipulation de PDF qui fournit de nombreuses fonctionnalités pour effectuer diverses opérations sur des documents PDF. L'une de ces fonctionnalités est la possibilité d'obtenir le facteur de zoom d'un fichier PDF. Dans ce didacticiel, nous expliquerons comment utiliser Aspose.PDF pour .NET pour obtenir le facteur de zoom d'un fichier PDF à l'aide du code source C#.


## Étape 1 : instanciez le nouvel objet Document

 La première étape pour obtenir le facteur de zoom d'un fichier PDF à l'aide d'Aspose.PDF pour .NET consiste à instancier un nouveau`Document` objet. Le`Document` L'objet représente un document PDF qui peut être chargé à partir d'un fichier ou d'un flux.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier un nouvel objet Document
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Dans le code ci-dessus, nous avons créé un`Document` objet en transmettant le chemin du fichier PDF au constructeur de l'objet`Document` classe. Vous devez remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin réel du répertoire où se trouve votre fichier PDF.

## Étape 2 : Créer un objet GoToAction

 L'étape suivante consiste à créer un`GoToAction` objet. UN`GoToAction` L'objet représente une action qui va vers une destination spécifique dans un document PDF. Dans notre cas, nous voulons obtenir le facteur de zoom du fichier PDF, nous allons donc utiliser le`OpenAction` propriété de la`Document` objet pour obtenir le`GoToAction` objet.

```csharp
// Créer un objet GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 Dans le code ci-dessus, nous avons créé un`GoToAction` objet en jetant le`OpenAction` propriété de la`Document` s'opposer à`GoToAction`.

## Étape 3 : Obtenez le facteur de zoom du fichier PDF

La troisième étape consiste à obtenir le facteur de zoom du fichier PDF. Nous pouvons obtenir le facteur de zoom du fichier PDF en accédant au`Destination` propriété de la`GoToAction` objet, puis le lancer sur`XYZExplicitDestination` . Le`XYZExplicitDestination` La classe représente une destination dans un document PDF qui spécifie les coordonnées et le facteur de zoom à atteindre.

```csharp
// Obtenir le facteur de zoom du fichier PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valeur de zoom du document ;
```

 Dans le code ci-dessus, nous avons accédé au`Destination` propriété de la`GoToAction` objet, puis lancez-le sur`XYZExplicitDestination` . Après cela, nous avons accédé au`Zoom` propriété de la`XYZExplicitDestination` objet pour obtenir le facteur de zoom du fichier PDF.

## Étape 4 : Générer le facteur de zoom

 La dernière étape consiste à générer le facteur de zoom du fichier PDF. Nous pouvons utiliser le`System.Console.WriteLine`

```csharp
// Obtenir le facteur de zoom du fichier PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valeur de zoom du document ;
```        

### Exemple de code source pour obtenir le facteur de zoom à l'aide d'Aspose.PDF pour .NET

Voici l'exemple de code source complet pour Get Zoom Factor en utilisant Aspose.PDF pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instancier un nouvel objet Document
	Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

	// Créer un objet GoToAction
	GoToAction action = doc.OpenAction as GoToAction;
	
	// Obtenir le facteur de zoom du fichier PDF
	System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valeur de zoom du document ;
	
```

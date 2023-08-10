---
title: Obtenir le facteur de zoom dans le fichier PDF
linktitle: Obtenir le facteur de zoom dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour obtenir le facteur de zoom dans un fichier PDF avec ce guide étape par étape.
type: docs
weight: 210
url: /fr/net/programming-with-document/getzoomfactor/
---
Aspose.PDF pour .NET est une bibliothèque de manipulation de PDF qui fournit de nombreuses fonctionnalités pour effectuer diverses opérations sur des documents PDF. L'une de ces fonctionnalités est la possibilité d'obtenir le facteur de zoom dans le fichier PDF. Dans ce didacticiel, nous expliquerons comment utiliser Aspose.PDF pour .NET pour obtenir le facteur de zoom dans un fichier PDF à l'aide du code source C#.


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

 L'étape suivante consiste à créer un`GoToAction` objet. UN`GoToAction`L'objet représente une action qui va vers une destination spécifique dans un document PDF. Dans notre cas, nous voulons obtenir le facteur de zoom du fichier PDF, nous allons donc utiliser le`OpenAction` propriété de la`Document` objet pour obtenir le`GoToAction` objet.

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

## Conclusion

Dans ce tutoriel, nous avons exploré comment utiliser Aspose.PDF pour .NET pour obtenir le facteur de zoom d'un fichier PDF. Le facteur de zoom est un aspect crucial d'un document PDF, car il détermine la taille d'affichage initiale lorsqu'il est ouvert dans une visionneuse. En accédant et en utilisant le facteur de zoom, les développeurs peuvent personnaliser l'expérience de visualisation pour les utilisateurs finaux. Aspose.PDF pour .NET fournit une API simple et efficace pour récupérer le facteur de zoom et d'autres informations liées à la navigation à partir d'un document PDF, permettant aux développeurs de créer des applications PDF riches en fonctionnalités et interactives.

### FAQ pour obtenir le facteur de zoom dans le fichier PDF

#### Q : Quel est le facteur de zoom dans un fichier PDF ?

: Le facteur de zoom dans un fichier PDF fait référence au niveau d'agrandissement appliqué au document lors de sa visualisation. Il détermine la taille d'affichage initiale du fichier PDF à l'écran. Un facteur de zoom de 1,0 représente la taille réelle (zoom 100 %), tandis qu'un facteur de zoom supérieur à 1,0 représente un agrandissement et un facteur de zoom inférieur à 1,0 représente une réduction.

#### Q : Comment puis-je utiliser les informations sur le facteur de zoom dans mon application ?

R : Vous pouvez utiliser les informations sur le facteur de zoom pour personnaliser la taille d'affichage initiale d'un document PDF lorsqu'il est ouvert dans une visionneuse. Par exemple, vous pouvez définir un facteur de zoom spécifique pour vous assurer que le PDF est affiché à une taille particulière ou pour adapter la page entière à la fenêtre du visualiseur.

#### Q : Puis-je modifier le facteur de zoom d'un document PDF par programmation à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, vous pouvez modifier le facteur de zoom d'un document PDF par programme à l'aide d'Aspose.PDF pour .NET. Vous pouvez définir le facteur de zoom pour des actions spécifiques, telles que`GoToAction` ou`GoToRemoteAction`pour contrôler l'affichage du document lorsque l'utilisateur interagit avec des liens ou des signets.

#### Q : Existe-t-il d'autres moyens de naviguer vers des emplacements spécifiques dans un document PDF à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, Aspose.PDF pour .NET fournit diverses fonctionnalités pour naviguer vers des emplacements spécifiques dans un document PDF. En plus d'utiliser`GoToAction` , vous pouvez utiliser d'autres actions comme`GoToURIAction` ouvrir une URL,`GoToEmbeddedAction` pour accéder aux fichiers intégrés, et`GoToNamedAction` pour accéder aux destinations nommées dans le document PDF.
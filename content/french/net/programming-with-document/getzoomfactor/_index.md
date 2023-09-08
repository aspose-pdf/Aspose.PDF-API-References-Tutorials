---
title: Obtenez le facteur de zoom dans un fichier PDF
linktitle: Obtenez le facteur de zoom dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment utiliser Aspose.PDF pour .NET pour obtenir le facteur de zoom dans un fichier PDF avec ce guide étape par étape.
type: docs
weight: 210
url: /fr/net/programming-with-document/getzoomfactor/
---
Aspose.PDF pour .NET est une bibliothèque de manipulation PDF qui fournit de nombreuses fonctionnalités pour effectuer diverses opérations sur les documents PDF. L'une de ces fonctionnalités est la possibilité d'obtenir le facteur de zoom dans un fichier PDF. Dans ce didacticiel, nous expliquerons comment utiliser Aspose.PDF pour .NET pour obtenir le facteur de zoom dans un fichier PDF à l'aide du code source C#.


## Étape 1 : Instancier un nouvel objet Document

 La première étape pour obtenir le facteur de zoom d'un fichier PDF à l'aide d'Aspose.PDF pour .NET consiste à instancier un nouveau fichier.`Document` objet. Le`Document` L'objet représente un document PDF pouvant être chargé à partir d'un fichier ou d'un flux.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier un nouvel objet Document
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

 Dans le code ci-dessus, nous avons créé un`Document` objet en passant le chemin du fichier PDF au constructeur du`Document` classe. Vous devez remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel du répertoire où se trouve votre fichier PDF.

## Étape 2 : Créer un objet GoToAction

 La prochaine étape consiste à créer un`GoToAction` objet. UN`GoToAction`L'objet représente une action qui va vers une destination spécifique dans un document PDF. Dans notre cas, nous voulons obtenir le facteur de zoom du fichier PDF, nous utiliserons donc le`OpenAction` propriété du`Document` s'opposer à obtenir le`GoToAction` objet.

```csharp
// Créer un objet GoToAction
GoToAction action = doc.OpenAction as GoToAction;
```

 Dans le code ci-dessus, nous avons créé un`GoToAction` objet en lançant le`OpenAction` propriété du`Document` s'opposer à`GoToAction`.

## Étape 3 : Obtenez le facteur de zoom du fichier PDF

 La troisième étape consiste à obtenir le facteur de zoom du fichier PDF. Nous pouvons obtenir le facteur de zoom du fichier PDF en accédant au`Destination` propriété du`GoToAction` objet, puis le lancer vers`XYZExplicitDestination` . Le`XYZExplicitDestination` La classe représente une destination dans un document PDF qui spécifie les coordonnées et le facteur de zoom vers lesquels accéder.

```csharp
// Obtenez le facteur de zoom du fichier PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valeur de zoom du document ;
```

 Dans le code ci-dessus, nous avons accédé au`Destination` propriété du`GoToAction` objet, puis lancez-le vers`XYZExplicitDestination` . Après cela, nous avons accédé au`Zoom` propriété du`XYZExplicitDestination` objet pour obtenir le facteur de zoom du fichier PDF.

## Étape 4 : Afficher le facteur de zoom

 La dernière étape consiste à générer le facteur de zoom du fichier PDF. Nous pouvons utiliser le`System.Console.WriteLine`

```csharp
// Obtenez le facteur de zoom du fichier PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valeur de zoom du document ;
```        

### Exemple de code source pour obtenir le facteur de zoom à l'aide d'Aspose.PDF pour .NET

Voici l'exemple complet de code source pour obtenir un facteur de zoom à l'aide d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier un nouvel objet Document
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

// Créer un objet GoToAction
GoToAction action = doc.OpenAction as GoToAction;

// Obtenez le facteur de zoom du fichier PDF
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); // Valeur de zoom du document ;
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment utiliser Aspose.PDF pour .NET pour obtenir le facteur de zoom d'un fichier PDF. Le facteur de zoom est un aspect crucial d'un document PDF, car il détermine la taille d'affichage initiale lors de son ouverture dans une visionneuse. En accédant et en utilisant le facteur de zoom, les développeurs peuvent personnaliser l'expérience de visualisation pour les utilisateurs finaux. Aspose.PDF pour .NET fournit une API simple et efficace pour récupérer le facteur de zoom et d'autres informations liées à la navigation à partir d'un document PDF, permettant ainsi aux développeurs de créer des applications PDF interactives et riches en fonctionnalités.

### FAQ pour obtenir le facteur de zoom dans un fichier PDF

#### Q : Quel est le facteur de zoom dans un fichier PDF ?

R : Le facteur de zoom dans un fichier PDF fait référence au niveau d'agrandissement appliqué au document lors de sa visualisation. Il détermine la taille d'affichage initiale du fichier PDF à l'écran. Un facteur de zoom de 1,0 représente la taille réelle (zoom 100 %), tandis qu'un facteur de zoom supérieur à 1,0 représente un agrandissement et un facteur de zoom inférieur à 1,0 représente une réduction.

#### Q : Comment puis-je utiliser les informations sur le facteur de zoom dans mon application ?

R : Vous pouvez utiliser les informations sur le facteur de zoom pour personnaliser la taille d'affichage initiale d'un document PDF lorsqu'il est ouvert dans une visionneuse. Par exemple, vous pouvez définir un facteur de zoom spécifique pour garantir que le PDF est affiché à une taille particulière ou adapter la page entière à la fenêtre de la visionneuse.

#### Q : Puis-je modifier le facteur de zoom d'un document PDF par programme à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, vous pouvez modifier le facteur de zoom d'un document PDF par programmation à l'aide d'Aspose.PDF pour .NET. Vous pouvez définir le facteur de zoom pour des actions spécifiques, telles que`GoToAction` ou`GoToRemoteAction`pour contrôler la façon dont le document est affiché lorsque l'utilisateur interagit avec des liens ou des signets.

#### Q : Existe-t-il d'autres moyens de naviguer vers des emplacements spécifiques dans un document PDF à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, Aspose.PDF pour .NET fournit diverses fonctionnalités pour accéder à des emplacements spécifiques dans un document PDF. En plus d'utiliser`GoToAction` , vous pouvez utiliser d'autres actions comme`GoToURIAction` pour ouvrir une URL,`GoToEmbeddedAction` pour accéder aux fichiers intégrés, et`GoToNamedAction` pour accéder aux destinations nommées dans le document PDF.
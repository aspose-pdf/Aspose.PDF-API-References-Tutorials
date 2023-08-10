---
title: Définir le facteur de zoom dans le fichier PDF
linktitle: Définir le facteur de zoom dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir le facteur de zoom dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec notre guide étape par étape.
type: docs
weight: 340
url: /fr/net/programming-with-document/setzoomfactor/
---
Aspose.PDF pour .NET est une API puissante qui permet aux développeurs de travailler avec des documents PDF dans leurs applications .NET. L'une des fonctionnalités qu'il offre est la possibilité de définir le facteur de zoom d'un document PDF. Dans ce guide étape par étape, nous expliquerons comment utiliser Aspose.PDF pour .NET pour définir le facteur de zoom d'un document PDF à l'aide du code source C# fourni.

## Étape 1 : Définissez le chemin d'accès au répertoire de documents

 La première étape consiste à définir le chemin d'accès au répertoire où se trouve le document PDF. Cela peut être fait en réglant le`dataDir` variable au chemin du répertoire. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 2 : instanciez un nouvel objet Document

 Pour travailler avec un document PDF en utilisant Aspose.PDF pour .NET, nous devons créer un nouveau`Document` objet et chargez-y le fichier PDF. 

```csharp
Document doc = new Document(dataDir + "SetZoomFactor.pdf");
```

 Ce code va créer un nouveau`Document` objet et chargez le fichier PDF nommé "SetZoomFactor.pdf" à partir du`dataDir` répertoire dans celui-ci.

## Étape 3 : Définir le facteur de zoom

 Une fois la`Document`objet est créé, nous pouvons définir le facteur de zoom du document PDF. Dans le code suivant, nous définissons le facteur de zoom sur 50 %.

```csharp
GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
```

 Ce code fixe le facteur de zoom à 50 % en créant un nouveau`GoToAction` objet et en passant un`XYZExplicitDestination` objet avec un facteur de zoom de 50 %. Le`OpenAction` propriété de la`Document` l'objet est alors défini sur this`GoToAction` objet.

## Étape 4 : Enregistrez le document PDF

 Enfin, nous pouvons enregistrer le document PDF modifié dans un nouveau fichier. Dans le code suivant, nous enregistrons le document PDF dans un nouveau fichier nommé "Zoomed_pdf_out.pdf" dans le`dataDir` annuaire.

```csharp
dataDir = dataDir + "Zoomed_pdf_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour Définir le facteur de zoom à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier un nouvel objet Document
Document doc = new Document(dataDir + "SetZoomFactor.pdf");

GoToAction action = new GoToAction(new XYZExplicitDestination(1, 0, 0, .5));
doc.OpenAction = action;
dataDir = dataDir + "Zoomed_pdf_out.pdf";
// Enregistrer le document
doc.Save(dataDir);
```

## Conclusion

Aspose.PDF pour .NET fournit un moyen simple et efficace de définir le facteur de zoom d'un document PDF à l'aide de code C#. En suivant les étapes ci-dessus, vous pouvez facilement modifier le facteur de zoom de n'importe quel document PDF dans votre application .NET.

### FAQ

#### Q : Qu'est-ce que le facteur de zoom dans un document PDF et comment affecte-t-il l'affichage ?

R : Le facteur de zoom dans un document PDF détermine le niveau d'agrandissement lorsque le document est affiché. Il spécifie l'échelle à laquelle le document est affiché, affectant la taille ou la taille du contenu affiché à l'écran. Un facteur de zoom de 1,0 représente un zoom de 100 % (taille réelle), tandis qu'un facteur supérieur à 1,0 effectue un zoom avant et un facteur inférieur à 1,0 effectue un zoom arrière.

#### Q : Puis-je définir un facteur de zoom spécifique pour différentes pages d'un même document PDF ?

 R : Oui, avec Aspose.PDF pour .NET, vous pouvez définir différents facteurs de zoom pour différentes pages dans le même document PDF. L'exemple de code source fourni montre comment définir le facteur de zoom pour la première page à l'aide de la`GoToAction` objet. Vous pouvez modifier le code pour définir différents facteurs de zoom pour d'autres pages selon vos besoins.

#### Q : Comment la modification du facteur de zoom affecte-t-elle l'impression et l'enregistrement du document PDF ?

R : La modification du facteur de zoom à l'aide d'Aspose.PDF pour .NET n'affecte pas le contenu réel du document PDF lui-même. Cela n'affecte l'expérience de visualisation que lorsque le document est ouvert dans une visionneuse PDF. Le facteur de zoom défini par programmation n'aura aucun impact sur la sortie imprimée ou le fichier PDF enregistré.
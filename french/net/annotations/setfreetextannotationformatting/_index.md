---
title: Définir la mise en forme libre des annotations de texte
linktitle: Définir la mise en forme libre des annotations de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Cet article fournit un guide étape par étape sur la façon de créer une annotation de texte libre et de spécifier son contenu à l'aide d'Aspose.PDF pour .NET
type: docs
weight: 140
url: /fr/net/annotations/setfreetextannotationformatting/
---
Aspose.PDF pour .NET est une API de manipulation de documents PDF puissante et facile à utiliser qui vous permet de travailler avec des fichiers PDF par programmation dans vos applications .NET. L'une des fonctionnalités fournies par Aspose.PDF pour .NET est la possibilité de définir une mise en forme d'annotation de texte libre dans les documents PDF. Dans cet article, nous vous guiderons pas à pas dans le processus de définition du formatage d'annotation de texte libre à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous que vous disposez des prérequis suivants :

- Microsoft Visual Studio 2010 ou version ultérieure
- Aspose.PDF pour .NET
- Connaissance de base de C#



## Étape 1 : Créer une nouvelle application de console C#

Tout d'abord, créez une nouvelle application console C# dans Microsoft Visual Studio. Pour créer une nouvelle application console, sélectionnez "Fichier" > "Nouveau" > "Projet" > "Visual C#" > "Application console" dans le menu principal.

## Étape 2 : Ajouter une référence à Aspose.PDF pour .NET

Ensuite, ajoutez une référence à Aspose.PDF pour .NET dans votre projet. Pour ce faire, faites un clic droit sur votre projet dans le volet "Explorateur de solutions", sélectionnez "Ajouter" > "Référence", puis accédez à l'emplacement où vous avez enregistré le fichier DLL Aspose.PDF pour .NET. Sélectionnez le fichier DLL et cliquez sur "OK" pour ajouter la référence à votre projet.

## Étape 3 : Configurer l'environnement

Après avoir ajouté la référence à Aspose.PDF pour .NET, vous devez configurer l'environnement. Pour ce faire, créez une nouvelle variable de chaîne appelée "dataDir" et définissez-la sur le chemin du répertoire où se trouve votre document PDF. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" dans le code ci-dessous par le chemin réel de votre répertoire de documents :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 4 : Ouvrez le document PDF

Une fois que vous avez configuré l'environnement, vous pouvez ouvrir le document PDF en utilisant le code suivant :

```csharp
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Remplacez "SetFreeTextAnnotationFormatting.pdf" par le nom réel de votre document PDF.

## Étape 5 : Configurer l'apparence par défaut

Pour configurer l'apparence par défaut de l'annotation de texte libre, vous devez instancier l'objet DefaultAppearance avec la police, la taille de police et la couleur souhaitées. Dans ce didacticiel, nous définissons la police sur "Arial", la taille de la police sur 28 et la couleur sur le rouge.

```csharp
// Instancier l'objet DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## Étape 6 : Créer une annotation de texte libre

Maintenant que vous avez configuré l'apparence par défaut, vous pouvez créer une annotation de texte libre à l'aide du code suivant :

```csharp
// Créer une annotation
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Le code ci-dessus crée une nouvelle annotation de texte libre sur la deuxième page du document PDF. L'annotation sera positionnée à (200, 400) et aura une largeur de 400 et une hauteur de 600.

## Étape 7 : Spécifiez le contenu de l'annotation

Après avoir créé l'annotation de texte libre, vous pouvez spécifier le contenu de l'annotation à l'aide du code suivant :

```csharp
// Spécifier le contenu de l'annotation
freetext.Contents = "Free Text
```

### Exemple de code source pour définir la mise en forme d'annotation de texte libre à l'aide d'Aspose.PDF pour .NET
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");

// Instancier l'objet DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
// Créer une annotation
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
// Spécifier le contenu de l'annotation
freetext.Contents = "Free Text";
// Ajouter une annotation à la collection d'annotations de la page
pdfDocument.Pages[1].Annotations.Add(freetext);
dataDir = dataDir + "SetFreeTextAnnotationFormatting_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);            
```

## Conclusion

Dans ce didacticiel, nous avons appris à définir la mise en forme d'annotation de texte libre dans un document PDF à l'aide d'Aspose.PDF pour .NET. La bibliothèque offre un moyen simple et efficace de travailler avec des documents PDF par programmation, permettant aux développeurs de créer et de personnaliser divers types d'annotations, y compris des annotations de texte libre. En suivant le guide étape par étape et en utilisant le code source C# fourni, vous pouvez facilement configurer l'environnement, ouvrir un document PDF et créer une annotation de texte libre avec une mise en forme personnalisée. Aspose.PDF pour .NET est une API robuste et fiable qui simplifie les tâches de manipulation de documents PDF, ce qui en fait un outil précieux pour les développeurs .NET travaillant avec des fichiers PDF.

### FAQ

#### Q : Qu'est-ce qu'une annotation de texte libre dans un document PDF ?

R : Une annotation de texte libre dans un document PDF est un type d'annotation qui vous permet d'ajouter du texte au document sans être lié à un emplacement ou à une structure spécifique. Il est couramment utilisé pour fournir des commentaires, des notes ou d'autres informations supplémentaires dans le document.

#### Q : Puis-je personnaliser l'apparence de l'annotation de texte libre à l'aide d'Aspose.PDF pour .NET ?

R : Oui, vous pouvez personnaliser diverses propriétés de l'annotation de texte libre, telles que la police, la taille de la police, la couleur, la position, etc.

#### Q : Comment spécifier le contenu de l'annotation de texte libre ?

 R : Pour spécifier le contenu de l'annotation de texte libre, vous pouvez définir le`Contents` propriété de la`FreeTextAnnotation` s'opposer au texte souhaité.

#### Q : Puis-je ajouter plusieurs annotations de texte libre à un document PDF à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, vous pouvez créer plusieurs annotations de texte libre dans un document PDF en créant plusieurs instances du`FreeTextAnnotation`objet et en les ajoutant à différentes pages ou emplacements dans le document.
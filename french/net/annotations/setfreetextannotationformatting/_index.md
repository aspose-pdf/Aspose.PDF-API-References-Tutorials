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



## 1. Créer une nouvelle application console C#

Tout d'abord, créez une nouvelle application console C# dans Microsoft Visual Studio. Pour créer une nouvelle application console, sélectionnez "Fichier" > "Nouveau" > "Projet" > "Visual C#" > "Application console" dans le menu principal.

## 2. Ajouter une référence à Aspose.PDF pour .NET

Ensuite, ajoutez une référence à Aspose.PDF pour .NET dans votre projet. Pour ce faire, faites un clic droit sur votre projet dans le volet "Explorateur de solutions", sélectionnez "Ajouter" > "Référence", puis accédez à l'emplacement où vous avez enregistré le fichier DLL Aspose.PDF pour .NET. Sélectionnez le fichier DLL et cliquez sur "OK" pour ajouter la référence à votre projet.

## 3. Configurer l'environnement

Après avoir ajouté la référence à Aspose.PDF pour .NET, vous devez configurer l'environnement. Pour ce faire, créez une nouvelle variable de chaîne appelée "dataDir" et définissez-la sur le chemin du répertoire où se trouve votre document PDF. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" dans le code ci-dessous par le chemin réel de votre répertoire de documents :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4. Ouvrez le document PDF

Une fois que vous avez configuré l'environnement, vous pouvez ouvrir le document PDF en utilisant le code suivant :

```csharp
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SetFreeTextAnnotationFormatting.pdf");
```

Remplacez "SetFreeTextAnnotationFormatting.pdf" par le nom réel de votre document PDF.

## 5. Configurer l'apparence par défaut

Pour configurer l'apparence par défaut de l'annotation de texte libre, vous devez instancier l'objet DefaultAppearance avec la police, la taille de police et la couleur souhaitées. Dans ce didacticiel, nous définissons la police sur "Arial", la taille de la police sur 28 et la couleur sur le rouge.

```csharp
// Instancier l'objet DefaultAppearance
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 28, System.Drawing.Color.Red);
```

## 6. Créez une annotation de texte libre

Maintenant que vous avez configuré l'apparence par défaut, vous pouvez créer une annotation de texte libre à l'aide du code suivant :

```csharp
// Créer une annotation
FreeTextAnnotation freetext = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600), default_appearance);
```

Le code ci-dessus crée une nouvelle annotation de texte libre sur la deuxième page du document PDF. L'annotation sera positionnée à (200, 400) et aura une largeur de 400 et une hauteur de 600.

## 7. Spécifiez le contenu de l'annotation

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
	//Enregistrer le document mis à jour
	pdfDocument.Save(dataDir);            
 
```

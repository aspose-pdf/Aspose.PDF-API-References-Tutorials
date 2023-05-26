---
title: Ajouter un fichier SWF en tant qu'annotation
linktitle: Ajouter un fichier SWF en tant qu'annotation
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter des fichiers SWF en tant qu'annotations dans Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 30
url: /fr/net/annotations/addswffileasannotation/
---
Si vous êtes un développeur .NET cherchant à ajouter un fichier multimédia SWF en tant qu'annotation à votre document PDF à l'aide d'Aspose.PDF pour .NET, ce guide étape par étape est fait pour vous. Dans cet article, nous expliquerons comment ajouter des fichiers SWF en tant qu'annotations dans vos documents PDF à l'aide du langage de programmation C#. 

Suivez les étapes ci-dessous pour ajouter un fichier SWF en tant qu'annotation dans votre document PDF à l'aide d'Aspose.PDF pour .NET :

## Étape 1 : Définissez le chemin du répertoire

Tout d'abord, nous devons définir le chemin du répertoire où le fichier PDF et le fichier SWF sont stockés. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès à votre répertoire de documents.

## Étape 2 : Chargez le document PDF

Ensuite, nous devons charger le document PDF en utilisant le code suivant :

```csharp
Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");
```

Ce code chargera le fichier "AddSwfFileAsAnnotation.pdf" à partir du répertoire du document.

## Étape 3 : Obtenir la page pour ajouter une annotation

Maintenant, nous devons obtenir la référence de la page à laquelle nous voulons ajouter l'annotation. Dans ce didacticiel, nous allons ajouter l'annotation à la première page du document.

```csharp
Page page = doc.Pages[1];
```

## Étape 4 : Créer un objet ScreenAnnotation

 Nous pouvons maintenant créer un`ScreenAnnotation` objet avec le fichier SWF comme argument.

```csharp
ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");
```

 Le`ScreenAnnotation` constructeur prend trois arguments :

- `page`: La page à laquelle l'annotation sera ajoutée.
- `rectangle`: Le rectangle dans lequel le fichier SWF sera affiché sur la page.
- `dataDir + "input.swf"`: chemin d'accès au fichier SWF.

## Étape 5 : Ajouter l'annotation à la page

Maintenant, nous pouvons ajouter l'annotation à la collection d'annotations de la page.

```csharp
page.Annotations.Add(annotation);
```

## Étape 6 : Enregistrez le document PDF mis à jour

Enfin, nous devons enregistrer le document PDF mis à jour avec l'annotation en utilisant le code suivant :

```csharp
dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
doc.Save(dataDir);
```

Ce code enregistrera le document PDF mis à jour avec l'annotation "AddSwfFileAsAnnotation_out.pdf" dans le répertoire du document.

### Exemple de code source pour l'ajout d'un fichier SWF en tant qu'annotation à l'aide d'Aspose.PDF pour .NET

```csharp
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Ouvrir le document PDF
	Document doc = new Document(dataDir + "AddSwfFileAsAnnotation.pdf");

	// Obtenir la référence de la page à laquelle vous devez ajouter l'annotation
	Page page = doc.Pages[1];

	// Créer un objet ScreenAnnotation avec un fichier multimédia .swf comme argument
	ScreenAnnotation annotation = new ScreenAnnotation(page, new Aspose.Pdf.Rectangle(0, 400, 600, 700), dataDir + "input.swf");

	// Ajouter l'annotation à la collection d'annotations de la page
	page.Annotations.Add(annotation);

	dataDir = dataDir + "AddSwfFileAsAnnotation_out.pdf";
	// Enregistrer le document PDF de mise à jour avec annotation
	doc.Save(dataDir);
```        

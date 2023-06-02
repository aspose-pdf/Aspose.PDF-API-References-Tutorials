---
title: Obtenir toutes les annotations de la page
linktitle: Obtenir toutes les annotations de la page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour récupérer toutes les annotations d'une page PDF avec ce guide étape par étape.
type: docs
weight: 70
url: /fr/net/annotations/getallannotationsfrompage/
---
Cet article vous guidera tout au long du processus d'extraction de toutes les annotations d'une page PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de créer, modifier et convertir des documents PDF. Avec l'aide de ce guide, vous pourrez obtenir toutes les annotations d'une page PDF spécifique en utilisant le code source C# fourni.

Suivez les étapes ci-dessous pour obtenir toutes les annotations d'une page PDF à l'aide d'Aspose.PDF pour .NET :

## Étape 1 : Le chemin d'accès au répertoire des documents

La première étape pour obtenir toutes les annotations d'une page PDF à l'aide d'Aspose.PDF pour .NET consiste à définir le chemin d'accès au répertoire de documents dans lequel vos fichiers PDF sont stockés. Vous pouvez le faire en modifiant la ligne de code suivante :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## Étape 2 : Vos fichiers PDF sont stockés

Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès au dossier dans lequel vos fichiers PDF sont stockés. Par exemple:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## Étape 3 : Ouvrir le document

L'étape suivante consiste à ouvrir le document PDF contenant les annotations que vous souhaitez extraire. Vous pouvez le faire en ajoutant le code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

Cette ligne de code initialise une nouvelle instance de la classe Document et charge le document PDF "GetAllAnnotationsFromPage.pdf". Remplacez ce nom de fichier par le nom de votre fichier PDF.

## Étape 4 : parcourir toutes les annotations

Une fois que vous avez ouvert le document PDF, vous pouvez parcourir toutes les annotations sur une page spécifique. Par exemple, pour parcourir toutes les annotations de la première page du document PDF, ajoutez le code suivant :

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // Le code va ici
}
```

Ce code parcourt toutes les annotations de la première page du document PDF et attribue chaque annotation à la variable "annotation".

## Étape 5 : Obtenir les propriétés d'annotation

Pour extraire les propriétés de chaque annotation, vous pouvez ajouter le code suivant dans la boucle foreach :

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

Ce code écrit le titre, le sujet et le contenu de chaque annotation dans la console.

### Exemple de code source pour obtenir toutes les annotations de la page à l'aide d'Aspose.PDF pour .NET

Voici le code source complet pour obtenir toutes les annotations d'une page PDF en utilisant Aspose.PDF pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// Parcourez toutes les annotations
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// Obtenir les propriétés d'annotation
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```

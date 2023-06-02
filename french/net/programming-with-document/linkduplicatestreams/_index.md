---
title: Lier les flux en double
linktitle: Lier les flux en double
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour la fonction .NET Link Duplicate Streams pour optimiser vos documents PDF avec ce guide étape par étape.
type: docs
weight: 230
url: /fr/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF pour .NET est une bibliothèque complète et puissante qui fournit une variété de fonctionnalités pour travailler avec des fichiers PDF. L'une de ses principales caractéristiques est la possibilité d'optimiser les fichiers PDF. Dans cet article, nous expliquerons comment utiliser la fonctionnalité Lier les flux en double d'Aspose.PDF pour .NET pour optimiser les fichiers PDF. Nous fournirons des instructions étape par étape et inclurons un exemple de code source complet pour faciliter le suivi des développeurs.

## Étape 1 : Ouverture du document PDF

Pour ouvrir le document PDF à l'aide d'Aspose.PDF pour .NET, suivez ces étapes :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

Dans le code ci-dessus, remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès au répertoire de votre projet.

## Étape 2 : Définition de l'option LinkDuplicateStreams

Pour définir l'option LinkDuplicateStreams, procédez comme suit :

```csharp
// Définir l'option LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

Dans le code ci-dessus, nous avons créé une nouvelle instance de OptimizationOptions et défini l'option LinkDuplicateStreams sur true.

## Étape 3 : Optimisation du document PDF

Pour optimiser le document PDF, procédez comme suit :

```csharp
// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

Dans le code ci-dessus, nous avons utilisé la méthode OptimizeResources de l'objet pdfDocument pour optimiser le document PDF à l'aide des OptimizationOptions que nous avons créées précédemment.

## Étape 4 : Enregistrer le document mis à jour

Pour enregistrer le document mis à jour, procédez comme suit :

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
```

Dans le code ci-dessus, nous avons utilisé la méthode Save de l'objet pdfDocument pour enregistrer le document mis à jour dans un nouveau fichier nommé "OptimizeDocument_out.pdf" dans le répertoire du projet.

### Exemple de code source pour relier des flux en double à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Définir l'option LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// Optimiser le document PDF à l'aide d'OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
```

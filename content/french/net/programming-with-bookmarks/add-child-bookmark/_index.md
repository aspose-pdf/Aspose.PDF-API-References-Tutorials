---
title: Ajouter un signet enfant dans un fichier PDF
linktitle: Ajouter un signet enfant dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Ajoutez facilement un signet enfant dans un fichier PDF pour une navigation plus organisée avec Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-bookmarks/add-child-bookmark/
---
L'ajout de signets enfants dans un fichier PDF permet une organisation et une navigation plus structurées. Avec Aspose.PDF pour .NET, vous pouvez facilement ajouter un sous-signet en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF auquel vous souhaitez ajouter un sous-signet. Remplacer`"YOUR DOCUMENT DIRECTORY"`dans le code suivant avec le chemin réel de votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF auquel nous souhaitons ajouter un sous-signet en utilisant le code suivant :

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## Étape 4 : Créer un objet de signet parent

 Dans cette étape, nous allons créer un objet signet parent en utilisant le`OutlineItemCollection` classe et définissez ses propriétés telles que le titre, l'attribut italique et l'attribut gras. Voici le code correspondant :

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## Étape 5 : Créer un objet de signet enfant

Dans cette étape, nous allons créer à nouveau un objet sous-signet en utilisant le`OutlineItemCollection` classe et définir ses propriétés. Voici le code correspondant :

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## Étape 6 : Ajouter le sous-signet au signet parent

 Enfin, nous ajoutons le sous-signet créé à la collection de sous-signets du signet parent en utilisant le`Add` méthode de l’objet parent. Voici le code correspondant :

```csharp
pdfOutline.Add(pdfChildOutline);
```

## Étape 7 : Ajouter le signet parent à la collection de signets du document

 Enfin, nous ajoutons le signet parent à la collection de signets du document en utilisant le`Add` méthode du`Outlines` propriété. Voici le code correspondant :

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### Exemple de code source pour Ajouter un signet enfant à l’aide d’Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// Créer un objet signet parent
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// Créer un objet signet enfant
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// Ajouter un signet enfant dans la collection du signet parent
pdfOutline.Add(pdfChildOutline);
// Ajoutez un signet parent dans la collection de plans du document.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// Enregistrer la sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous disposez maintenant d'un guide étape par étape pour ajouter un sous-signet avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour organiser et structurer vos signets dans vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de manipulation de signets.

### FAQ pour ajouter un signet enfant dans un fichier PDF

#### Q : Que sont les signets enfants dans un fichier PDF ?

R : Les signets enfants, également appelés sous-signets, sont des éléments de navigation dans un document PDF qui sont structurés hiérarchiquement sous un signet parent. Ils permettent de créer une table des matières plus organisée et détaillée pour le document.

#### Q : Comment importer les bibliothèques nécessaires pour mon projet C# ?

R : Pour importer les bibliothèques requises pour votre projet C#, vous pouvez utiliser la directive d'importation suivante :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Ces bibliothèques fournissent les classes et fonctions nécessaires pour travailler avec des documents PDF et des fonctionnalités interactives.

#### Q : Comment puis-je spécifier le chemin d'accès au dossier de documents ?

 R : Dans le code source fourni, vous devez remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel du dossier contenant le fichier PDF avec lequel vous souhaitez travailler. Cela garantit que le code localise correctement le fichier PDF cible.

#### Q : Puis-je créer plusieurs niveaux de favoris enfants ?

R : Oui, vous pouvez créer plusieurs niveaux de signets enfants en étendant le processus décrit dans le didacticiel. En créant des signets parents avec des sous-signets et en les imbriquant davantage, vous pouvez créer une structure hiérarchique de signets pour les documents PDF complexes.

####  Q : Quel est le but du`OutlineItemCollection` class?

 R : Le`OutlineItemCollection` La classe Aspose.PDF pour .NET est utilisée pour créer et gérer des plans, qui sont essentiellement des signets dans un document PDF. Cette classe vous permet de définir des propriétés telles que le titre, le style de police et les actions des signets.

#### Q : Comment ajouter un sous-signet à un signet parent ?

 R : Pour ajouter un sous-signet à un signet parent, vous créez un nouveau`OutlineItemCollection` objet pour le sous-signet et définissez ses propriétés. Ensuite, vous utilisez le`Add` méthode du signet parent`OutlineItemCollection` pour ajouter le sous-signet à la collection parent.

#### Q : Puis-je personnaliser l’apparence des favoris enfants ?

R : Oui, comme pour les signets parents, vous pouvez personnaliser l'apparence des signets enfants en définissant des propriétés telles que le titre, le style de police et d'autres attributs. Cela vous permet de créer des signets visuellement distinctifs et informatifs.

#### Q : Aspose.PDF pour .NET est-il compatible avec d'autres langages de programmation ?

R : Aspose.PDF pour .NET est spécialement conçu pour les environnements C# et .NET. Cependant, Aspose propose des bibliothèques similaires pour d'autres langages de programmation tels que Java et Android, chacun adapté à leurs plates-formes respectives.

#### Q : Comment les signets enfants améliorent-ils la navigation dans les PDF ?

R : Les signets enfants améliorent la navigation dans les PDF en fournissant une table des matières plus structurée et organisée. Les utilisateurs peuvent accéder rapidement à des sections spécifiques du document via la structure hiérarchique des signets.
---
title: Définir l'image comme arrière-plan
linktitle: Définir l'image comme arrière-plan
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour définir une image comme arrière-plan de page dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-pdf-pages/image-as-background/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus de définition d'une image comme arrière-plan de page à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment ajouter une image en arrière-plan de page dans un document PDF à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où vous souhaitez enregistrer votre document PDF modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Créer un nouveau document
 Ensuite, vous pouvez créer un nouvel objet Document en utilisant le`Document` classe.

```csharp
Document doc = new Document();
```

## Étape 3 : Ajouter une nouvelle page au document
 Vous pouvez maintenant ajouter une nouvelle page à l'objet Document à l'aide de la`Add()` méthode de la`Pages` classe.

```csharp
Page page = doc.Pages.Add();
```

## Étape 4 : Créer un objet Artefact d'arrière-plan
Ensuite, vous pouvez créer un nouvel objet BackgroundArtifact pour définir l'image d'arrière-plan.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## Étape 5 : Ajoutez l'arrière-plan à la page
 Ensuite, vous pouvez ajouter l'objet BackgroundArtifact à la collection d'artefacts de la page à l'aide de l'objet`Artifacts` propriété de la`Page` classe.

```csharp
page. Artifacts. Add(background);
```

## Étape 6 : Enregistrez le document PDF
 Enfin, vous pouvez enregistrer le document PDF dans un fichier à l'aide de la`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### Exemple de code source pour Image en arrière-plan à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer un nouvel objet Document
Document doc = new Document();
// Ajouter une nouvelle page à l'objet document
Page page = doc.Pages.Add();
// Créer un objet d'artefact d'arrière-plan
BackgroundArtifact background = new BackgroundArtifact();
// Spécifiez l'image pour l'objet backgroundartifact
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// Ajouter un artefact d'arrière-plan à la collection d'artefacts de la page
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// Enregistrer le document
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## Conclusion
Dans ce didacticiel, nous avons appris à définir une image comme arrière-plan de page dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ce guide étape par étape, vous pouvez facilement ajouter une image d'arrière-plan à vos documents PDF. Aspose.PDF offre une API puissante et flexible pour travailler avec des fichiers PDF, y compris la personnalisation de l'arrière-plan de la page. Vous pouvez maintenant appliquer cette fonctionnalité dans vos propres projets pour créer des documents PDF avec des images d'arrière-plan personnalisées

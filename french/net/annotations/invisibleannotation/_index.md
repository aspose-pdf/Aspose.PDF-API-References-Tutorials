---
title: Annotations invisibles
linktitle: Annotations invisibles
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à annoter des PDF de manière invisible à l'aide du code source C# avec Aspose.PDF pour .NET. Guide étape par étape.
type: docs
weight: 100
url: /fr/net/annotations/invisibleannotation/
---
## Comprendre les annotations dans les documents PDF

Les annotations dans les documents PDF sont une fonctionnalité puissante qui vous permet d'ajouter des informations supplémentaires ou des notes à un document sans modifier le contenu réel. Ils peuvent être utilisés pour mettre en surbrillance du texte, attirer l'attention sur des zones spécifiques d'un document ou ajouter des commentaires ou des réactions.

Il existe de nombreux types d'annotations que vous pouvez utiliser dans les documents PDF, notamment :

- Annotations de texte
- Annotations de lien
- Annotations de tampon
- Annotations sonores
- Annotations des pièces jointes
- et beaucoup plus

## Création d'une annotation invisible dans un document PDF à l'aide d'Aspose.PDF pour .NET

 Pour créer une annotation invisible dans un document PDF à l'aide d'Aspose.PDF pour .NET, nous devons d'abord créer un`FreeTextAnnotation` objet et spécifiez l'emplacement et la taille de l'annotation.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Dans le code ci-dessus, nous créons un`FreeTextAnnotation`objet et indiquez l'emplacement de l'annotation sur la page 2 du document PDF. Nous spécifions également le type de police, la taille et la couleur du texte qui sera affiché dans l'annotation.

## Ajout de caractéristiques à l'annotation invisible

Ensuite, nous pouvons ajouter certaines caractéristiques à l'annotation, telles qu'une couleur de bordure, une couleur d'arrière-plan ou une opacité.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Dans le code ci-dessus, nous définissons la couleur de la bordure de l'annotation sur rouge.

## Définition des drapeaux d'annotation

Après avoir créé l'annotation et défini ses caractéristiques, nous pouvons spécifier les drapeaux d'annotation. Dans ce didacticiel, nous voulons que l'annotation soit imprimable, mais pas visible.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
```

## Enregistrement du document PDF modifié

Enfin, nous pouvons enregistrer le document PDF modifié avec la nouvelle annotation invisible.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Exemple de code source pour savoir comment réaliser une annotation invisible à l'aide d'Aspose.PDF pour .NET

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1
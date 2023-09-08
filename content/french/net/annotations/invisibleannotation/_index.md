---
title: Annotation invisible dans un fichier PDF
linktitle: Annotation invisible dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Apprenez à masquer des annotations dans un fichier PDF à l'aide du code source C# avec Aspose.PDF pour .NET. Guide étape par étape.
type: docs
weight: 100
url: /fr/net/annotations/invisibleannotation/
---
Les annotations dans un fichier PDF sont une fonctionnalité puissante qui vous permet d'ajouter des informations ou des notes supplémentaires à un document sans modifier le contenu réel. Ils peuvent être utilisés pour surligner du texte, attirer l’attention sur des zones spécifiques d’un document ou ajouter des commentaires ou des retours.

Il existe de nombreux types d'annotations que vous pouvez utiliser dans les documents PDF, notamment :

- Annotations de texte
- Annotations de liens
- Annotations de tampon
- Annotations sonores
- Annotations des pièces jointes
- et beaucoup plus

## Étape 1 : Création d'une annotation invisible dans un document PDF à l'aide d'Aspose.PDF pour .NET

 Pour créer une annotation invisible dans un document PDF à l'aide d'Aspose.PDF pour .NET, nous devons d'abord créer un`FreeTextAnnotation` objet et spécifiez l’emplacement et la taille de l’annotation.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 Dans le code ci-dessus, nous créons un`FreeTextAnnotation`objet et précisez l’emplacement de l’annotation sur la page 2 du document PDF. Nous spécifions également le type de police, la taille et la couleur du texte qui sera affiché dans l'annotation.

## Étape 2 : ajout de caractéristiques à l'annotation invisible

Ensuite, nous pouvons ajouter quelques caractéristiques à l'annotation, comme une couleur de bordure, une couleur d'arrière-plan ou une opacité.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

Dans le code ci-dessus, nous définissons la couleur de la bordure de l'annotation sur rouge.

## Étape 3 : Définition des indicateurs d'annotation

Après avoir créé l'annotation et défini ses caractéristiques, nous pouvons spécifier les indicateurs d'annotation. Dans ce didacticiel, nous souhaitons que l'annotation soit imprimable, mais non visible.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## Étape 4 : Enregistrement du document PDF modifié

Enfin, nous pouvons enregistrer le document PDF modifié avec la nouvelle annotation invisible.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## Exemple de code source pour savoir comment créer une annotation invisible à l'aide d'Aspose.PDF pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// Enregistrer le fichier de sortie
doc.Save(dataDir);
// ExEnd : Annotation invisible
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons appris à créer une annotation invisible dans un document PDF à l'aide d'Aspose.PDF pour .NET. Les annotations invisibles sont une fonctionnalité utile lorsque vous souhaitez ajouter des informations ou des notes supplémentaires à un document sans les afficher au lecteur. En suivant le guide étape par étape et en utilisant le code source C# fourni, les développeurs peuvent facilement créer et personnaliser des annotations invisibles dans leurs documents PDF. Aspose.PDF pour .NET fournit un ensemble complet d'outils pour travailler avec des annotations, vous permettant d'améliorer l'interactivité et la convivialité de vos fichiers PDF.

### FAQ

#### Q : Qu'est-ce qu'une annotation invisible dans un document PDF ?

R : Une annotation invisible dans un document PDF est une annotation qui n'est pas visible sur la page mais qui contient des informations ou des notes supplémentaires. Il vous permet d'ajouter des commentaires ou des retours sans les afficher au lecteur.

#### Q : Quels types de caractéristiques peuvent être ajoutés à une annotation invisible ?

R : Diverses caractéristiques peuvent être ajoutées à une annotation invisible, telles que la couleur de la bordure, la couleur de l'arrière-plan, l'opacité, le type de police, la taille et la couleur du texte qui sera affiché.

#### Q : Puis-je définir différents indicateurs d'annotation pour une annotation invisible ?

R : Oui, vous pouvez définir différents indicateurs d'annotation pour une annotation invisible, en fonction de vos besoins. Par exemple, vous pouvez rendre l'annotation imprimable mais non visible.

#### Q : Comment puis-je ajouter une annotation invisible à une page spécifique du document PDF ?

 R : Pour ajouter une annotation invisible à une page spécifique du document PDF, vous devez créer un`FreeTextAnnotation` objet et spécifiez l’emplacement et la taille de l’annotation sur cette page.

#### Q : Puis-je modifier les caractéristiques d'une annotation invisible existante dans un fichier PDF ?

: Oui, vous pouvez modifier les caractéristiques d'une annotation invisible existante dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez modifier le type de police, la taille, la couleur, la couleur de la bordure, la couleur d'arrière-plan, l'opacité et d'autres propriétés de l'annotation.
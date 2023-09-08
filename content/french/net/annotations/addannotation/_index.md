---
title: Ajouter une annotation PDF
linktitle: Ajouter une annotation
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter des annotations texte PDF avec Aspose.PDF pour .NET à l'aide de ce code source C#. Personnalisez vos annotations avec des détails et des icônes spécifiques.
type: docs
weight: 10
url: /fr/net/annotations/addannotation/
---
L'ajout d'annotations aux documents PDF est une fonctionnalité puissante qui peut améliorer les processus de collaboration et de révision. Aspose.PDF pour .NET facilite l'ajout d'annotations par programmation aux documents PDF à l'aide de C#. Dans ce guide, nous expliquerons étape par étape comment utiliser Aspose.PDF pour .NET pour ajouter des annotations à un document PDF.

## Étape 1 : Créez un nouveau projet et installez Aspose.PDF pour .NET

Avant de commencer à écrire le code pour ajouter des annotations, nous devons créer un nouveau projet et installer Aspose.PDF pour .NET. Pour installer Aspose.PDF pour .NET, suivez ces étapes :

1. Ouvrez Visual Studio et créez un nouveau projet C#.
2. Cliquez avec le bouton droit sur le projet dans l'Explorateur de solutions et sélectionnez « Gérer les packages NuGet ».
3. Recherchez « Aspose.PDF » et sélectionnez « Installer ».

Une fois l'installation terminée, nous pouvons commencer à écrire le code.

## Étape 2 : ouvrez le document PDF

La première étape pour ajouter des annotations consiste à ouvrir le document PDF. Nous pouvons utiliser le code suivant pour ouvrir le document :

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

Dans ce code, nous spécifions le chemin d'accès au document PDF que nous souhaitons ouvrir. Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DONNÉES » par le chemin réel de votre répertoire de données.

## Étape 3 : Créer l'annotation

 Pour ajouter une annotation, nous devons créer une nouvelle instance du`TextAnnotation` classe. Nous pouvons utiliser le code suivant pour créer une nouvelle annotation de texte :

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

Dans ce code, nous créons une nouvelle annotation de texte sur la deuxième page du document PDF. Nous définissons également les propriétés de titre, de sujet, d'état, de contenu, d'ouverture et d'icône de l'annotation.

## Étape 4 : Personnaliser l'annotation

 Nous pouvons personnaliser l'apparence de l'annotation à l'aide du`Border` classe. Nous pouvons utiliser le code suivant pour personnaliser la bordure de l'annotation :

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 Dans ce code, nous créons un nouveau`Border`objet et définissez ses propriétés de largeur et de tiret. Nous fixons ensuite le`Border` propriété de l'annotation au nouveau`Border` objet. Enfin, nous fixons le`Rect` propriété de l’annotation pour spécifier sa position et sa taille.

## Étape 5 : ajouter l'annotation au document PDF

Une fois que nous avons créé et personnalisé l'annotation, nous devons l'ajouter au document PDF. Nous pouvons utiliser le code suivant pour ajouter l'annotation au document PDF :

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

Dans ce code, nous ajoutons l'annotation à la collection d'annotations de la deuxième page du document PDF.

## Étape 6 : Enregistrez le fichier de sortie

Enfin, nous devons enregistrer le document PDF avec l'annotation ajoutée. Nous pouvons utiliser le code suivant pour enregistrer le fichier de sortie :

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### Exemple de code source pour l'ajout d'une annotation à l'aide d'Aspose.PDF pour .NET


```csharp   
 // Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DATA DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// Créer une annotation
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// Ajouter une annotation dans la collection d'annotations de la page
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// Enregistrer le fichier de sortie
pdfDocument.Save(dataDir);
```
Ce code montre comment ajouter une annotation de texte avec un titre, un sujet, un état, un contenu et une icône spécifiques à une page PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez modifier ce code selon vos besoins pour ajouter des annotations à vos documents PDF. N'oubliez pas de remplacer VOTRE RÉPERTOIRE DE DONNÉES par le chemin du répertoire réel où se trouve votre fichier PDF et où vous souhaitez enregistrer le fichier de sortie.

## Conclusion

L'ajout d'annotations aux documents PDF à l'aide d'Aspose.PDF pour .NET offre un outil précieux pour améliorer les processus de collaboration et de révision de documents. En suivant le guide étape par étape fourni dans cet article, les développeurs peuvent intégrer de manière transparente des fonctionnalités d'annotation dans leurs applications C#.

### FAQ

#### Q : Quels types d'annotations peuvent être ajoutés à l'aide d'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET prend en charge différents types d'annotations, notamment les annotations de texte, les tampons, les liens, les formes, etc. Les développeurs peuvent personnaliser l'apparence et les propriétés de ces annotations en fonction de leurs besoins spécifiques.

#### Q : Puis-je ajouter des annotations à des pages spécifiques dans un document PDF de plusieurs pages ?

R : Oui, Aspose.PDF pour .NET vous permet de spécifier la page sur laquelle vous souhaitez ajouter l'annotation. Vous pouvez choisir une page spécifique ou ajouter des annotations à plusieurs pages selon vos besoins.

#### Q : Comment personnaliser l'apparence des annotations ?

R : Les annotations peuvent être personnalisées à l'aide de propriétés telles que la largeur de la bordure, la couleur, le style de tiret, le style de texte, etc. Aspose.PDF pour .NET fournit un riche ensemble d'options pour personnaliser l'apparence des annotations.

#### Q : Est-il possible d'ajouter des hyperliens sous forme d'annotations à l'aide d'Aspose.PDF pour .NET ?

R : Oui, vous pouvez ajouter des hyperliens sous forme d'annotations aux documents PDF à l'aide d'Aspose.PDF pour .NET. Les annotations de liens hypertextes peuvent être utilisées pour créer des liens vers des URL externes ou des emplacements spécifiques dans le même document.

#### Q : Des annotations peuvent-elles être ajoutées à des documents PDF existants sans altérer le contenu original ?

: Oui, Aspose.PDF pour .NET ajoute des annotations en tant qu'éléments supplémentaires sans altérer le contenu original du document PDF. Le contenu PDF original reste intact.
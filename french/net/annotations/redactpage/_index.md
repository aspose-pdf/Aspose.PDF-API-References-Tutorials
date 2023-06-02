---
title: Caviarder la page
linktitle: Caviarder la page
second_title: Référence de l'API Aspose.PDF pour .NET
description: Cet article explique comment rédiger une page PDF à l'aide d'Aspose.PDF pour .NET, y compris des instructions détaillées et un exemple de code source.
type: docs
weight: 120
url: /fr/net/annotations/redactpage/
---
Si vous cherchez à expurger des informations sensibles d'un document PDF en utilisant Aspose.PDF pour .NET, vous avez de la chance ! Voici un guide étape par étape pour vous aider à démarrer :

## Étape 1 : Dans le code, définissez le chemin d'accès au répertoire où se trouve votre document PDF :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF :

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 3 : Créez une instance RedactionAnnotation pour une région de page spécifique :

```csharp
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
```

## Étape 4 : Définissez la couleur de remplissage, la couleur de la bordure et la couleur du texte de l'annotation de rédaction :

```csharp
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
```

## Étape 5 : Définissez le texte à imprimer sur l'annotation de rédaction et son alignement :

```csharp
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## Étape 6 : Répétez le texte superposé sur l'annotation de rédaction :

```csharp
annot.Repeat = true;
```

## Étape 7 : Ajoutez l'annotation à la collection d'annotations de la première page :

```csharp
doc.Pages[1].Annotations.Add(annot);
```

## Étape 8 : Aplatissez l'annotation et censurez le contenu de la page, c'est-à-dire supprimez le texte et les images sous l'annotation censurée :

```csharp
annot.Redact();
```

## Étape 9 : Définissez le chemin et le nom du fichier PDF de sortie :

```csharp
dataDir = dataDir + "RedactPage_out.pdf";
```

## Étape 10 : Enregistrez le document PDF avec la page expurgée :

```csharp
doc.Save(dataDir);
```

C'est ça! Vous avez réussi à expurger une page de votre document PDF en utilisant Aspose.PDF pour .NET.

### Exemple de code source pour Redact Page utilisant Aspose.PDF pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document doc = new Document(dataDir + "input.pdf");

// Créer une instance RedactionAnnotation pour une région de page spécifique
RedactionAnnotation annot = new RedactionAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(200, 500, 300, 600));
annot.FillColor = Aspose.Pdf.Color.Green;
annot.BorderColor = Aspose.Pdf.Color.Yellow;
annot.Color = Aspose.Pdf.Color.Blue;
// Texte à imprimer sur l'annotation expurgée
annot.OverlayText = "REDACTED";
annot.TextAlignment = Aspose.Pdf.HorizontalAlignment.Center;
// Repat Superposer le texte sur l'annotation biffée
annot.Repeat = true;
// Ajouter une annotation à la collection d'annotations de la première page
doc.Pages[1].Annotations.Add(annot);
//Aplatit les annotations et caviarde le contenu de la page (c'est-à-dire supprime le texte et l'image
// Sous annotation expurgée)
annot.Redact();
dataDir = dataDir + "RedactPage_out.pdf";
doc.Save(dataDir);
```
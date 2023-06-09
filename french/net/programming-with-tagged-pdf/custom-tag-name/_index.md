---
title: Nom de balise personnalisé
linktitle: Nom de balise personnalisé
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour utiliser un nom de balise personnalisé avec Aspose.PDF pour .NET. Améliorez la structure de vos PDF avec des balises personnalisées.
type: docs
weight: 90
url: /fr/net/programming-with-tagged-pdf/custom-tag-name/
---
Dans ce guide étape par étape, nous vous expliquerons comment utiliser un nom de balise personnalisé avec Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de manipuler des documents PDF par programmation. L'utilisation de balises personnalisées vous permet d'ajouter des informations structurelles spécifiques à votre document PDF, ce qui en facilite l'utilisation et l'accès.

Plongeons-nous dans le code et apprenons à utiliser un nom de balise personnalisé avec Aspose.PDF pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Bibliothèque Aspose.PDF pour .NET installée.
2. Une connaissance de base du langage de programmation C#.

## Étape 1 : Configurer l'environnement

Pour commencer, ouvrez votre environnement de développement C# et créez un nouveau projet. Assurez-vous d'avoir ajouté une référence à la bibliothèque Aspose.PDF pour .NET dans votre projet.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document

 La première étape consiste à créer un nouveau document PDF à l'aide de`Document` classe.

```csharp
// Créer le document PDF
Document document = new Document();
```

## Étape 3 : Travailler avec du contenu balisé

Ensuite, nous obtenons le contenu balisé du document avec lequel travailler.

```csharp
// Obtenir le contenu balisé du document
ITaggedContent taggedContent = document.TaggedContent;
```

## Étape 4 : Définissez le titre et la langue du document

Nous pouvons maintenant définir le titre et la langue du document.

```csharp
// Définir le titre et la langue du document
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Étape 5 : Créer des éléments de structure logique

Créons maintenant des éléments de structure logique pour organiser notre contenu.

```csharp
// Créer des éléments de structure logique
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1.");
p2.SetText("P2.");
p3.SetText("P3.");
p4.SetText("P4.");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);
```

Ici, nous créons des éléments de paragraphe et des éléments d'étendue pour notre contenu, et nous leur attribuons des balises personnalisées.

## Étape 6 : Enregistrer le document PDF balisé

Enfin, nous enregistrons le document PDF balisé.

```csharp
// Enregistrer le document PDF balisé
document.Save(dataDir + "CustomTag.pdf");
```

### Exemple de code source pour le nom de balise personnalisé à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un document PDF
Document document = new Document();

// Obtenir du contenu pour travailler avec TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Définir le titre et la langue pour Documnet
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");

// Créer des éléments de structure logique
SectElement sect = taggedContent.CreateSectElement();
taggedContent.RootElement.AppendChild(sect);
ParagraphElement p1 = taggedContent.CreateParagraphElement();
ParagraphElement p2 = taggedContent.CreateParagraphElement();
ParagraphElement p3 = taggedContent.CreateParagraphElement();
ParagraphElement p4 = taggedContent.CreateParagraphElement();
p1.SetText("P1. ");
p2.SetText("P2. ");
p3.SetText("P3. ");
p4.SetText("P4. ");
p1.SetTag("P1");
p2.SetTag("Para");
p3.SetTag("Para");
p4.SetTag("Paragraph");
sect.AppendChild(p1);
sect.AppendChild(p2);
sect.AppendChild(p3);
sect.AppendChild(p4);
SpanElement span1 = taggedContent.CreateSpanElement();
SpanElement span2 = taggedContent.CreateSpanElement();
SpanElement span3 = taggedContent.CreateSpanElement();
SpanElement span4 = taggedContent.CreateSpanElement();
span1.SetText("Span 1.");
span2.SetText("Span 2.");
span3.SetText("Span 3.");
span4.SetText("Span 4.");
span1.SetTag("SPAN");
span2.SetTag("Sp");
span3.SetTag("Sp");
span4.SetTag("TheSpan");
p1.AppendChild(span1);
p2.AppendChild(span2);
p3.AppendChild(span3);
p4.AppendChild(span4);

// Enregistrer le document PDF balisé
document.Save(dataDir + "CustomTag.pdf");

```

## Conclusion

Félicitation ! Vous avez appris à utiliser un nom de balise personnalisé avec Aspose.PDF pour .NET. Vous pouvez désormais ajouter des informations structurelles spécifiques à votre document PDF à l'aide de balises personnalisées. Explorez plus de fonctionnalités d'Aspose.PDF pour découvrir tout son potentiel.

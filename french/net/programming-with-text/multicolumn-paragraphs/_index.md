---
title: Paragraphes multicolonnes
linktitle: Paragraphes multicolonnes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à travailler avec des paragraphes multicolonnes dans un document PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 250
url: /fr/net/programming-with-text/multicolumn-paragraphs/
---

Dans ce didacticiel, nous expliquerons comment travailler avec des paragraphes multicolonnes dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons passer par le processus étape par étape de manipulation et d'accès aux paragraphes multicolonnes à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire où se trouve votre fichier PDF d'entrée. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès à votre fichier PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le document PDF

 Ensuite, nous chargeons le document PDF d'entrée à l'aide de la`Document` classe de la bibliothèque Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
```

## Étape 3 : Accéder aux paragraphes multicolonnes

 Nous utilisons le`ParagraphAbsorber` classe pour absorber et visiter les paragraphes du document PDF. Nous récupérons ensuite les balises de la page et accédons aux paragraphes multicolonnes.

```csharp
ParagraphAbsorber absorb = new ParagraphAbsorber();
absorb.Visit(doc);
PageMarkup markup = absorb.PageMarkups[0];
```

## Étape 4 : Travailler avec des paragraphes multicolonnes

Nous accédons à des sections et paragraphes spécifiques dans la structure multicolonne et imprimons leur texte.

```csharp
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");

// Accéder au dernier paragraphe d'une section
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Accéder au premier paragraphe d'une section
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Activer les paragraphes multicolonnes
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");

// Accéder au dernier paragraphe d'une section après avoir activé les paragraphes multicolonnes
section = markup. Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);

// Accéder au premier paragraphe d'une section après avoir activé les paragraphes multicolonnes
section = markup. Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

### Exemple de code source pour les paragraphes multicolonnes à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "MultiColumnPdf.pdf");
ParagraphAbsorber absorber = new ParagraphAbsorber();
absorber.Visit(doc);
PageMarkup markup = absorber.PageMarkups[0];
Console.WriteLine("IsMulticolumnParagraphsAllowed == false\r\n");
MarkupSection section = markup.Sections[2];
MarkupParagraph paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
markup.IsMulticolumnParagraphsAllowed = true;
Console.WriteLine("\r\nIsMulticolumnParagraphsAllowed == true\r\n");
section = markup.Sections[2];
paragraph = section.Paragraphs[section.Paragraphs.Count - 1];
Console.WriteLine("Section at {0} last paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
section = markup.Sections[1];
paragraph = section.Paragraphs[0];
Console.WriteLine("\r\nSection at {0} first paragraph text:\r\n", section.Rectangle.ToString());
Console.WriteLine(paragraph.Text);
```

## Conclusion

Dans ce didacticiel, vous avez appris à travailler avec des paragraphes multicolonnes dans un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez accéder et manipuler des paragraphes multicolonnes dans un document PDF.
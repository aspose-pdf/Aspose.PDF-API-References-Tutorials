---
title: Créer des éléments de structure
linktitle: Créer des éléments de structure
second_title: Référence de l'API Aspose.PDF pour .NET
description: Dans ce didacticiel, vous apprendrez à utiliser Aspose.PDF pour .NET pour créer des éléments structurels dans un document PDF balisé.
type: docs
weight: 60
url: /fr/net/programming-with-tagged-pdf/create-structure-elements/
---
Le code source C# suivant utilise Aspose.PDF pour .NET pour créer des éléments de structure. Suivez les étapes ci-dessous pour comprendre le fonctionnement du code.

## Étape 1 : Importer les bibliothèques nécessaires

```csharp
using Aspose.Pdf;
```

## Etape 2 : Définir le répertoire de vos documents

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Assurez-vous de spécifier le chemin correct vers votre répertoire de documents.

## Étape 3 : Créer un document PDF

```csharp
Document document = new Document();
```

Nous créons un nouvel objet Document qui représente le document PDF.

## Étape 4 : Faites en sorte que le contenu fonctionne avec TaggedPdf

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

Nous récupérons le contenu balisé du document PDF. Cela nous permettra de manipuler des éléments structurels.

## Étape 5 : Définissez le titre et la langue du document

```csharp
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Nous définissons le titre et la langue du document PDF balisé. Cela améliore l'accessibilité du document.

## Étape 6 : Créer des éléments de regroupement

```csharp
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
```

Nous créons différents éléments structurels pour regrouper le contenu dans le document PDF.

## Étape 7 : Créer des éléments de structure de paragraphe

```csharp
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
```

Nous créons des éléments structurels au niveau du bloc pour les paragraphes et les titres. L'exemple ci-dessus montre la création d'un en-tête de niveau 1.

## Étape 8 : Créer des éléments de structure de niveau en ligne

```csharp
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
```

Nous créons des éléments de structure de niveau en ligne pour les parties de texte qui apparaissent à l'intérieur d'un paragraphe ou d'un titre.

## Étape 9 : Créer des éléments de structure d'illustration

```csharp
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
```

Nous créons des éléments de structure pour les illustrations et les formules mathématiques présentes dans le document.

## Étape 10 : Enregistrer le document PDF balisé

```csharp
document.Save(dataDir + "StructureElements.pdf");
```

Nous enregistrons le document PDF balisé avec les éléments de structure créés.

### Exemple de code source pour créer des éléments de structure à l'aide d'Aspose.PDF pour .NET 

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
// Créer des éléments de regroupement
PartElement partElement = taggedContent.CreatePartElement();
ArtElement artElement = taggedContent.CreateArtElement();
SectElement sectElement = taggedContent.CreateSectElement();
DivElement divElement = taggedContent.CreateDivElement();
BlockQuoteElement blockQuoteElement = taggedContent.CreateBlockQuoteElement();
CaptionElement captionElement = taggedContent.CreateCaptionElement();
TOCElement tocElement = taggedContent.CreateTOCElement();
TOCIElement tociElement = taggedContent.CreateTOCIElement();
IndexElement indexElement = taggedContent.CreateIndexElement();
NonStructElement nonStructElement = taggedContent.CreateNonStructElement();
PrivateElement privateElement = taggedContent.CreatePrivateElement();
// Créer des éléments de structure au niveau du bloc de texte
ParagraphElement paragraphElement = taggedContent.CreateParagraphElement();
HeaderElement headerElement = taggedContent.CreateHeaderElement();
HeaderElement h1Element = taggedContent.CreateHeaderElement(1);
//Créer des éléments de structure de texte en ligne
SpanElement spanElement = taggedContent.CreateSpanElement();
QuoteElement quoteElement = taggedContent.CreateQuoteElement();
NoteElement noteElement = taggedContent.CreateNoteElement();
// Créer des éléments de structure d'illustration
FigureElement figureElement = taggedContent.CreateFigureElement();
FormulaElement formulaElement = taggedContent.CreateFormulaElement();
// Des méthodes sont en cours de développement
ListElement listElement = taggedContent.CreateListElement();
TableElement tableElement = taggedContent.CreateTableElement();
ReferenceElement referenceElement = taggedContent.CreateReferenceElement();
BibEntryElement bibEntryElement = taggedContent.CreateBibEntryElement();
CodeElement codeElement = taggedContent.CreateCodeElement();
LinkElement linkElement = taggedContent.CreateLinkElement();
AnnotElement annotElement = taggedContent.CreateAnnotElement();
RubyElement rubyElement = taggedContent.CreateRubyElement();
WarichuElement warichuElement = taggedContent.CreateWarichuElement();
FormElement formElement = taggedContent.CreateFormElement();
// Enregistrer le document PDF balisé
document.Save(dataDir + "StructureElements.pdf");

```

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser Aspose.PDF pour .NET pour créer des éléments de structure dans un document PDF balisé. Les éléments structurels aident à améliorer l'accessibilité des documents et à organiser le contenu de manière significative. Vous pouvez désormais utiliser ces connaissances pour créer des documents PDF structurés et faciles à parcourir.

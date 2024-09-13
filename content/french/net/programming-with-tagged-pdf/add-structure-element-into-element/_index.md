---
title: Ajouter un élément de structure dans un élément
linktitle: Ajouter un élément de structure dans un élément
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour ajouter un élément de structure à un élément dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-tagged-pdf/add-structure-element-into-element/
---
Dans ce didacticiel, nous vous fournirons un guide étape par étape sur la façon d'ajouter un élément de structure à un élément dans un document PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de créer, de manipuler et de convertir des documents PDF par programmation. En utilisant les fonctionnalités de structure de contenu marquées d'Aspose.PDF, vous pouvez créer une structure hiérarchique dans votre document PDF.

## Prérequis

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Visual Studio installé avec .NET Framework.
2. La bibliothèque Aspose.PDF pour .NET.

## Étape 1 : Configuration du projet

Pour commencer, créez un nouveau projet dans Visual Studio et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Vous pouvez télécharger la bibliothèque depuis le site officiel d'Aspose et l'installer sur votre machine.

## Étape 2 : Importer les espaces de noms nécessaires

Dans votre fichier de code C#, importez les espaces de noms requis pour accéder aux classes et méthodes fournies par Aspose.PDF :

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Étape 3 : Création du document PDF et définition des éléments structurés

Utilisez le code suivant pour créer un document PDF et définir les éléments structurés :

```csharp

string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Text Items");
taggedContent.SetLanguage("fr-FR");

StructureElement rootElement = taggedContent.RootElement;

ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);

ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);

ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");

ParagraphElement p4 = taggedContent.CreateParagraphElement();
root

Element.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
```

Ce code crée un document PDF vide et ajoute des éléments structurés tels que des paragraphes et des plages. Chaque élément de structure est créé à l'aide des méthodes fournies par Aspose.PDF.

## Étape 4 : Enregistrer le document PDF

Utilisez le code suivant pour enregistrer le document PDF :

```csharp
document. Save(outFile);
```

Ce code enregistre le document PDF avec les éléments structurés dans un fichier spécifié.

### Exemple de code source pour ajouter un élément de structure dans un élément à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddStructureElementIntoElement_Output.pdf";
string logFile = dataDir + "46144_log.xml";
//Création de document et obtention de contenu PDF balisé
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
// Définition du titre et de la langue naturelle du document
taggedContent.SetTitle("Text Elements Example");
taggedContent.SetLanguage("en-US");
// Obtenir l'élément de structure racine (élément de structure du document)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
SpanElement span11 = taggedContent.CreateSpanElement();
span11.SetText("Span_11");
SpanElement span12 = taggedContent.CreateSpanElement();
span12.SetText(" and Span_12.");
p1.SetText("Paragraph with ");
p1.AppendChild(span11);
p1.AppendChild(span12);
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
SpanElement span21 = taggedContent.CreateSpanElement();
span21.SetText("Span_21");
SpanElement span22 = taggedContent.CreateSpanElement();
span22.SetText("Span_22.");
p2.AppendChild(span21);
p2.SetText(" and ");
p2.AppendChild(span22);
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("Span_31");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText(" and Span_32");
p3.AppendChild(span31);
p3.AppendChild(span32);
p3.SetText(".");
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
SpanElement span41 = taggedContent.CreateSpanElement();
SpanElement span411 = taggedContent.CreateSpanElement();
span411.SetText("Span_411, ");
span41.SetText("Span_41, ");
span41.AppendChild(span411);
SpanElement span42 = taggedContent.CreateSpanElement();
SpanElement span421 = taggedContent.CreateSpanElement();
span421.SetText("Span 421 and ");
span42.AppendChild(span421);
span42.SetText("Span_42");
p4.AppendChild(span41);
p4.AppendChild(span42);
p4.SetText(".");
// Enregistrer le document PDF balisé
document.Save(outFile);
// Vérification de la conformité PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

Dans ce didacticiel, vous avez appris à ajouter un élément de structure à un élément d'un document PDF à l'aide d'Aspose.PDF pour .NET. À l'aide des fonctionnalités de structure de contenu marquées d'Aspose.PDF, vous pouvez créer une structure hiérarchique dans votre document PDF, ce qui facilite la gestion et la navigation dans le contenu.

### FAQ

#### Q : Quel est le but d’ajouter un élément de structure à un élément dans un document PDF à l’aide d’Aspose.PDF pour .NET ?

R : L'ajout d'un élément de structure à un élément d'un document PDF à l'aide d'Aspose.PDF pour .NET vous permet de créer une structure hiérarchique au sein du contenu du document. Cette structure hiérarchique améliore l'organisation et la navigation du contenu, facilitant ainsi la gestion et l'accès à des éléments spécifiques.

#### Q : Comment la bibliothèque Aspose.PDF aide-t-elle à ajouter des éléments de structure à un document PDF ?

R : Aspose.PDF pour .NET est une bibliothèque puissante qui fournit des fonctionnalités de création, de manipulation et de conversion de documents PDF par programmation. Dans ce didacticiel, les fonctionnalités de structure de contenu marquées de la bibliothèque sont exploitées pour créer et ajouter des éléments de structure au contenu du document PDF.

#### Q : Quelles sont les conditions préalables pour ajouter des éléments de structure à un document PDF à l’aide d’Aspose.PDF pour .NET ?

R : Avant de commencer, assurez-vous que Visual Studio est installé avec le framework .NET et que la bibliothèque Aspose.PDF pour .NET est référencée dans votre projet.

#### Q : Comment le code C# fourni crée-t-il et ajoute-t-il des éléments de structure au contenu du document PDF ?

R : Le code montre comment créer un document PDF, définir un élément de structure racine et y ajouter divers éléments structurés tels que des paragraphes et des plages. Chaque élément structuré est créé à l'aide de méthodes fournies par Aspose.PDF, ce qui vous permet de créer une structure hiérarchique.

#### Q : Puis-je personnaliser les types d’éléments de structure que j’ajoute au document PDF ?

R : Oui, vous pouvez personnaliser les types d'éléments de structure en explorant différentes méthodes fournies par la bibliothèque Aspose.PDF. Le code présente des paragraphes et des plages à titre d'exemple, mais vous pouvez créer et ajouter d'autres types d'éléments structurés selon vos besoins.

#### Q : Comment définir la relation hiérarchique entre les éléments de structure ajoutés ?

 R : La relation hiérarchique entre les éléments de structure est définie par l'ordre dans lequel vous les ajoutez à leurs éléments parents. Dans le code, les relations parent-enfant sont établies à l'aide de`AppendChild` méthode.

#### Q : Quels sont les avantages de créer une structure hiérarchique dans un document PDF ?

R : La création d'une structure hiérarchique dans un document PDF améliore son accessibilité, sa navigation et son organisation. Elle permet aux technologies d'assistance de mieux interpréter et transmettre le contenu du document, le rendant ainsi plus convivial pour les personnes handicapées.

#### Q : Comment puis-je valider la conformité PDF/UA après avoir ajouté des éléments de structure ?

R : Le code fourni dans le didacticiel montre comment valider la conformité PDF/UA à l'aide de`Validate` méthode. En validant le document par rapport à la norme PDF/UA, vous pouvez vous assurer que les éléments de structure ajoutés sont conformes aux directives d'accessibilité.

#### Q : Puis-je utiliser cette approche pour ajouter des éléments de structure à un document PDF existant ?

R : Oui, vous pouvez modifier l'approche fournie pour ajouter des éléments de structure à un document PDF existant. Au lieu de créer un nouveau document, vous devez charger le document existant à l'aide d'Aspose.PDF, puis suivre des étapes similaires pour ajouter des éléments de structure.
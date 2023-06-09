---
title: Créer un élément de structure de note
linktitle: Créer un élément de structure de note
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour créer des éléments de note structurés dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-tagged-pdf/create-note-structure-element/
---
Dans ce didacticiel, nous vous fournirons un guide étape par étape sur la création d'un élément de structure de note dans un document PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de créer, manipuler et convertir des documents PDF par programme. En utilisant les fonctionnalités de structure de contenu marqué d'Aspose.PDF, vous pouvez ajouter des notes structurées à votre document PDF.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont en place :

1. Visual Studio installé avec le framework .NET.
2. La bibliothèque Aspose.PDF pour .NET.

## Étape 1 : configuration du projet

Pour commencer, créez un nouveau projet dans Visual Studio et ajoutez une référence à la bibliothèque Aspose.PDF pour .NET. Vous pouvez télécharger la bibliothèque depuis le site officiel d'Aspose et l'installer sur votre machine.

## Étape 2 : Importez les espaces de noms nécessaires

Dans votre fichier de code C#, importez les espaces de noms requis pour accéder aux classes et méthodes fournies par Aspose.PDF :

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## Étape 3 : Création du document PDF et des éléments structurés de la note

Utilisez le code suivant pour créer un document PDF et ajouter des éléments structurés de note :

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";

Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample Grade Items");
taggedContent.SetLanguage("fr-FR");

ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);

NoteElement note1 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note1);
note1.SetText("Note with automatically generated ID. ");

NoteElement note2 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note2);
note2.SetText("Note with ID = 'note_002'.");
note2.SetId("note_002");

NoteElement note3 = taggedContent.CreateNoteElement();
paragraph. AppendChild(note3);
note3.SetText("Note with ID = 'note_003'.");
note3.SetId("note_003");
```

Ce code crée un document PDF vide et ajoute des éléments de note structurés à un paragraphe. Chaque note est créée à l'aide des méthodes fournies par Aspose.PDF.

## Étape 4 : Enregistrer le document PDF

Utilisez le code suivant pour enregistrer le document PDF :

```csharp
document. Save(outFile);
```

Ce code enregistre le document PDF avec les éléments structurés de note dans un fichier spécifié.

### Exemple de code source pour créer un élément de structure de note à l'aide d'Aspose.PDF pour .NET 

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "45929_doc.pdf";
string logFile = dataDir + "45929_log.xml";
// Créer un document PDF
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Sample of Note Elements");
taggedContent.SetLanguage("en-US");
// Ajouter un élément de paragraphe
ParagraphElement paragraph = taggedContent.CreateParagraphElement();
taggedContent.RootElement.AppendChild(paragraph);
// Ajouter un élément de note
NoteElement note1 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note1);
note1.SetText("Note with auto generate ID. ");
// Ajouter un élément de note
NoteElement note2 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note2);
note2.SetText("Note with ID = 'note_002'. ");
note2.SetId("note_002");
// Ajouter un élément de note
NoteElement note3 = taggedContent.CreateNoteElement();
paragraph.AppendChild(note3);
note3.SetText("Note with ID = 'note_003'. ");
note3.SetId("note_003");
//Doit lever une exception - Aspose.Pdf.Tagged.TaggedException : l'élément de structure avec ID='note_002' existe déjà
//note3.SetId("note_002");
// Le document résultant n'est pas conforme au PDF/UA Si ClearId() est utilisé pour l'élément de structure de note
//note3.ClearId();
// Enregistrer le document PDF balisé
document.Save(outFile);
// Vérification de la conformité PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

Dans ce didacticiel, vous avez appris à créer des éléments de structure de note dans un document PDF à l'aide d'Aspose.PDF pour .NET. Les éléments de note structurés vous permettent d'ajouter des informations structurées supplémentaires à votre document PDF.

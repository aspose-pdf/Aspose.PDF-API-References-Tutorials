---
title: Créer un élément de structure de note
linktitle: Créer un élément de structure de note
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour créer des éléments de notes structurés dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-tagged-pdf/create-note-structure-element/
---
Dans ce didacticiel, nous vous fournirons un guide étape par étape sur la façon de créer un élément de structure de note dans un document PDF à l'aide d'Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de créer, de manipuler et de convertir des documents PDF par programmation. En utilisant les fonctionnalités de structure de contenu marquées d'Aspose.PDF, vous pouvez ajouter des notes structurées à votre document PDF.

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

## Étape 3 : Création du document PDF et des éléments structurés de notes

Utilisez le code suivant pour créer un document PDF et ajouter des éléments structurés sous forme de notes :

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

Ce code enregistre le document PDF avec les éléments structurés de notes dans un fichier spécifié.

### Exemple de code source pour créer un élément de structure de note à l'aide d'Aspose.PDF pour .NET 

```csharp
// Le chemin vers le répertoire des documents.
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
// Doit générer une exception - Aspose.Pdf.Tagged.TaggedException : l'élément de structure avec l'ID = 'note_002' existe déjà
//note3.SetId("note_002");
// Le document résultant n'est pas conforme à PDF/UA si ClearId() est utilisé pour l'élément de structure de note
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

### FAQ

#### Q : Quel est le but de la création d’éléments de structure de notes dans un document PDF à l’aide d’Aspose.PDF pour .NET ?

R : La création d'éléments de structure de note dans un document PDF à l'aide d'Aspose.PDF pour .NET vous permet d'ajouter des notes structurées au contenu du document. Ces notes peuvent fournir un contexte supplémentaire, des explications ou des références à des parties spécifiques du contenu.

#### Q : Comment la bibliothèque Aspose.PDF aide-t-elle à créer des éléments de structure de notes dans un document PDF ?

R : Aspose.PDF pour .NET est une bibliothèque puissante qui fournit des fonctionnalités pour créer, manipuler et convertir des documents PDF par programmation. Dans ce didacticiel, les fonctionnalités de structure de contenu marquées de la bibliothèque sont utilisées pour créer des éléments de note structurés dans le contenu du document PDF.

#### Q : Quelles sont les conditions préalables à la création d’éléments de structure de notes dans un document PDF à l’aide d’Aspose.PDF pour .NET ?

R : Avant de commencer, assurez-vous que Visual Studio est installé avec le framework .NET et que la bibliothèque Aspose.PDF pour .NET est référencée dans votre projet.

#### Q : Comment le code C# fourni crée-t-il des éléments de structure de note dans le contenu du document PDF ?

R : Le code montre comment créer un document PDF, définir des éléments structurés de notes et les ajouter à un paragraphe. Chaque note est créée à l'aide des méthodes fournies par Aspose.PDF, ce qui vous permet d'incorporer des notes structurées dans le contenu.

#### Q : Puis-je personnaliser le contenu et les propriétés des éléments de structure de note que je crée ?

R : Oui, vous pouvez personnaliser le contenu et les propriétés des éléments de structure de note en utilisant les méthodes et les propriétés fournies par la bibliothèque Aspose.PDF. Le code montre comment définir le texte et l'ID des éléments de note, mais vous pouvez les personnaliser davantage selon vos besoins.

#### Q : Comment s'établit la relation hiérarchique entre les éléments de la structure des notes et le contenu du document ?

 R : La relation hiérarchique est établie en ajoutant des éléments de structure de note en tant qu'enfants d'autres éléments structurés, tels que des paragraphes. Dans le code, les éléments de note sont ajoutés à un élément de paragraphe à l'aide de`AppendChild` méthode.

#### Q : Puis-je attribuer des identifiants uniques aux éléments de structure de notes ?

 : Oui, vous pouvez attribuer des identifiants uniques aux éléments de structure de note à l'aide de l'`SetId` méthode. Le code montre comment définir les identifiants des éléments de note sur des valeurs uniques.

#### Q : Que se passe-t-il si j’essaie d’attribuer un ID en double à un élément de structure de note ?

R : Toute tentative d'attribution d'un identifiant en double à un élément de structure de note entraînera une exception. Le code fourni dans le didacticiel inclut un commentaire illustrant ce scénario.

#### Q : Comment puis-je garantir la conformité PDF/UA lors de la création d’éléments de structure de notes ?

 R : Le code fourni dans le didacticiel montre comment valider la conformité PDF/UA à l'aide de`Validate` méthode. En validant le document par rapport à la norme PDF/UA, vous pouvez garantir que les éléments de structure de note ajoutés respectent les directives d'accessibilité.

#### Q : Puis-je utiliser cette approche pour ajouter des éléments de structure de note à un document PDF existant ?

: Oui, vous pouvez modifier l'approche fournie pour ajouter des éléments de structure de note à un document PDF existant. Au lieu de créer un nouveau document, vous devez charger le document existant à l'aide d'Aspose.PDF, puis suivre des étapes similaires pour ajouter des éléments de note.

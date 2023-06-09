---
title: Configuration de la langue et du titre
linktitle: Configuration de la langue et du titre
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour configurer la langue et le titre d'un document PDF avec Aspose.PDF pour .NET. Créez des documents multilingues personnalisés.
type: docs
weight: 140
url: /fr/net/programming-with-tagged-pdf/setup-language-and-title/
---
Dans ce guide, nous allons vous expliquer comment configurer la langue et le titre d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de créer, manipuler et convertir par programme des fichiers PDF.

Plongeons-nous dans le code et apprenons à configurer la langue et le titre d'un document PDF à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir installé Aspose.PDF pour .NET et configuré votre environnement de développement.

## Étape 1 : Création du document

 La première étape consiste à créer un nouveau document PDF à l'aide de`Document` classe.

```csharp
// Créer le document PDF
Document document = new Document();
```

## Étape 2 : Accéder au contenu balisé

 Ensuite, nous accédons au contenu balisé du document en utilisant le`ITaggedContent` objet.

```csharp
//Accéder au contenu tagué
Tagged.ITaggedContent taggedContent = document.TaggedContent;
```

## Étape 3 : Définissez le titre et la langue

 Nous pouvons maintenant définir le titre et la langue du document à l'aide de la`SetTitle` et`SetLanguage` méthodes de la`ITaggedContent` objet.

```csharp
// Définir le titre du document
taggedContent.SetTitle("Example of tagged document");

// Définir la langue du document
taggedContent.SetLanguage("fr-FR");
```

## Étape 4 : Ajouter du contenu multilingue

Ensuite, nous ajoutons du contenu multilingue au document en utilisant des éléments de paragraphe pour chaque langue.

```csharp
// Ajouter un paragraphe en anglais
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Ajouter un paragraphe en allemand
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hello Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Ajouter un paragraphe en français
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Hello world!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Ajouter un paragraphe en espagnol
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);
```

## Étape 5 : Enregistrer le document PDF balisé

Enfin, nous enregistrons le document PDF balisé.

```csharp
// Enregistrer le document PDF balisé
document.Save(dataDir + "SetupLanguageAndTitle.pdf");
```

### Exemple de code source pour la configuration de la langue et du titre à l'aide d'Aspose.PDF pour .NET 
```csharp

Document document = new Document();

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Obtenir le contenu tagué
Tagged.ITaggedContent taggedContent = document.TaggedContent;

// Définir le titre et la langue
taggedContent.SetTitle("Example Tagged Document");
taggedContent.SetLanguage("en-US");

// En-tête (en-US, hérité du document)
LogicalStructure.HeaderElement h1 = taggedContent.CreateHeaderElement(1);
h1.SetText("Phrase on different languages");
taggedContent.RootElement.AppendChild(h1);

// Paragraphe (anglais)
LogicalStructure.ParagraphElement pEN = taggedContent.CreateParagraphElement();
pEN.SetText("Hello, World!");
pEN.Language = "en-US";
taggedContent.RootElement.AppendChild(pEN);

// Paragraphe (allemand)
LogicalStructure.ParagraphElement pDE = taggedContent.CreateParagraphElement();
pDE.SetText("Hallo Welt!");
pDE.Language = "de-DE";
taggedContent.RootElement.AppendChild(pDE);

// Paragraphe (français)
LogicalStructure.ParagraphElement pFR = taggedContent.CreateParagraphElement();
pFR.SetText("Bonjour le monde!");
pFR.Language = "fr-FR";
taggedContent.RootElement.AppendChild(pFR);

// Paragraphe (espagnol)
LogicalStructure.ParagraphElement pSP = taggedContent.CreateParagraphElement();
pSP.SetText("¡Hola Mundo!");
pSP.Language = "es-ES";
taggedContent.RootElement.AppendChild(pSP);

// Enregistrer le document PDF balisé
document.Save(dataDir + "SetupLanguageAndTitle.pdf");

```

## Conclusion

Félicitation ! Vous savez maintenant comment configurer la langue et le titre d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez explorer davantage les fonctionnalités d'Aspose.PDF pour créer des documents PDF personnalisés et multilingues.

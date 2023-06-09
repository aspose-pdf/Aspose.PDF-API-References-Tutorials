---
title: Éléments de structure de bloc de texte
linktitle: Éléments de structure de bloc de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser Aspose.PDF pour .NET pour ajouter des éléments de structure de bloc de texte, tels que des titres et des paragraphes balisés, à un document PDF existant.
type: docs
weight: 220
url: /fr/net/programming-with-tagged-pdf/text-block-structure-elements/
---

Dans ce didacticiel détaillé, nous vous expliquerons étape par étape le code source C # fourni pour créer des éléments de structure de bloc de texte dans un document PDF balisé à l'aide d'Aspose.PDF pour .NET. Suivez les instructions ci-dessous pour comprendre comment ajouter des titres à plusieurs niveaux et des paragraphes balisés à votre document PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement pour utiliser Aspose.PDF pour .NET. Cela inclut l'installation de la bibliothèque Aspose.PDF et la configuration de votre projet pour le référencer.

## Étape 2 : Création du document PDF

Dans cette étape, nous allons créer un nouvel objet de document PDF avec Aspose.PDF.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer le document PDF
Document document = new Document();
```

Nous avons créé un nouveau document PDF avec Aspose.PDF.

## Étape 3 : Obtenir le contenu balisé et définir le titre et la langue

Maintenant, récupérons le contenu balisé du document PDF et définissons le titre et la langue du document.

```csharp
// Obtenir du contenu tagué
ITaggedContent taggedContent = document.TaggedContent;

// Définir le titre et la langue du document
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

Nous avons défini le titre et la langue du document PDF balisé.

## Etape 4 : Obtention de l'élément de structure racine

Obtenons maintenant l'élément de structure racine du document PDF.

```csharp
// Obtenir l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;
```

Nous avons obtenu l'élément de structure racine du document PDF.

## Étape 5 : Ajouter des titres et des paragraphes

Nous allons maintenant ajouter des titres de différents niveaux et des paragraphes balisés à notre document PDF.

```csharp
//Créer des en-têtes de différents niveaux
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);

// Définition du texte d'en-tête
h1.SetText("H1. Level 1 header");
h2.SetText("H2. Level 2 header");
h3.SetText("H3. Level 3 header");
h4.SetText("H4. Level 4 header");
h5.SetText("H5. Heading level 5");
h6.SetText("H6. Level 6 header");

// Ajouter des en-têtes à l'élément de structure racine
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Créer le paragraphe
ParagraphElement p = taggedContent.CreateParagraphElement();

// Définition du texte du paragraphe
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet Nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");

// Ajouter le paragraphe à l'élément de structure racine
rootElement.AppendChild(p);
```

Nous avons ajouté des titres de différents niveaux et un paragraphe balisé à l'élément de structure racine du document PDF.

## Étape 6 : Enregistrer le document PDF

Maintenant que nous avons fini de modifier le document PDF, enregistrons-le dans un fichier.

```csharp
// Enregistrer le document PDF balisé
document.Save(dataDir + "ElementsDeStructureDeBlocsDeTexte.pdf");
```

Nous avons enregistré le document PDF balisé avec les éléments de structure du bloc de texte dans le répertoire spécifié.

### Exemple de code source pour les éléments de structure de bloc de texte à l'aide d'Aspose.PDF pour .NET 
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

// Obtenir l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
h1.SetText("H1. Header of Level 1");
h2.SetText("H2. Header of Level 2");
h3.SetText("H3. Header of Level 3");
h4.SetText("H4. Header of Level 4");
h5.SetText("H5. Header of Level 5");
h6.SetText("H6. Header of Level 6");
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean nec lectus ac sem faucibus imperdiet. Sed ut erat ac magna ullamcorper hendrerit. Cras pellentesque libero semper, gravida magna sed, luctus leo. Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
rootElement.AppendChild(p);

// Enregistrer le document PDF balisé
document.Save(dataDir + "TextBlockStructureElements.pdf");
```

## Conclusion

Dans ce didacticiel, nous avons appris à utiliser Aspose.PDF pour .NET pour ajouter des éléments de structure de bloc de texte, tels que des titres et des paragraphes balisés, à un document PDF. Vous pouvez désormais utiliser ces fonctionnalités pour améliorer la structure et l'accessibilité de vos documents PDF.

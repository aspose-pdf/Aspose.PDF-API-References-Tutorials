---
title: Éléments de structure en ligne
linktitle: Éléments de structure en ligne
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour utiliser les éléments structurels en ligne avec Aspose.PDF pour .NET. Organisez vos PDF avec des titres et des paragraphes.
type: docs
weight: 110
url: /fr/net/programming-with-tagged-pdf/inline-structure-elements/
---
Dans ce guide étape par étape, nous allons vous montrer comment utiliser les éléments de structure en ligne avec Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de manipuler des documents PDF par programme. Les éléments de structure en ligne vous permettent de créer une structure hiérarchique dans votre document PDF en utilisant des titres de différents niveaux et paragraphes.

Plongeons dans le code et apprenons à utiliser les éléments de structure en ligne avec Aspose.PDF pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Bibliothèque Aspose.PDF pour .NET installée.
2. Une connaissance de base du langage de programmation C#.

## Étape 1 : Configuration de l'environnement

Pour commencer, ouvrez votre environnement de développement C# et créez un nouveau projet. Assurez-vous d'avoir ajouté une référence à la bibliothèque Aspose.PDF pour .NET dans votre projet.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Création du document

 La première étape consiste à créer un nouveau document PDF à l'aide du`Document` classe.

```csharp
// Créer le document PDF
Document document = new Document();
```

## Étape 3 : Travailler avec du contenu balisé

Ensuite, nous obtenons le contenu balisé du document avec lequel travailler.

```csharp
// Récupérer le contenu balisé du document
ITaggedContent taggedContent = document.TaggedContent;
```

## Étape 4 : Définir le titre et la langue du document

Nous pouvons maintenant définir le titre et la langue du document.

```csharp
// Définir le titre et la langue du document
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");
```

## Étape 5 : Ajouter des éléments structurels en ligne

Nous allons maintenant ajouter des éléments de structure en ligne tels que des titres de différents niveaux et des paragraphes à notre document.

```csharp
// Obtenez l'élément de structure racine
StructureElement rootElement = taggedContent.RootElement;

// Ajouter des en-têtes de différents niveaux
HeaderElement h1 = taggedContent.CreateHeaderElement(1);
HeaderElement h2 = taggedContent.CreateHeaderElement(2);
HeaderElement h3 = taggedContent.CreateHeaderElement(3);
HeaderElement h4 = taggedContent.CreateHeaderElement(4);
HeaderElement h5 = taggedContent.CreateHeaderElement(5);
HeaderElement h6 = taggedContent.CreateHeaderElement(6);
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);

// Ajouter du contenu à chaque en-tête
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1.");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 header");
h1.AppendChild(spanH12);

SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2.");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 header");
h2.AppendChild(spanH22);

SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3.");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 header");
h3.AppendChild(spanH32);

SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4.");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 header");
h4.AppendChild(spanH42);

SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5.");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 header");
h5.AppendChild(spanH52);

SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6.");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Heading level 6");
h6.AppendChild(spanH62);

// Ajouter un paragraphe
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P.");
rootElement.AppendChild(p);

// Ajouter du contenu au paragraphe
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit.");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet.");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit.");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo.");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit.");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. So cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit.");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);
```

Ici, nous créons des éléments de structure en ligne, tels que des titres de différents niveaux et un paragraphe, et leur ajoutons du contenu.

## Étape 6 : Enregistrez le document PDF balisé

Enfin, nous enregistrons le document PDF balisé.

```csharp
// Enregistrez le document PDF balisé
document.Save(dataDir + "InlineStructureElements.pdf");
```

### Exemple de code source pour les éléments de structure en ligne utilisant Aspose.PDF pour .NET 

```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un document PDF
Document document = new Document();

// Obtenez du contenu pour travailler avec TaggedPdf
ITaggedContent taggedContent = document.TaggedContent;

// Définir le titre et la langue du document
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
rootElement.AppendChild(h1);
rootElement.AppendChild(h2);
rootElement.AppendChild(h3);
rootElement.AppendChild(h4);
rootElement.AppendChild(h5);
rootElement.AppendChild(h6);
SpanElement spanH11 = taggedContent.CreateSpanElement();
spanH11.SetText("H1. ");
h1.AppendChild(spanH11);
SpanElement spanH12 = taggedContent.CreateSpanElement();
spanH12.SetText("Level 1 Header");
h1.AppendChild(spanH12);
SpanElement spanH21 = taggedContent.CreateSpanElement();
spanH21.SetText("H2. ");
h2.AppendChild(spanH21);
SpanElement spanH22 = taggedContent.CreateSpanElement();
spanH22.SetText("Level 2 Header");
h2.AppendChild(spanH22);
SpanElement spanH31 = taggedContent.CreateSpanElement();
spanH31.SetText("H3. ");
h3.AppendChild(spanH31);
SpanElement spanH32 = taggedContent.CreateSpanElement();
spanH32.SetText("Level 3 Header");
h3.AppendChild(spanH32);
SpanElement spanH41 = taggedContent.CreateSpanElement();
spanH41.SetText("H4. ");
h4.AppendChild(spanH41);
SpanElement spanH42 = taggedContent.CreateSpanElement();
spanH42.SetText("Level 4 Header");
h4.AppendChild(spanH42);
SpanElement spanH51 = taggedContent.CreateSpanElement();
spanH51.SetText("H5. ");
h5.AppendChild(spanH51);
SpanElement spanH52 = taggedContent.CreateSpanElement();
spanH52.SetText("Level 5 Header");
h5.AppendChild(spanH52);
SpanElement spanH61 = taggedContent.CreateSpanElement();
spanH61.SetText("H6. ");
h6.AppendChild(spanH61);
SpanElement spanH62 = taggedContent.CreateSpanElement();
spanH62.SetText("Level 6 Header");
h6.AppendChild(spanH62);
ParagraphElement p = taggedContent.CreateParagraphElement();
p.SetText("P. ");
rootElement.AppendChild(p);
SpanElement span1 = taggedContent.CreateSpanElement();
span1.SetText("Lorem ipsum dolor sit amet, consectetur adipiscing elit. ");
p.AppendChild(span1);
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Aenean nec lectus ac sem faucibus imperdiet. ");
p.AppendChild(span2);
SpanElement span3 = taggedContent.CreateSpanElement();
span3.SetText("Sed ut erat ac magna ullamcorper hendrerit. ");
p.AppendChild(span3);
SpanElement span4 = taggedContent.CreateSpanElement();
span4.SetText("Cras pellentesque libero semper, gravida magna sed, luctus leo. ");
p.AppendChild(span4);
SpanElement span5 = taggedContent.CreateSpanElement();
span5.SetText("Fusce lectus odio, laoreet nec ullamcorper ut, molestie eu elit. ");
p.AppendChild(span5);
SpanElement span6 = taggedContent.CreateSpanElement();
span6.SetText("Interdum et malesuada fames ac ante ipsum primis in faucibus. ");
p.AppendChild(span6);
SpanElement span7 = taggedContent.CreateSpanElement();
span7.SetText("Aliquam lacinia sit amet elit ac consectetur. Donec cursus condimentum ligula, vitae volutpat sem tristique eget. ");
p.AppendChild(span7);
SpanElement span8 = taggedContent.CreateSpanElement();
span8.SetText("Nulla in consectetur massa. Vestibulum vitae lobortis ante. Nulla ullamcorper pellentesque justo rhoncus accumsan. ");
p.AppendChild(span8);
SpanElement span9 = taggedContent.CreateSpanElement();
span9.SetText("Mauris ornare eu odio non lacinia. Aliquam massa leo, rhoncus ac iaculis eget, tempus et magna. Sed non consectetur elit. ");
p.AppendChild(span9);
SpanElement span10 = taggedContent.CreateSpanElement();
span10.SetText("Sed vulputate, quam sed lacinia luctus, ipsum nibh fringilla purus, vitae posuere risus odio id massa. Cras sed venenatis lacus.");
p.AppendChild(span10);

// Enregistrer le document PDF balisé
document.Save(dataDir + "InlineStructureElements.pdf");

```

## Conclusion

Félicitation ! Vous avez appris à utiliser les éléments de structure en ligne avec Aspose.PDF pour .NET. Vous pouvez désormais créer une structure hiérarchique dans votre document PDF en utilisant des titres de différents niveaux et paragraphes. Explorez plus de fonctionnalités d’Aspose.PDF pour découvrir tout son potentiel.

### FAQ

#### Q : Que sont les éléments de structure en ligne dans un document PDF et comment contribuent-ils à créer une structure hiérarchique ?

R : Les éléments de structure en ligne dans un document PDF, tels que les titres de différents niveaux et paragraphes, sont utilisés pour créer une structure hiérarchique qui organise et présente le contenu de manière structurée. Ces éléments vous permettent d'établir une hiérarchie et un flux d'informations clairs au sein du document.

#### Q : Comment les éléments de structure en ligne peuvent-ils améliorer la lisibilité et l'organisation d'un document PDF ?

R : Les éléments de structure en ligne, en particulier les titres et les paragraphes, contribuent à améliorer la lisibilité et l'organisation d'un document PDF en fournissant une structure logique. Les titres indiquent différents niveaux d'importance et aident les lecteurs à naviguer dans le contenu, tandis que les paragraphes regroupent les informations connexes.

#### Q : Comment Aspose.PDF pour .NET facilite-t-il l'utilisation d'éléments de structure en ligne ?

R : Aspose.PDF pour .NET propose des classes et des méthodes pour créer et manipuler des éléments de structure en ligne, tels que des titres et des paragraphes. Ces éléments peuvent être personnalisés, organisés hiérarchiquement et enrichis de contenu pour améliorer la présentation visuelle et l'accessibilité du document.

####  Q : Quel est le but du`taggedContent` object in relation to inline structure elements?

 R : Le`taggedContent` objet, obtenu à partir du`TaggedContent` propriété d'un`Document`, vous permet de travailler avec des éléments structurés, y compris des éléments de structure en ligne. Il vous permet de créer, personnaliser et organiser des titres et des paragraphes dans le document.

#### Q : Comment les éléments de structure en ligne aident-ils à créer une hiérarchie de documents claire ?

R : Les éléments de structure en ligne, tels que les titres de différents niveaux, contribuent à établir une hiérarchie claire et bien définie dans le document. Les lecteurs peuvent rapidement identifier les sujets principaux, les sous-thèmes et le contenu associé, ce qui facilite la navigation et la compréhension du document.

#### Q : Puis-je personnaliser l'apparence et le formatage des éléments de structure en ligne à l'aide d'Aspose.PDF pour .NET ?

R : Oui, vous pouvez personnaliser l’apparence et le formatage des éléments de structure en ligne. Vous pouvez définir des propriétés telles que les styles de police, les tailles, les couleurs, l'alignement, l'indentation et l'espacement pour obtenir la présentation visuelle souhaitée pour les titres et les paragraphes.

#### Q : Comment créer et ajouter des titres de différents niveaux à un document PDF à l'aide d'éléments de structure en ligne dans Aspose.PDF pour .NET ?

 R : Vous pouvez créer des titres de différents niveaux à l'aide de l'outil`CreateHeaderElement` méthode, puis ajoutez-les à l’élément de structure racine. Par la suite, vous pouvez ajouter du contenu à chaque élément de titre à l'aide du`CreateSpanElement` méthode pour créer des étendues de texte.

#### Q : Puis-je utiliser des éléments de structure en ligne pour créer des listes, des puces ou d'autres types d'organisation de contenu dans un document PDF ?

R : Bien que les éléments de structure en ligne eux-mêmes soient principalement utilisés pour les titres et les paragraphes, vous pouvez les utiliser en combinaison avec d'autres fonctionnalités offertes par Aspose.PDF pour .NET pour créer des listes, des puces, des tableaux et d'autres types d'organisation de contenu pour une présentation complète. structure des documents.

#### Q : Comment les éléments de structure en ligne contribuent-ils à l'accessibilité des documents ?

R : Les éléments de structure en ligne jouent un rôle crucial dans l’amélioration de l’accessibilité des documents. Des titres et des paragraphes correctement structurés fournissent une hiérarchie de documents claire qui aide les lecteurs d'écran et autres technologies d'assistance à interpréter et à transmettre avec précision le contenu aux utilisateurs handicapés.

#### Q : Puis-je explorer des utilisations plus avancées des éléments de structure en ligne, telles que la création d'éléments interactifs ou l'intégration de contenu multimédia ?

: Absolument ! Alors que ce didacticiel se concentre sur la création de titres et de paragraphes, Aspose.PDF pour .NET propose des fonctionnalités avancées pour créer des éléments interactifs, intégrer du multimédia, ajouter des hyperliens, etc. Consultez la documentation et les exemples de la bibliothèque pour découvrir ces fonctionnalités avancées.
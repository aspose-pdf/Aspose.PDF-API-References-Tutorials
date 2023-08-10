---
title: Marquer l'image dans un PDF existant
linktitle: Marquer l'image dans un PDF existant
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à marquer une image dans un PDF existant avec Aspose.PDF pour .NET. Un guide étape par étape pour ajouter des balises aux images.
type: docs
weight: 210
url: /fr/net/programming-with-tagged-pdf/tag-image-in-existing-pdf/
---
Dans ce didacticiel détaillé, nous vous expliquerons étape par étape le code source C # fourni pour marquer une image dans un PDF existant à l'aide d'Aspose.PDF pour .NET. Suivez les instructions ci-dessous pour comprendre comment ajouter des balises à une image dans un PDF.

## Étape 1 : Configurer l'environnement

Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement pour utiliser Aspose.PDF pour .NET. Cela inclut l'installation de la bibliothèque Aspose.PDF et la configuration de votre projet pour le référencer.

## Étape 2 : Ouvrez le document PDF existant

Dans cette étape, nous allons ouvrir un document PDF existant en utilisant Aspose.PDF.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chemins des fichiers d'entrée et de sortie
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Ouvrir le document
Document document = new Document(inFile);
```

Nous avons ouvert le document PDF existant en utilisant Aspose.PDF.

## Étape 3 : Obtenir le contenu balisé et l'élément de structure racine

Nous allons maintenant obtenir le contenu balisé du document PDF et l'élément de structure racine correspondant.

```csharp
// Obtenir le contenu balisé et l'élément de structure racine
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;
```

Nous avons obtenu le contenu balisé du document PDF et l'élément de structure racine correspondant.

## Étape 4 : Définition du titre du document PDF balisé

Définissons maintenant le titre du document PDF balisé.

```csharp
// Définir le titre du document PDF balisé
taggedContent.SetTitle("Document with images");
```

Nous avons défini le titre du document PDF balisé.

## Étape 5 : Attribuez des textes alternatifs et un cadre de sélection à l'image

Maintenant, pour chaque élément d'image, nous allons attribuer un texte alternatif et un cadre de sélection.

```csharp
foreach(FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
     // Attribuer un texte alternatif à l'image
     figureElement.AlternativeText = "Alternative text for image (technique 2)";
     // Créer et affecter la boîte englobante (bbox)
     StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
     bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
     StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
     figureLayoutAttributes.SetAttribute(bboxAttribute);
}
```

Nous avons attribué un texte alternatif et un cadre de sélection à chaque élément d'image dans le document PDF.

## Étape 6 : Déplacer l'élément Span dans le paragraphe

Déplaçons maintenant l'élément Span dans le paragraphe.

```csharp
// Déplacer l'élément Span dans le paragraphe (trouver la portée et le paragraphe incorrects dans le premier TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Déplacer l'élément Span dans le paragraphe
spanElement.ChangeParentElement(paragraph);
```

Nous avons déplacé l'élément Span dans le paragraphe spécifié.

## Étape 7 : Enregistrer le document PDF modifié

Maintenant que nous avons apporté les modifications nécessaires, nous allons enregistrer le document PDF modifié.

```csharp
// Enregistrez le document PDF
document. Save(outFile);
```

Nous avons enregistré le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour l'image de balise dans un PDF existant à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "TH.pdf";
string outFile = dataDir + "TH_out.pdf";
string logFile = dataDir + "TH_out.xml";

// Ouvrir le document
Document document = new Document(inFile);

// Obtient le contenu balisé et l'élément de structure racine
ITaggedContent taggedContent = document.TaggedContent;
StructureElement rootElement = taggedContent.RootElement;

// Définir le titre du document pdf balisé
taggedContent.SetTitle("Document with images");
foreach (FigureElement figureElement in rootElement.FindElements<FigureElement>(true))
{
	// Définir un texte alternatif pour la figure
	figureElement.AlternativeText = "Figure alternative text (technique 2)";
	// Créer et définir l'attribut BBox
	StructureAttribute bboxAttribute = new StructureAttribute(AttributeKey.BBox);
	bboxAttribute.SetRectangleValue(new Rectangle(0.0, 0.0, 100.0, 100.0));
	StructureAttributes figureLayoutAttributes = figureElement.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
	figureLayoutAttributes.SetAttribute(bboxAttribute);
}

// Déplacer l'élément Span dans le paragraphe (trouver la mauvaise étendue et le mauvais paragraphe dans le premier TD)
TableElement tableElement = rootElement.FindElements<TableElement>(true)[0];
SpanElement spanElement = tableElement.FindElements<SpanElement>(true)[0];
TableTDElement firstTdElement = tableElement.FindElements<TableTDElement>(true)[0];
ParagraphElement paragraph = firstTdElement.FindElements<ParagraphElement>(true)[0];

// Déplacer l'élément Span dans le paragraphe
spanElement.ChangeParentElement(paragraph);

// Enregistrer le document
document.Save(outFile);

//Vérification de la conformité PDF/UA pour notre document
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

Dans ce didacticiel, nous avons appris à baliser une image dans un PDF existant à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser Aspose.PDF pour ajouter des balises et apporter des modifications aux images de vos documents PDF.

### FAQ

#### Q : Quel est l'objectif principal de ce didacticiel sur le balisage d'images dans un PDF existant à l'aide d'Aspose.PDF pour .NET ?

R : L'objectif principal de ce didacticiel est de vous guider tout au long du processus de balisage d'une image dans un document PDF existant à l'aide d'Aspose.PDF pour .NET. Le didacticiel fournit des instructions détaillées et des exemples de code source C# pour vous aider à comprendre comment attribuer un texte alternatif et des cadres de délimitation aux images, déplacer des éléments dans le document et ajouter des balises aux images.

#### Q : Quelles sont les conditions préalables pour suivre ce didacticiel sur le balisage d'images dans un PDF à l'aide d'Aspose.PDF pour .NET ?

R : Avant de commencer, assurez-vous d'avoir configuré votre environnement de développement pour utiliser Aspose.PDF pour .NET. Cela implique d'installer la bibliothèque Aspose.PDF et de configurer votre projet pour le référencer.

#### Q : Comment puis-je ouvrir un document PDF existant et accéder à son contenu balisé à l'aide d'Aspose.PDF pour .NET ?

R : Le didacticiel fournit des exemples de code source C# qui montrent comment ouvrir un document PDF existant à l'aide d'Aspose.PDF pour .NET et accéder à son contenu balisé pour une manipulation ultérieure.

#### Q : Quel est le but d'attribuer un texte alternatif et des cadres de délimitation aux images dans un document PDF ?

R : L'attribution de texte alternatif et de cadres de délimitation aux images améliore l'accessibilité en fournissant un texte descriptif pour les images et en définissant leur mise en page et leur position dans le document. Ces informations sont cruciales pour les lecteurs d'écran et autres technologies d'assistance.

#### Q : Comment puis-je définir le titre d'un document PDF balisé à l'aide d'Aspose.PDF pour .NET ?

R : Le didacticiel comprend des exemples de code source C# qui illustrent comment définir le titre d'un document PDF balisé à l'aide d'Aspose.PDF pour .NET.

#### Q : En quoi consiste le processus de déplacement d'éléments dans un document PDF ?

R : Le déplacement d'éléments dans un document PDF implique la modification de l'élément parent d'un élément particulier. Dans ce didacticiel, vous apprendrez à déplacer un élément Span dans un élément Paragraph spécifié dans un tableau.

#### Q : Comment puis-je enregistrer le document PDF modifié après avoir ajouté des balises et apporté des modifications aux images ?

 R : Une fois que vous avez ajouté des balises, attribué un texte de remplacement, défini des cadres de délimitation et apporté des modifications au document PDF, vous pouvez utiliser les exemples de code source C# fournis pour enregistrer le document PDF modifié à l'aide de`Save()` méthode.

#### Q : À quoi sert l'exemple de code source fourni dans le didacticiel ?

R : L'exemple de code source sert de référence pratique pour la mise en œuvre du balisage et de la manipulation d'images à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce code comme point de départ et le modifier en fonction de vos besoins spécifiques.

#### Q : Puis-je appliquer ces techniques à d'autres types d'éléments dans un document PDF, pas seulement aux images ?

: Oui, les techniques présentées dans ce didacticiel peuvent être adaptées pour fonctionner avec différents types d'éléments dans un document PDF. Vous pouvez appliquer des principes similaires pour baliser et manipuler d'autres éléments tels que du texte, des tableaux, etc.

#### Q : Comment puis-je valider la conformité PDF/UA du document PDF modifié ?

 R : Le didacticiel fournit des exemples de code source C# qui montrent comment valider la conformité PDF/UA du document PDF modifié à l'aide de la`Validate()` méthode et génération d'un rapport XML.

#### Q : Quelles autres fonctionnalités offre Aspose.PDF pour .NET pour travailler avec des documents PDF ?

R : Aspose.PDF pour .NET offre un large éventail de fonctionnalités pour travailler avec des documents PDF, notamment la manipulation de texte, l'insertion d'images, la création de tableaux, la gestion des champs de formulaire, les signatures numériques, les annotations, etc. Consultez la documentation officielle et les ressources pour une exploration plus approfondie.
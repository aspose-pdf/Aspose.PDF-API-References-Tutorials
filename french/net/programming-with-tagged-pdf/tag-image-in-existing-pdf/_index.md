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
//Définir le titre du document PDF balisé
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

// Vérification de la conformité PDF/UA pour notre document
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## Conclusion

Dans ce didacticiel, nous avons appris à baliser une image dans un PDF existant à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser Aspose.PDF pour ajouter des balises et apporter des modifications aux images de vos documents PDF.

---
title: Éléments de structure de lien
linktitle: Éléments de structure de lien
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour utiliser les éléments de structure de liens avec Aspose.PDF pour .NET. Créez des hyperliens dans vos documents PDF.
type: docs
weight: 120
url: /fr/net/programming-with-tagged-pdf/link-structure-elements/
---
Dans ce guide étape par étape, nous allons vous montrer comment utiliser les éléments de structure de liens avec Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui vous permet de créer et de manipuler des documents PDF par programme. Les éléments de structure de liens vous permettent d'ajouter des hyperliens à votre document PDF, permettant aux utilisateurs de cliquer sur les liens et de naviguer vers des ressources en ligne.

Plongeons dans le code et apprenons à utiliser les éléments de structure de lien avec Aspose.PDF pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1. Bibliothèque Aspose.PDF pour .NET installée.
2. Une connaissance de base du langage de programmation C#.

## Étape 1 : Configuration de l'environnement

Pour commencer, ouvrez votre environnement de développement C# et créez un nouveau projet. Assurez-vous d'avoir ajouté une référence à la bibliothèque Aspose.PDF pour .NET dans votre projet.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";
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
taggedContent.SetTitle("Example Link Items");
taggedContent.SetLanguage("fr-FR");
```

## Étape 5 : Ajouter des éléments de structure de lien

Ajoutons maintenant des éléments de structure de liens à notre document. Nous créerons différents types de liens, notamment des liens texte simples, des liens image et des liens multilignes.
```csharp
// Obtenir l'élément de structure racine (élément de structure du document)
StructureElement rootElement = taggedContent.RootElement;

// Ajouter un paragraphe avec un lien hypertexte
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";

// Ajouter un paragraphe avec un lien hypertexte contenant du texte enrichi
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";

// Ajouter un paragraphe avec un lien hypertexte contenant du texte partiellement formaté
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";

// Ajouter un paragraphe avec un lien hypertexte multiligne
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";

// Ajouter un paragraphe avec un lien hypertexte contenant une image
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";
```

## Étape 6 : Enregistrez le document PDF balisé

Enfin, nous enregistrons le document PDF balisé.

```csharp
// Enregistrez le document PDF balisé
document. Save(outFile);
```

## Étape 7 : Vérifiez la conformité PDF/UA

 Nous pouvons également vérifier la conformité du document PDF/UA en utilisant le`Validate` méthode du`Document` classe.

```csharp
// Vérifier la conformité PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```


### Exemple de code source pour les éléments de structure de lien utilisant Aspose.PDF pour .NET 
```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Document de création et obtention du contenu PDF balisé
Document document = new Document(); 
ITaggedContent taggedContent = document.TaggedContent;

// Définition du titre et de la langue naturelle du document
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");

// Obtention de l'élément de structure racine (élément de structure du document)
StructureElement rootElement = taggedContent.RootElement;
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);
link2.AlternateDescriptions = "Link to Google";
ParagraphElement p3 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p3);
LinkElement link3 = taggedContent.CreateLinkElement();
p3.AppendChild(link3);
link3.Hyperlink = new WebHyperlink("http://google.com");
SpanElement span31 = taggedContent.CreateSpanElement();
span31.SetText("G");
SpanElement span32 = taggedContent.CreateSpanElement();
span32.SetText("oogle");
link3.AppendChild(span31);
link3.SetText("-");
link3.AppendChild(span32);
link3.AlternateDescriptions = "Link to Google";
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);
LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google Google");
link4.AlternateDescriptions = "Link to Google (multiline)";
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);
LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
StructureAttributes linkLayoutAttributes = link5.Attributes.GetAttributes(AttributeOwnerStandard.Layout);
StructureAttribute placementAttribute = new StructureAttribute(AttributeKey.Placement);
placementAttribute.SetNameValue(AttributeName.Placement_Block);
linkLayoutAttributes.SetAttribute(placementAttribute);
link5.AppendChild(figure5);
link5.AlternateDescriptions = "Link to Google";

// Enregistrer le document PDF balisé
document.Save(outFile);

// Vérification de la conformité PDF/UA
document = new Document(outFile);
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```
## Conclusion

Félicitation ! Vous avez appris à utiliser les éléments de structure de liens avec Aspose.PDF pour .NET. Vous pouvez désormais créer des hyperliens dans vos documents PDF, permettant aux utilisateurs de naviguer vers des ressources en ligne. Expérimentez et explorez davantage de fonctionnalités d'Aspose.PDF pour créer des documents PDF interactifs et enrichis.

### FAQ

#### Q : Que sont les éléments de structure de liens dans un document PDF et comment améliorent-ils l'interactivité du document ?

R : Les éléments de structure de liens dans un document PDF sont utilisés pour créer des hyperliens qui permettent aux utilisateurs de naviguer vers des ressources en ligne ou des emplacements spécifiques dans le document. Ces éléments améliorent l'interactivité en fournissant des liens cliquables qui permettent aux utilisateurs d'accéder à du contenu associé ou à des sites Web externes.

#### Q : Comment les éléments de structure de liens peuvent-ils être bénéfiques dans un document PDF ?

R : Les éléments de structure de lien améliorent l'expérience utilisateur en rendant le document PDF interactif. Ils fournissent un accès rapide à des informations supplémentaires, à du contenu connexe, à des sites Web externes ou à des sections spécifiques du document, améliorant ainsi la navigation et facilitant la récupération d'informations.

#### Q : Puis-je créer différents types de liens hypertexte à l'aide d'éléments de structure de lien dans Aspose.PDF pour .NET ?

R : Oui, vous pouvez créer différents types de liens hypertexte à l’aide d’éléments de structure de lien. Aspose.PDF pour .NET vous permet de créer des hyperliens avec du texte brut, du texte enrichi, des images et des descriptions multilignes, offrant ainsi une polyvalence dans la manière dont vous créez des liens vers du contenu externe ou des emplacements dans le document.

#### Q : Comment configurer et initialiser les éléments de structure de liens dans un document PDF à l'aide d'Aspose.PDF pour .NET ?

 R : Pour utiliser les éléments de structure de liens, vous devez d'abord créer un nouveau document PDF à l'aide du`Document` classe. Ensuite, obtenez le contenu balisé à l'aide du`TaggedContent`propriété du document. À partir de là, vous pouvez créer et personnaliser des éléments de structure de lien et les ajouter à l’élément de structure racine.

#### Q : Comment puis-je créer un lien hypertexte simple à l'aide d'éléments de structure de lien ?
 R : Vous pouvez créer un lien hypertexte simple en créant un`LinkElement` et en définissant son`Hyperlink` propriété à un`WebHyperlink` avec l'URL vers laquelle vous souhaitez créer un lien. Vous pouvez également définir le texte d'affichage du lien à l'aide du`SetText` méthode.

#### Q : Est-il possible de créer des hyperliens avec des images à l'aide d'éléments de structure de lien ?

 R : Oui, vous pouvez créer des hyperliens avec des images à l’aide d’éléments de structure de lien. Vous créeriez un`LinkElement` puis ajoutez un`FigureElement` avec une image dessus. Cela vous permet de créer un lien hypertexte basé sur une image.

#### Q : Comment puis-je m'assurer que mon document PDF contenant des hyperliens est conforme à la norme PDF/UA en matière d'accessibilité ?

 R : Aspose.PDF pour .NET offre la possibilité de valider la conformité de votre document PDF avec la norme PDF/UA à l'aide de l'outil`Validate` méthode du`Document`classe. Cela garantit que les hyperliens du document sont accessibles aux utilisateurs handicapés.

#### Q : Quelles sont les descriptions alternatives des éléments de structure de lien et pourquoi sont-elles importantes ?

R : Les descriptions alternatives (texte alternatif) pour les éléments de structure de lien fournissent des descriptions textuelles des hyperliens. Ces descriptions sont essentielles à l'accessibilité, permettant aux utilisateurs malvoyants de comprendre le but du lien et sa destination.

#### Q : Puis-je personnaliser l'apparence et le comportement des hyperliens créés à l'aide d'éléments de structure de lien ?

R : Bien que les éléments de structure des liens se concentrent principalement sur la création d'hyperliens, vous pouvez personnaliser davantage l'apparence et le comportement des hyperliens à l'aide d'autres fonctionnalités offertes par Aspose.PDF pour .NET. Cela inclut la spécification des couleurs, des styles et des actions de lien.

#### Q : Comment les éléments de structure de liens contribuent-ils à rendre les documents PDF plus interactifs et plus conviviaux ?

R : Les éléments de structure de liens transforment les documents PDF statiques en expériences interactives en ajoutant des hyperliens cliquables. Cette interactivité améliore l'engagement des utilisateurs, permet une navigation transparente entre les contenus associés et améliore la convivialité globale du document.
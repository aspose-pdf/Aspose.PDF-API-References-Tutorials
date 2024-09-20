---
title: Éléments de structure de lien
linktitle: Éléments de structure de lien
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment créer des éléments de structure de liens dans un PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape pour ajouter des liens accessibles, des images et une validation de conformité.
type: docs
weight: 120
url: /fr/net/programming-with-tagged-pdf/link-structure-elements/
---
## Introduction

La création et la gestion des éléments de structure de liens dans un PDF peuvent être cruciales pour les documents nécessitant une accessibilité et une navigation fluide. Dans ce didacticiel, nous vous expliquerons comment procéder à l'aide d'Aspose.PDF pour .NET. Si vous débutez avec Aspose.PDF ou la manipulation de PDF en général, ne vous inquiétez pas. Je vous expliquerai chaque étape en détail afin que vous puissiez facilement suivre !

## Prérequis  

Avant de nous plonger dans le codage, commençons par quelques points. Voici les exigences de base pour garantir une expérience de développement fluide.

1.  Aspose.PDF pour .NET : vous pouvez télécharger la dernière version[ici](https://releases.aspose.com/pdf/net/).
2. Environnement de développement .NET : qu'il s'agisse de Visual Studio ou de tout autre IDE compatible .NET, assurez-vous qu'il est installé et prêt.
3.  Licence Aspose : Vous pouvez utiliser la version d'essai gratuite d'Aspose.PDF[ici](https://releases.aspose.com/) ou acquérir un[permis temporaire](https://purchase.aspose.com/temporary-license/).
4. Connaissances de base de C# : nous travaillerons avec du code C#, donc comprendre les fondamentaux rendra les choses beaucoup plus faciles.

## Paquets d'importation

Vous devrez importer quelques packages avant d'écrire le code des éléments de structure de liens. Commencez par référencer les bibliothèques Aspose.PDF nécessaires dans votre projet :

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Ces importations nous permettent de travailler avec des documents PDF, d'ajouter des balises et de gérer les éléments de structure.

Nous allons maintenant créer un document PDF avec différents types de structures de liens, et chaque étape sera décomposée pour vous aider à bien comprendre le processus.

## Étape 1 : Initialiser le document  

Commençons par créer un nouveau document PDF et configurer le contenu balisé pour l’accessibilité.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "LinkStructureElements_Output.pdf";
string logFile = dataDir + "46035_log.xml";
string imgFile = dataDir + "google-icon-512.png";

// Créer un nouveau document PDF
Document document = new Document(); 

// Récupérer l'interface TaggedContent
ITaggedContent taggedContent = document.TaggedContent;
```
  
 Ici, nous initialisons le`Document` objet, qui représente notre fichier PDF. Nous récupérons également le`TaggedContent` interface, nous permettant d'ajouter des éléments de structure tels que des paragraphes, des liens et des images.

## Étape 2 : définir le titre et la langue  

Chaque PDF doit avoir un titre et un paramètre de langue, surtout si vous souhaitez vous conformer aux normes PDF/UA.

```csharp
// Définir le titre et la langue du document
taggedContent.SetTitle("Link Elements Example");
taggedContent.SetLanguage("en-US");
```
  
Cette étape garantit que votre PDF a un titre significatif et définit la langue sur l'anglais (`en-US`). Ceci est essentiel pour l’accessibilité et garantit que les lecteurs d’écran ou autres technologies d’assistance peuvent interpréter correctement votre document.

## Étape 3 : Créer et ajouter des paragraphes  

Dans cette étape, nous allons ajouter des paragraphes pour contenir nos éléments de lien.

```csharp
// Créer l'élément racine
StructureElement rootElement = taggedContent.RootElement;

// Créez un paragraphe et ajoutez-le à l'élément racine
ParagraphElement p1 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p1);
```
  
Nous créons un élément de structure racine, qui est essentiellement le conteneur de niveau supérieur pour tous les autres éléments. Nous créons ensuite un paragraphe (`p1`) et l'ajouter à l'élément racine.

## Étape 4 : ajouter un lien simple  

Ajoutons maintenant un lien hypertexte de base qui pointe vers Google.

```csharp
// Créez un élément de lien et ajoutez-le au paragraphe
LinkElement link1 = taggedContent.CreateLinkElement();
p1.AppendChild(link1);

// Définir l'hyperlien et le texte du lien
link1.Hyperlink = new WebHyperlink("http://google.com");
link1.SetText("Google");
link1.AlternateDescriptions = "Link to Google";
```
  
Dans cette étape, nous avons créé un élément de lien, défini son lien hypertexte sur « http://google.com » et fourni le texte (« Google ») pour le lien. Nous avons également ajouté une description alternative pour garantir l'accessibilité.

## Étape 5 : Ajout d'un lien avec des spans  

Nous pouvons également créer des liens avec différentes portions de texte.

```csharp
// Créer un autre paragraphe
ParagraphElement p2 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p2);

// Créer un lien avec un élément span
LinkElement link2 = taggedContent.CreateLinkElement();
p2.AppendChild(link2);
link2.Hyperlink = new WebHyperlink("http://google.com");

SpanElement span2 = taggedContent.CreateSpanElement();
span2.SetText("Google");
link2.AppendChild(span2);

link2.AlternateDescriptions = "Link to Google";
```
  
Ici, nous avons utilisé un élément span pour enfermer une partie du texte dans le lien, nous permettant de personnaliser l'apparence de certaines parties du lien.

## Étape 6 : Lien multiligne  

Que faire si le texte de votre lien est trop long ? Pas de soucis, vous pouvez le répartir sur plusieurs lignes.

```csharp
ParagraphElement p4 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p4);

LinkElement link4 = taggedContent.CreateLinkElement();
p4.AppendChild(link4);
link4.Hyperlink = new WebHyperlink("http://google.com");
link4.SetText("The multiline link: Google Google Google Google Google...");
link4.AlternateDescriptions = "Link to Google (multiline)";
```
  
Dans ce cas, nous avons créé un lien multiligne en définissant simplement une valeur de texte longue, et le texte s'enroulera automatiquement sur plusieurs lignes.

## Étape 7 : ajouter une image au lien  

Enfin, vous pouvez également ajouter des images à l’intérieur d’un lien.

```csharp
// Créer un nouveau paragraphe et un élément de lien
ParagraphElement p5 = taggedContent.CreateParagraphElement();
rootElement.AppendChild(p5);

LinkElement link5 = taggedContent.CreateLinkElement();
p5.AppendChild(link5);
link5.Hyperlink = new WebHyperlink("http://google.com");

// Ajouter une image au lien
FigureElement figure5 = taggedContent.CreateFigureElement();
figure5.SetImage(imgFile, 1200);
figure5.AlternativeText = "Google icon";
link5.AppendChild(figure5);

link5.AlternateDescriptions = "Link to Google";
```
  
Cette étape montre comment vous pouvez améliorer vos liens avec une image. Dans ce cas, nous avons ajouté une icône Google à l'intérieur du lien. Nous avons également assuré l'accessibilité en définissant un texte alternatif pour l'image.

## Étape 8 : Valider le PDF pour la conformité  

Si vous souhaitez atteindre la conformité PDF/UA (une norme d'accessibilité), il est recommandé de valider votre document.

```csharp
// Enregistrer le document PDF
document.Save(outFile);

// Valider le document pour la conformité PDF/UA
bool isPdfUaCompliance = document.Validate(logFile, PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```
  
Nous avons enregistré le document et l'avons validé par rapport à la norme PDF/UA, qui garantit que le PDF répond aux exigences d'accessibilité.

## Conclusion  

Dans ce didacticiel, nous avons expliqué comment créer des documents PDF structurés à l'aide d'Aspose.PDF pour .NET. De l'ajout d'hyperliens de base à des structures plus complexes telles que des étendues, des liens multilignes et même des images, ce guide fournit une base solide pour la manipulation des éléments de lien dans vos PDF. Grâce à l'avantage supplémentaire de la conformité PDF/UA, vous êtes désormais équipé pour créer des PDF accessibles et navigables.

## FAQ

### Puis-je ajouter des structures plus complexes comme des tableaux à l'intérieur des liens ?  
Non, les liens sont principalement destinés au texte et aux images, mais vous pouvez intégrer des éléments complexes à proximité.

### La validation PDF/UA est-elle obligatoire ?  
Pas toujours, mais c'est fortement recommandé si vous êtes préoccupé par l'accessibilité.

### Que se passe-t-il si le chemin du fichier image est incorrect ?  
Le document n'affichera pas l'image et il pourrait générer une erreur lors du rendu.

### Puis-je styliser le texte dans le lien ?  
Oui, vous pouvez appliquer des styles de texte à l’aide des éléments span.

### Est-il possible de créer des liens internes vers des documents ?  
Absolument ! Vous pouvez créer des liens vers des sections spécifiques au sein d'un même document.
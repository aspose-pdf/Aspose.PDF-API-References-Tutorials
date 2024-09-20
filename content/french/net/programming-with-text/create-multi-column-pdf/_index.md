---
title: Créer un PDF multi-colonnes
linktitle: Créer un PDF multi-colonnes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à créer des PDF multicolonnes à l'aide d'Aspose.PDF pour .NET. Un guide étape par étape avec des exemples de code et des explications détaillées. Parfait pour les professionnels.
type: docs
weight: 110
url: /fr/net/programming-with-text/create-multi-column-pdf/
---
## Introduction

La création de PDF multicolonnes est un excellent moyen de présenter du texte dans un format plus organisé et plus lisible. Que vous rédigiez un rapport, un article ou une mise en page pour une publication, les structures multicolonnes peuvent rendre votre contenu plus attrayant. Dans ce didacticiel, nous vous expliquerons comment créer un PDF multicolonnes à l'aide d'Aspose.PDF pour .NET. Ne vous inquiétez pas, nous allons tout décomposer en étapes simples qui seront faciles à suivre, même si vous êtes nouveau sur la plateforme.

## Prérequis

Avant de passer au code, vous devez mettre en place quelques éléments pour pouvoir suivre le processus en douceur :

1.  Aspose.PDF pour .NET : vous devez avoir installé cette bibliothèque. Vous pouvez la télécharger à partir de[ici](https://releases.aspose.com/pdf/net/).
2. Environnement de développement : configurez votre IDE préféré comme Visual Studio pour écrire et exécuter du code C#.
3. .NET Framework : assurez-vous que vous disposez d’une version compatible de .NET installée.
4. Compréhension de base de C# : une connaissance de la syntaxe C# sera utile, mais nous expliquerons chaque étape en détail.
5.  Licence temporaire : Aspose.PDF nécessite une licence pour éviter les filigranes ou les limitations. Vous pouvez obtenir une[permis temporaire](https://purchase.aspose.com/temporary-license/) si besoin.

## Paquets d'importation

Avant de commencer à coder, vous devez importer les espaces de noms nécessaires qui vous permettront d'interagir avec Aspose.PDF. Voici ce que vous devrez importer :

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Ces espaces de noms donnent accès aux classes nécessaires à la création de PDF, au dessin de formes et à la gestion du formatage du texte.

Décomposons le processus de création d’un PDF multicolonne en étapes simples et gérables.

## Étape 1 : Configuration du document

Pour commencer, vous devez créer un nouveau document PDF. Cela implique de définir les marges et d'ajouter une page où votre contenu sera placé.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un nouveau document PDF
Document doc = new Document();

// Définir les marges du fichier PDF
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;

// Ajouter une page au document
Page page = doc.Pages.Add();
```

 Ici, nous avons créé un`Document`objet et définissez les marges gauche et droite à 40 unités. Ensuite, nous avons ajouté une nouvelle page à ce document, qui contiendra notre mise en page multi-colonnes.

## Étape 2 : Ajout d'une ligne pour séparer les sections

Ensuite, ajoutons une ligne horizontale à la page pour une séparation visuelle. Cela permet de créer un aspect propre et professionnel.

```csharp
// Créer un objet graphique pour contenir la ligne
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500.0, 2.0);

// Ajoutez la ligne à la collection de paragraphes de la page
page.Paragraphs.Add(graph1);

// Définir les coordonnées de la ligne
float[] posArr = new float[] { 1, 2, 500, 2 };

// Créez une ligne et ajoutez-la au graphique
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
```

 Ici, nous créons une ligne horizontale en utilisant le`Graph` et`Line` classes. Cette ligne est ajoutée à la page`Paragraphs` collection, qui contient tous les éléments visuels.

## Étape 3 : Ajout de texte HTML avec mise en forme

Ensuite, insérons du texte qui inclut des balises HTML pour montrer comment vous pouvez formater du texte de manière dynamique dans le PDF.

```csharp
// Créer une chaîne avec du contenu HTML
string s = "<font face=\"Times New Roman\" size=4>" +
           "<strong> How to Steer Clear of Money Scams </strong>" +
           "</font>";

// Créer un nouveau HtmlFragment avec le texte formaté
HtmlFragment heading_text = new HtmlFragment(s);

// Ajoutez le texte HTML à la page
page.Paragraphs.Add(heading_text);
```

 En utilisant le`HtmlFragment`classe, nous pouvons ajouter du texte formaté qui inclut des balises HTML telles que la taille de la police, le style et le texte en gras. Ceci est utile pour améliorer l'apparence de votre contenu PDF.

## Étape 4 : Création d'une mise en page à plusieurs colonnes

Nous allons maintenant créer une mise en page à plusieurs colonnes. C'est là que la magie opère : vous pouvez spécifier le nombre de colonnes que vous souhaitez et leur largeur.

```csharp
// Créer une boîte flottante pour contenir les colonnes
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();

// Définissez le nombre de colonnes et l'espacement entre elles
box.ColumnInfo.ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

// Ajouter la boîte à la page
page.Paragraphs.Add(box);
```

Ici, nous créons une boîte flottante qui contiendra deux colonnes. Nous définissons l'espacement entre les colonnes et spécifions que chaque colonne doit avoir une largeur de 105 unités. Cela nous permet de créer la disposition de colonnes souhaitée dans le PDF.

## Étape 5 : Ajout de texte aux colonnes

 Remplissons maintenant les colonnes avec du contenu textuel. Vous pouvez ajouter différents`TextFragment` objets à chaque colonne.

```csharp
// Créer et formater le premier fragment de texte
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.FontStyle = FontStyles.Italic;
box.Paragraphs.Add(text1);

// Ajouter une autre ligne pour la séparation
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50.0, 10.0);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

//Créer et ajouter un deuxième fragment de texte
TextFragment text2 = new TextFragment("Lorem ipsum dolor sit amet, consectetur adipiscing elit...");
box.Paragraphs.Add(text2);
```

 Nous ajoutons un`TextFragment` à la boîte flottante, suivie d'une autre ligne horizontale. La deuxième`TextFragment` contient plus de texte pour remplir la deuxième colonne. Ces fragments nous permettent d'ajouter divers éléments de texte au PDF avec différentes options de formatage.

## Étape 6 : Enregistrer le PDF

Après avoir ajouté tout votre contenu, l’étape finale consiste à enregistrer le document sous forme de fichier PDF.

```csharp
// Définir le chemin de sortie du PDF
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";

// Enregistrer le document PDF
doc.Save(dataDir);

// Message de réussite de sortie
Console.WriteLine("\nMulti-column PDF file created successfully.\nFile saved at " + dataDir);
```

Ce bloc enregistre le fichier PDF dans le répertoire spécifié et affiche un message de réussite dans la console. Le PDF est maintenant prêt à être visualisé !

## Conclusion

En suivant ces étapes simples, vous pouvez facilement créer un PDF multicolonne d'aspect professionnel à l'aide d'Aspose.PDF pour .NET. Qu'il s'agisse d'un rapport, d'un article ou d'une newsletter, cette technique permet d'organiser le contenu dans un format visuellement attrayant. Aspose.PDF propose des outils puissants pour personnaliser vos PDF, des marges et de la mise en page au formatage du texte et au dessin de formes. C'est maintenant à votre tour de l'essayer et de faire passer vos compétences en création de PDF au niveau supérieur !

## FAQ

### Puis-je créer plus de deux colonnes dans un PDF ?
 Oui, vous pouvez créer autant de colonnes que vous le souhaitez. Ajustez simplement les`ColumnCount` propriété pour correspondre au nombre de colonnes souhaité.

### Comment modifier la largeur de chaque colonne ?
 Vous pouvez modifier le`ColumnWidths` propriété permettant de spécifier des largeurs différentes pour chaque colonne. Cette propriété accepte une chaîne de valeurs séparées par des espaces.

### Est-il possible d'ajouter des images aux colonnes ?
 Absolument ! Vous pouvez ajouter des images en utilisant le`Image` classe et les incluez dans la boîte flottante ou tout autre élément de mise en page de votre PDF.

### Puis-je styliser du texte avec des balises HTML dans les colonnes ?
 Oui, vous pouvez utiliser des balises HTML dans`HtmlFragment` objets pour styliser votre texte. Cela inclut l'ajout de polices, de tailles, de couleurs, etc.

### Comment puis-je ajouter plus de pages avec la même disposition en colonnes ?
 Vous pouvez ajouter des pages supplémentaires en utilisant`doc.Pages.Add()` et répétez le processus d'ajout de colonnes et de contenu pour chaque page.
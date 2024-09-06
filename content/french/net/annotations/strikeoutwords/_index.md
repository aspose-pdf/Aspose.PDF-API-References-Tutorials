---
title: Barrer les mots
linktitle: Barrer les mots
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à barrer des mots dans un PDF à l'aide d'Aspose.PDF pour .NET grâce à ce guide complet étape par étape. Améliorez vos compétences en édition de documents.
type: docs
weight: 150
url: /fr/net/annotations/strikeoutwords/
---
## Introduction

Avez-vous déjà eu besoin de mettre en valeur un texte spécifique dans un PDF en le barrant ? Que vous révisiez des documents, marquiez du texte ou ayez simplement besoin de surligner certaines sections, barrer des mots peut être un outil précieux. Dans ce didacticiel, nous verrons comment procéder à l'aide d'Aspose.PDF pour .NET. Ce guide complet vous guidera à travers chaque étape, en vous assurant de disposer de toutes les informations nécessaires pour implémenter efficacement cette fonctionnalité dans vos applications .NET. 

## Prérequis

Avant de passer au code, vous devez respecter quelques conditions préalables pour suivre ce tutoriel :

1.  Bibliothèque Aspose.PDF pour .NET : assurez-vous que la bibliothèque Aspose.PDF pour .NET est installée. Vous pouvez[téléchargez-le ici](https://releases.aspose.com/pdf/net/).

2. .NET Framework : assurez-vous que .NET Framework est installé sur votre ordinateur. Ce didacticiel est conçu pour les applications .NET.

3. Environnement de développement : vous aurez besoin d’un IDE comme Visual Studio pour écrire et exécuter votre code.

4. Document PDF : préparez un exemple de fichier PDF sur lequel vous souhaitez travailler. Ce sera le document dans lequel nous barrerons le texte.

5. Connaissances de base en C# : une connaissance de la programmation C# est nécessaire pour comprendre et mettre en œuvre les étapes de ce didacticiel.

## Paquets d'importation

Avant de commencer à coder, nous devons importer les espaces de noms nécessaires dans notre projet .NET. Cela nous donnera accès aux classes et méthodes nécessaires pour manipuler les fichiers PDF à l'aide d'Aspose.PDF.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

Ces espaces de noms sont essentiels pour travailler avec des documents PDF, gérer du texte et ajouter des annotations telles que des barrés.

Dans cette section, nous allons décomposer le processus de suppression de mots dans un document PDF en étapes simples et faciles à gérer. Chaque étape sera accompagnée d'une explication détaillée pour vous assurer de bien comprendre le fonctionnement de tout cela.

## Étape 1 : Charger le document PDF

La première étape consiste à charger le document PDF que vous souhaitez modifier. Ce document sera celui dans lequel vous supprimerez des mots ou des phrases spécifiques.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document PDF
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : Cette variable contient le chemin d'accès à votre répertoire de documents. Remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où se trouve votre fichier PDF.
- `Document` : Le`Document` La classe représente un document PDF. En passant le chemin du fichier à son constructeur, nous ouvrons le fichier PDF pour le traitement.

## Étape 2 : créer un absorbeur de fragments de texte pour rechercher un texte spécifique

 Ensuite, nous allons créer une instance de`TextFragmentAbsorber` pour rechercher un fragment de texte spécifique dans le document PDF. Cela nous permet de localiser le texte que nous souhaitons rayer.

```csharp
// Créez une instance TextFragment Absorber pour rechercher un fragment de texte spécifique
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`Cette classe est utilisée pour rechercher et travailler avec des fragments de texte spécifiques dans le document PDF. Dans cet exemple, nous recherchons le mot « Estoque ». Remplacez « Estoque » par le mot ou la phrase que vous souhaitez trouver dans votre document.

## Étape 3 : parcourir les pages du document PDF

 Maintenant que nous avons notre`TextFragmentAbsorber`, nous devons parcourir chaque page du document PDF pour trouver le texte spécifié.

```csharp
// Parcourir les pages du document PDF
for (int i = 1; i <= document.Pages.Count; i++)
{
    // Obtenir la page actuelle du document PDF
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`:Cette boucle parcourt chaque page du document PDF.
- `document.Pages[i]`: Récupère la page en cours de traitement.
- `page.Accept(textFragmentAbsorber)` :Cette méthode applique la`TextFragmentAbsorber` vers la page actuelle, en recherchant le texte spécifié.

## Étape 4 : Collecter et traiter les fragments de texte

Après avoir parcouru les pages, nous collecterons les fragments de texte trouvés et les préparerons pour un traitement ultérieur.

```csharp
// Créer une collection de fragments de texte absorbés
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`Cette collection stocke tous les fragments de texte trouvés dans le document. Nous utiliserons cette collection à l'étape suivante pour rayer le texte.

## Étape 5 : Parcourez les fragments de texte et supprimez-les

Dans cette étape, nous allons parcourir chaque fragment de texte de notre collection et lui appliquer une annotation barrée.

```csharp
// Itérer sur la collection de fragments de texte
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // Obtenir les dimensions rectangulaires de l'objet TextFragment
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // Instancier l'instance d'annotation StrikeOut
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // Définir les propriétés de l'annotation barrée
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // Ajoutez l'annotation à la collection d'annotations de la page du fragment de texte
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`:Cette ligne récupère le fragment de texte actuel.
- `Aspose.Pdf.Rectangle`:Nous calculons les dimensions rectangulaires du fragment de texte pour déterminer où appliquer le barré.
- `StrikeOutAnnotation`: Cette classe représente l'annotation barrée. Nous l'instancions avec le rectangle calculé et la page courante.
- `strikeOut.Opacity`:Cette propriété définit l'opacité du barré, le rendant visible à 80 %.
- `strikeOut.Color`:Nous avons défini la couleur du texte barré sur le rouge. Vous pouvez le modifier pour la couleur de votre choix.
- `textFragment.Page.Annotations.Add(strikeOut)`:Cela ajoute l'annotation barrée à la page.

## Étape 6 : Enregistrer le document PDF modifié

L’étape finale consiste à enregistrer le document PDF modifié avec les barrés appliqués.

```csharp
// Enregistrer le document PDF mis à jour
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`:Cela crée un nouveau nom de fichier pour le document modifié. Le fichier d'origine reste inchangé.
- `document.Save(dataDir)`: Enregistre le document PDF avec les barrés à l'emplacement spécifié.

## Conclusion

Félicitations ! Vous avez réussi à supprimer des mots spécifiques dans un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant ce guide étape par étape, vous pouvez désormais personnaliser des documents PDF en mettant en surbrillance ou en supprimant du texte, ce qui les rend plus dynamiques et adaptés à vos besoins. Que vous annotiez des documents juridiques, prépariez des rapports ou marquiez simplement du texte pour révision, ce didacticiel vous a fourni les compétences nécessaires pour le faire efficacement.

## FAQ

### Puis-je changer la couleur du retrait barré ?

 Oui, vous pouvez changer la couleur en modifiant le`strikeOut.Color`propriété. Par exemple, vous pouvez le définir sur`Aspose.Pdf.Color.Blue` pour un strikeout bleu.

### Est-il possible de rayer plusieurs mots à la fois ?

 Absolument! Le`TextFragmentAbsorber` peut être utilisé pour rechercher n'importe quel mot ou expression dans le document. Vous pouvez appliquer le barré à plusieurs instances en parcourant le`TextFragmentCollection`.

### Que faire si je souhaite rayer du texte sur des pages spécifiques uniquement ?

 Vous pouvez modifier la boucle qui parcourt les pages pour inclure uniquement les pages que vous souhaitez modifier. Par exemple,`for (int i = 1; i <= 3; i++)` appliquerait la radiation uniquement aux trois premières pages.

### Comment puis-je ajuster l'épaisseur de la ligne de barrage ?

 Vous pouvez ajuster l'épaisseur de la ligne de barré en modifiant le`Border` propriété de la`StrikeOutAnnotation`. Cela permet de personnaliser l'apparence du texte barré.

### Existe-t-il un moyen d’annuler le barré après avoir enregistré le document ?

Une fois le document enregistré, le texte barré est permanent. Si vous devez conserver le texte d'origine sans le texte barré, pensez à enregistrer une sauvegarde du document d'origine avant d'appliquer des modifications.
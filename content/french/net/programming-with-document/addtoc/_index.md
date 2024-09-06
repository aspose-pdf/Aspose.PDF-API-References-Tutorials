---
title: Ajouter la table des matières au fichier PDF
linktitle: Ajouter la table des matières au fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter une table des matières à un PDF à l'aide d'Aspose.PDF pour .NET. Ce guide étape par étape simplifie le processus et garantit une navigation aisée dans vos documents.
type: docs
weight: 40
url: /fr/net/programming-with-document/addtoc/
---
## Introduction

Avez-vous déjà parcouru sans fin un long PDF, en souhaitant qu'il contienne une table des matières bien organisée ? Eh bien, aujourd'hui est votre jour de chance ! Dans ce didacticiel, vous apprendrez à ajouter une table des matières à votre fichier PDF à l'aide d'Aspose.PDF pour .NET. Que vous travailliez sur un rapport complexe, un livre électronique ou une proposition commerciale, une table des matières peut transformer votre document en un chef-d'œuvre professionnel et navigable.

## Prérequis

Avant de passer au code, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1. Aspose.PDF pour .NET : Assurez-vous d'avoir téléchargé et installé la bibliothèque Aspose.PDF. Vous pouvez la télécharger à partir de[ici](https://releases.aspose.com/pdf/net/).
   
2. Environnement de développement : assurez-vous que vous disposez d’un environnement de développement .NET tel que Visual Studio configuré sur votre ordinateur.

3.  Licence : Si vous n'avez pas de licence, vous pouvez obtenir un essai gratuit ou demander une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).

## Paquets d'importation

Pour commencer, assurez-vous d'importer les espaces de noms nécessaires au début de votre fichier de code. Voici comment procéder :

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Ces espaces de noms vous permettent d'accéder aux fonctionnalités spécifiques au PDF et de manipuler des éléments de texte dans votre document.

Décomposons cette tâche en plusieurs étapes. Chaque étape vous guidera tout au long du processus de création et d'insertion d'une table des matières dans votre document PDF.

## Étape 1 : Charger le document PDF

La première chose que nous devons faire est de charger le fichier PDF existant dans lequel nous voulons ajouter la table des matières.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

 Dans cette étape, nous spécifions le chemin d'accès au répertoire du document et chargeons le PDF à l'aide de l'`Document` objet. Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre fichier.

## Étape 2 : insérer une nouvelle page pour la table des matières

Ensuite, nous insérons une nouvelle page au début du document PDF. Cette page hébergera la table des matières.

```csharp
Page tocPage = doc.Pages.Insert(1);
```

En insérant la page TOC au début, nous garantissons qu'elle apparaît comme la toute première chose que les lecteurs voient dans le PDF.

## Étape 3 : Créer un objet d'information TOC

Créons maintenant un objet qui représentera les informations de la table des matières. Nous ajouterons également un titre à la table des matières pour la faire ressortir.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

Ici, nous avons défini le titre de la table des matières comme « Table des matières », augmenté la taille de la police et l'avons mis en gras pour plus de précision.

## Étape 4 : Définir les éléments de la table des matières

Dans cette étape, nous définissons les éléments (ou titres) qui seront affichés dans la table des matières. Ces éléments aideront les lecteurs à naviguer vers des sections spécifiques du document.

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
```

Nous avons créé un tableau de chaînes qui serviront d'éléments de table des matières, correspondant à différentes pages du PDF.

## Étape 5 : Créer des titres de table des matières

Vient maintenant la partie cruciale : ajouter des titres à la table des matières et les lier à leurs pages respectives.

```csharp
for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;
    segment2.Text = titles[i];

    tocPage.Paragraphs.Add(heading2);
}
```

Voici ce qui se passe :
- Titre : Nous créons un`Heading` objet et ajouter un`TextSegment` à cela.
- Page de destination : nous définissons la page vers laquelle chaque titre sera lié.
- Position supérieure : nous spécifions la position sur la page vers laquelle le titre pointera.
- Texte : Chaque titre obtient son titre respectif à partir du tableau que nous avons créé précédemment.

Cette boucle crée des titres pour les deux premiers éléments de la table des matières et les relie aux pages correspondantes.

## Étape 6 : Enregistrer le PDF avec la table des matières

Enfin, après avoir ajouté tous les éléments de la table des matières, il est temps d'enregistrer le PDF mis à jour.

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
```

Le fichier est maintenant enregistré avec la table des matières ajoutée au PDF. Félicitations, vous avez ajouté avec succès une table des matières !

## Étape 7 : Message de confirmation

Pour informer l'utilisateur que le processus est terminé, nous afficherons un message simple dans la console.

```csharp
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## Conclusion

Et voilà ! Avec Aspose.PDF pour .NET, ajouter une table des matières à un PDF est non seulement facile mais également personnalisable. Que vous ayez besoin de créer des liens de navigation simples ou des structures complexes, cet outil est fait pour vous. Alors, la prochaine fois que vous travaillerez sur un long PDF, n'oubliez pas d'ajouter une table des matières pour une touche professionnelle !

## FAQ

### Puis-je personnaliser l'apparence de la table des matières dans Aspose.PDF ?  
Oui, vous pouvez entièrement personnaliser l'apparence de la table des matières, y compris le style de police, la taille et l'alignement.

### Comment ajouter des sous-titres à la table des matières ?  
 Vous pouvez ajouter des sous-titres en ajustant le`Heading` niveau (par exemple,`Heading(2)`) pour créer une table des matières hiérarchique.

### Est-il possible de mettre à jour automatiquement la table des matières si le document change ?  
Non, la table des matières ne se mettra pas à jour automatiquement. Vous devrez la recréer si la structure du document change.

### Puis-je lier des entrées de table des matières à des documents externes ?  
Oui, vous pouvez utiliser des hyperliens pour lier des entrées de table des matières à des PDF ou des URL externes.

### Aspose.PDF prend-il en charge les tables des matières à plusieurs niveaux ?  
Oui, Aspose.PDF prend en charge les tables des matières à plusieurs niveaux pour les documents complexes avec des sous-sections.
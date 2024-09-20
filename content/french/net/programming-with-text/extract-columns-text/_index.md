---
title: Extraire le texte des colonnes dans un fichier PDF
linktitle: Extraire le texte des colonnes dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire des colonnes de texte à partir de fichiers PDF à l'aide d'Aspose.PDF pour .NET. Ce guide détaille chaque étape avec des exemples de code et des explications.
type: docs
weight: 150
url: /fr/net/programming-with-text/extract-columns-text/
---
## Introduction

Vous travaillez avec des fichiers PDF et devez extraire du texte dans un format de colonne spécifique ? Que vous traitiez des factures, des rapports ou tout autre document structuré, extraire du texte avec précision à partir d'un PDF peut s'avérer une tâche délicate. C'est là qu'Aspose.PDF pour .NET intervient pour simplifier le processus. Dans ce didacticiel, nous vous expliquerons comment extraire facilement des colonnes de texte d'un fichier PDF. 

## Prérequis

Avant de plonger dans le code, couvrons les éléments essentiels dont vous aurez besoin :

-  Aspose.PDF pour .NET : Assurez-vous que la dernière version d'Aspose.PDF pour .NET est installée. Sinon, vous pouvez[téléchargez-le ici](https://releases.aspose.com/pdf/net/).
- Environnement de développement : vous aurez besoin de Visual Studio ou d’un autre environnement de développement .NET pour travailler avec le code.
- Document PDF : Ayez un exemple de document PDF à portée de main, de préférence avec des colonnes de texte, car nous allons en extraire du texte.

 Si vous n'avez pas encore installé Aspose.PDF pour .NET, vous pouvez récupérer un[essai gratuit](https://releases.aspose.com/) ou[acheter une licence](https://purchase.aspose.com/buy) pour toutes les fonctionnalités. Vous pouvez également demander un[permis temporaire](https://purchase.aspose.com/temporary-license) si besoin.

## Importer des espaces de noms

Pour utiliser Aspose.PDF pour .NET dans votre projet, vous devez importer les espaces de noms suivants :

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

## Guide étape par étape : extraire des colonnes de texte d'un PDF

Maintenant, décomposons chaque partie du code pour mieux comprendre son fonctionnement. Suivez-nous étape par étape, en expliquant chaque segment du processus.

## Étape 1 : Charger le document PDF

 La première chose que vous devez faire est de charger votre fichier PDF dans le`Document`objet. Voici comment Aspose.PDF interagit avec votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

 Dans cette étape, nous définissons simplement le répertoire dans lequel votre document PDF est stocké. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès à votre fichier PDF local.`Document` L'objet charge le PDF en mémoire, le rendant accessible pour un traitement ultérieur.

## Étape 2 : Configurer l'absorbeur de fragments de texte

 Ensuite, nous utiliserons un`TextFragmentAbsorber` pour absorber ou capturer tout le texte du fichier PDF. Cette classe d'absorption est conçue pour extraire des fragments de texte de zones spécifiques de votre PDF, ce qui la rend idéale pour extraire des colonnes de texte.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
```

Ici, nous créons une instance de`TextFragmentAbsorber` et l'appliquer à toutes les pages du PDF en utilisant`Accept()` . Le`TextFragmentCollection` stocke le texte extrait et, à partir de cette collection, nous pouvons manipuler ou extraire du texte selon les besoins.

## Étape 3 : Ajustez la taille de la police du texte extrait

Une fois que vous avez capturé les fragments de texte, vous souhaiterez peut-être réduire leur taille de police, en particulier lorsque le texte d'origine est trop grand. Dans cet exemple, nous réduisons la taille de la police de 70 %.

```csharp
foreach (TextFragment tf in tfc)
{
    // Réduire la taille de la police de 70 %
    tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

Ce code parcourt chaque`TextFragment` dans la collection et réduit sa taille de police de 70 %. Le réglage de la taille de police peut rendre le texte extrait plus facile à gérer, en particulier si vous le formatez à des fins différentes.

## Étape 4 : Enregistrer le document dans un flux de mémoire

 Après avoir modifié le texte, nous enregistrons le PDF dans un`MemoryStream`Cela nous permet de conserver le document en mémoire pour un traitement ultérieur sans avoir besoin de le réécrire sur le disque.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
```

Ici, nous enregistrons le PDF dans un flux mémoire, puis nous rechargeons le document. Cette méthode est utile lorsque vous travaillez avec des fichiers volumineux et que vous souhaitez éviter des opérations inutiles sur le disque.

## Étape 5 : Extraire tout le texte à l'aide de Text Absorber

 Maintenant que nous avons préparé le PDF, il est temps d'extraire le texte. Nous utiliserons`TextAbsorber` pour récupérer tout le texte du document.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
```

 Dans cette étape, le`TextAbsorber` absorbe tout le texte du PDF et le texte extrait est stocké dans le`extractedText` chaîne. C'est ici que la magie opère : vos colonnes de texte sont désormais au format texte brut !

## Étape 6 : Enregistrer le texte extrait dans un fichier

 Enfin, nous sauvegardons le texte extrait dans un`.txt` fichier pour un accès facile et une utilisation ultérieure.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

 Ce code écrit le texte extrait dans un nouveau`.txt` fichier et l'enregistre dans le répertoire spécifié. Un message s'affiche dans la console pour confirmer que le processus a réussi.

## Conclusion

Et voilà ! Extraire des colonnes de texte d'un fichier PDF à l'aide d'Aspose.PDF pour .NET est plus simple que vous ne le pensez. Avec seulement quelques lignes de code, vous pouvez charger un PDF, extraire du texte spécifique, ajuster la mise en forme et enregistrer les résultats dans un fichier texte.

Cette technique est extrêmement utile pour traiter des documents structurés tels que des tableaux, des rapports ou tout contenu organisé en colonnes. Que vous ayez besoin d'automatiser l'extraction de données ou de traiter des documents en masse, Aspose.PDF fournit les outils nécessaires pour y parvenir efficacement.

## FAQ

### Puis-je extraire du texte de pages spécifiques d’un PDF ?  
 Oui ! Vous pouvez modifier le`TextFragmentAbsorber` pour cibler des pages spécifiques à l'aide du`pdfDocument.Pages[pageIndex].Accept(tfa);` méthode.

### Est-il possible d'extraire du texte d'une seule colonne dans un PDF multicolonne ?  
 Oui, mais vous devrez travailler avec les coordonnées des fragments de texte en utilisant`TextFragment.Rectangle` pour cibler des zones spécifiques du document.

### Comment puis-je améliorer la précision de l’extraction de texte ?  
 Pour une meilleure précision, assurez-vous que la structure du PDF est bien définie et évitez les documents avec des mises en page complexes. Vous pouvez également affiner la`TextFragmentAbsorber` pour extraire du texte en fonction des styles de police, des tailles ou des régions.

### Aspose.PDF prend-il en charge l’extraction de texte à partir de documents numérisés ?  
Oui, mais vous devrez utiliser la technologie OCR (reconnaissance optique de caractères). Aspose fournit également des outils pour cela.

### Comment gérer des fichiers PDF volumineux contenant des milliers de pages ?  
Pour les fichiers PDF volumineux, traitez le document par morceaux en extrayant le texte de quelques pages à la fois pour éviter une utilisation élevée de la mémoire.
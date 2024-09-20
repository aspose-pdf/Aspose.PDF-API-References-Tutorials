---
title: Rechercher du texte et ajouter un lien hypertexte
linktitle: Rechercher du texte et ajouter un lien hypertexte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment rechercher du texte et ajouter des hyperliens dans des fichiers PDF à l'aide d'Aspose.PDF pour .NET avec notre didacticiel étape par étape.
type: docs
weight: 450
url: /fr/net/programming-with-text/search-text-and-add-hyperlink/
---
## Introduction

Vous cherchez un moyen de non seulement manipuler des fichiers PDF, mais également de les améliorer en insérant des hyperliens ? Eh bien, vous êtes au bon endroit ! Avec la puissante bibliothèque Aspose.PDF pour .NET, vous pouvez rechercher des modèles de texte dans vos documents PDF et ajouter des hyperliens en toute transparence. Imaginez avoir un document qui non seulement transmet des informations, mais connecte également les lecteurs à des ressources pertinentes en cliquant simplement sur un lien. Cela semble intéressant, n'est-ce pas ? Dans ce didacticiel, nous vous guiderons étape par étape sur la façon de rechercher du texte à l'aide d'expressions régulières et d'ajouter des hyperliens dans vos PDF. Que vous soyez un développeur chevronné ou que vous débutiez, vous trouverez ce processus simple et gratifiant.

## Prérequis

Avant de passer aux choses sérieuses, assurons-nous que vous disposez de tout ce dont vous avez besoin pour suivre le cours. Voici une liste de contrôle pratique :

- .NET Framework : Vous devez avoir le .NET Framework installé sur votre machine (version 4.0 ou supérieure).
- Bibliothèque Aspose.PDF pour .NET : n'oubliez pas de télécharger et d'ajouter une référence à la bibliothèque Aspose.PDF dans votre projet. Vous pouvez la trouver[ici](https://releases.aspose.com/pdf/net/).
- IDE : vous aurez besoin d’un environnement de développement intégré (IDE) comme Visual Studio pour écrire et exécuter le code.
- Exemple de fichier PDF : récupérez un exemple de fichier PDF sur lequel vous pouvez tester le code. Vous pouvez créer un PDF simple ou utiliser l'un de vos documents existants.

Une fois que vous avez coché tout ce qui figure sur cette liste, nous sommes prêts à partir !

## Paquets d'importation

La première étape de notre parcours consiste à importer les packages nécessaires. C'est ici que nous indiquons à notre projet les outils que nous allons utiliser. Voici comment procéder :

Dans votre fichier C#, commencez par inclure les espaces de noms suivants en haut :

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

En important ces espaces de noms, vous donnez à votre programme accès à toutes les fonctionnalités intéressantes qu'Aspose.PDF a à offrir.

Maintenant que tout est prêt, il est temps de passer à l'action. Nous allons procéder par étapes, alors suivez-les attentivement !

### Étape 1 : définissez votre répertoire de documents

Tout d'abord, vous devez spécifier où sont stockés vos fichiers PDF. Modifiez le`dataDir` variable pour pointer vers le répertoire de votre document. Voici comment procéder :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers vos documents.

### Étape 2 : Créer un TextFragmentAbsorber

 Ensuite, nous avons besoin d'un outil pour trouver le texte que nous voulons lier. Entrez le`TextFragmentAbsorber`Ce petit gars nous aidera à rechercher le modèle de texte spécifique dans notre PDF.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

Ici, nous recherchons un modèle spécifique : quatre chiffres, un tiret, suivi de quatre autres chiffres (comme un numéro de téléphone ou une année).

### Étape 3 : Activer la recherche par expression régulière

 Nous utilisons déjà une expression régulière pour trouver notre modèle de texte, mais nous devons nous assurer que notre`absorber` sait qu'il est activé. Ceci est crucial pour qu'il effectue une recherche correctement.

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

### Étape 4 : Initialiser PdfContentEditor

 Maintenant que notre absorbeur est prêt, nous avons besoin d'un`PdfContentEditor` pour travailler avec notre fichier PDF. Cette classe nous permet de nous lier à notre PDF et de le manipuler.

```csharp
PdfContentEditor editor = new PdfContentEditor();
```

### Étape 5 : liez votre fichier PDF source

Notre éditeur de contenu étant prêt, il est temps de le lier au fichier PDF réel sur lequel nous souhaitons travailler.

```csharp
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

 Assurez-vous de remplacer`"SearchRegularExpressionPage.pdf"` avec le nom de votre fichier PDF.

### Étape 6 : Accepter l'absorbeur pour la page

Nous devons faire savoir à notre éditeur que nous souhaitons effectuer une recherche sur une page spécifique du document. Dans ce cas, nous choisirons la page 1.

```csharp
editor.Document.Pages[1].Accept(absorber);
```

### Étape 7 : Préparez-vous à parcourir des fragments de texte

Nous sommes maintenant prêts à parcourir tous les fragments de texte trouvés par notre absorbeur. Nous allons peaufiner leur apparence et configurer notre lien hypertexte.

```csharp
int[] dashArray = { };
String[] LEArray = { };
Color blue = Color.Blue;
```

Ici, nous définissons certains paramètres, comme la couleur de notre lien hypertexte.

### Étape 8 : Parcourir chaque fragment de texte

Pour chaque fragment de texte correspondant à notre recherche, nous allons changer sa couleur et créer un lien hypertexte. Voici à quoi cela ressemble :

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    Rectangle rect = new Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
    
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, bleu, actionName);
    editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
        (float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
```

### Étape 9 : Enregistrer le PDF modifié

Nous avons presque terminé ! Il est maintenant temps d'enregistrer nos modifications dans un nouveau fichier PDF.

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
```

### Étape 10 : Fermer l'éditeur

Enfin, n'oubliez pas de fermer votre document pour libérer les ressources !

```csharp
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

Vous venez de créer un PDF avec un lien hypertexte généré de manière dynamique à partir des résultats de recherche. C'est génial, non ?

## Conclusion

Et voilà ! En suivant ces étapes, vous avez appris à effectuer une recherche dans un PDF et à ajouter des hyperliens à l'aide de la bibliothèque Aspose.PDF pour .NET. Cela peut ouvrir un monde de possibilités, en particulier si vous travaillez avec des documents qui nécessitent de l'interactivité. Imaginez ajouter des liens vers des ressources connexes, des sites Web de référence ou même des pages internes, le tout avec seulement quelques lignes de code !
## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?  
Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de créer, manipuler et gérer des documents PDF dans des applications .NET.

### Comment puis-je télécharger Aspose.PDF pour .NET ?  
 Vous pouvez télécharger la bibliothèque[ici](https://releases.aspose.com/pdf/net/).

### Puis-je essayer Aspose.PDF gratuitement ?  
 Absolument ! Vous pouvez obtenir un essai gratuit[ici](https://releases.aspose.com/).

### Existe-t-il un support disponible pour les produits Aspose ?  
 Oui, vous pouvez trouver du soutien et des discussions communautaires[ici](https://forum.aspose.com/c/pdf/10).

### Comment puis-je obtenir une licence temporaire pour Aspose.PDF ?  
 Vous pouvez demander une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
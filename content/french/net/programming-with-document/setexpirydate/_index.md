---
title: Définir la date d'expiration dans le fichier PDF
linktitle: Définir la date d'expiration dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment définir une date d'expiration dans les fichiers PDF à l'aide d'Aspose.PDF pour .NET. Améliorez la sécurité des documents avec ce guide étape par étape.
type: docs
weight: 300
url: /fr/net/programming-with-document/setexpirydate/
---
## Introduction

À l'ère du numérique, la gestion et la sécurisation des documents sont plus cruciales que jamais. Imaginez que vous envoyez un PDF qui devient automatiquement inaccessible après une certaine date. Cela ressemble à de la magie, n'est-ce pas ? Eh bien, avec Aspose.PDF pour .NET, vous pouvez facilement définir une date d'expiration pour vos fichiers PDF. Cette fonctionnalité est particulièrement utile pour les documents sensibles qui doivent être restreints après une certaine période. Dans ce tutoriel, nous vous expliquerons étape par étape le processus de définition d'une date d'expiration dans un fichier PDF. Alors, prenez votre casquette de codeur et plongeons-nous dans le vif du sujet !

## Prérequis

Avant de commencer, vous devez mettre en place quelques éléments :

1. Environnement de développement : assurez-vous de disposer d'un environnement de développement .NET. Il peut s'agir de Visual Studio ou de tout autre IDE prenant en charge .NET.
2.  Aspose.PDF pour .NET : vous devez avoir installé la bibliothèque Aspose.PDF. Si vous ne l'avez pas encore fait, vous pouvez la télécharger à partir de[ici](https://releases.aspose.com/pdf/net/).
3. Connaissances de base de C# : ce tutoriel suppose que vous avez une compréhension de base de la programmation C#. Si vous débutez avec C#, ne vous inquiétez pas ! Nous allons faire en sorte que cela reste simple et direct.

## Paquets d'importation

Pour commencer à utiliser Aspose.PDF, vous devez importer les espaces de noms nécessaires dans votre projet C#. Voici comment procéder :

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

Ces espaces de noms vous donnent accès aux fonctionnalités principales requises pour travailler avec des documents PDF dans Aspose.PDF.

## Étape 1 : Configurez votre répertoire de documents

Tout d'abord, vous devez spécifier le chemin d'accès à votre répertoire de documents. C'est là que votre PDF de sortie sera enregistré. 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où vous souhaitez enregistrer votre fichier PDF. C'est comme si vous disiez à votre programme : « Hé, c'est ici que je garde mes fichiers ! »

## Étape 2 : instancier l'objet document

 Ensuite, vous devez créer une nouvelle instance de`Document` classe. C'est votre toile où vous allez créer votre PDF.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

 Pensez à la`Document` objet comme une feuille de papier vierge. Vous pouvez y ajouter du contenu comme vous le souhaitez !

## Étape 3 : Ajouter une page au PDF

Maintenant que votre document est configuré, il est temps d'y ajouter une page. C'est là que votre contenu sera placé.

```csharp
doc.Pages.Add();
```

Vous venez de créer une nouvelle page dans votre PDF. C'est comme ajouter une nouvelle page dans votre carnet sur laquelle vous pouvez noter vos pensées.

## Étape 4 : Ajouter du texte à la page

Rendons cette page un peu plus intéressante en ajoutant du texte. Nous ajouterons un simple message « Bonjour le monde ».

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

Cette ligne de code ajoute un fragment de texte à la première page de votre PDF. C'est comme écrire un titre en haut de votre page !

## Étape 5 : Créer un JavaScript pour la date d'expiration

Vient maintenant la partie amusante ! Vous allez créer une action JavaScript qui vérifiera la date d'expiration du PDF. Si la date actuelle dépasse la date d'expiration, un message avertira l'utilisateur.

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
```

Voici ce qui se passe :
- Vous définissez l'année et le mois d'expiration.
- Vous obtenez la date d'aujourd'hui.
- Vous comparez la date d'aujourd'hui avec la date d'expiration.
- Si la date d'aujourd'hui est dépassée, un message apparaît !

## Étape 6 : définir JavaScript comme action d'ouverture de PDF

Vous devez maintenant définir l'action JavaScript comme action d'ouverture pour votre document PDF. Cela signifie que le JavaScript s'exécutera dès que le PDF sera ouvert.

```csharp
doc.OpenAction = javaScript;
```

Cette ligne indique au PDF d'exécuter le JavaScript lorsque quelqu'un l'ouvre. C'est comme définir un rappel qui se déclenche dès que vous ouvrez votre calendrier !

## Étape 7 : Enregistrer le document PDF

Enfin, il est temps d'enregistrer votre document PDF avec la fonction de date d'expiration. 

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
doc.Save(dataDir);
```

Cette ligne enregistre votre PDF dans le répertoire spécifié sous le nom « SetExpiryDate_out.pdf ». C'est comme mettre votre œuvre terminée dans un cadre !

## Conclusion

Et voilà ! Vous avez réussi à créer un fichier PDF avec une date d'expiration à l'aide d'Aspose.PDF pour .NET. Cette fonctionnalité améliore non seulement la sécurité, mais garantit également que les informations sensibles sont conservées sous contrôle. Que vous envoyiez des contrats, des rapports ou tout autre document important, la définition d'une date d'expiration peut changer la donne.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir des documents PDF dans des applications .NET.

### Puis-je utiliser Aspose.PDF gratuitement ?
 Oui, vous pouvez utiliser une version d'essai gratuite d'Aspose.PDF. Vous pouvez la télécharger[ici](https://releases.aspose.com/).

### Comment acheter Aspose.PDF ?
Vous pouvez acheter Aspose.PDF en visitant le[page d'achat](https://purchase.aspose.com/buy).

### Et si j'ai besoin d'assistance ?
Si vous avez des questions ou besoin d'aide, vous pouvez visiter le[Forum d'assistance Aspose](https://forum.aspose.com/c/pdf/10).

### Puis-je obtenir une licence temporaire pour Aspose.PDF ?
 Oui, vous pouvez demander une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
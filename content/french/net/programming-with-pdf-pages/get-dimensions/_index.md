---
title: Obtenir les dimensions de la page PDF
linktitle: Obtenir les dimensions de la page PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Dans ce tutoriel, nous expliquons comment obtenir les dimensions d'une page PDF et effectuer des manipulations à l'aide d'Aspose.PDF pour .NET. Des étapes détaillées sont fournies pour vous guider tout au long du processus.
type: docs
weight: 60
url: /fr/net/programming-with-pdf-pages/get-dimensions/
---
## Introduction

Avez-vous déjà eu besoin de manipuler les dimensions de page d'un document PDF ? Peut-être avez-vous voulu redimensionner une page ou la faire pivoter pour l'adapter à vos besoins ? Si tel est le cas, vous êtes au bon endroit ! Dans ce didacticiel, nous vous expliquerons comment récupérer et modifier les dimensions de page PDF à l'aide d'Aspose.PDF pour .NET. Que vous soyez un développeur débutant ou expérimenté, vous trouverez ce guide simple et facile à suivre.

Aspose.PDF pour .NET est une bibliothèque puissante qui vous permet de créer, de manipuler et de transformer des fichiers PDF sans effort. C'est comme avoir un couteau suisse pour les PDF : vous pouvez peaufiner chaque petit détail pour l'adapter exactement à vos besoins. Alors, plongeons-nous dans le vif du sujet et apprenons à récupérer et à mettre à jour les dimensions des pages PDF à l'aide de cet outil génial !

## Prérequis

Avant de commencer, vous aurez besoin de quelques éléments pour suivre ce tutoriel en douceur :

1.  Aspose.PDF pour .NET : vous pouvez[téléchargez la dernière version ici](https://releases.aspose.com/pdf/net/) . Si vous n'avez pas de permis, ne vous inquiétez pas ! Vous pouvez en demander un[essai gratuit](https://releases.aspose.com/) , ou optez pour un[permis temporaire](https://purchase.aspose.com/temporary-license/).
2. Visual Studio : l’environnement de développement que vous utiliserez pour écrire et exécuter le code.
3. Connaissances de base de C# : Bien que nous gardions les choses simples, une certaine familiarité avec C# rendra le processus plus fluide.
4. Fichier PDF avec lequel travailler : récupérez n’importe quel exemple de fichier PDF ou créez-en un nouveau pour le tester.

## Paquets d'importation

Pour travailler avec Aspose.PDF pour .NET, vous devez importer quelques espaces de noms essentiels. Cela prépare le terrain pour interagir avec les documents PDF. Voici comment procéder :

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

Ces importations garantissent que vous avez accès aux classes de base nécessaires à la manipulation des fichiers PDF, notamment pour la gestion des pages et la récupération de leurs dimensions.

Maintenant que tout est en place, décomposons le processus en étapes faciles à suivre.

## Étape 1 : Définir le chemin d’accès au fichier et charger le document

La première étape consiste à spécifier le chemin d'accès à votre document PDF et à le charger à l'aide d'Aspose.PDF. Cela vous permettra d'interagir avec les pages du fichier PDF.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

Dans cette étape, vous ouvrez essentiellement le fichier PDF sur lequel vous souhaitez travailler. Si vous avez déjà ouvert un livre sur une page particulière, c'est assez similaire, mais à la place, vous ouvrez un document PDF pour accéder à ses pages.

## Étape 2 : ajouter une page vierge si aucune page n’existe

Que faire si votre document ne contient aucune page ? Ne vous inquiétez pas ! Nous pouvons ajouter une page vierge au document et travailler dessus. Voici comment vérifier si une page existe et en ajouter une nouvelle si nécessaire :

```csharp
// Ajoute une page vierge au document PDF
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

Cette ligne de code vérifie s'il existe déjà une page dans le document. Si oui, elle sélectionne la première page (`Pages[1]`). Sinon, il crée une page vierge et l'ajoute au PDF.

Imaginez que vous ouvrez un cahier vide et que vous écrivez sur la première page s’il n’y a rien. Facile, n’est-ce pas ?

## Étape 3 : Obtenir des informations sur la hauteur et la largeur de la page

 Maintenant que nous avons une page avec laquelle travailler, récupérons les dimensions de la page. Nous utiliserons le`GetPageRect()` méthode pour obtenir la hauteur et la largeur.

```csharp
// Obtenir des informations sur la hauteur et la largeur de la page
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

 Ici,`GetPageRect(true)` renvoie un rectangle qui inclut la hauteur et la largeur de la page. C'est comme mesurer un morceau de papier avec une règle. Le résultat sera affiché dans la console, vous donnant les dimensions actuelles de la page.

## Étape 4 : faites pivoter la page de 90 degrés

Vous souhaitez faire pivoter la page ? Aucun problème ! Avec une simple propriété, vous pouvez faire pivoter la page de 90 degrés.

```csharp
// Faire pivoter la page à un angle de 90 degrés
page.Rotate = Rotation.on90;
```

Cette étape permet de faire pivoter la page de 90 degrés dans le sens des aiguilles d'une montre. Imaginez que vous tournez une feuille imprimée sur votre bureau : elle est désormais en mode paysage !

## Étape 5 : revérifiez les dimensions de la page après la rotation

Après avoir fait pivoter la page, il est judicieux de vérifier à nouveau les dimensions. Pourquoi ? Parce que la rotation peut affecter la façon dont vous interprétez la hauteur et la largeur.

```csharp
// Obtenir des informations sur la hauteur et la largeur de la page
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height.ToString());
```

Désormais, les dimensions de la page seront mises à jour en fonction de la nouvelle orientation. C'est comme faire pivoter une photo sur votre téléphone : soudain, la largeur devient la hauteur, et vice versa.


## Conclusion

Félicitations ! Vous avez appris avec succès à récupérer et modifier les dimensions d'une page PDF à l'aide d'Aspose.PDF pour .NET. À présent, vous devriez être en mesure de charger un PDF, de vérifier ses dimensions et même de faire pivoter la page si nécessaire.

La manipulation des fichiers PDF n'est pas forcément compliquée. Avec Aspose.PDF, il suffit de suivre quelques étapes et d'utiliser des méthodes intuitives. Ainsi, la prochaine fois que vous aurez besoin de gérer les dimensions d'une page PDF, vous saurez exactement quoi faire !

## FAQ

### Puis-je faire pivoter la page selon d’autres angles que 90 degrés ?
 Oui, Aspose.PDF vous permet de faire pivoter les pages de 0, 90, 180 ou 270 degrés à l'aide de la`Rotation` propriété.

### Que se passe-t-il si mon PDF n’a pas de pages ?
 Si votre PDF ne contient pas de pages, vous pouvez ajouter une page vierge à l'aide de l'`Pages.Add()` méthode, comme indiqué dans ce tutoriel.

### Puis-je manipuler plusieurs pages à la fois ?
Oui, vous pouvez parcourir plusieurs pages et appliquer des transformations, comme le redimensionnement ou la rotation, à chacune d'elles.

### Les dimensions de la page affectent-elles le contenu à l’intérieur du PDF ?
Les dimensions de la page modifient uniquement la taille de la zone de travail, pas le contenu. Cependant, le redimensionnement peut modifier la façon dont le contenu apparaît sur la page.

### Où puis-je trouver plus d'informations sur Aspose.PDF pour .NET ?
 Vous pouvez visiter le[documentation ici](https://reference.aspose.com/pdf/net/) pour des informations plus détaillées et des cas d'utilisation avancés.
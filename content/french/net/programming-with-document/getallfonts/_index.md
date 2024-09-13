---
title: Obtenir toutes les polices dans le fichier PDF
linktitle: Obtenir toutes les polices dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire toutes les polices d'un fichier PDF à l'aide d'Aspose.PDF pour .NET dans ce didacticiel étape par étape. Idéal pour les développeurs et les passionnés de PDF.
type: docs
weight: 160
url: /fr/net/programming-with-document/getallfonts/
---
## Introduction

Vous êtes-vous déjà demandé comment extraire toutes les polices utilisées dans un fichier PDF ? Que vous soyez un développeur cherchant à analyser des documents PDF ou simplement curieux de connaître les polices de votre livre électronique préféré, il peut être extrêmement utile de comprendre comment récupérer les informations sur les polices. Dans ce tutoriel, nous allons plonger dans le monde d'Aspose.PDF pour .NET, une bibliothèque puissante qui vous permet de manipuler facilement des fichiers PDF. À la fin de ce guide, vous serez en mesure d'extraire et de répertorier toutes les polices utilisées dans n'importe quel document PDF. Alors, commençons !

## Prérequis

Avant de passer au code, vous devez mettre en place quelques éléments :

1. Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur. C'est l'IDE que nous utiliserons pour ce tutoriel.
2.  Aspose.PDF pour .NET : vous devez disposer de la bibliothèque Aspose.PDF. Vous pouvez la télécharger à partir du[site web](https://releases.aspose.com/pdf/net/).
3. Connaissances de base de C# : la familiarité avec la programmation C# vous aidera à mieux comprendre les extraits de code.

## Paquets d'importation

Pour commencer, vous devez importer les packages nécessaires dans votre projet C#. Voici comment procéder :

### Créer un nouveau projet

Ouvrez Visual Studio et créez un nouveau projet d'application console C#. Ce sera l'environnement dans lequel nous écrirons notre code.

### Ajouter une référence Aspose.PDF

1. Faites un clic droit sur votre projet dans l’Explorateur de solutions.
2. Sélectionnez « Gérer les packages NuGet ».
3. Recherchez « Aspose.PDF » et installez la dernière version.

### Importer les espaces de noms requis

En haut de votre fichier C#, importez les espaces de noms nécessaires en incluant les lignes suivantes :

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Maintenant que nous avons tout configuré, passons au code !

## Étape 1 : Configurez votre répertoire de documents

Tout d'abord, vous devez spécifier le chemin d'accès à votre document PDF. C'est là qu'Aspose.PDF recherchera le fichier que vous souhaitez analyser.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où se trouve votre fichier PDF. Cela pourrait être quelque chose comme`@"C:\Documents\"`.

## Étape 2 : Charger le document PDF

 Ensuite, vous devrez charger le document PDF dans votre application. Cela se fait à l'aide de l'`Document` cours fourni par Aspose.PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 Ici, remplacez`"input.pdf"` avec le nom de votre fichier PDF. Cette ligne de code initialise un nouveau`Document` objet qui représente votre PDF.

## Étape 3 : Récupérer toutes les polices

 Vient maintenant la partie passionnante ! Vous utiliserez le`FontUtilities` classe pour obtenir toutes les polices utilisées dans le document.

```csharp
Aspose.Pdf.Text.Font[] fonts = doc.FontUtilities.GetAllFonts();
```

 Cette ligne récupère un tableau de`Font` objets, chacun représentant une police utilisée dans le PDF.

## Étape 4 : Parcourir les polices

Enfin, vous souhaiterez afficher les noms des polices. Cela se fait à l'aide d'une simple boucle.

```csharp
foreach (Aspose.Pdf.Text.Font font in fonts)
{
    Console.WriteLine(font.FontName);
}
```

Cette boucle parcourt chaque police du tableau et affiche son nom sur la console. C'est un moyen simple de voir quelles polices sont disponibles dans votre PDF.

## Conclusion

Et voilà ! Vous avez réussi à extraire toutes les polices d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Cette puissante bibliothèque facilite la manipulation des documents PDF et, avec seulement quelques lignes de code, vous pouvez accéder à des informations précieuses comme les noms de polices. Que vous développiez un visualiseur PDF, analysiez des documents ou que vous soyez simplement curieux, ces connaissances vous seront utiles.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de créer, manipuler et convertir des documents PDF par programmation.

### Puis-je utiliser Aspose.PDF gratuitement ?
 Oui, Aspose propose une version d'essai gratuite que vous pouvez utiliser pour évaluer la bibliothèque. Vous pouvez la télécharger[ici](https://releases.aspose.com/).

### Où puis-je trouver plus de documentation ?
 Vous trouverez une documentation complète sur le[Site Web d'Aspose](https://reference.aspose.com/pdf/net/).

### Est-il possible d'extraire d'autres informations d'un PDF ?
Absolument ! Aspose.PDF vous permet d'extraire du texte, des images et des métadonnées, entre autres.

### Comment puis-je obtenir de l'aide pour Aspose.PDF ?
 Vous pouvez obtenir de l'aide en visitant le[Forum Aspose](https://forum.aspose.com/c/pdf/10).
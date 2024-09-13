---
title: Boutons radio horizontaux et verticaux
linktitle: Boutons radio horizontaux et verticaux
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment créer des boutons radio alignés horizontalement et verticalement dans PDF à l'aide d'Aspose.PDF pour .NET avec ce didacticiel étape par étape.
type: docs
weight: 180
url: /fr/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
## Introduction

La création de formulaires PDF interactifs peut améliorer considérablement l'expérience utilisateur, notamment en matière de collecte d'informations. L'un des éléments de formulaire les plus courants est le bouton radio, qui permet aux utilisateurs de sélectionner une option parmi un ensemble. Dans ce didacticiel, nous allons découvrir comment créer des boutons radio alignés horizontalement et verticalement à l'aide d'Aspose.PDF pour .NET. Que vous soyez un développeur expérimenté ou que vous débutiez, ce guide vous guidera tout au long du processus, étape par étape, en vous assurant une compréhension claire de chaque partie.

## Prérequis

Avant de plonger dans le code, vous devez mettre en place quelques prérequis :

1.  Aspose.PDF pour .NET : Assurez-vous que la bibliothèque Aspose.PDF est installée. Vous pouvez la télécharger à partir du[site](https://releases.aspose.com/pdf/net/).
2. Visual Studio : un environnement de développement dans lequel vous pouvez écrire et tester votre code.
3. Connaissances de base de C# : la familiarité avec la programmation C# vous aidera à mieux comprendre les extraits de code.

## Paquets d'importation

Pour commencer, vous devez importer les packages nécessaires dans votre projet C#. Voici comment procéder :

### Créer un nouveau projet

Ouvrez Visual Studio et créez un nouveau projet C#. Vous pouvez choisir une application console pour plus de simplicité.

### Ajouter une référence Aspose.PDF

1. Faites un clic droit sur votre projet dans l’Explorateur de solutions.
2. Sélectionnez « Gérer les packages NuGet ».
3. Recherchez « Aspose.PDF » et installez la dernière version.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Facades;
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

Maintenant que tout est configuré, décomposons le code pour créer des boutons radio alignés horizontalement et verticalement.

## Étape 1 : Configurer le répertoire de documents

Dans cette étape, nous allons définir le chemin vers le répertoire où seront stockés vos documents PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où vous souhaitez enregistrer votre fichier PDF. Ceci est crucial car cela indique au programme où rechercher les fichiers d'entrée et où enregistrer la sortie.

## Étape 2 : charger le document PDF existant

 Ensuite, nous devons charger le document PDF avec lequel nous allons travailler. Cela se fait à l'aide de l'`FormEditor` classe.

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

Ici, nous créons une instance de`FormEditor` et le lier à un fichier PDF existant nommé`input.pdf`Assurez-vous que ce fichier existe dans le répertoire spécifié.

## Étape 3 : Configurer les propriétés des boutons radio

Maintenant, définissons quelques propriétés pour nos boutons radio. Cela inclut l'espace entre les boutons, leur orientation et leur taille.

```csharp
formEditor.RadioGap = 4; // Distance entre les options des boutons radio
formEditor.RadioHoriz = true; // Définir sur vrai pour l'alignement horizontal
formEditor.RadioButtonItemSize = 20; // Taille du bouton radio
formEditor.Facade.BorderWidth = 1; // Largeur de la bordure
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Couleur de la bordure
```

 Ces propriétés aideront à définir la manière dont les boutons radio apparaîtront dans le PDF.`RadioGap` la propriété contrôle l'espace entre les boutons, tandis que`RadioHoriz` détermine leur disposition.

## Étape 4 : ajouter des boutons radio horizontaux

Maintenant, ajoutons les boutons radio horizontaux au PDF.

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

 Dans ce code, nous définissons les éléments des boutons radio et les ajoutons au PDF.`AddField`La méthode prend plusieurs paramètres, notamment le type de champ, le nom du champ et les coordonnées de placement.

## Étape 5 : ajouter des boutons radio verticaux

Ensuite, nous allons ajouter les boutons radio verticaux. Pour ce faire, nous devons rétablir l'orientation verticale.

```csharp
formEditor.RadioHoriz = false; // Définir sur faux pour l'alignement vertical
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

Comme précédemment, nous définissons les éléments et les ajoutons au PDF, mais cette fois, ils seront alignés verticalement.

## Étape 6 : Enregistrer le document PDF

Enfin, nous devons enregistrer le document PDF modifié.

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
```

Ce code enregistre le PDF avec les boutons radio nouvellement ajoutés. Assurez-vous de vérifier le répertoire spécifié pour le fichier de sortie.

## Conclusion

Créer des boutons radio dans un PDF à l'aide d'Aspose.PDF pour .NET est un processus simple. En suivant les étapes décrites dans ce didacticiel, vous pouvez facilement ajouter des boutons radio alignés horizontalement et verticalement à vos formulaires PDF. Cela améliore non seulement l'interactivité de vos documents, mais aussi l'expérience utilisateur globale. Alors, allez-y et essayez-le !

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir des documents PDF par programmation.

### Puis-je utiliser Aspose.PDF gratuitement ?
 Oui, Aspose propose une version d'essai gratuite que vous pouvez utiliser pour évaluer la bibliothèque. Vous pouvez la télécharger[ici](https://releases.aspose.com/).

### Comment puis-je obtenir de l'aide pour Aspose.PDF ?
 Vous pouvez obtenir de l'aide en visitant le[Forum Aspose](https://forum.aspose.com/c/pdf/10).

### Est-il possible de créer d'autres éléments de formulaire avec Aspose.PDF ?
Absolument ! Aspose.PDF prend en charge divers éléments de formulaire, notamment les champs de texte, les cases à cocher et les listes déroulantes.

### Où puis-je acheter Aspose.PDF pour .NET ?
 Vous pouvez acheter Aspose.PDF pour .NET sur le site[page d'achat](https://purchase.aspose.com/buy).
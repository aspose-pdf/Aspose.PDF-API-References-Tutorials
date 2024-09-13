---
title: Créer un lien hypertexte local dans un fichier PDF
linktitle: Créer un lien hypertexte local dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à créer des hyperliens locaux dans des fichiers PDF à l'aide d'Aspose.PDF pour .NET sans effort grâce à notre guide étape par étape.
type: docs
weight: 40
url: /fr/net/programming-with-links-and-actions/create-local-hyperlink/
---
## Introduction

Dans ce guide, nous vous expliquerons le processus de création de liens hypertexte locaux dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous détaillerons chaque étape de manière claire, afin que même si vous êtes novice dans le monde de la manipulation de PDF, vous puissiez suivre le processus sans effort.

## Prérequis

Avant de plonger tête baissée dans le code, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1.  Visual Studio : vous en aurez besoin pour développer vos applications .NET. Téléchargez-le à partir du[site web](https://visualstudio.microsoft.com/).
2.  Aspose.PDF pour .NET : Vous pouvez télécharger cette bibliothèque via le[lien de téléchargement ici](https://releases.aspose.com/pdf/net/)Il est livré avec un riche ensemble de fonctionnalités pour la manipulation de PDF.
3. Connaissances de base de C# : une petite familiarité avec la programmation C# vous aidera, mais ne vous inquiétez pas ; nous allons parcourir le code ligne par ligne.
4.  .NET Framework : Assurez-vous que .NET Framework est installé sur votre ordinateur. Vous pouvez vérifier la configuration requise sur le fichier Aspose.PDF[documentation](https://reference.aspose.com/pdf/net/).

Une fois ces prérequis définis, vous êtes prêt à apprendre à créer des hyperliens locaux dans vos documents PDF !

## Paquets d'importation

Maintenant que vous êtes prêt, il est temps d'importer les packages nécessaires dans votre projet C#. La bibliothèque Aspose.PDF contient toutes les classes dont nous avons besoin. Voici comment procéder :

### Ouvrez votre projet

Ouvrez votre projet .NET existant ou créez-en un nouveau dans Visual Studio. Si vous démarrez de zéro, sélectionnez « Créer un nouveau projet » dans l'écran de démarrage.

### Ajouter une référence à Aspose.PDF

 Cliquez avec le bouton droit sur « Dépendances » dans votre dossier de projet dans l'Explorateur de solutions. Sélectionnez « Gérer les packages NuGet », puis recherchez`Aspose.PDF`. Installez la dernière version disponible. Elle vous apportera tous les outils dont vous avez besoin pour créer et manipuler des PDF.

### Importer des espaces de noms

En haut de votre fichier .cs, ajoutez des directives d'utilisation pour la bibliothèque Aspose.PDF comme ceci :

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

De cette façon, vous pourrez accéder aux fonctionnalités de la bibliothèque.

Décomposons le processus de création de liens hypertexte locaux en étapes simples. Chaque étape sera expliquée de manière détaillée pour vous aider à comprendre la logique qui la sous-tend.

## Étape 1 : Configurer l'instance de document

Dans cette étape, vous allez créer une nouvelle instance de la classe Document, qui représente le fichier PDF avec lequel vous allez travailler.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Définissez votre répertoire de documents
Document doc = new Document(); // Créer une instance de document
```
 Le`dataDir` la variable est l'endroit où votre PDF nouvellement créé résidera. Vous devrez remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel sur votre système.`Document` la classe crée un nouveau document PDF dans lequel nous pouvons ajouter des pages et des liens.

## Étape 2 : Ajouter une page au document

Ensuite, vous allez ajouter une page à votre document PDF. 

```csharp
Page page = doc.Pages.Add(); // Ajouter une page à la collection de pages
```
 Le`Pages.Add()` La méthode ajoute une nouvelle page au document. C'est là que résidera tout votre contenu.

## Étape 3 : Créer un fragment de texte

Maintenant, créons un morceau de texte qui fera office de lien cliquable.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
 Le`TextFragment` représente un segment de texte dans le PDF. Ici, nous créons un lien qui indique aux utilisateurs qu'il les mènera à la page 7.

## Étape 4 : Créer un lien hypertexte local

C'est ici que la magie opère ! Vous devez créer un lien hypertexte local qui indiquera au fragment de texte où pointer.

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); // Créer un lien hypertexte local
link.TargetPageNumber = 7; //Définir la page cible pour l'instance de lien
text.Hyperlink = link; // Définir un lien hypertexte TextFragment
```
 Le`LocalHyperlink` classe est ce qui nous permet de pointer vers d'autres pages dans le même document. En définissant`TargetPageNumber` jusqu'à 7, vous indiquez au lien hypertexte de passer à cette page spécifique lorsqu'il est cliqué.

## Étape 5 : ajouter le fragment de texte à la page

Après avoir configuré l'hyperlien, il est temps d'ajouter notre fragment de texte à la page que nous avons créée.

```csharp
page.Paragraphs.Add(text); // Ajouter du texte à la collection de paragraphes de la page
```
Cette ligne ajoute votre texte cliquable à la collection de paragraphes de la page.

## Étape 6 : Créer un autre fragment de texte (facultatif)

Ajoutons un autre lien hypertexte pour revenir à la page 1.

```csharp
text = new TextFragment("link page number test to page 1"); // Créer un nouveau fragment de texte
text.IsInNewPage = true; // Ajoutez-le à une nouvelle page
```
 Créer un nouveau`TextFragment` pour le deuxième lien, nous avons mis`IsInNewPage` à vrai, indiquant que ce texte sera placé sur une nouvelle page.

## Étape 7 : Configurer le deuxième lien hypertexte local

Tout comme précédemment, vous allez créer un autre lien hypertexte local pour la page 1.

```csharp
link = new LocalHyperlink(); // Créer une autre instance d’hyperlien local
link.TargetPageNumber = 1; //Définir la page cible pour le deuxième lien hypertexte
text.Hyperlink = link; // Définir le lien pour le deuxième TextFragment
```
Ce lien hypertexte cible la page 1, permettant aux utilisateurs de revenir en arrière lorsqu'ils atteignent la deuxième page.

## Étape 8 : ajouter le deuxième fragment de texte à la nouvelle page

Maintenant, ajoutons ce texte à sa page.

```csharp
page.Paragraphs.Add(text); // Ajouter du texte à la collection de paragraphes de l'objet de page
```
Similaire à l’étape 5, cette ligne ajoute le nouveau texte d’hyperlien à la page nouvellement créée.

## Étape 9 : Enregistrer le document

Enfin, il est temps de sauvegarder votre dur labeur ! 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; // Spécifier le nom du fichier de sortie
doc.Save(dataDir); // Enregistrer le document mis à jour
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
 Ceci combine votre chemin de répertoire avec le nom du fichier.`Save()` La méthode enregistre votre document et un message de confirmation vous indique que tout s'est bien passé !

## Conclusion

Créer des hyperliens locaux dans des fichiers PDF à l'aide d'Aspose.PDF pour .NET n'est pas seulement une astuce intéressante : c'est une fonctionnalité pratique qui améliore la navigation et l'expérience utilisateur. Vous disposez désormais des connaissances nécessaires pour orienter vos lecteurs directement vers les informations dont ils ont besoin. Repensez à notre analogie initiale : fini les âmes perdues errant dans des pages interminables.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de créer, manipuler et convertir des documents PDF par programmation à l'aide du framework .NET.

### Puis-je créer des hyperliens vers des pages Web externes ?
Oui, Aspose.PDF prend également en charge la création d'hyperliens vers des URL externes en plus des hyperliens locaux dans le PDF.

### Existe-t-il un essai gratuit pour Aspose.PDF ?
 Absolument ! Vous pouvez accéder à l'essai gratuit à partir du[site](https://releases.aspose.com/).

### Quels langages de programmation Aspose prend-il en charge ?
Aspose propose des bibliothèques pour divers langages de programmation, notamment Java, C++, et Python, entre autres.

### Comment puis-je obtenir de l'assistance pour les produits Aspose ?
 Vous pouvez demander de l'aide via le[Forum Aspose](https://forum.aspose.com/c/pdf/10).
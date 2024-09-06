---
title: Définir le nom de police par défaut
linktitle: Définir le nom de police par défaut
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment définir un nom de police par défaut lors du rendu de fichiers PDF en images à l'aide d'Aspose.PDF pour .NET. Ce guide couvre les conditions préalables, les instructions étape par étape et les FAQ.
type: docs
weight: 270
url: /fr/net/document-conversion/set-default-font-name/
---
## Introduction

Avez-vous déjà essayé de convertir un document PDF en image, mais vous avez constaté que les polices ne s'affichaient pas correctement ? Peut-être que le texte est déformé ou que la police d'origine n'est pas prise en charge. C'est là que la définition d'une police par défaut peut sauver la mise ! En utilisant Aspose.PDF pour .NET, vous pouvez facilement définir une police par défaut pour votre rendu PDF, garantissant ainsi que votre document soit net et professionnel. Dans ce didacticiel, nous allons vous expliquer comment définir le nom de police par défaut lors du rendu d'un PDF en image. À la fin de ce guide, vous aurez les compétences nécessaires pour relever tous les défis de rendu PDF qui se présenteront à vous. Prêt ? Plongeons-nous dans le vif du sujet !

## Prérequis

Avant de passer au code, vous devez mettre en place quelques éléments :

- Aspose.PDF pour .NET : Cette puissante bibliothèque est celle que nous allons utiliser pour manipuler notre document PDF. Vous pouvez la télécharger à partir du[Site Web d'Aspose](https://releases.aspose.com/pdf/net/).
- Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur. Il s'agira de notre environnement de développement.
- .NET Framework : assurez-vous que .NET Framework est installé. Aspose.PDF pour .NET prend en charge plusieurs versions. Consultez donc la documentation pour savoir si elle correspond à vos besoins.
- Un document PDF : vous aurez besoin d'un exemple de document PDF avec lequel travailler. Si vous n'en avez pas, créez un PDF simple ou téléchargez un exemple en ligne.

Une fois que tout est configuré, nous sommes prêts à commencer à coder !

## Paquets d'importation

Avant de nous plonger dans le code, il est essentiel d'importer les packages nécessaires. Cela nous permet de nous assurer d'avoir accès à toutes les classes et méthodes dont nous avons besoin pour notre projet.

```csharp
using Aspose.Pdf.Devices;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

Ces importations sont vitales car elles apportent les espaces de noms requis pour gérer la manipulation PDF, le rendu d'image et les opérations de flux de fichiers.

## Étape 1 : Configurez votre projet et le chemin d'accès au document

Tout d'abord, définissons le chemin d'accès au répertoire où se trouve votre document PDF. Ce sera votre point de départ pour manipuler le fichier PDF.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Ici,`dataDir` est le répertoire dans lequel se trouve votre document PDF. Assurez-vous de remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers votre document. Ceci est essentiel car le code doit savoir où récupérer le fichier PDF.

## Étape 2 : Charger le document PDF

Maintenant que nous avons le chemin du document, l’étape suivante consiste à charger le document PDF en mémoire afin que nous puissions commencer à travailler dessus.

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
```
 Nous utilisons le`Document` classe de la bibliothèque Aspose.PDF pour charger notre fichier PDF. Cette classe fournit diverses méthodes et propriétés pour travailler avec le document PDF.`"input.pdf"` doit être remplacé par le nom de fichier réel de votre PDF. Ce fichier sera utilisé comme entrée pour le rendu.

## Étape 3 : Créer un flux d'images pour la sortie

Une fois le document chargé, nous devons configurer un flux pour enregistrer l'image rendue. C'est là que l'image de sortie sera stockée.

```csharp
using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
```
 Le`FileStream`La classe est utilisée pour créer un nouveau fichier dans lequel l'image rendue sera enregistrée. Dans cet exemple, nous enregistrons l'image sous`"SetDefaultFontName.png"` . Le`FileMode.Create` garantit qu'un nouveau fichier est créé ou qu'un fichier existant est écrasé.

## Étape 4 : définir la résolution de l’image

Avant de convertir le PDF en image, il est essentiel de définir la résolution. Cela détermine la qualité et la clarté de l'image de sortie.

```csharp
Resolution resolution = new Resolution(300);
```
 Le`Resolution` La classe définit la résolution de l'image de sortie. Ici, nous avons choisi une résolution de 300 DPI (points par pouce), ce qui est la norme pour les images de haute qualité. Cela garantit que le texte et les graphiques de votre PDF s'affichent clairement sans perte de détails.

## Étape 5 : Configurer le périphérique PNG

Ensuite, nous devons configurer le périphérique qui gérera le rendu du PDF en image PNG.

```csharp
PngDevice pngDevice = new PngDevice(resolution);
```
 Le`PngDevice` La classe est responsable du rendu du document PDF en une image PNG. En passant la classe`resolution` pour nous y opposer, nous nous assurons que l'image est créée avec le DPI spécifié.

## Étape 6 : définir le nom de police par défaut

Voici la partie critique : définir le nom de la police par défaut. Il s'agira de la police de secours au cas où la police d'origine du PDF ne serait pas disponible.

```csharp
RenderingOptions ro = new RenderingOptions();
ro.DefaultFontName = "Arial";
pngDevice.RenderingOptions = ro;
```
 Nous créons une instance de`RenderingOptions` et définissez son`DefaultFontName` propriété à`"Arial"`. Cela signifie que si la police d'origine du PDF est introuvable, c'est Arial qui sera utilisée. Cette étape est cruciale pour maintenir la lisibilité et l'apparence du texte dans l'image rendue.

## Étape 7 : Rendre la page PDF en image

Enfin, avec tout configuré, nous pouvons maintenant restituer la première page du document PDF en une image et l’enregistrer à l’aide du flux de fichiers que nous avons créé précédemment.

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```
 Le`Process` méthode de la`PngDevice` La classe est utilisée pour restituer la page PDF spécifiée (dans ce cas, la première page) en une image. La sortie est ensuite enregistrée dans le`imageStream`. Cette étape convertit la page PDF en une image PNG avec la résolution spécifiée et la police par défaut.

## Étape 8 : fermez le flux de fichiers et le document PDF

Après avoir rendu l'image, il est essentiel de fermer le flux de fichiers et le document PDF pour libérer des ressources.

```csharp
imageStream.Close();
pdfDocument.Dispose();
```
Fermeture de la`imageStream` garantit que le fichier est enregistré correctement et qu'aucune donnée n'est perdue. Élimination du`pdfDocument` libère de la mémoire et des ressources, évitant ainsi toute fuite de mémoire potentielle.

## Conclusion

Et voilà ! Avec seulement quelques lignes de code, vous avez appris à définir un nom de police par défaut lors du rendu d'un PDF en image à l'aide d'Aspose.PDF pour .NET. Cette compétence est incroyablement pratique, en particulier lorsqu'il s'agit de fichiers PDF susceptibles de contenir des polices non prises en charge. En définissant une police par défaut, vous vous assurez que vos images rendues conservent leur lisibilité et leur aspect professionnel.

## FAQ

### Que se passe-t-il si la police par défaut spécifiée n'est pas installée sur le système ?
 Si la police par défaut spécifiée dans le`RenderingOptions` n'est pas installé sur le système, Aspose.PDF utilisera une police de secours définie par le système.

### Puis-je utiliser d’autres polices qu’Arial comme police par défaut ?
Absolument ! Vous pouvez définir n'importe quelle police installée sur votre système comme police par défaut.

### Est-il possible de rendre plusieurs pages d'un PDF en images en une seule fois ?
Oui, vous pouvez parcourir les pages de votre PDF et restituer chaque page individuellement en utilisant le même processus.

### La définition d’une résolution élevée affecte-t-elle les performances du rendu PDF ?
Oui, des résolutions plus élevées donneront lieu à des fichiers image plus volumineux et peuvent augmenter le temps de rendu, mais elles produiront également des images plus claires.

### Puis-je restituer le PDF dans d'autres formats d'image que PNG ?
Oui, Aspose.PDF prend en charge le rendu dans divers formats d'image tels que JPEG, BMP et TIFF.
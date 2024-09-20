---
title: Extraire du texte à l'aide d'un périphérique texte
linktitle: Extraire du texte à l'aide d'un périphérique texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire du texte d’un document PDF à l’aide du périphérique texte dans Aspose.PDF pour .NET.
type: docs
weight: 210
url: /fr/net/programming-with-text/extract-text-using-text-device/
---
## Introduction

L'extraction de texte d'un PDF peut s'avérer délicate, en particulier lorsqu'il s'agit de documents ayant différents formats, des polices intégrées ou des mises en page complexes. Mais avec Aspose.PDF pour .NET, ce processus devient un jeu d'enfant ! Que vous souhaitiez convertir des pages d'un PDF en texte brut pour une analyse plus approfondie ou que vous ayez simplement besoin d'extraire des sections spécifiques, Aspose.PDF est là pour vous. Dans ce didacticiel, nous allons détailler étape par étape comment extraire du texte d'un PDF à l'aide de la classe TextDevice dans Aspose.PDF. Nous fournirons également des explications claires, afin que vous puissiez appliquer facilement les mêmes méthodes à vos propres projets.

## Prérequis

Avant de passer au code, assurez-vous que tout est en place pour suivre la procédure. Voici ce dont vous aurez besoin :

1.  Aspose.PDF pour .NET : Téléchargez la dernière version à partir du[Page de téléchargement d'Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/).
2. Environnement de développement : Visual Studio ou tout autre environnement de développement C#.
3. .NET Framework : assurez-vous que votre projet cible .NET Framework 4.x ou supérieur.
4. Fichier PDF d'entrée : un fichier PDF que vous utiliserez pour l'extraction de texte. Placez-le dans un répertoire sur votre machine (nous l'appellerons`YOUR DOCUMENT DIRECTORY`).

## Paquets d'importation

En haut de votre code, vous devrez importer les espaces de noms nécessaires pour travailler avec Aspose.PDF :

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## Étape 1 : Chargez votre document PDF

 Avant d'extraire le texte, nous devons charger le document PDF en mémoire. Dans cette étape, vous ouvrirez votre PDF à l'aide d'Aspose.PDF`Document` classe. Cela vous permettra d'accéder à toutes les pages et à tous les contenus du fichier.

```csharp
// Définissez le chemin d'accès à votre document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Charger le document PDF
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Ici, nous utilisons`Document pdfDocument = new Document(dataDir + "input.pdf");` pour charger le PDF. Le`dataDir` La variable contient le chemin du répertoire de votre fichier PDF. Cela nous donnera accès à l'intégralité du document, nous permettant de parcourir les pages et d'extraire le contenu.

## Étape 2 : Configurer un générateur de chaînes pour le stockage de texte

 Maintenant que le document est chargé, nous avons besoin d'un moyen de stocker le texte extrait. Pour cela, nous utiliserons un`StringBuilder` qui permet une concaténation efficace des chaînes.

```csharp
// StringBuilder pour contenir le texte extrait
StringBuilder builder = new StringBuilder();
```

 Nous initialisons un`StringBuilder`instance, qui collectera le texte extrait de chaque page. C'est une manière plus efficace de gérer des chaînes volumineuses par rapport à la concaténation de chaînes classique dans une boucle.

## Étape 3 : Parcourir les pages PDF

 Ensuite, nous parcourons chaque page du document PDF pour extraire le texte. Nous traiterons chaque page individuellement à l'aide de la fonction`TextDevice` classe, qui est responsable de la conversion du contenu PDF au format texte.

```csharp
// Parcourir toutes les pages du PDF
foreach (Page pdfPage in pdfDocument.Pages)
{
    // Traiter chaque page pour l'extraction de texte
}
```

Cette boucle parcourt chaque page du PDF (`pdfDocument.Pages` ). Pour chaque page, nous allons extraire le texte et l'ajouter à notre`StringBuilder`.

## Étape 4 : Extraire le texte de chaque page

 Maintenant, nous allons configurer le processus d'extraction de texte pour chaque page. Ici, nous allons créer un`TextDevice` objet et l'utiliser pour traiter les pages PDF.`TextDevice` extrait du texte brut ou formaté en fonction des options d'extraction que nous définissons.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // Créer un périphérique texte pour l'extraction de texte
    TextDevice textDevice = new TextDevice();
    
    // Définir les options d'extraction de texte sur le mode « Pure »
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //Extraire le texte de la page actuelle et l'enregistrer dans le flux de mémoire
    textDevice.Process(pdfPage, textStream);

    // Convertir le flux de mémoire en texte
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // Ajoutez le texte extrait au StringBuilder
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : Le`TextDevice` la classe est utilisée pour extraire du texte du PDF.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : Cette option extrait le texte brut sans conserver aucun formatage comme les polices ou les positions. Vous pouvez également utiliser`TextFormattingMode.Raw` si vous avez besoin de plus de contrôle sur le formatage.
- `textDevice.Process(pdfPage, textStream);` :Cela traite chaque page du PDF et stocke le texte extrait dans un`MemoryStream`.
-  Enfin, nous convertissons le texte de la`MemoryStream` à une chaîne et l'ajouter à la`StringBuilder`.

## Étape 5 : Enregistrer le texte extrait dans un fichier

 Après avoir traité toutes les pages, le texte est stocké dans le`StringBuilder`La dernière étape consiste à enregistrer ce texte extrait dans un fichier.

```csharp
// Définir le chemin de sortie du fichier texte
dataDir = dataDir + "input_Text_Extracted_out.txt";

// Enregistrer le texte extrait dans un fichier
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : Ceci écrit tout le contenu du`StringBuilder` dans un fichier texte.
- Le chemin d'accès au fichier de sortie est défini en ajoutant un nom de fichier (`"input_Text_Extracted_out.txt"` ) au`dataDir` chemin.

## Conclusion

L'extraction de texte d'un PDF à l'aide d'Aspose.PDF pour .NET est un processus simple et efficace. En suivant les étapes décrites dans ce guide, vous pouvez facilement ouvrir des documents PDF, parcourir des pages et extraire du texte dans un fichier texte. Cela est particulièrement utile pour traiter de gros volumes de données PDF, effectuer une analyse de texte ou convertir des documents en vue d'une manipulation ultérieure.

Avec Aspose.PDF, vous n'êtes pas limité à l'extraction de texte : vous pouvez gérer des annotations, manipuler des images ou même convertir des PDF dans d'autres formats tels que HTML ou Word. La flexibilité et la puissance de cette bibliothèque en font un outil précieux pour la gestion des PDF dans les applications .NET.

## FAQ

### Aspose.PDF peut-il extraire du texte à partir de fichiers PDF basés sur des images ?
Non, Aspose.PDF est conçu pour extraire du texte à partir de fichiers PDF basés sur le contenu. Pour les fichiers PDF basés sur des images, la technologie OCR est nécessaire.

### Aspose.PDF conserve-t-il le formatage lors de l'extraction de texte ?
Par défaut, le texte est extrait sans mise en forme, mais vous pouvez ajuster les options d'extraction si vous souhaitez conserver une certaine mise en forme.

### Puis-je extraire du texte d’une plage de pages spécifique ?
Oui, vous pouvez modifier le code pour qu'il boucle sur une plage spécifique de pages au lieu de toutes les pages.

### Quels sont les modes d'extraction de texte dans Aspose.PDF ?
Aspose.PDF propose deux modes : Brut et Pur. Le mode Brut tente de conserver la mise en page d'origine, tandis que le mode Pur extrait uniquement le texte sans mise en forme.

### Aspose.PDF pour .NET est-il compatible avec .NET Core ?
Oui, Aspose.PDF pour .NET est entièrement compatible avec .NET Core et .NET Framework.
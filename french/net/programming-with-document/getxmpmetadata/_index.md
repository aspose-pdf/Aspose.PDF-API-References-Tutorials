---
title: Obtenir les métadonnées XMP
linktitle: Obtenir les métadonnées XMP
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment utiliser la fonctionnalité GetXmpMetadata d'Aspose.PDF pour .NET pour extraire les métadonnées XMP d'un document PDF à l'aide du code source C#.
type: docs
weight: 200
url: /fr/net/programming-with-document/getxmpmetadata/
---

 Aspose.PDF pour .NET est une bibliothèque de manipulation PDF populaire qui permet aux développeurs de créer, éditer et convertir des fichiers PDF dans leurs applications .NET. L'une des fonctionnalités offertes par cette bibliothèque est la possibilité d'extraire les métadonnées XMP d'un document PDF. Ce didacticiel vous guidera à travers les étapes d'utilisation de`GetXmpMetadata` fonctionnalité d'Aspose.PDF pour .NET pour extraire les métadonnées XMP d'un document PDF.

## Étape 1 : Installer Aspose.PDF pour .NET

 Pour utiliser Aspose.PDF pour .NET dans vos applications .NET, vous devez d'abord installer la bibliothèque. Vous pouvez télécharger la dernière version de la bibliothèque à partir du[Aspose.PDF pour la page de téléchargement .NET](https://releases.aspose.com/pdf/net).

Une fois que vous avez téléchargé la bibliothèque, extrayez le contenu du fichier ZIP dans un dossier sur votre ordinateur. Vous devrez ensuite ajouter une référence à la DLL Aspose.PDF pour .NET dans votre projet .NET.

## Étape 2 : Chargez le document PDF

 Une fois que vous avez installé Aspose.PDF pour .NET et ajouté une référence à la DLL dans votre projet .NET, vous pouvez commencer à utiliser le`GetXmpMetadata` fonctionnalité pour extraire les métadonnées XMP d'un document PDF.

La première étape de l'utilisation de cette fonctionnalité consiste à charger le document PDF dont vous souhaitez extraire les métadonnées XMP. Pour ce faire, vous pouvez utiliser le code suivant :

```csharp
// Le chemin d'accès au document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Ouvrir le document PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

 Dans le code ci-dessus, remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où se trouve votre document PDF. Ce code chargera le document PDF dans un`Document` objet, que vous pouvez ensuite utiliser pour extraire les métadonnées XMP.

## Étape 3 : Extraire les métadonnées XMP

Pour extraire les métadonnées XMP d'un document PDF, vous pouvez utiliser le code suivant :

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Dans le code ci-dessus,`xmp:CreateDate`, `xmp:Nickname` , et`xmp:CustomProperty`sont des exemples de propriétés de métadonnées XMP que vous pouvez extraire d'un document PDF. Vous pouvez remplacer ces noms de propriété par les noms de toute autre propriété de métadonnées XMP que vous souhaitez extraire.

### Exemple de code source pour obtenir des métadonnées XMP à l'aide d'Aspose.PDF pour .NET

 Voici le code source complet pour extraire les métadonnées XMP d'un document PDF à l'aide de`GetXmpMetadata` fonctionnalité d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

//Ouvrir le document PDF
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

// Extraire les métadonnées XMP
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

 Dans le code ci-dessus, remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où se trouve votre document PDF. Ce code extraira les métadonnées XMP du document PDF et les sortira sur la console.
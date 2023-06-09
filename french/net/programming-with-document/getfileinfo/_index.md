---
title: Obtenir des informations sur le fichier
linktitle: Obtenir des informations sur le fichier
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à utiliser la fonctionnalité GetFileInfo d'Aspose.PDF pour .NET pour récupérer des informations de métadonnées sur un document PDF.
type: docs
weight: 180
url: /fr/net/programming-with-document/getfileinfo/
---

 Aspose.PDF pour .NET est une bibliothèque de manipulation PDF populaire qui permet aux développeurs de créer, éditer et convertir des fichiers PDF dans leurs applications .NET. L'une des fonctionnalités offertes par cette bibliothèque est la possibilité de récupérer des informations sur les métadonnées d'un document PDF. Ce didacticiel vous guidera à travers les étapes d'utilisation de`GetFileInfo`fonctionnalité d'Aspose.PDF pour .NET pour récupérer des informations sur les métadonnées d'un document PDF.

## Étape 1 : Installer Aspose.PDF pour .NET

 Pour utiliser Aspose.PDF pour .NET dans vos applications .NET, vous devez d'abord installer la bibliothèque. Vous pouvez télécharger la dernière version de la bibliothèque à partir du[Aspose.PDF pour la page de téléchargement .NET](https://releases.aspose.com/pdf/net).

Une fois que vous avez téléchargé la bibliothèque, extrayez le contenu du fichier ZIP dans un dossier sur votre ordinateur. Vous devrez ensuite ajouter une référence à la DLL Aspose.PDF pour .NET dans votre projet .NET.

## Étape 2 : Chargez le document PDF

 Une fois que vous avez installé Aspose.PDF pour .NET et ajouté une référence à la DLL dans votre projet .NET, vous pouvez commencer à utiliser le`GetFileInfo` fonctionnalité pour récupérer des informations sur les métadonnées d'un document PDF.

La première étape de l'utilisation de cette fonctionnalité consiste à charger le document PDF sur lequel vous souhaitez récupérer des informations. Pour ce faire, vous pouvez utiliser le code suivant :

```csharp
// Le chemin d'accès au document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Dans le code ci-dessus, remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où se trouve votre document PDF. Ce code chargera le document PDF dans un`Document` objet, que vous pouvez ensuite utiliser pour récupérer des informations sur les métadonnées du document.

## Étape 3 : Récupérer les métadonnées du document

Pour récupérer des informations sur les métadonnées d'un document PDF, vous pouvez utiliser le code suivant :

```csharp
// Obtenir des informations sur les documents
DocumentInfo docInfo = pdfDocument.Info;

// Afficher les informations sur le document
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

Dans le code ci-dessus, chaque ligne récupère une propriété de métadonnées différente du document PDF et l'envoie à la console. Vous pouvez personnaliser ce code pour récupérer uniquement les propriétés qui vous intéressent.

### Exemple de code source pour obtenir des informations sur le fichier PDF à l'aide d'Aspose.PDF pour .NET

 Voici le code source complet pour récupérer les métadonnées d'un document PDF en utilisant le`GetFileInfo` fonctionnalité d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Obtenir des informations sur les documents
DocumentInfo docInfo = pdfDocument.Info;

// Afficher les informations sur le document
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```
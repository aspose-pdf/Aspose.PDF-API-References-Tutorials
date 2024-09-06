---
title: Obtenir les informations sur le fichier dans le fichier PDF
linktitle: Obtenir les informations sur le fichier dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment utiliser la fonctionnalité GetFileInfo dans un fichier PDF d'Aspose.PDF pour .NET pour récupérer des informations de métadonnées sur un document PDF.
type: docs
weight: 180
url: /fr/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET est une bibliothèque de manipulation PDF populaire qui permet aux développeurs de créer, de modifier et de convertir des fichiers PDF dans leurs applications .NET. L'une des fonctionnalités offertes par cette bibliothèque est la possibilité de récupérer des informations sur les métadonnées d'un document PDF. Ce didacticiel vous guidera à travers les étapes d'utilisation de l'Aspose.PDF for .NET`GetFileInfo` fonctionnalité d'Aspose.PDF pour .NET pour récupérer des informations sur les métadonnées d'un document PDF.

## Étape 1 : Installer Aspose.PDF pour .NET

 Pour utiliser Aspose.PDF for .NET dans vos applications .NET, vous devez d'abord installer la bibliothèque. Vous pouvez télécharger la dernière version de la bibliothèque à partir du[Page de téléchargement d'Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net).

Une fois la bibliothèque téléchargée, extrayez le contenu du fichier ZIP dans un dossier de votre ordinateur. Vous devrez ensuite ajouter une référence à la DLL Aspose.PDF pour .NET dans votre projet .NET.

## Étape 2 : Charger le document PDF

 Une fois que vous avez installé Aspose.PDF pour .NET et ajouté une référence à la DLL dans votre projet .NET, vous pouvez commencer à utiliser le`GetFileInfo` fonctionnalité permettant de récupérer des informations sur les métadonnées d'un document PDF.

La première étape pour utiliser cette fonctionnalité consiste à charger le document PDF sur lequel vous souhaitez récupérer des informations. Pour ce faire, vous pouvez utiliser le code suivant :

```csharp
// Le chemin vers le document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 Dans le code ci-dessus, remplacez`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès au répertoire où se trouve votre document PDF. Ce code chargera le document PDF dans un`Document` objet, que vous pouvez ensuite utiliser pour récupérer des informations sur les métadonnées du document.

## Étape 3 : Récupérer les métadonnées du document

Pour récupérer des informations sur les métadonnées d'un document PDF, vous pouvez utiliser le code suivant :

```csharp
// Obtenir des informations sur le document
DocumentInfo docInfo = pdfDocument.Info;

// Afficher les informations du document
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

Dans le code ci-dessus, chaque ligne récupère une propriété de métadonnées différente du document PDF et la renvoie vers la console. Vous pouvez personnaliser ce code pour récupérer uniquement les propriétés qui vous intéressent.

### Exemple de code source pour obtenir des informations sur le fichier PDF à l'aide d'Aspose.PDF pour .NET

 Voici le code source complet pour récupérer les métadonnées d'un document PDF à l'aide de`GetFileInfo` fonctionnalité d'Aspose.PDF pour .NET :

```csharp
// Le chemin vers le document PDF
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document PDF
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// Obtenir des informations sur le document
DocumentInfo docInfo = pdfDocument.Info;

// Afficher les informations du document
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment utiliser Aspose.PDF pour .NET pour récupérer des informations sur les métadonnées d'un document PDF. En chargeant un document PDF et en accédant à ses propriétés de métadonnées, vous pouvez recueillir des informations sur les caractéristiques et les propriétés du document. Aspose.PDF pour .NET fournit une API simple et facile à utiliser pour travailler avec des documents PDF, notamment pour récupérer des informations sur les métadonnées, ce qui en fait un outil précieux pour la manipulation de PDF dans les applications .NET.

### FAQ

#### Q : Que sont les métadonnées dans un document PDF ?

R : Les métadonnées d'un document PDF font référence aux informations qui décrivent les propriétés et les caractéristiques du document. Ces informations incluent généralement le titre du document, l'auteur, le sujet, les mots-clés, la date de création, la date de modification, etc.

#### Q : Comment puis-je installer Aspose.PDF pour .NET dans mon projet .NET ?

 R : Pour installer Aspose.PDF pour .NET, vous devez télécharger la bibliothèque à partir du[Page de téléchargement d'Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net). Après le téléchargement, extrayez le contenu du fichier ZIP et ajoutez une référence à la DLL Aspose.PDF pour .NET dans votre projet .NET.

#### Q : Puis-je personnaliser le code pour récupérer uniquement des propriétés de métadonnées spécifiques ?

R : Oui, vous pouvez personnaliser le code pour récupérer des propriétés de métadonnées spécifiques en commentant les lignes dont vous n'avez pas besoin. Chaque ligne du code correspond à une propriété de métadonnées spécifique, vous pouvez donc inclure ou exclure des propriétés en fonction de vos besoins.

#### Q : Quels types de propriétés de métadonnées puis-je récupérer à l’aide d’Aspose.PDF pour .NET ?

R : En utilisant Aspose.PDF pour .NET, vous pouvez récupérer diverses propriétés de métadonnées d’un document PDF, notamment l’auteur, le titre, le sujet, les mots-clés, la date de création et la date de modification.
---
title: Définir les informations sur le fichier dans un fichier PDF
linktitle: Définir les informations sur le fichier dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment utiliser Aspose.PDF pour .NET pour définir les informations de fichier dans un fichier PDF avec ce guide étape par étape.
type: docs
weight: 310
url: /fr/net/programming-with-document/setfileinfo/
---
Si vous travaillez sur un projet nécessitant la gestion de fichiers PDF à l'aide d'Aspose.PDF pour .NET, l'une des fonctionnalités que vous souhaiterez peut-être utiliser est la possibilité de définir les informations de fichier pour un document PDF. Les informations du fichier comprennent divers détails tels que l'auteur, la date de création, les mots-clés, la date de modification, le sujet et le titre. Ce guide vous guidera tout au long du processus de définition des informations de fichier pour un document PDF à l'aide du code source C# avec Aspose.PDF pour .NET.

## Guide étape par étape pour définir les informations sur les fichiers à l'aide d'Aspose.PDF pour .NET

1. Créez un nouveau projet C# dans votre IDE Visual Studio.
2. Ajoutez une référence à la bibliothèque Aspose.PDF pour .NET dans votre projet.
3. Créez un nouvel objet de document PDF en fournissant le chemin d'accès au fichier PDF dont vous souhaitez modifier les informations sur le fichier.

## Étape 1 : Définissez le chemin d’accès au répertoire des documents.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF

```csharp
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Étape 3 : utilisez l'objet DocumentInfo pour accéder aux informations de fichier du document PDF.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Étape 4 : définissez les valeurs d'informations de fichier souhaitées à l'aide des propriétés de l'objet DocumentInfo.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Étape 5 : Enregistrez le document PDF mis à jour à l'emplacement spécifié.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Étape 6 : Vérifiez que les informations du fichier ont été mises à jour avec succès.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Vous avez réussi à définir les informations de fichier pour un document PDF à l'aide d'Aspose.PDF pour .NET.

### Exemple de code source pour définir les informations sur le fichier à l'aide d'Aspose.PDF pour .NET


```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

// Spécifier les informations du document
DocumentInfo docInfo = new DocumentInfo(pdfDocument);

docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";

dataDir = dataDir + "SetFileInfo_out.pdf";
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);

Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

## Conclusion

En conclusion, Aspose.PDF pour .NET fournit un moyen simple et efficace de définir les informations de fichier pour les documents PDF. En suivant les étapes mentionnées ci-dessus, vous pouvez facilement définir les valeurs d'informations de fichier souhaitées pour vos documents PDF à l'aide du code source C#.

### FAQ pour définir les informations sur le fichier dans un fichier PDF

#### Q : Puis-je définir des propriétés d'informations de fichier supplémentaires non mentionnées dans l'exemple ?

 R : Oui, vous pouvez définir des propriétés d'informations de fichier supplémentaires à l'aide de l'option`DocumentInfo` objet dans Aspose.PDF pour .NET. Le`DocumentInfo`La classe fournit diverses propriétés qui vous permettent de définir des informations supplémentaires telles que le producteur, la version et les propriétés personnalisées.

#### Q : Est-il possible de récupérer les informations d'un fichier à partir d'un document PDF existant ?

 R : Oui, vous pouvez récupérer les informations de fichier d'un document PDF existant à l'aide d'Aspose.PDF pour .NET. Pour ce faire, vous pouvez utiliser le`DocumentInfo` objet pour accéder aux propriétés des informations du fichier et lire les informations stockées dans le document PDF.

#### Q : La définition des informations sur le fichier modifie-t-elle le document PDF original ?

R : Non, la définition des informations de fichier à l'aide d'Aspose.PDF pour .NET ne modifie pas le document PDF d'origine. Au lieu de cela, il crée un nouveau document PDF avec les informations de fichier mises à jour. Le document PDF original reste inchangé.
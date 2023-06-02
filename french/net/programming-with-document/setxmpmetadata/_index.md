---
title: Définir les métadonnées XMP
linktitle: Définir les métadonnées XMP
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir XMPMetadata dans des fichiers PDF à l'aide d'Aspose.PDF pour .NET. Suivez ce guide étape par étape.
type: docs
weight: 330
url: /fr/net/programming-with-document/setxmpmetadata/
---
Dans cet article, nous fournirons un guide étape par étape sur la façon d'utiliser Aspose.PDF pour .NET pour définir les métadonnées XMP dans un fichier PDF. Nous fournirons un exemple complet de code source à la fin de l'article.

## Étape 1 : Définissez le chemin d'accès au répertoire de documents

Avant de commencer, nous devons définir le chemin d'accès au répertoire où se trouve notre document PDF. Nous stockerons ce chemin dans une variable appelée "dataDir".

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Assurez-vous de remplacer`YOUR DOCUMENT DIRECTORY` avec le chemin d'accès réel à votre fichier PDF.

## Étape 2 : Ouvrez le fichier PDF

 La première étape consiste à ouvrir le fichier PDF pour lequel vous souhaitez définir les métadonnées XMP. Pour ce faire, vous devrez créer un nouveau`Document` objet et transmettez le chemin d'accès à votre fichier PDF.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Étape 3 : Définir les propriétés des métadonnées XMP

Maintenant que votre fichier PDF est ouvert, vous pouvez commencer à définir les propriétés des métadonnées XMP. Les propriétés que vous définissez dépendent de vos besoins spécifiques, mais voici quelques propriétés courantes que vous pouvez définir :

- `xmp:CreateDate`: La date de création du fichier PDF.
- `xmp:Nickname`: un surnom ou un alias pour le fichier PDF.
- `xmp:CustomProperty`: Une propriété personnalisée avec une valeur que vous spécifiez.

 Pour définir ces propriétés, vous pouvez utiliser le`Metadata` propriété de la`Document` objet. Voici un exemple :

```csharp
// Définir les propriétés
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

Dans ce didacticiel, nous définissons la date de création sur la date et l'heure actuelles, le surnom sur "Pseudonyme" et une propriété personnalisée sur "Valeur personnalisée". Vous pouvez remplacer ces valeurs par les vôtres.

## Étape 4 : Enregistrer le fichier PDF

 Après avoir défini les propriétés des métadonnées XMP, vous devez enregistrer le fichier PDF. Pour ce faire, vous pouvez utiliser le`Save` méthode de la`Document` objet et transmettez le chemin d'accès à l'endroit où vous souhaitez enregistrer le fichier PDF mis à jour.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Enregistrer le document
pdfDocument.Save(dataDir);
```

### Exemple de code source pour Set XMPMetadata à l'aide d'Aspose.PDF pour .NET

Voici l'exemple de code source complet pour définir XMPMetadata à l'aide d'Aspose.PDF pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");

// Définir les propriétés
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";

dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Enregistrer le document
pdfDocument.Save(dataDir);

Console.WriteLine("\nXMP metadata in a pdf file setup successfully.\nFile saved at " + dataDir);
```

---
title: Définir XMPMetadata dans un fichier PDF
linktitle: Définir XMPMetadata dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment définir XMPMetadata dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Suivez ce guide étape par étape.
type: docs
weight: 330
url: /fr/net/programming-with-document/setxmpmetadata/
---
Dans cet article, nous fournirons un guide étape par étape sur la façon d'utiliser Aspose.PDF pour .NET pour définir des métadonnées XMP dans un fichier PDF. Nous fournirons un exemple complet de code source à la fin de l'article.

## Étape 1 : Définir le chemin d'accès au répertoire de documents

Avant de commencer, nous devons définir le chemin d’accès au répertoire où se trouve notre document PDF. Nous stockerons ce chemin dans une variable appelée "dataDir".

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Assurez-vous de remplacer`YOUR DOCUMENT DIRECTORY` avec le chemin réel vers votre fichier PDF.

## Étape 2 : ouvrez le fichier PDF

 La première étape consiste à ouvrir le fichier PDF pour lequel vous souhaitez définir les métadonnées XMP. Pour ce faire, vous devrez créer un nouveau`Document` object et transmettez le chemin d’accès à votre fichier PDF.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "SetXMPMetadata.pdf");
```

## Étape 3 : Définir les propriétés des métadonnées XMP

Maintenant que votre fichier PDF est ouvert, vous pouvez commencer à définir les propriétés des métadonnées XMP. Les propriétés que vous définissez dépendront de vos besoins spécifiques, mais voici quelques propriétés courantes que vous souhaiterez peut-être définir :

- `xmp:CreateDate`: La date de création du fichier PDF.
- `xmp:Nickname`: Un surnom ou un alias pour le fichier PDF.
- `xmp:CustomProperty`: Une propriété personnalisée avec une valeur que vous spécifiez.

 Pour définir ces propriétés, vous pouvez utiliser le`Metadata` propriété du`Document` objet. Voici un exemple :

```csharp
// Définir les propriétés
pdfDocument.Metadata["xmp:CreateDate"] = DateTime.Now;
pdfDocument.Metadata["xmp:Nickname"] = "Nickname";
pdfDocument.Metadata["xmp:CustomProperty"] = "Custom Value";
```

Dans ce didacticiel, nous définissons la date de création sur la date et l'heure actuelles, le surnom sur « Pseudo » et une propriété personnalisée sur « Valeur personnalisée ». Vous pouvez remplacer ces valeurs par les vôtres.

## Étape 4 : Enregistrez le fichier PDF

 Après avoir défini les propriétés des métadonnées XMP, vous devez enregistrer le fichier PDF. Pour ce faire, vous pouvez utiliser le`Save` méthode du`Document` objet et transmettez le chemin vers l'endroit où vous souhaitez enregistrer le fichier PDF mis à jour.

```csharp
dataDir = dataDir + "SetXMPMetadata_out.pdf";
// Enregistrer le document
pdfDocument.Save(dataDir);
```

### Exemple de code source pour définir XMPMetadata à l'aide d'Aspose.PDF pour .NET

Voici l'exemple complet de code source pour définir XMPMetadata à l'aide d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
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

## Conclusion

Aspose.PDF pour .NET offre un moyen simple de définir des métadonnées XMP dans des fichiers PDF, vous permettant d'ajouter des informations descriptives et des propriétés à vos documents. Le guide étape par étape fourni ci-dessus vous montre comment définir diverses propriétés de métadonnées XMP à l'aide du code source C#. De plus, vous pouvez personnaliser les métadonnées XMP pour répondre à vos besoins spécifiques et aux exigences de votre entreprise. Avec Aspose.PDF pour .NET, la gestion des métadonnées PDF devient efficace et permet une meilleure organisation et une meilleure recherche de vos documents PDF.

### FAQ pour Définir les métadonnées XMP dans un fichier PDF

#### Q : Que sont les métadonnées XMP dans un fichier PDF et pourquoi est-ce important ?

R : XMP (Extensible Metadata Platform) est une norme permettant d'intégrer des métadonnées dans divers formats de fichiers, notamment PDF. Les métadonnées XMP dans un fichier PDF vous permettent d'ajouter des informations descriptives et des propriétés au document, telles que la date de création, l'auteur, le titre, les mots-clés et les propriétés personnalisées. Il est essentiel pour une meilleure organisation, une meilleure recherche et un meilleur archivage des documents PDF.

#### Q : Puis-je définir d'autres propriétés de métadonnées XMP en plus de celles mentionnées dans l'exemple ?

 R : Oui, vous pouvez définir un large éventail de propriétés de métadonnées XMP en fonction de vos besoins spécifiques. Certaines propriétés communes incluent`dc:title` (titre du document),`dc:creator` (créateur de documents),`dc:description` (description du document),`pdf:Keywords` (mots-clés du document), et plus encore. La spécification XMP propose divers espaces de noms standard et espaces de noms personnalisés pour définir différents types de métadonnées.

#### Q : Est-il possible de récupérer et de lire les métadonnées XMP à partir d'un fichier PDF existant ?

 R : Oui, Aspose.PDF pour .NET offre la possibilité de lire et de récupérer les métadonnées XMP d'un fichier PDF existant. Vous pouvez utiliser le`Metadata` propriété du`Document` classe pour accéder aux métadonnées XMP et récupérer les valeurs de propriétés spécifiques.
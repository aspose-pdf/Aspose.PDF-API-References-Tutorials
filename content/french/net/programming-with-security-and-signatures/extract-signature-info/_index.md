---
title: Extraire les informations de signature
linktitle: Extraire les informations de signature
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment extraire des signatures numériques et des informations de certificat à partir de documents PDF à l'aide d'Aspose.PDF pour .NET. Un guide complet étape par étape pour les développeurs C#.
type: docs
weight: 80
url: /fr/net/programming-with-security-and-signatures/extract-signature-info/
---
## Introduction

Dans le monde numérique d'aujourd'hui, il est essentiel de garantir la sécurité et l'intégrité des documents. L'une des méthodes courantes utilisées pour sécuriser les PDF consiste à ajouter une signature numérique. Cependant, la récupération et la vérification des détails de la signature peuvent parfois s'avérer difficiles, en particulier lorsque vous avez affaire à différents certificats. Dans ce guide, nous vous expliquerons le processus d'extraction des informations de signature à partir de documents PDF à l'aide d'Aspose.PDF pour .NET, ce qui simplifie la tâche. Vous apprendrez à accéder aux champs de signature, à extraire les informations de certificat et à les enregistrer dans un fichier.

## Prérequis

Avant de commencer, assurons-nous que vous avez tout prêt pour commencer.

-  Bibliothèque Aspose.PDF pour .NET : si vous ne l'avez pas encore, vous pouvez la télécharger à partir du[Page de téléchargement d'Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/). 
- Environnement de développement .NET : vous aurez besoin d’un IDE comme Visual Studio.
- Connaissances de base de C# : une connaissance de C# est utile pour comprendre les extraits de code de ce didacticiel.
- Document PDF avec une signature numérique : à des fins de test, assurez-vous que vous disposez d'un fichier PDF contenant au moins une signature numérique.

## Importation des espaces de noms requis

Avant de passer au code, il est important d'importer les espaces de noms nécessaires. Ces espaces de noms vous permettront d'accéder à la fonctionnalité Aspose.PDF et de travailler avec des documents PDF.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Maintenant que vous avez configuré les éléments essentiels, passons au processus proprement dit d'extraction des informations de signature d'un PDF.

## Étape 1 : Configuration du répertoire de documents

 Avant de travailler sur un document PDF, vous devez spécifier l'emplacement du fichier que vous allez utiliser. Vous pouvez remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel du répertoire où sont stockés vos PDF.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Ici, nous spécifions le répertoire contenant le fichier PDF et le nom du fichier lui-même. Assurez-vous que le fichier existe dans ce répertoire !

## Étape 2 : Chargement du document PDF

 Maintenant que vous avez configuré votre répertoire, l'étape suivante consiste à charger le document PDF à l'aide de l'`Document` classe d'Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Traitez le PDF ici.
}
```

 Cette ligne de code initialise un`Document`objet qui représente le fichier PDF.`using` L'instruction garantit que les ressources sont nettoyées après le traitement du document.

## Étape 3 : Accéder aux champs du formulaire

Dans cette étape, nous allons parcourir tous les champs de formulaire du document PDF. Étant donné que les signatures sont généralement stockées sous forme de champs de formulaire, cette étape nous aidera à identifier les champs de signature.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Identifiez les champs de signature ici.
}
```

 En parcourant le`Form` propriété de la`Document` objet, nous pouvons examiner chaque champ de formulaire pour vérifier s'il s'agit d'un champ de signature.

## Étape 4 : Identification des champs de signature

 Une fois que vous avez accédé aux champs du formulaire, l'étape suivante consiste à identifier ceux qui sont des champs de signature. Nous pouvons le faire en convertissant chaque champ en un`SignatureField` objet.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Extraire les informations de signature.
}
```

 Ici, nous utilisons le`as` mot-clé pour tenter de convertir chaque champ de formulaire en un`SignatureField`Si le casting réussit, nous savons que le champ est une signature.

## Étape 5 : Extraction du certificat

Maintenant que vous avez identifié le champ de signature, la tâche suivante consiste à extraire le certificat de la signature. Les certificats contiennent des informations cruciales sur le signataire et la validité de la signature.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 Le`ExtractCertificate` la méthode renvoie un`Stream` objet contenant les données du certificat. Ce flux peut être utilisé pour enregistrer le certificat en vue d'une analyse ou d'un stockage ultérieur.

## Étape 6 : Enregistrer le certificat dans un fichier

 Une fois le certificat extrait, l'étape finale consiste à l'enregistrer dans un fichier. Dans ce cas, nous allons enregistrer le certificat sous forme de fichier`.cer` déposer.

```csharp
if (cerStream != null)
{
    using (cerStream)
    {
        byte[] bytes = new byte[cerStream.Length];
        using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
        {
            cerStream.Read(bytes, 0, bytes.Length);
            fs.Write(bytes, 0, bytes.Length);
        }
    }
}
```

Dans ce bloc de code, nous :

1. Vérifiez si le flux de certificat n'est pas nul.
2. Lire les données du certificat dans un tableau d’octets.
3.  Écrire le tableau d'octets dans un`.cer` fichier dans le répertoire du document.

## Conclusion

L'extraction de signatures numériques et des informations de certificat associées à partir de documents PDF à l'aide d'Aspose.PDF pour .NET est assez simple lorsqu'elle est décomposée en étapes simples. Que vous vérifiiez des documents, des signatures ou que vous stockiez simplement des certificats pour les conserver, ce didacticiel vous fournit les connaissances nécessaires pour le faire efficacement. N'oubliez pas que la sécurisation et la vérification des documents sont essentielles dans le monde numérique d'aujourd'hui, et l'utilisation d'outils comme Aspose.PDF pour .NET facilite grandement la gestion de ces tâches.

## FAQ

### Puis-je extraire plusieurs signatures d'un PDF à l'aide d'Aspose.PDF pour .NET ?
Oui, le code parcourt tous les champs de formulaire du document, vous permettant d'extraire plusieurs signatures si elles existent.

### Que se passe-t-il si aucune signature n'est trouvée dans le PDF ?
Si aucun champ de signature n'est présent, le code les ignorera simplement sans générer d'erreur.

### Puis-je utiliser cette approche pour vérifier la validité d’une signature ?
Bien que vous puissiez extraire le certificat, la vérification de la validité d'une signature nécessite des étapes supplémentaires, telles que la vérification de la chaîne de confiance du certificat.

### Est-il possible d'extraire d'autres données de champs de formulaire à l'aide d'Aspose.PDF pour .NET ?
Oui, Aspose.PDF vous permet d'accéder et de manipuler différents types de champs de formulaire dans un PDF, pas seulement les champs de signature.

### Comment puis-je visualiser les détails du certificat extrait ?
 Une fois le certificat enregistré en tant que`.cer` fichier, vous pouvez l'ouvrir à l'aide de n'importe quel visualiseur de certificats ou l'importer dans un magasin de certificats système pour une inspection plus approfondie.
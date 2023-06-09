---
title: Décrypter
linktitle: Décrypter
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à décrypter des fichiers PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-security-and-signatures/decrypt/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de décryptage d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Cette bibliothèque vous permet d'ouvrir un fichier PDF existant, de le décrypter et d'enregistrer la version mise à jour. Cette fonctionnalité est utile lorsque vous devez supprimer le mot de passe d'un fichier PDF pour un accès plus facile.

## Étape 1 : Prérequis

Avant de commencer, assurez-vous d'avoir les prérequis suivants :

- Connaissance de base du langage de programmation C#
- Installation de Visual Studio sur votre machine
- Bibliothèque Aspose.PDF pour .NET installée

## Étape 2 : Configuration de l'environnement

Pour commencer, procédez comme suit pour configurer votre environnement de développement :

1. Ouvrez Visual Studio et créez un nouveau projet C#.
2. Installez la bibliothèque Aspose.PDF pour .NET à l'aide du gestionnaire de packages NuGet.
3. Importez les espaces de noms requis dans votre fichier de code :

```csharp
using Aspose.Pdf;
```

## Étape 3 : Ouverture du document PDF

La première étape consiste à ouvrir le document PDF que vous souhaitez décrypter. Dans cet exemple, nous supposons que vous avez un fichier PDF nommé "Decrypt.pdf" dans le répertoire spécifié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document document = new Document(dataDir + "Decrypt.pdf", "password");
```

Assurez-vous de remplacer les espaces réservés par les emplacements réels et les mots de passe que vous souhaitez utiliser.

## Étape 4 : décryptage du PDF

Une fois que vous avez ouvert le document PDF, vous pouvez le déchiffrer en utilisant le`Decrypt` méthode. Aucun paramètre n'est requis pour cette méthode.

```csharp
document. Decrypt();
```

## Étape 5 : Enregistrer le PDF mis à jour

 Après avoir déchiffré le PDF, vous devez enregistrer la version mise à jour du document. Spécifiez le chemin du fichier de sortie et utilisez le`Save` méthode pour enregistrer le document.

```csharp
dataDir = dataDir + "Decrypt_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nPDF file decrypted successfully.\nFile saved at " + dataDir);
```

Le PDF mis à jour sera enregistré à l'emplacement spécifié.

### Exemple de code source pour décrypter à l'aide d'Aspose.PDF pour .NET 

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir+ "Decrypt.pdf", "password");
// Décrypter le PDF
document.Decrypt();
dataDir = dataDir + "Decrypt_out.pdf";
// Enregistrer le PDF mis à jour
document.Save(dataDir);
Console.WriteLine("\nPDF file decrypted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez réussi à déchiffrer un fichier PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a couvert le processus étape par étape, de l'ouverture du document à l'enregistrement de la version mise à jour. Vous pouvez maintenant utiliser cette fonctionnalité pour supprimer les mots de passe de vos fichiers PDF.
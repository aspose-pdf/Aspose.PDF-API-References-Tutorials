---
title: Crypter
linktitle: Crypter
second_title: Référence de l'API Aspose.PDF pour .NET
description: Chiffrez en toute sécurité vos fichiers PDF avec Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-security-and-signatures/encrypt/
---

Le cryptage des fichiers PDF est une mesure de sécurité importante pour protéger les informations confidentielles. Avec Aspose.PDF pour .NET, vous pouvez facilement crypter vos fichiers PDF en utilisant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici les directives d'importation nécessaires :

```csharp
using Aspose.Pdf;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF à chiffrer. Remplacer`"YOUR DOCUMENTS DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Ensuite, vous devez ouvrir le document PDF que vous souhaitez chiffrer. Utilisez le code suivant pour charger le document :

```csharp
Document document = new Document(dataDir + "Encrypt.pdf");
```

## Étape 4 : Crypter le PDF

Vous pouvez maintenant crypter le PDF en utilisant le code suivant :

```csharp
document. Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
```

Dans cet exemple, nous utilisons l'algorithme de chiffrement RC4x128 avec les mots de passe "utilisateur" et "propriétaire". Vous pouvez modifier ces paramètres selon vos besoins.

## Étape 5 : Sauvegardez le PDF crypté

Enfin, vous pouvez enregistrer le PDF crypté à l'emplacement spécifié à l'aide du code suivant :

```csharp
dataDir = dataDir + "Encrypt_out.pdf";
document. Save(dataDir);
```

Assurez-vous de spécifier le chemin et le nom de fichier souhaités pour le PDF crypté.

### Exemple de code source pour Encrypt à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir+ "Encrypt.pdf");
// Crypter le PDF
document.Encrypt("user", "owner", 0, CryptoAlgorithm.RC4x128);
dataDir = dataDir + "Encrypt_out.pdf";
// Enregistrer le PDF mis à jour
document.Save(dataDir);
Console.WriteLine("\nPDF file encrypted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous avez maintenant un aperçu étape par étape du cryptage des fichiers PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez intégrer ce code dans vos propres projets pour sécuriser facilement vos fichiers PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités de cryptage et de sécurité avancées.
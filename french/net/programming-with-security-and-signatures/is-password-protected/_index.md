---
title: Est protégé par un mot de passe
linktitle: Est protégé par un mot de passe
second_title: Référence de l'API Aspose.PDF pour .NET
description: Vérifiez facilement si un document PDF est protégé par un mot de passe avec Aspose.PDF pour .NET.
type: docs
weight: 90
url: /fr/net/programming-with-security-and-signatures/is-password-protected/
---

Il est souvent important de savoir si un document PDF est protégé par un mot de passe avant de le traiter. Avec Aspose.PDF pour .NET, vous pouvez facilement vérifier si un document PDF est protégé en utilisant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici les directives d'importation nécessaires :

```csharp
using Aspose.Pdf;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF que vous souhaitez vérifier. Remplacer`"YOUR DOCUMENTS DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 3 : charger le document PDF source

Nous allons maintenant charger le document PDF source et vérifier s'il est protégé par un mot de passe à l'aide du code suivant :

```csharp
PdfFileInfo fileInfo = new PdfFileInfo(dataDir + @"IsPasswordProtected.pdf");
```

## Étape 4 : Vérifiez si le PDF est protégé

 Dans cette étape, nous déterminerons si le document PDF est protégé par un mot de passe en utilisant le`IsEncrypted` méthode de la`PdfFileInfo` objet. Voici le code correspondant :

```csharp
bool encrypted = fileInfo.IsEncrypted;
```

## Étape 5 : Afficher l'état du chiffrement

 Enfin, nous pouvons afficher l'état de cryptage actuel du PDF à l'aide de la`Console.WriteLine` méthode. Voici le code correspondant :

```csharp
Console.WriteLine(encrypted.ToString());
```

Le message affiché indiquera si le document PDF est protégé par mot de passe ou non.

### Exemple de code source pour Is Password Protected utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger le document PDF source
PdfFileInfo fileInfo = new PdfFileInfo(dataDir+ @"IsPasswordProtected.pdf");
//Déterminez que le fichier PDF source est crypté avec un mot de passe
bool encrypted = fileInfo.IsEncrypted;
// MessageBox affiche l'état actuel lié au cryptage PDF
Console.WriteLine(encrypted.ToString());
```

## Conclusion

Félicitation ! Vous disposez maintenant d'un guide étape par étape pour vérifier si un document PDF est protégé par un mot de passe à l'aide d'Aspose.PDF pour .NET. Vous pouvez intégrer ce code dans vos propres projets pour effectuer des opérations spécifiques en fonction du statut de protection du PDF.

Assurez-vous de consulter la documentation officielle d'Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de sécurité des documents PDF et de gestion des mots de passe.
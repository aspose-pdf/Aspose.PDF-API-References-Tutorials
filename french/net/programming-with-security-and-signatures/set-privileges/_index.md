---
title: Définir les privilèges
linktitle: Définir les privilèges
second_title: Référence de l'API Aspose.PDF pour .NET
description: Définissez facilement des privilèges d'accès pour vos fichiers PDF avec Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-security-and-signatures/set-privileges/
---

Il est souvent nécessaire de définir des privilèges d'accès spécifiques pour les fichiers PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement définir des privilèges d'accès à l'aide du code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici les directives d'importation nécessaires :

```csharp
using Aspose.Pdf;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF que vous souhaitez modifier. Remplacer`"YOUR DOCUMENTS DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 3 : Charger le fichier PDF source

Nous allons maintenant charger le fichier PDF source en utilisant le code suivant :

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Étape 4 : Définir les privilèges d'accès

 Dans cette étape, nous allons instancier le`DocumentPrivilege` objet pour définir les privilèges d'accès souhaités. Vous pouvez appliquer des restrictions sur tous les privilèges en utilisant`DocumentPrivilege.ForbidAll` . Par exemple, si vous souhaitez autoriser uniquement la lecture d'écran, vous pouvez définir`AllowScreenReaders` pour`true`. Voici le code correspondant :

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Étape 5 : Crypter et enregistrer le document

 Enfin, nous pouvons crypter le document PDF avec un mot de passe utilisateur et propriétaire en utilisant`Encrypt` et spécifier l'algorithme de cryptage souhaité. Ensuite, nous enregistrons le document mis à jour. Voici le code correspondant :

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Exemple de code source pour Set Privileges à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger un fichier PDF source
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Instancier l'objet Privilèges de document
	// Appliquer des restrictions sur tous les privilèges
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Autoriser uniquement la lecture d'écran
	documentPrivilege.AllowScreenReaders = true;
	// Chiffrez le fichier avec le mot de passe utilisateur et propriétaire.
	// Besoin de définir le mot de passe, de sorte qu'une fois que l'utilisateur affiche le fichier avec le mot de passe utilisateur,
	//Seule l'option de lecture d'écran est activée
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Enregistrer le document mis à jour
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Conclusion

Félicitation ! Vous disposez maintenant d'un guide étape par étape pour définir les privilèges d'accès à un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour appliquer des restrictions spécifiques et protéger vos fichiers PDF selon vos besoins.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur la sécurité avancée des documents PDF et les fonctionnalités de gestion des privilèges d'accès.
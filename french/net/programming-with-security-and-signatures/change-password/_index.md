---
title: Changer le mot de passe
linktitle: Changer le mot de passe
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à changer le mot de passe d'un document PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-security-and-signatures/change-password/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de modification du mot de passe d'un document PDF à l'aide d'Aspose.PDF pour .NET. La bibliothèque vous permet d'ouvrir un fichier PDF existant, de modifier son mot de passe et d'enregistrer la version mise à jour. Cette fonctionnalité est pratique lorsque vous devez sécuriser vos documents PDF en modifiant le mot de passe.

## Étape 1 : Exigences

Avant de commencer, assurez-vous d'avoir les prérequis suivants :

- Connaissance de base du langage de programmation C#
- Visual Studio installé sur votre machine
- Bibliothèque Aspose.PDF pour .NET installée

## Étape 2 : Configuration de l'environnement

Pour commencer, procédez comme suit pour configurer votre environnement de développement :

1. Ouvrez Visual Studio et créez un nouveau projet C#.
2. Installez la bibliothèque Aspose.PDF pour .NET à l'aide du gestionnaire de packages NuGet.
3. Importez les espaces de noms requis dans votre fichier de code :

```csharp
using Aspose.Pdf;
```

## Étape 3 : Chargement du document PDF

La première étape consiste à charger le document PDF dont vous souhaitez modifier le mot de passe. Dans cet exemple, nous supposons que vous avez un fichier PDF nommé "ChangePassword.pdf" dans le répertoire spécifié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document document = new Document(dataDir + "ChangePassword.pdf", "owner");
```

## Étape 4 : Modification du mot de passe

 Une fois que vous avez chargé le document PDF, vous pouvez changer son mot de passe en utilisant le`ChangePasswords`méthode. La méthode nécessite trois paramètres : le mot de passe actuel du propriétaire, le nouveau mot de passe utilisateur et le nouveau mot de passe propriétaire.

```csharp
document.ChangePasswords("owner", "newuser", "newowner");
```

Assurez-vous de remplacer les espaces réservés par les mots de passe réels que vous souhaitez définir.

## Étape 5 : Enregistrer le PDF mis à jour

 Après avoir changé le mot de passe, vous devez enregistrer le document PDF mis à jour. Spécifiez le chemin du fichier de sortie et utilisez le`Save` méthode pour enregistrer le document.

```csharp
dataDir = dataDir + "ChangePassword_out.pdf";
document. Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

Le PDF mis à jour sera enregistré à l'emplacement spécifié.

### Exemple de code source pour Changer le mot de passe à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir+ "ChangePassword.pdf", "owner");
// Changer le mot de passe
document.ChangePasswords("owner", "newuser", "newowner");
dataDir = dataDir + "ChangePassword_out.pdf";
// Enregistrer le PDF mis à jour
document.Save(dataDir);
Console.WriteLine("\nPDF file password changed successfully.\nFile saved at " + dataDir);
```

## Conclusion

Toutes nos félicitations! Vous avez changé avec succès le mot de passe d'un document PDF en utilisant Aspose.PDF pour .NET. Ce didacticiel a couvert le processus étape par étape, du chargement du document à l'enregistrement de la version mise à jour. Vous pouvez maintenant utiliser cette fonctionnalité pour sécuriser vos fichiers PDF avec de nouveaux mots de passe.
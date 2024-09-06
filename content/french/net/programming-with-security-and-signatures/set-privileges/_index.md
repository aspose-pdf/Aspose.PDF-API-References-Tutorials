---
title: Définir les privilèges dans le fichier PDF
linktitle: Définir les privilèges dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Définissez facilement les privilèges d'accès dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-security-and-signatures/set-privileges/
---
Il est souvent nécessaire de définir des privilèges d'accès spécifiques dans un fichier PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement définir des privilèges d'accès à l'aide du code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici les directives d'importation nécessaires :

```csharp
using Aspose.Pdf;
```

## Étape 2 : définir le chemin d’accès au dossier des documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF que vous souhaitez modifier. Remplacer`"YOUR DOCUMENTS DIRECTORY"` dans le code suivant avec le chemin réel vers votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 3 : Charger le fichier PDF source

Nous allons maintenant charger le fichier PDF source en utilisant le code suivant :

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Étape 4 : définir les privilèges d’accès

 Dans cette étape, nous allons instancier le`DocumentPrivilege` objet pour définir les privilèges d'accès souhaités. Vous pouvez appliquer des restrictions sur tous les privilèges à l'aide de`DocumentPrivilege.ForbidAll` . Par exemple, si vous souhaitez autoriser uniquement la lecture d'écran, vous pouvez définir`AllowScreenReaders` à`true`. Voici le code correspondant :

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Étape 5 : Crypter et enregistrer le document

 Enfin, nous pouvons crypter le document PDF avec un mot de passe utilisateur et propriétaire en utilisant`Encrypt` et en spécifiant l'algorithme de chiffrement souhaité. Ensuite, nous sauvegardons le document mis à jour. Voici le code correspondant :

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Exemple de code source pour définir des privilèges à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger un fichier PDF source
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Instancier l'objet Privilèges de document
	// Appliquer des restrictions sur tous les privilèges
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Autoriser uniquement la lecture d'écran
	documentPrivilege.AllowScreenReaders = true;
	// Crypter le fichier avec le mot de passe de l'utilisateur et du propriétaire.
	// Il faut définir le mot de passe, de sorte qu'une fois que l'utilisateur visualise le fichier avec le mot de passe utilisateur,
	// Seule l'option de lecture d'écran est activée
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Enregistrer le document mis à jour
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Conclusion

Félicitations ! Vous disposez désormais d'un guide étape par étape pour définir les privilèges d'accès à un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour appliquer des restrictions spécifiques et protéger vos fichiers PDF selon vos besoins.

Assurez-vous de consulter la documentation officielle d'Aspose.PDF pour plus d'informations sur la sécurité avancée des documents PDF et les fonctionnalités de gestion des privilèges d'accès.

### FAQ sur les privilèges définis dans le fichier PDF

#### Q : Pourquoi aurais-je besoin de définir des privilèges d’accès dans un fichier PDF ?

R : La définition des privilèges d'accès vous permet de contrôler la manière dont les utilisateurs interagissent avec vos documents PDF. Vous pouvez restreindre des actions telles que l'impression, la copie et la modification pour améliorer la sécurité des documents.

#### Q : Comment puis-je bénéficier de la définition de privilèges d’accès à l’aide d’Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET fournit un moyen simple d’implémenter des privilèges d’accès, vous donnant le pouvoir de personnaliser les autorisations utilisateur et de protéger le contenu sensible.

#### Q : Puis-je appliquer des privilèges différents à différents utilisateurs ?

R : Oui, vous pouvez définir des privilèges d’accès spécifiques pour différents groupes d’utilisateurs, ce qui vous permet d’affiner l’accès aux documents en fonction des rôles des utilisateurs.

#### Q : Quels sont les privilèges d’accès courants que je peux définir ?

: Les privilèges d’accès courants incluent l’autorisation ou l’interdiction d’actions telles que l’impression, la copie de texte ou d’images, la modification du document et le remplissage de champs de formulaire.

#### Q : Comment la définition du privilège de lecture d’écran améliore-t-elle l’accessibilité des documents ?

R : L’activation du privilège de lecture d’écran garantit que les utilisateurs peuvent accéder au contenu du PDF à l’aide de lecteurs d’écran, améliorant ainsi l’accessibilité pour les personnes malvoyantes.

#### Q : Puis-je définir une protection par mot de passe ainsi que des privilèges d’accès ?

R : Absolument, vous pouvez crypter votre document PDF avec des mots de passe tout en appliquant des privilèges d'accès. Cela fournit une couche de sécurité supplémentaire.

#### Q : Existe-t-il un moyen de révoquer les privilèges d’accès après les avoir appliqués ?

R : Une fois les privilèges d'accès appliqués et le document chiffré, les utilisateurs auront besoin du mot de passe approprié pour accéder au contenu. Les privilèges peuvent être modifiés en modifiant le code source.

#### Q : Y a-t-il des considérations de performances à prendre en compte lors de la définition des privilèges d’accès ?

: L’impact sur les performances est minime, car les paramètres de privilèges d’accès sont appliqués pendant le chiffrement, ce qui est un processus rapide.

#### Q : Puis-je appliquer des privilèges d’accès à un document PDF existant ?

R : Oui, vous pouvez utiliser Aspose.PDF pour .NET pour appliquer des privilèges d’accès aux documents PDF nouveaux et existants.
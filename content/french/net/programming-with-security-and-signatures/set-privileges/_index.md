---
title: Définir des privilèges dans un fichier PDF
linktitle: Définir des privilèges dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Définissez facilement les privilèges d'accès dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 100
url: /fr/net/programming-with-security-and-signatures/set-privileges/
---
Il est souvent nécessaire de définir des privilèges d'accès spécifiques au fichier PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement définir les privilèges d'accès à l'aide du code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici les directives d'importation nécessaires :

```csharp
using Aspose.Pdf;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF que vous souhaitez modifier. Remplacer`"YOUR DOCUMENTS DIRECTORY"`dans le code suivant avec le chemin réel de votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 3 : Charger le fichier PDF source

Nous allons maintenant charger le fichier PDF source en utilisant le code suivant :

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## Étape 4 : Définir les privilèges d'accès

 Dans cette étape, nous allons instancier le`DocumentPrivilege` objet pour définir les privilèges d’accès souhaités. Vous pouvez appliquer des restrictions sur tous les privilèges en utilisant`DocumentPrivilege.ForbidAll` . Par exemple, si vous souhaitez autoriser uniquement la lecture d'écran, vous pouvez définir`AllowScreenReaders` à`true`. Voici le code correspondant :

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## Étape 5 : Crypter et enregistrer le document

 Enfin, nous pouvons crypter le document PDF avec un mot de passe utilisateur et propriétaire en utilisant`Encrypt` et spécifier l'algorithme de chiffrement souhaité. Ensuite, nous enregistrons le document mis à jour. Voici le code correspondant :

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### Exemple de code source pour définir des privilèges à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Charger un fichier PDF source
using (Document document = new Document(dataDir + "input.pdf"))
{
	// Instancier l'objet Privilèges de document
	// Appliquer des restrictions sur tous les privilèges
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	// Autoriser uniquement la lecture d'écran
	documentPrivilege.AllowScreenReaders = true;
	// Cryptez le fichier avec le mot de passe utilisateur et propriétaire.
	// Besoin de définir le mot de passe, de sorte qu'une fois que l'utilisateur consulte le fichier avec le mot de passe utilisateur,
	// Seule l'option de lecture d'écran est activée
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	// Enregistrer le document mis à jour
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## Conclusion

Félicitation ! Vous disposez désormais d'un guide étape par étape pour définir les privilèges d'accès à un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour appliquer des restrictions spécifiques et protéger vos fichiers PDF si nécessaire.

Assurez-vous de consulter la documentation officielle d'Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de sécurité des documents PDF et de gestion des privilèges d'accès.

### FAQ pour définir les privilèges dans un fichier PDF

#### Q : Pourquoi devrais-je définir des privilèges d'accès dans un fichier PDF ?

R : La définition des privilèges d'accès vous permet de contrôler la manière dont les utilisateurs interagissent avec vos documents PDF. Vous pouvez restreindre des actions telles que l'impression, la copie et la modification pour améliorer la sécurité des documents.

#### Q : Comment puis-je bénéficier de la définition de privilèges d'accès à l'aide d'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET fournit un moyen simple de mettre en œuvre des privilèges d'accès, vous donnant le pouvoir de personnaliser les autorisations des utilisateurs et de protéger le contenu sensible.

#### Q : Puis-je appliquer différents privilèges à différents utilisateurs ?

R : Oui, vous pouvez définir des privilèges d'accès spécifiques pour différents groupes d'utilisateurs, ce qui vous permet d'affiner l'accès aux documents en fonction des rôles des utilisateurs.

#### Q : Quels sont les privilèges d'accès courants que je peux définir ?

R : Les privilèges d'accès courants incluent l'autorisation ou l'interdiction d'actions telles que l'impression, la copie de texte ou d'images, la modification du document et le remplissage des champs de formulaire.

#### Q : Comment la définition du privilège de lecture d'écran améliore-t-elle l'accessibilité des documents ?

R : L'activation du privilège de lecture d'écran garantit que les utilisateurs peuvent accéder au contenu du PDF à l'aide de lecteurs d'écran, améliorant ainsi l'accessibilité pour les personnes malvoyantes.

#### Q : Puis-je définir une protection par mot de passe ainsi que des privilèges d'accès ?

R : Absolument, vous pouvez crypter votre document PDF avec des mots de passe tout en appliquant des privilèges d'accès. Cela fournit une couche de sécurité supplémentaire.

#### Q : Existe-t-il un moyen de révoquer les privilèges d'accès après les avoir appliqués ?

R : Une fois les privilèges d'accès appliqués et le document crypté, les utilisateurs auront besoin du mot de passe approprié pour accéder au contenu. Les privilèges peuvent être modifiés en modifiant le code source.

#### Q : Y a-t-il des considérations en matière de performances lors de la définition des privilèges d'accès ?

R : L'impact sur les performances est minime, car les paramètres de privilèges d'accès sont appliqués lors du chiffrement, ce qui est un processus rapide.

#### Q : Puis-je appliquer des privilèges d'accès à un document PDF existant ?

R : Oui, vous pouvez utiliser Aspose.PDF pour .NET pour appliquer des privilèges d'accès aux documents PDF nouveaux et existants.
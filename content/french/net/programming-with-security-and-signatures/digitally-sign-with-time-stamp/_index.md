---
title: Signer numériquement avec horodatage dans un fichier PDF
linktitle: Signer numériquement avec horodatage dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment effectuer une signature numérique avec horodatage dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
Dans ce tutoriel, nous vous expliquerons le processus de signature numérique d'un fichier PDF avec horodatage à l'aide d'Aspose.PDF pour .NET. La signature numérique avec horodatage garantit l'authenticité et l'intégrité du document, en ajoutant une empreinte électronique avec horodatage.

## Étape 1 : Prérequis

Avant de commencer, assurez-vous de disposer des prérequis suivants :

- Connaissances de base du langage de programmation C#
- Installation de Visual Studio sur votre machine
- Bibliothèque Aspose.PDF pour .NET installée

## Étape 2 : Configuration de l’environnement

Pour commencer, suivez ces étapes pour configurer votre environnement de développement :

1. Ouvrez Visual Studio et créez un nouveau projet C#.
2. Importez les espaces de noms requis dans votre fichier de code :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## Étape 3 : Signature numérique avec horodatage

La première étape consiste à effectuer la signature numérique avec horodatage sur le fichier PDF. Le code fourni montre comment réaliser cette signature avec Aspose.PDF pour .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

Ce code charge un fichier PDF, crée une signature numérique avec horodatage à l'aide d'un fichier PFX (clé privée) et des paramètres d'horodatage spécifiés. La signature est ensuite ajoutée au fichier PDF et enregistrée avec le suffixe "_dehors".

### Exemple de code source pour la signature numérique avec horodatage à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // L'utilisateur/mot de passe peut être omis
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// Créez l’un des trois types de signature
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Enregistrer le fichier PDF de sortie
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusion

Félicitations ! Vous avez réussi à apposer une signature numérique avec horodatage sur un fichier PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a couvert le processus étape par étape, de la création de la signature à l'enregistrement du fichier PDF mis à jour. Vous pouvez désormais utiliser cette fonctionnalité pour ajouter des signatures numériques avec horodatage à vos fichiers PDF.

### FAQ sur la signature numérique avec horodatage dans un fichier PDF

#### Q : Quel est le but de la signature numérique avec un horodatage ?

: La signature numérique avec un horodatage ajoute une empreinte électronique avec un horodatage à un fichier PDF, garantissant l'authenticité et l'intégrité du document à un moment précis.

#### Q : Quels prérequis sont nécessaires pour démarrer ce tutoriel ?

R : Avant de commencer, assurez-vous d’avoir une compréhension de base du langage de programmation C#, d’avoir installé Visual Studio et d’avoir installé la bibliothèque Aspose.PDF pour .NET.

#### Q : Comment puis-je configurer mon environnement de développement ?

R : Suivez les étapes fournies pour configurer votre environnement de développement, notamment la création d’un nouveau projet C# dans Visual Studio et l’importation des espaces de noms nécessaires.

#### Q : Comment ajouter une signature numérique avec un horodatage à un PDF ?

R : L’exemple de code fourni montre comment charger un fichier PDF, créer une signature numérique avec un horodatage à l’aide d’un fichier PFX (clé privée) et des paramètres d’horodatage spécifiés, ajouter la signature au fichier PDF et enregistrer le fichier mis à jour.

#### Q : Qu’est-ce qu’un fichier PFX et pourquoi est-il utilisé dans l’exemple ?

R : Un fichier PFX (Personal Exchange Format) contient une clé privée et un certificat. Il est utilisé ici pour fournir une fonctionnalité cryptographique pour les signatures numériques. Assurez-vous de remplacer l'espace réservé par votre fichier PFX et votre mot de passe.

#### Q : Que sont les TimestampSettings ?

A : TimestampSettings définit les paramètres du serveur d'horodatage utilisé pour ajouter l'horodatage électronique à la signature. Il comprend l'URL du serveur d'horodatage et les informations d'identification facultatives de l'utilisateur.

#### Q : Puis-je utiliser un serveur d’horodatage autre que celui de l’exemple ?
 R : Oui, vous pouvez utiliser n'importe quel serveur d'horodatage compatible. Remplacez l'URL et, si nécessaire, fournissez les informations d'identification de l'utilisateur appropriées dans le champ`TimestampSettings` objet.

#### Q : Quel est le but de spécifier le rectangle de signature ?

A : Le rectangle de signature définit la position et les dimensions de l'apparence de la signature numérique sur la page PDF. Ajustez ces valeurs pour positionner la signature comme vous le souhaitez.

#### Q : Que se passe-t-il si le serveur d’horodatage n’est pas disponible pendant la signature ?

R : Si le serveur d'horodatage n'est pas disponible pendant la signature, le processus peut échouer ou prendre plus de temps. Assurez-vous que votre serveur d'horodatage est fiable et accessible.

#### Q : Comment puis-je vérifier la présence d’un horodatage dans le PDF signé ?

 R : Vous pouvez examiner le PDF signé à l'aide de l'exemple de code fourni.`TimestampSettings` que vous avez utilisé lors de la signature doit être disponible dans les détails de la signature.

#### Q : Les signatures numériques avec horodatage sont-elles juridiquement contraignantes ?

R : Les signatures numériques avec horodatage ont une valeur juridique dans de nombreuses juridictions et sont souvent considérées comme plus fiables que les simples signatures numériques. Consultez les experts juridiques de votre juridiction pour connaître les réglementations spécifiques.

#### Q : Puis-je ajouter plusieurs signatures numériques avec horodatages à un PDF ?

R : Oui, vous pouvez ajouter plusieurs signatures numériques avec horodatage à un fichier PDF en appelant plusieurs fois le processus de création de signature. Chaque signature aura son propre horodatage.
---
title: Signer numériquement avec horodatage
linktitle: Signer numériquement avec horodatage
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à effectuer une signature numérique avec horodatage sur un fichier PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---

Dans ce didacticiel, nous vous expliquerons le processus de signature numérique d'un fichier PDF avec horodatage à l'aide d'Aspose.PDF pour .NET. La signature numérique avec horodatage garantit l'authenticité et l'intégrité du document, en ajoutant une empreinte électronique avec horodatage.

## Étape 1 : Prérequis

Avant de commencer, assurez-vous d'avoir les prérequis suivants :

- Connaissance de base du langage de programmation C#
- Installation de Visual Studio sur votre machine
- Bibliothèque Aspose.PDF pour .NET installée

## Étape 2 : Configuration de l'environnement

Pour commencer, procédez comme suit pour configurer votre environnement de développement :

1. Ouvrez Visual Studio et créez un nouveau projet C#.
2. Importez les espaces de noms requis dans votre fichier de code :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## Étape 3 : Signature numérique avec horodatage

La première étape consiste à effectuer la signature numérique avec horodatage sur le fichier PDF. Le code fourni montre comment obtenir cette signature avec Aspose.PDF pour .NET.

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

### Exemple de code source pour signer numériquement avec horodatage à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // L'utilisateur/le mot de passe peut être omis
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//Créez l'un des trois types de signature
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// Enregistrer le fichier PDF de sortie
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## Conclusion

Félicitation ! Vous avez effectué avec succès une signature numérique avec horodatage sur un fichier PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a couvert le processus étape par étape, de la création de la signature à l'enregistrement du fichier PDF mis à jour. Vous pouvez désormais utiliser cette fonctionnalité pour ajouter des signatures numériques avec horodatage à vos fichiers PDF.
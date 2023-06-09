---
title: Signer numériquement
linktitle: Signer numériquement
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à signer numériquement un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-security-and-signatures/digitally-sign/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de signature numérique d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. La signature numérique garantit l'authenticité et l'intégrité du document, en ajoutant une empreinte digitale électronique unique.

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
using System.Collections.Generic;
```

## Étape 3 : Signature numérique

La première étape consiste à signer numériquement le fichier PDF. Le code fourni montre comment créer une signature numérique avec Aspose.PDF pour .NET.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

Ce code charge un fichier PDF, crée une signature numérique avec une apparence spécifiée, puis enregistre le fichier PDF avec la signature ajoutée.

## Étape 4 : Vérification de la signature

Après avoir ajouté la signature numérique, vous pouvez vérifier si le fichier PDF contient une signature valide.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // Faire quelque chose
                     }
                 }
             }
         }
     }
}
```

Ce code vérifie la première signature du fichier PDF et effectue des actions supplémentaires si la signature est certifiée et dispose d'autorisations spécifiques.

### Exemple de code source pour la signature numérique à l'aide d'Aspose.PDF pour .NET 
```csharp
try
{
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // Utiliser les objets PKCS7/PKCS7Detached
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// Définir l'apparence de la signature
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			//Créez l'un des trois types de signature
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// Enregistrer le fichier PDF de sortie
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // Des signatures ?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // Vérifiez le premier
				{
					if (signature.IsCertified) // Agréé?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // Obtenir l'autorisation d'accès
						{
							// Faire quelque chose
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion

Félicitation ! Vous avez effectué avec succès une signature numérique sur un fichier PDF en utilisant Aspose.PDF pour .NET. Ce didacticiel a couvert le processus étape par étape, de l'ajout de la signature numérique à la vérification de sa validité. Vous pouvez désormais utiliser cette fonction pour sécuriser vos fichiers PDF avec des signatures numériques.
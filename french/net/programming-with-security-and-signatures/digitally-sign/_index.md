---
title: Connectez-vous numériquement au fichier PDF
linktitle: Connectez-vous numériquement au fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à vous connecter numériquement à un fichier PDF avec Aspose.PDF pour .NET.
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
			// Créez l'un des trois types de signature
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

Félicitation ! Vous avez effectué avec succès une signature numérique sur un fichier PDF à l'aide d'Aspose.PDF pour .NET. Ce didacticiel a couvert le processus étape par étape, de l'ajout de la signature numérique à la vérification de sa validité. Vous pouvez désormais utiliser cette fonction pour sécuriser vos fichiers PDF avec des signatures numériques.

### FAQ

#### Q : Quel est l'objectif de ce didacticiel ?

R : Ce didacticiel vous guide tout au long du processus de signature numérique d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Les signatures numériques ajoutent une empreinte digitale électronique pour garantir l'authenticité et l'intégrité du document.

#### Q : Quels sont les prérequis requis avant de commencer ?

R : Avant de commencer, assurez-vous d'avoir une compréhension de base du langage de programmation C#, d'avoir installé Visual Studio et d'avoir installé la bibliothèque Aspose.PDF pour .NET.

#### Q : Comment configurer l'environnement de développement ?

R : Suivez les étapes fournies pour configurer votre environnement de développement, y compris la création d'un nouveau projet C# dans Visual Studio et l'importation des espaces de noms requis.

#### Q : Comment ajouter une signature numérique à un fichier PDF ?

 R : L'exemple de code fourni montre comment charger un fichier PDF, créer une signature numérique, spécifier l'apparence et enregistrer le fichier PDF signé. La signature numérique est ajoutée à l'aide de la`Certify` méthode de la`PdfFileSignature` objet.

#### Q : Comment vérifier la validité d'une signature numérique ?

R : Après avoir ajouté la signature numérique, vous pouvez utiliser l'exemple de code pour vérifier la validité de la signature. Il vérifie si la signature est certifiée et dispose d'autorisations d'accès spécifiques.

####  Q : Qu'est-ce que le`PKCS7` object represent?

 R : Le`PKCS7` L'objet est utilisé pour fournir la fonctionnalité cryptographique pour les signatures numériques. Il est utilisé pour créer la signature numérique dans l'exemple de code fourni.

#### Q : Puis-je personnaliser l'apparence de la signature numérique ?

 R : Oui, vous pouvez personnaliser l'apparence de la signature numérique en spécifiant le chemin d'accès à une image dans le`SignatureAppearance` propriété de la`PdfFileSignature` objet.

#### Q : Que se passe-t-il si la signature n'est pas valide ?

R : Si la signature n'est pas valide, le processus de vérification échouera et les actions correspondantes dans le bloc de code de vérification ne seront pas exécutées.

#### Q : Comment puis-je garantir la sécurité de mes signatures numériques ?

: Les signatures numériques sont sécurisées dès leur conception et utilisent des techniques cryptographiques pour garantir l'authenticité et l'intégrité. Assurez-vous de conserver votre clé privée en sécurité et de suivre les meilleures pratiques de gestion des signatures numériques.

#### Q : Puis-je ajouter plusieurs signatures numériques à un PDF ?

 R : Oui, vous pouvez ajouter plusieurs signatures numériques à un fichier PDF à l'aide de`PdfFileSignature` objets`Sign` ou`Certify` méthodes. Chaque signature aura sa propre apparence et sa propre configuration.
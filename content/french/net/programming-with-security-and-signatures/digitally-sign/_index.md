---
title: Connexion numérique au fichier PDF
linktitle: Connexion numérique au fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment signer numériquement un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-security-and-signatures/digitally-sign/
---
Dans ce tutoriel, nous vous expliquerons le processus de signature numérique d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. La signature numérique garantit l'authenticité et l'intégrité du document en ajoutant une empreinte électronique unique.

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

## Étape 4 : Vérification de la signature

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
	// Le chemin vers le répertoire des documents.
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
			// Créez l’un des trois types de signature
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
				if (signature.VerifySigned(sigNames[0] as string)) // Vérifiez d'abord
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

Félicitations ! Vous avez réussi à apposer une signature numérique sur un fichier PDF à l'aide d'Aspose.PDF pour .NET. Ce tutoriel a couvert le processus étape par étape, de l'ajout de la signature numérique à la vérification de sa validité. Vous pouvez désormais utiliser cette fonctionnalité pour sécuriser vos fichiers PDF avec des signatures numériques.

### FAQ

#### Q : Quel est le but de ce tutoriel ?

R : Ce didacticiel vous guide tout au long du processus de signature numérique d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Les signatures numériques ajoutent une empreinte électronique pour garantir l'authenticité et l'intégrité du document.

#### Q : Quels sont les prérequis nécessaires avant de commencer ?

R : Avant de commencer, assurez-vous d’avoir une compréhension de base du langage de programmation C#, d’avoir installé Visual Studio et d’avoir installé la bibliothèque Aspose.PDF pour .NET.

#### Q : Comment configurer l’environnement de développement ?

R : Suivez les étapes fournies pour configurer votre environnement de développement, notamment la création d’un nouveau projet C# dans Visual Studio et l’importation des espaces de noms requis.

#### Q : Comment ajouter une signature numérique à un fichier PDF ?

 R : L'exemple de code fourni montre comment charger un fichier PDF, créer une signature numérique, spécifier l'apparence et enregistrer le fichier PDF signé. La signature numérique est ajoutée à l'aide de`Certify` méthode de la`PdfFileSignature` objet.

#### Q : Comment vérifier la validité d’une signature numérique ?

: Après avoir ajouté la signature numérique, vous pouvez utiliser l'exemple de code pour vérifier la validité de la signature. Il vérifie si la signature est certifiée et dispose d'autorisations d'accès spécifiques.

####  Q : Que signifie le`PKCS7` object represent?

 A : Le`PKCS7` L'objet est utilisé pour fournir la fonctionnalité cryptographique pour les signatures numériques. Il est utilisé pour créer la signature numérique dans l'exemple de code fourni.

#### Q : Puis-je personnaliser l’apparence de la signature numérique ?

 R : Oui, vous pouvez personnaliser l'apparence de la signature numérique en spécifiant le chemin d'accès à une image dans le`SignatureAppearance` propriété de la`PdfFileSignature` objet.

#### Q : Que se passe-t-il si la signature n’est pas valide ?

R : Si la signature n'est pas valide, le processus de vérification échouera et les actions correspondantes dans le bloc de code de vérification ne seront pas exécutées.

#### Q : Comment puis-je garantir la sécurité de mes signatures numériques ?

: Les signatures numériques sont sécurisées par conception et utilisent des techniques cryptographiques pour garantir leur authenticité et leur intégrité. Assurez-vous de conserver votre clé privée en sécurité et de suivre les meilleures pratiques en matière de gestion des signatures numériques.

#### Q : Puis-je ajouter plusieurs signatures numériques à un PDF ?

 R : Oui, vous pouvez ajouter plusieurs signatures numériques à un fichier PDF à l'aide de l'`PdfFileSignature` objet`Sign` ou`Certify` méthodes. Chaque signature aura sa propre apparence et sa propre configuration.
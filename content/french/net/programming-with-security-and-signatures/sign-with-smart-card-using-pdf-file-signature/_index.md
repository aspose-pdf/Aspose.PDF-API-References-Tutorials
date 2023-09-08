---
title: Signez avec une carte à puce à l'aide de la signature d'un fichier PDF
linktitle: Signez avec une carte à puce à l'aide de la signature d'un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Signez vos fichiers PDF en toute sécurité avec une carte à puce à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 110
url: /fr/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
La signature numérique avec une carte à puce est un moyen sécurisé de signer des fichiers PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement signer un fichier PDF à l'aide d'une carte à puce en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici les directives d'importation nécessaires :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF que vous souhaitez signer. Remplacer`"YOUR DOCUMENTS DIRECTORY"`dans le code suivant avec le chemin réel de votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 3 : Charger le document PDF

Nous allons maintenant charger le document PDF à signer en utilisant le code suivant :

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## Étape 4 : Effectuer la signature avec la carte à puce

 Dans cette étape, nous effectuerons la signature avec la carte à puce en utilisant le`PdfFileSignature` classe de la`Facades`bibliothèque. Nous sélectionnons le certificat de carte à puce dans le magasin de certificats Windows et spécifions les informations de signature nécessaires. Voici le code correspondant :

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // Sélectionnez le certificat dans la boutique
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## Étape 5 : Vérifier la signature

 Enfin, nous vérifions la signature du fichier PDF signé à l'aide du`PdfFileSignature` classe. Nous obtenons les noms de signature et les vérifions un par un. Si une signature échoue à la vérification, une exception est levée. Voici le code correspondant :

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### Exemple de code source pour signer avec une carte à puce à l'aide d'une signature de fichier PDF à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Signer avec la sélection de certificat dans le magasin de certificats Windows
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// Choisissez manuellement le certificat dans le magasin
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## Conclusion

Félicitation ! Vous disposez désormais d'un guide étape par étape pour signer un fichier PDF avec une carte à puce à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour ajouter des signatures numériques sécurisées à vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de signature numérique et de gestion des certificats.

### FAQ

#### Q : Pourquoi devrais-je envisager de signer des fichiers PDF avec une carte à puce ?

R : La signature de fichiers PDF avec une carte à puce améliore la sécurité en garantissant l'authenticité et l'intégrité du document. Les signatures basées sur des cartes à puce offrent un niveau plus élevé de confiance et de conformité.

#### Q : Comment fonctionne la signature numérique basée sur une carte à puce ?

R : La signature numérique basée sur une carte à puce implique l'utilisation d'une clé cryptographique stockée sur une carte à puce pour créer une signature numérique unique. Cette signature est jointe au fichier PDF, permettant aux destinataires de vérifier l'origine et l'intégrité du document.

#### Q : Quel est le rôle d'Aspose.PDF pour .NET dans la signature par carte à puce ?

R : Aspose.PDF pour .NET fournit un ensemble complet d'outils et de bibliothèques pour faciliter la signature numérique de fichiers PDF par carte à puce. Il simplifie le processus et garantit une signature sécurisée des documents.

#### Q : Puis-je choisir un certificat de carte à puce spécifique à signer ?

R : Oui, vous pouvez sélectionner un certificat de carte à puce spécifique dans le magasin de certificats Windows pour le signer. Aspose.PDF pour .NET vous permet d'intégrer de manière transparente la sélection de certificats dans votre application.

#### Q : Comment le code source fourni gère-t-il la signature basée sur une carte à puce ?

R : Le code source montre comment lier un document PDF, sélectionner un certificat de carte à puce, spécifier les informations de signature et créer une signature numérique. Il montre également comment vérifier la validité de la signature.

#### Q : Puis-je appliquer plusieurs signatures à l’aide de cartes à puce dans un seul fichier PDF ?

R : Absolument, vous pouvez appliquer plusieurs signatures basées sur une carte à puce à un seul fichier PDF. Chaque signature est unique et contribue à la sécurité globale du document.

#### Q : Que se passe-t-il si la vérification d'une signature échoue lors de l'étape de vérification ?

R : Si la vérification d'une signature échoue, une exception est levée, indiquant que la signature n'est pas valide. Cela garantit que seules les signatures valides et fiables sont acceptées.

#### Q : La signature par carte à puce est-elle compatible avec tous les types de documents PDF ?

R : Oui, la signature par carte à puce est compatible avec tous les types de documents PDF. Vous pouvez appliquer des signatures numériques à différents types de fichiers PDF, notamment des formulaires, des rapports, etc.

#### Q : Comment puis-je en savoir plus sur la gestion avancée des signatures numériques et des certificats ?

R : Explorez la documentation officielle Aspose.PDF pour obtenir des informations détaillées sur les fonctionnalités avancées de signature numérique, la gestion des certificats et les meilleures pratiques pour garantir la sécurité des documents.

#### Q : Où puis-je trouver une assistance ou un support supplémentaire pour la mise en œuvre de la signature par carte à puce ?

R : Pour obtenir des conseils et une assistance supplémentaires, contactez les forums de la communauté Aspose.PDF ou reportez-vous à la documentation pour obtenir des informations complètes sur la signature par carte à puce.
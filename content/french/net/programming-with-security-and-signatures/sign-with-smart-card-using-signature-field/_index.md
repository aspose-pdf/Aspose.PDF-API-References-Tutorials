---
title: Signer avec une carte à puce en utilisant le champ de signature
linktitle: Signer avec une carte à puce en utilisant le champ de signature
second_title: Référence de l'API Aspose.PDF pour .NET
description: Signez vos fichiers PDF en toute sécurité avec une carte à puce en utilisant Aspose.PDF pour .NET.
type: docs
weight: 120
url: /fr/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
La signature numérique avec une carte à puce est un moyen sécurisé de signer des fichiers PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement signer un fichier PDF à l'aide d'un champ de signature et d'une carte à puce en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires à votre projet C#. Voici les directives d'importation nécessaires :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## Étape 2 : définir le chemin d’accès au dossier des documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF que vous souhaitez signer. Remplacer`"YOUR DOCUMENTS DIRECTORY"` dans le code suivant avec le chemin réel vers votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 3 : Copiez et ouvrez le document PDF

Nous allons maintenant copier et ouvrir le document PDF à signer en utilisant le code suivant :

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // Créer un champ de signature
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // Sélectionnez le certificat dans la boutique
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // Créer une signature externe avec les informations nécessaires
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## Étape 4 : Vérifier la signature

 Enfin, nous vérifions la signature du fichier PDF signé à l'aide de la`PdfFileSignature` classe. Nous récupérons les noms des signatures et les vérifions une par une. Si une signature échoue à la vérification, une exception est levée. Voici le code correspondant :

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

### Exemple de code source pour Sign With Smart Card Using Signature Field avec Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Signer avec la sélection de certificat dans le magasin de certificats Windows
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// Choisissez manuellement le certificat dans le magasin
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
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

Félicitations ! Vous disposez désormais d'un guide étape par étape pour signer un fichier PDF avec une carte à puce en utilisant un champ de signature avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour ajouter des signatures numériques sécurisées à vos documents PDF.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées de signature numérique et de gestion des certificats.

### FAQ

#### Q : Quel est l’avantage d’utiliser un champ de signature pour la signature numérique avec une carte à puce ?

: L'utilisation d'un champ de signature pour la signature numérique avec une carte à puce fournit une zone désignée dans le PDF où la signature est appliquée. Cela améliore la clarté du document et garantit l'authenticité de la signature.

#### Q : Comment la bibliothèque Aspose.PDF pour .NET facilite-t-elle la signature numérique basée sur une carte à puce avec un champ de signature ?

R : Aspose.PDF pour .NET simplifie le processus de création d’un champ de signature, de sélection d’un certificat de carte à puce et d’application d’une signature numérique à une zone spécifique du document PDF.

#### Q : Pourquoi est-il important de sélectionner un certificat spécifique pour la signature par carte à puce ?

R : La sélection d'un certificat spécifique vous permet d'identifier de manière unique le signataire et de garantir l'intégrité de la signature. Cela permet d'établir la confiance et la conformité aux normes de signature numérique.

#### Q : Comment le code source fourni gère-t-il le processus de signature basé sur une carte à puce avec un champ de signature ?

R : Le code source montre comment créer un champ de signature, sélectionner un certificat de carte à puce et appliquer une signature numérique avec des informations de signature spécifiques. Il montre également comment vérifier la validité de la signature.

#### Q : Puis-je personnaliser l’apparence du champ de signature ?

R : Oui, vous pouvez personnaliser l’apparence du champ de signature, comme sa taille, sa position et sa représentation visuelle, pour l’aligner sur la mise en page de votre document.

#### Q : Que se passe-t-il si une signature échoue à la vérification lors de l’étape de vérification ?

R : Si une signature échoue à la vérification, une exception est levée, indiquant que la signature n'est pas valide. Cela garantit que seules les signatures valides et fiables sont acceptées.

#### Q : Puis-je appliquer plusieurs champs de signature et des signatures basées sur des cartes à puce à un seul document PDF ?

R : Absolument, vous pouvez appliquer plusieurs champs de signature et signatures basées sur des cartes à puce à différentes zones du même document PDF, offrant ainsi plusieurs niveaux de sécurité.

#### Q : Comment l’utilisation d’un champ de signature améliore-t-elle le processus global de signature du document ?

: L’utilisation d’un champ de signature rationalise le processus de signature du document, car il guide le signataire pour placer sa signature dans une zone désignée, rendant le processus de signature plus organisé et convivial.

#### Q : Existe-t-il des limites à l’utilisation des champs de signature avec la signature par carte à puce ?

R : Il n'existe aucune limitation inhérente à l'utilisation des champs de signature avec la signature par carte à puce. Cependant, il est important de veiller à ce que l'emplacement du champ de signature choisi ne masque pas le contenu important du document.

#### Q : Où puis-je trouver une assistance ou un support supplémentaire pour la mise en œuvre de la signature par carte à puce avec un champ de signature ?

R : Pour des conseils et une assistance supplémentaires, vous pouvez vous référer à la documentation officielle d'Aspose.PDF et aux forums communautaires, qui offrent des informations et des solutions précieuses pour la mise en œuvre de signatures numériques sécurisées.
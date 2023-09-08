---
title: Fournir des informations d'identification pendant HTML vers PDF
linktitle: Fournir des informations d'identification pendant HTML vers PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour convertir du HTML en PDF en fournissant des informations d'identification avec Aspose.PDF pour .NET.
type: docs
weight: 240
url: /fr/net/document-conversion/provide-credentials-during-html-to-pdf/
---
Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier HTML en PDF tout en fournissant des informations d'identification lors de l'accès à une URL sécurisée à l'aide d'Aspose.PDF pour .NET. En suivant les étapes ci-dessous, vous pourrez convertir le contenu HTML en PDF en utilisant les informations d'identification appropriées.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Récupérer du contenu HTML sécurisé
Au cours de cette étape, nous récupérerons le contenu HTML sécurisé à partir d'une URL à l'aide des informations d'identification appropriées. Utilisez le code suivant :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créez une demande pour l'URL.
WebRequest request = WebRequest.Create("http://My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
// Si nécessaire pour le serveur, définissez les informations d'identification.
request.Credentials = CredentialCache.DefaultCredentials;
// Obtenez la réponse.
HttpWebResponse response = (HttpWebResponse)request.GetResponse();

// Récupère le flux contenant le contenu renvoyé par le serveur.
Stream dataStream = response. GetResponseStream();
// Ouvrez le flux à l'aide d'un StreamReader pour un accès facile.
StreamReader reader = new StreamReader(dataStream);
// Lisez le contenu.
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel dans lequel vous souhaitez enregistrer le fichier PDF résultant.

## Étape 2 : Convertissez le HTML en PDF en fournissant les informations d'identification
Nous allons maintenant charger le contenu HTML récupéré et le convertir au format PDF tout en fournissant les informations d'identification appropriées. Utilisez le code suivant :

```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

HtmlLoadOptions options = new HtmlLoadOptions("http://Mon.signchart.com/");
options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

// Charger le fichier HTML
Document pdfDocument = new Document(stream, options);
```

## Étape 3 : Enregistrement du fichier PDF résultant
Enfin, nous enregistrerons le fichier PDF résultant. Utilisez le code suivant :

```csharp
// Enregistrez le fichier PDF résultant
pdfDocument.Save(dataDir + "ProvideCredentialsDuringHTMLToPDF_out.pdf");
```

 Le code ci-dessus enregistre le fichier PDF résultant avec le nom de fichier`"ProvideCredentialsDuringHTMLToPDF_out.pdf"`.

### Exemple de code source pour Fournir des informations d'identification lors du format HTML vers PDF à l'aide d'Aspose.PDF pour .NET

```csharp
try
{
	
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Créez une demande pour l'URL.
	WebRequest request = WebRequest.Create("http:// My.signchart.com/Report/PrintBook.asp?ProjectGuid=6FB9DBB0-");
	// Si le serveur l'exige, définissez les informations d'identification.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Obtenez la réponse.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Récupère le flux contenant le contenu renvoyé par le serveur.
	Stream dataStream = response.GetResponseStream();
	// Ouvrez le flux à l'aide d'un StreamReader pour un accès facile.
	StreamReader reader = new StreamReader(dataStream);
	// Lisez le contenu.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));

	HtmlLoadOptions options = new HtmlLoadOptions("http:// Mon.signchart.com/");
	options.ExternalResourcesCredentials = CredentialCache.DefaultCredentials;

	// Charger le fichier HTML
	Document pdfDocument = new Document(stream, options);
	// Enregistrer le fichier résultant
	pdfDocument.Save("ProvideCredentialsDuringHTMLToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier HTML en PDF tout en fournissant des informations d'identification lors de l'accès à une URL sécurisée à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous pourrez convertir avec succès le contenu HTML en PDF tout en fournissant les informations d'identification correctes.

### FAQ

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET est une bibliothèque robuste qui permet aux développeurs de travailler avec des documents PDF dans des applications C#. Il offre un large éventail de fonctionnalités, notamment la conversion HTML en PDF.

#### Q : Comment puis-je récupérer du contenu HTML sécurisé à partir d'une URL ?

 R : Pour récupérer du contenu HTML sécurisé à partir d'une URL, vous pouvez utiliser l'outil`WebRequest` classe en C#. Assurez-vous de définir les informations d'identification appropriées à l'aide du`Credentials` propriété.

#### Q : Quels sont les prérequis pour ce didacticiel ?

R : Avant de poursuivre le didacticiel, assurez-vous que vous disposez des conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

#### Q : Comment Aspose.PDF pour .NET gère-t-il les ressources externes lors de la conversion de HTML en PDF ?

 R : Aspose.PDF pour .NET fournit le`HtmlLoadOptions`classe pour gérer les ressources externes lors de la conversion HTML en PDF. Vous pouvez définir les informations d'identification de la ressource externe à l'aide de l'outil`ExternalResourcesCredentials` propriété.

#### Q : Puis-je personnaliser le nom du fichier PDF résultant ?

 R : Oui, vous pouvez personnaliser le nom de fichier du fichier PDF résultant en modifiant le code qui enregistre le document PDF. Changez simplement le nom du fichier souhaité dans le`pdfDocument.Save()` méthode.
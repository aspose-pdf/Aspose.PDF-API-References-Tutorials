---
title: Page Web en PDF
linktitle: Page Web en PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir une page Web en PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 320
url: /fr/net/document-conversion/web-page-to-pdf/
---

Dans ce didacticiel, nous vous guiderons étape par étape sur la façon de convertir une page Web en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous vous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets. À la fin de ce didacticiel, vous serez en mesure de convertir sans effort des pages Web en documents PDF.

## Introduction
La conversion de pages Web au format PDF est une exigence courante dans de nombreuses applications. En convertissant le contenu Web au format PDF, vous pouvez facilement conserver la mise en page, le formatage et les images de la page Web d'origine. Aspose.PDF pour .NET est une bibliothèque puissante qui vous permet d'effectuer cette conversion de manière efficace et précise.

## Exigences
Avant de commencer, assurez-vous que les conditions préalables suivantes sont en place :
- Visual Studio installé sur votre machine
- Bibliothèque Aspose.PDF pour .NET (vous pouvez la télécharger sur le site officiel d'Aspose)
- Connaissances de base en programmation C#


## Étape 1 : Définir le répertoire de documents
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin où vous souhaitez enregistrer le fichier PDF généré.

## Étape 2 : Créer une demande Web
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Créez un objet de demande Web et spécifiez l'URL de la page Web que vous souhaitez convertir. Vous pouvez remplacer l'URL par n'importe quelle page Web souhaitée.

## Étape 3 : Obtenir la réponse Web
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Envoyez la requête Web et récupérez la réponse du serveur.

## Étape 4 : Lire le contenu Web
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 Lire le contenu de la page Web à l'aide d'un`StreamReader` et rangez-le dans le`responseFromServer` variable.

## Étape 5 : Convertir HTML en PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Créer un`MemoryStream` objet pour charger le contenu de la page Web. Ensuite, créez une instance de`HtmlLoadOptions` et transmettez l'URL de base de la page Web. Ensuite, créez un`Document` objet à l'aide du flux chargé et des options de chargement HTML. Met le`IsLandscape` propriété à`true` si vous souhaitez que le PDF soit en orientation paysage. Enfin, enregistrez le document PDF dans le répertoire spécifié

.

## Étape 6 : Gérer les exceptions
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Attrapez toutes les exceptions qui peuvent se produire pendant le processus de conversion et affichez le message d'erreur.

### Exemple de code source pour une page Web au format PDF en utilisant Aspose.Words pour .NET

```csharp
try
{
	
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Créez une requête pour l'URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Si requis par le serveur, définissez les informations d'identification.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Délai d'expiration en millisecondes avant l'expiration de la demande
	// Request.Timeout = 100 ;

	// Obtenez la réponse.
	HttpWebResponse response = (HttpWebResponse)request.GetResponse();

	// Obtenez le flux contenant le contenu renvoyé par le serveur.
	Stream dataStream = response.GetResponseStream();
	// Ouvrez le flux à l'aide d'un StreamReader pour un accès facile.
	StreamReader reader = new StreamReader(dataStream);
	// Lisez le contenu.
	string responseFromServer = reader.ReadToEnd();
	reader.Close();
	dataStream.Close();
	response.Close();

	MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
	HtmlLoadOptions options = new HtmlLoadOptions("https:// En.wikipedia.org/wiki/");


	// Charger le fichier HTML
	Document pdfDocument = new Document(stream, options);

	options.PageInfo.IsLandscape = true;

	// Enregistrer la sortie au format PDF
	pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
Dans ce didacticiel, nous avons appris à convertir une page Web en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous avons parcouru le guide étape par étape expliquant le code source C# fourni. En suivant ces instructions, vous pouvez facilement intégrer la fonctionnalité de conversion de page Web en PDF dans vos propres applications .NET.
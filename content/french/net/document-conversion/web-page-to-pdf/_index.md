---
title: Page Web en PDF
linktitle: Page Web en PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour convertir une page Web en PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 320
url: /fr/net/document-conversion/web-page-to-pdf/
---
Dans ce didacticiel, nous vous guiderons étape par étape sur la façon de convertir une page Web en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets. À la fin de ce didacticiel, vous serez en mesure de convertir des pages Web en documents PDF sans effort.

## Introduction
La conversion de pages Web au format PDF est une exigence courante dans de nombreuses applications. En convertissant le contenu Web en PDF, vous pouvez facilement conserver la mise en page, le formatage et les images de la page Web d'origine. Aspose.PDF pour .NET est une bibliothèque puissante qui vous permet d'effectuer cette conversion de manière efficace et précise.

## Exigences
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
- Visual Studio installé sur votre machine
- Bibliothèque Aspose.PDF pour .NET (vous pouvez le télécharger depuis le site officiel d'Aspose)
- Connaissance de base de la programmation C#


## Étape 1 : Définir le répertoire des documents
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
 Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin où vous souhaitez enregistrer le fichier PDF généré.

## Étape 2 : Créer une demande Web
```csharp
WebRequest request = WebRequest.Create("https://en.wikipedia.org/wiki/Main_Page");
request.Credentials = CredentialCache.DefaultCredentials;
```
Créez un objet de requête Web et spécifiez l'URL de la page Web que vous souhaitez convertir. Vous pouvez remplacer l'URL par n'importe quelle page Web souhaitée.

## Étape 3 : Obtenez la réponse Web
```csharp
HttpWebResponse response = (HttpWebResponse)request.GetResponse();
```
Envoyez la requête Web et récupérez la réponse du serveur.

## Étape 4 : Lire le contenu Web
```csharp
Stream dataStream = response. GetResponseStream();
StreamReader reader = new StreamReader(dataStream);
string responseFromServer = reader.ReadToEnd();
reader. Close();
dataStream.Close();
response. Close();
```
 Lire le contenu de la page Web à l'aide d'un`StreamReader`et rangez-le dans le`responseFromServer` variable.

## Étape 5 : Convertir le HTML en PDF
```csharp
MemoryStream stream = new MemoryStream(System.Text.Encoding.UTF8.GetBytes(responseFromServer));
HtmlLoadOptions options = new HtmlLoadOptions("https://en.wikipedia.org/wiki/");
Document pdfDocument = new Document(stream, options);
options.PageInfo.IsLandscape = true;
pdfDocument.Save(dataDir + "WebPageToPDF_out.pdf");
```
 Créer un`MemoryStream` objet pour charger le contenu de la page Web. Ensuite, créez une instance de`HtmlLoadOptions` et transmettez l'URL de base de la page Web. Ensuite, créez un`Document` objet en utilisant le flux chargé et les options de chargement HTML. Met le`IsLandscape` propriété à`true` si vous souhaitez que le PDF soit en orientation paysage. Enfin, enregistrez le document PDF dans le répertoire spécifié

.

## Étape 6 : Gérer les exceptions
```csharp
catch (Exception ex)
{
Console.WriteLine(ex.Message);
}
```
Détectez toutes les exceptions pouvant survenir pendant le processus de conversion et affichez le message d'erreur.

### Exemple de code source pour une page Web au format PDF à l'aide d'Aspose.PDF pour .NET

```csharp
try
{
	
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Créez une demande pour l'URL.
	WebRequest request = WebRequest.Create("https:// En.wikipedia.org/wiki/Main_Page");
	// Si le serveur l'exige, définissez les informations d'identification.
	request.Credentials = CredentialCache.DefaultCredentials;
	// Délai d'expiration en millisecondes avant l'expiration de la demande
	// Request.Timeout = 100 ;

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

### FAQ

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des documents PDF dans des applications C#. Il offre diverses fonctionnalités, notamment la conversion de pages Web en PDF.

#### Q : Pourquoi voudrais-je convertir une page Web en PDF ?

R : La conversion de pages Web au format PDF est utile pour préserver la mise en page, le formatage et les images du contenu Web d'origine. Il vous permet de créer un instantané de la page Web pour une visualisation hors ligne ou un partage avec d'autres.

#### Q : Quels sont les prérequis pour ce didacticiel ?

R : Pour suivre ce didacticiel, vous devez avoir installé Visual Studio sur votre ordinateur, la bibliothèque Aspose.PDF pour .NET et une compréhension de base de la programmation C#.

#### Q : Puis-je convertir n’importe quelle page Web en PDF ?

: Oui, vous pouvez convertir n'importe quelle page Web en PDF en fournissant l'URL de la page Web dans le code. Aspose.PDF pour .NET récupérera le contenu Web et le convertira au format PDF.

#### Q : Comment puis-je personnaliser la sortie PDF, comme l'orientation de la page ?

 R : Vous pouvez personnaliser la sortie PDF en utilisant des options telles que`IsLandscape` pour définir l’orientation de la page. Dans le code fourni,`options.PageInfo.IsLandscape = true` est utilisé pour créer le PDF en orientation paysage.
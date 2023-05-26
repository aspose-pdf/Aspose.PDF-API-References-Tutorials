---
title: Définir les propriétés de la boîte de dialogue d'impression
linktitle: Définir les propriétés de la boîte de dialogue d'impression
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir les propriétés de la boîte de dialogue d'impression dans Aspose.PDF pour .NET à l'aide du guide étape par étape.
type: docs
weight: 320
url: /fr/net/programming-with-document/setpropertiesforprintdialog/
---
voici un guide étape par étape pour définir les propriétés de la boîte de dialogue d'impression à l'aide d'Aspose.PDF pour .NET :


## Étape 1 : Définissez le répertoire où se trouve votre document PDF :

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";
```
   
##  Étape 2 : Créez une nouvelle instance de`Document` class:

```csharp
using (Document doc = new Document())
{
  // Codage ici
}
```
   
## Étape 3 : Ajoutez une nouvelle page au document :

```csharp
doc.Pages.Add();
```
   
##  Étape 4 : Définissez la propriété duplex sur`DuplexFlipLongEdge`:

```csharp
doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
```
   
## Étape 5 : Enregistrez le document avec le nom et le format de fichier spécifié :

```csharp
doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
```

## Conclusion

Aspose.PDF pour .NET facilite la définition des propriétés de la boîte de dialogue d'impression dans vos fichiers PDF. En suivant le guide étape par étape ci-dessus, vous pouvez rapidement optimiser vos fichiers PDF pour l'impression.

### Exemple de code source pour la boîte de dialogue Définir les propriétés pour l'impression à l'aide d'Aspose.PDF pour .NET

```csharp

	var dataDir = "YOUR DOCUMENT DIRECTORY";

	using (Document doc = new Document())
	{
		doc.Pages.Add();
		doc.Duplex = PrintDuplex.DuplexFlipLongEdge;
		doc.Save(dataDir + "35297_out.pdf", SaveFormat.Pdf);
	}

```

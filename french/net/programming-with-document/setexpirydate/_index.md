---
title: Définir la date d'expiration
linktitle: Définir la date d'expiration
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à définir la date d'expiration dans les documents PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 300
url: /fr/net/programming-with-document/setexpirydate/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui fournit diverses fonctionnalités pour travailler avec des fichiers PDF. L'une de ces fonctionnalités est la possibilité de définir une date d'expiration pour un document PDF. Dans ce didacticiel, nous vous guiderons tout au long du processus de définition d'une date d'expiration pour un document PDF à l'aide d'Aspose.PDF pour .NET. 

## Étape 1 : Définissez le chemin d'accès au répertoire de documents

Avant de commencer, nous devons définir le chemin d'accès au répertoire où se trouve notre document PDF. Nous stockerons ce chemin dans une variable appelée "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Création d'un nouveau document PDF

Pour créer un nouveau document PDF, nous devons instancier un nouveau`Aspose.Pdf.Document` objet. Nous pouvons le faire en utilisant le code suivant :

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Étape 3 : Ajouter une nouvelle page au document PDF

Une fois que nous avons créé le document PDF, nous pouvons y ajouter une nouvelle page. Nous pouvons le faire en utilisant le code suivant :

```csharp
doc.Pages.Add();
```

## Étape 4 : Ajouter du texte au document PDF

 Après avoir ajouté une page au document PDF, nous pouvons y ajouter du texte à l'aide de la`Paragraphs` collection. Nous pouvons le faire en utilisant le code suivant :

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Étape 5 : Définition de la date d'expiration du PDF à l'aide de JavaScript

Pour définir la date d'expiration du PDF, nous devons créer un objet JavaScript. Nous pouvons le faire en utilisant le code suivant :

```csharp
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");

// Définir JavaScript comme action d'ouverture de PDF
doc.OpenAction = javaScript;
```

Dans ce code, nous fixons la date d'expiration à mai 2017.

## Étape 6 : Enregistrez le fichier PDF

 Après avoir défini la date d'expiration, vous devez enregistrer le fichier PDF. Pour ce faire, vous pouvez utiliser le`Save` méthode de la`Document` objet et transmettez le chemin d'accès à l'endroit où vous souhaitez enregistrer le fichier PDF mis à jour.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);
```

### Exemple de code source pour Définir la date d'expiration à l'aide d'Aspose.PDF pour .NET

Voici l'exemple de code source complet pour définir la date d'expiration à l'aide d'Aspose.PDF pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'objet Document
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// Ajouter une page à la collection de pages du fichier PDF
doc.Pages.Add();
// Ajouter un fragment de texte à la collection de paragraphes de l'objet de page
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
// Créer un objet JavaScript pour définir la date d'expiration du PDF
JavascriptAction javaScript = new JavascriptAction(
"var year=2017;"
+ "var month=5;"
+ "today = new Date(); today = new Date(today.getFullYear(), today.getMonth());"
+ "expiry = new Date(year, month);"
+ "if (today.getTime() > expiry.getTime())"
+ "app.alert('The file is expired. You need a new one.');");
// Définir JavaScript comme action d'ouverture de PDF
doc.OpenAction = javaScript;

dataDir = dataDir + "SetExpiryDate_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);
```

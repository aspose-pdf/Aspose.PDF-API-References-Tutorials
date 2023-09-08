---
title: Définir la date d'expiration dans le fichier PDF
linktitle: Définir la date d'expiration dans le fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment définir la date d'expiration dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec ce guide étape par étape.
type: docs
weight: 300
url: /fr/net/programming-with-document/setexpirydate/
---
Aspose.PDF pour .NET est une bibliothèque puissante qui fournit diverses fonctionnalités pour travailler avec des fichiers PDF. L'une de ces fonctionnalités est la possibilité de définir une date d'expiration pour un document PDF. Dans ce didacticiel, nous vous guiderons tout au long du processus de définition d'une date d'expiration pour un document PDF à l'aide d'Aspose.PDF pour .NET. 

## Étape 1 : Définir le chemin d'accès au répertoire de documents

Avant de commencer, nous devons définir le chemin d’accès au répertoire où se trouve notre document PDF. Nous stockerons ce chemin dans une variable appelée "dataDir".

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Création d'un nouveau document PDF

 Pour créer un nouveau document PDF, nous devons instancier un nouveau`Aspose.Pdf.Document` objet. Nous pouvons le faire en utilisant le code suivant :

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Étape 3 : Ajout d'une nouvelle page au document PDF

Une fois que nous avons créé le document PDF, nous pouvons y ajouter une nouvelle page. Nous pouvons le faire en utilisant le code suivant :

```csharp
doc.Pages.Add();
```

## Étape 4 : Ajout de texte au document PDF

Après avoir ajouté une page au document PDF, nous pouvons y ajouter du texte en utilisant le`Paragraphs` collection. Nous pouvons le faire en utilisant le code suivant :

```csharp
doc.Pages[1].Paragraphs.Add(new TextFragment("Hello World..."));
```

## Étape 5 : Définition de la date d'expiration du PDF à l'aide de JavaScript

Pour définir la date d'expiration du PDF, nous devons créer un objet JavaScript. Nous pouvons le faire en utilisant le code suivant :

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

 Après avoir défini la date d'expiration, vous devez enregistrer le fichier PDF. Pour ce faire, vous pouvez utiliser le`Save` méthode du`Document` objet et transmettez le chemin vers l'endroit où vous souhaitez enregistrer le fichier PDF mis à jour.

```csharp
dataDir = dataDir + "SetExpiryDate_out.pdf";
// Enregistrer le document PDF
doc.Save(dataDir);
```

### Exemple de code source pour définir la date d'expiration à l'aide d'Aspose.PDF pour .NET

Voici l'exemple complet de code source pour définir la date d'expiration à l'aide d'Aspose.PDF pour .NET :

```csharp
// Le chemin d'accès au répertoire des documents.
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

## Conclusion

Définir une date d'expiration pour un document PDF à l'aide d'Aspose.PDF pour .NET est une fonctionnalité utile pour garantir que le document n'est valide que pour une période spécifiée. En suivant le guide étape par étape et en utilisant le code source C# fourni, les développeurs peuvent facilement définir la date d'expiration et créer des PDF avec une validité limitée dans le temps. Cette fonctionnalité peut être particulièrement utile pour les documents qui doivent être consultés ou distribués pendant une durée limitée.

### FAQ pour définir la date d'expiration dans un fichier PDF

#### Q : Puis-je définir une date d'expiration différente pour le document PDF ?

 R : Oui, vous pouvez définir une date d'expiration différente pour le document PDF en modifiant le code JavaScript à l'étape 5. Dans l'exemple fourni, la date d'expiration est définie sur mai 2017. Pour définir une date d'expiration différente, vous devez modifier le`year` et`month` variables dans le code JavaScript à l’année et au mois souhaités.

#### Q : Que se passe-t-il lorsque le document PDF a expiré ?

R : Lorsque le document PDF a expiré, comme spécifié dans le code JavaScript, la visionneuse affichera un message d'alerte indiquant que le fichier est expiré et que l'utilisateur en a besoin d'un nouveau. Ce message d'alerte s'affichera à l'ouverture du PDF.

#### Q : Puis-je utiliser une heure spécifique pour la date d'expiration au lieu de simplement la date ?

 R : Oui, vous pouvez définir une heure spécifique pour la date d'expiration dans le code JavaScript. En modifiant le`expiry` variable dans le code JavaScript pour inclure l'heure souhaitée, vous pouvez définir une heure spécifique pour la date d'expiration.
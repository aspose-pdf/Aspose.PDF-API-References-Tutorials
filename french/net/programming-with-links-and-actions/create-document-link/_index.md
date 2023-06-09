---
title: Créer un lien de document
linktitle: Créer un lien de document
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement des liens vers d'autres documents PDF avec Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/programming-with-links-and-actions/create-document-link/
---

La création d'un lien vers un autre document dans un fichier PDF vous permet de créer des liens cliquables qui redirigent les utilisateurs vers d'autres documents PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement créer de tels liens en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF auquel vous souhaitez ajouter un lien vers un autre document. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

Nous allons maintenant ouvrir le document PDF auquel nous voulons ajouter le lien vers un autre document en utilisant le code suivant :

```csharp
Document document = new Document(dataDir + "CreateDocumentLink.pdf");
```

## Étape 4 : Créer le lien vers un autre document

 Dans cette étape, nous allons créer le lien vers un autre document en utilisant le`LinkAnnotation` annotation. Nous préciserons les coordonnées et la zone du lien, ainsi que l'action de navigation vers un document externe. Voici le code correspondant :

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link. Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
```

## Étape 5 : Enregistrez le fichier mis à jour

Maintenant, enregistrons le fichier PDF mis à jour en utilisant le`Save` méthode de la`document` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "CreateDocumentLink_out.pdf";
document. Save(dataDir);
```

### Exemple de code source pour créer un lien de document à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir+ "CreateDocumentLink.pdf");
// Créer un lien
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
link.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
link.Action = new GoToRemoteAction(dataDir + "RemoveOpenAction.pdf", 1);
page.Annotations.Add(link);
dataDir = dataDir + "CreateDocumentLink_out.pdf";
// Enregistrer le document mis à jour
document.Save(dataDir);
Console.WriteLine("\nDocument link created successfully.\nFile saved at " + dataDir);            
```

## Conclusion

Félicitation ! Vous disposez maintenant d'un guide étape par étape pour créer des liens vers d'autres documents avec Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour créer des liens cliquables dans vos fichiers PDF, redirigeant les utilisateurs vers d'autres documents.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées des liens interactifs.
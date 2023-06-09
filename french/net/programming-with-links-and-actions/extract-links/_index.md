---
title: Extraire les liens
linktitle: Extraire les liens
second_title: Référence de l'API Aspose.PDF pour .NET
description: Extrayez facilement les liens d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-links-and-actions/extract-links/
---

L'extraction de liens d'un document PDF permet de récupérer tous les liens hypertextes présents dans le document. Avec Aspose.PDF pour .NET, vous pouvez facilement extraire ces liens en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier contenant le fichier PDF dont vous souhaitez extraire les liens. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Ouvrez le document PDF

 Nous allons ouvrir le document PDF en utilisant le`Document` classe. Voici le code correspondant :

```csharp
Document document = new Document(dataDir + "ExtractLinks.pdf");
```

## Étape 4 : Extraire les liens

 Dans cette étape, nous allons extraire les liens présents dans le document PDF en utilisant le`AnnotationSelector` classe. Voici le code correspondant :

```csharp
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page. Accept(selector);
IList<Annotation> list = selector. Selected;
Annotation annotation = (Annotation)list[0];
```

## Étape 5 : Enregistrer le document mis à jour

Maintenant, enregistrons le fichier PDF mis à jour en utilisant le`Save` méthode de la`document` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "ExtractLinks_out.pdf";
document. Save(dataDir);
```

### Exemple de code source pour les liens d'extraction à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document document = new Document(dataDir+ "ExtractLinks.pdf");
// Actions d'extraction
Page page = document.Pages[1];
AnnotationSelector selector = new AnnotationSelector(new LinkAnnotation(page, Aspose.Pdf.Rectangle.Trivial));
page.Accept(selector);
IList<Annotation> list = selector.Selected;
Annotation annotation = (Annotation)list[0];
dataDir = dataDir + "ExtractLinks_out.pdf";
// Enregistrer le document mis à jour
document.Save(dataDir);
Console.WriteLine("\nLinks extracted successfully.\nFile saved at " + dataDir);
```

## Conclusion

Félicitation ! Vous disposez maintenant d'un guide étape par étape pour extraire les liens d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour récupérer tous les liens hypertextes présents dans le document.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées d'extraction de liens.
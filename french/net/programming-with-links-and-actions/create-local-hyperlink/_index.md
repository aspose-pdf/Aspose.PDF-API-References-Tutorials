---
title: Créer un lien hypertexte local
linktitle: Créer un lien hypertexte local
second_title: Référence de l'API Aspose.PDF pour .NET
description: Créez facilement des hyperliens locaux dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-links-and-actions/create-local-hyperlink/
---

La création d'hyperliens locaux dans un fichier PDF vous permet de créer des liens cliquables qui dirigent les utilisateurs vers d'autres pages du même document PDF. Avec Aspose.PDF pour .NET, vous pouvez facilement créer de tels liens en suivant le code source suivant :

## Étape 1 : Importer les bibliothèques requises

Avant de commencer, vous devez importer les bibliothèques nécessaires pour votre projet C#. Voici la directive d'importation nécessaire :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## Étape 2 : Définir le chemin d'accès au dossier de documents

 Dans cette étape, vous devez spécifier le chemin d'accès au dossier dans lequel vous souhaitez enregistrer le fichier PDF résultant. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code suivant avec le chemin d'accès réel à votre dossier de documents :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 3 : Créer une instance de Document

 Nous allons créer une instance de`Document` classe pour représenter notre document PDF. Voici le code correspondant :

```csharp
Document doc = new Document();
```

## Étape 4 : Ajouter une page et du texte avec des hyperliens

Dans cette étape, nous allons ajouter une page à notre document PDF et ajouter du texte contenant des hyperliens locaux. Nous définirons les pages cibles pour chaque lien. Voici le code correspondant :

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## Étape 5 : Enregistrer le document mis à jour

Maintenant, enregistrons le fichier PDF mis à jour en utilisant le`Save` méthode de la`doc` objet. Voici le code correspondant :

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour créer un lien hypertexte local à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Créer une instance de document
Document doc = new Document();
// Ajouter une page à la collection de pages du fichier PDF
Page page = doc.Pages.Add();
// Créer une instance de fragment de texte
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
// Créer une instance de lien hypertexte local
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
// Définir la page cible pour l'instance de lien
link.TargetPageNumber = 7;
// Définir le lien hypertexte TextFragment
text.Hyperlink = link;
// Ajouter du texte à la collection de paragraphes de la page
page.Paragraphs.Add(text);
// Créer une nouvelle instance de TextFragment
text = new TextFragment("link page number test to page 1");
// TextFragment doit être ajouté sur la nouvelle page
text.IsInNewPage = true;
// Créer une autre instance de lien hypertexte local
link = new LocalHyperlink();
// Définir la page cible pour le deuxième lien hypertexte
link.TargetPageNumber = 1;
// Définir le lien pour le deuxième TextFragment
text.Hyperlink = link;
// Ajouter du texte à la collection de paragraphes de l'objet de page
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
// Enregistrer le document mis à jour
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## Conclusion

Félicitation ! Vous disposez maintenant d'un guide étape par étape pour créer des hyperliens locaux dans un PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ce code pour créer des liens cliquables qui dirigent les utilisateurs vers d'autres pages du même document.

Assurez-vous de consulter la documentation officielle Aspose.PDF pour plus d'informations sur les fonctionnalités avancées d'hyperliens.
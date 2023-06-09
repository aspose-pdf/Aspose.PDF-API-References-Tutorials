---
title: EPUB en PDF
linktitle: EPUB en PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir EPUB en PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 30
url: /fr/net/document-conversion/epub-to-pdf/
---

Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un fichier EPUB en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. EPUB (Electronic Publication) est un format largement utilisé pour les livres électroniques, tandis que PDF (Portable Document Format) est une norme d'échange de documents. En suivant les étapes ci-dessous, vous pourrez convertir des fichiers EPUB au format PDF sans effort.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Téléchargez le fichier EPUB
À cette étape, nous allons télécharger le fichier EPUB en utilisant Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instanciez l'objet LoadOption à l'aide de l'option de chargement EPUB
EpubLoadOptions epubload = new EpubLoadOptions();

// Créer un objet Document
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier EPUB.

## Étape 2 : conversion EPUB en PDF
Maintenant que nous avons téléchargé le fichier EPUB, nous pouvons procéder à la conversion en PDF. Utilisez le code suivant :

```csharp
// Enregistrez le document PDF résultant
pdf. Save(dataDir + "EPUBToPDF_out.pdf");
```

 Le code ci-dessus convertit le fichier EP EPUB chargé au format PDF et l'enregistre sous le nom de fichier`"EPUBToPDF_out.pdf"`. Assurez-vous de fournir le chemin d'accès et le nom de fichier corrects pour le fichier PDF de sortie.


 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire souhaité dans lequel vous souhaitez enregistrer le fichier PDF de sortie.

### Exemple de code source pour EPUB en PDF en utilisant Aspose.PDF pour .NET

```csharp
try
{
	
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Instancier l'objet LoadOption à l'aide de l'option de chargement EPUB
	EpubLoadOptions epubload = new EpubLoadOptions();

	// Créer un objet Document
	Aspose.Pdf.Document pdf = new Aspose.Pdf.Document(dataDir + "EPUBToPDF.epub", epubload);

	// Enregistrez le document PDF résultant
	pdf.Save(dataDir + "EPUBToPDF_out.pdf");
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}

```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'un fichier EPUB en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant pouvoir convertir des fichiers EPUB au format PDF sans effort. Cette conversion ouvre des possibilités de partage, d'impression et d'archivage de vos documents.


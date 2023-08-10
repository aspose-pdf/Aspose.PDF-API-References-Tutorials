---
title: XPS vers PDF
linktitle: XPS vers PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un fichier XPS en PDF avec Aspose.PDF pour .NET.
type: docs
weight: 350
url: /fr/net/document-conversion/xps-to-pdf/
---
Dans ce didacticiel, nous vous expliquerons comment convertir un fichier XPS en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET, étape par étape. Nous détaillerons le code source C# fourni et vous montrerons comment l'implémenter dans vos propres projets. À la fin de ce didacticiel, vous serez en mesure de convertir facilement des fichiers XPS en documents PDF.

## Étape 1 : Définir le répertoire des documents
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin où vous avez enregistré vos fichiers.

## Étape 2 : instancier l'objet LoadOptions à l'aide des options de chargement XPS
```csharp
Aspose.Pdf.LoadOptions options = new XpsLoadOptions();
```
Créez une instance de l'objet LoadOptions à l'aide des options de chargement XPS.

## Étape 3 : créer l'objet document
```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);
```
Créez un objet Document en spécifiant le fichier XPS d'entrée et les options de chargement.

## Étape 4 : Enregistrer le document PDF résultant
```csharp
document.Save(dataDir + "XPSToPDF_out.pdf");
```
Enregistrez le document PDF résultant dans le répertoire spécifié.

### Exemple de code source pour XPS en PDF en utilisant Aspose.PDF pour .NET

```csharp
try
{
	
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	//Instancier l'objet LoadOption à l'aide de l'option de chargement XPS
	Aspose.Pdf.LoadOptions options = new XpsLoadOptions();

	// Créer un objet document
	Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "XPSToPDF.xps", options);

	// Enregistrez le document PDF résultant
	document.Save(dataDir + "XPSToPDF_out.pdf");
	
}
catch(Exception ex)
   
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
Dans ce didacticiel, nous avons appris à convertir un fichier XPS en PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant les étapes fournies, vous pouvez facilement effectuer cette conversion dans vos propres applications. Obtenez des résultats précis et professionnels lors de la conversion de fichiers XPS en PDF.

### FAQ

#### Q : Qu'est-ce que XPS et pourquoi voudrais-je le convertir en PDF ?

R : XPS (XML Paper Specification) est un format de document à mise en page fixe développé par Microsoft. La conversion de XPS en PDF vous permet de rendre le document plus accessible et largement compatible, car le PDF est un format universellement pris en charge sur différentes plateformes et appareils.

#### Q : La bibliothèque Aspose.PDF prend-elle en charge d'autres formats de fichiers que XPS ?

R : Oui, Aspose.PDF pour .NET prend en charge divers autres formats de fichiers pour la conversion, tels que HTML, EPUB, SVG, XML, etc. Il vous permet également de créer et de manipuler des documents PDF par programme.

#### Q : Puis-je personnaliser le processus de conversion PDF, par exemple en définissant la taille de la page, les marges ou d'autres options ?

R : Oui, vous pouvez personnaliser le processus de conversion PDF en utilisant Aspose.PDF pour .NET. La bibliothèque fournit une large gamme d'options pour contrôler la taille de la page, les marges, la compression d'image, l'incorporation de polices et d'autres paramètres liés au PDF pour répondre à vos besoins spécifiques.

#### Q : Existe-t-il une version d'évaluation d'Aspose.PDF pour .NET disponible pour les tests ?

R : Oui, vous pouvez télécharger et essayer la version d'essai d'Aspose.PDF pour .NET à partir du site Web officiel d'Aspose. La version d'essai vous permet d'explorer les fonctionnalités de la bibliothèque avant d'effectuer un achat.

#### Q : Puis-je convertir plusieurs fichiers XPS en PDF dans un processus par lots ?

R : Oui, vous pouvez convertir plusieurs fichiers XPS en PDF dans un processus par lots en implémentant une boucle ou en parcourant la liste des fichiers XPS et en convertissant chaque fichier en PDF à l'aide du code fourni.
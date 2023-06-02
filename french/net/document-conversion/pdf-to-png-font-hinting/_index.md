---
title: Indice de police PDF vers PNG
linktitle: Indice de police PDF vers PNG
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour convertir un PDF en PNG avec un indice de police à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 160
url: /fr/net/document-conversion/pdf-to-png-font-hinting/
---

Dans ce didacticiel, nous vous expliquerons le processus de conversion d'un fichier PDF en images PNG à l'aide d'Aspose.PDF pour .NET, tout en activant l'indication de police. Le conseil de police est une technique qui améliore la lisibilité des petites polices. En suivant les étapes ci-dessous, vous pourrez convertir chaque page du PDF en une image PNG avec un indice de police.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Ouverture du document PDF source
Dans cette étape, nous allons ouvrir le fichier PDF source en utilisant Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Activer l'indication de police
Après avoir ouvert le fichier PDF, nous activerons l'indication de police à l'aide des options de rendu. Utilisez le code suivant :

```csharp
// Créer des options de rendu pour activer l'indication de police
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Étape 3 : convertir en images PNG
Nous allons maintenant convertir chaque page du PDF en une image PNG avec un indice de police. Utilisez le code suivant :

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Créer un objet PNGDevice avec les attributs spécifiés
         // Largeur, Hauteur, Résolution, Qualité
         // Qualité [0-100], 100 est le maximum
         // Créer un objet Résolution
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Définir des options de rendu prédéfinies
         pngDevice.RenderingOptions = opts;

         // Convertir une page spécifique et enregistrer l'image dans le flux
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Fermer le flux
         imageStream.Close();
     }
}
```

Le code ci-dessus convertit chaque page du PDF en une image PNG avec un indice de police et enregistre chaque image dans un fichier PNG séparé.

### Exemple de code source pour PDF vers PNGFont Hinting utilisant Aspose.Words pour .NET

```csharp
try
{
	
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ouvrir le document
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Créer Aspose.Pdf.RenderingOptions pour activer l'indication de police
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// Créer un périphérique PNG avec des attributs spécifiés
			// Largeur, Hauteur, Résolution, Qualité
			// Qualité [0-100], 100 est maximum
			// Créer un objet de résolution
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// Définir des options de rendu prédéfinies
			pngDevice.RenderingOptions = opts;

			// Convertir une page particulière et enregistrer l'image à diffuser
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			// Fermer le flux
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'images PDF en images PNG avec indication de police à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de convertir chaque page du PDF en une image PNG avec un indice de police. Cette fonctionnalité est utile lorsque vous souhaitez conserver la lisibilité des petites polices lors de la conversion en images PNG.
---
title: Indice de police PDF vers PNG
linktitle: Indice de police PDF vers PNG
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour convertir un PDF en PNG avec des indications de police à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 160
url: /fr/net/document-conversion/pdf-to-png-font-hinting/
---
Dans ce didacticiel, nous vous guiderons tout au long du processus de conversion d'un PDF en images PNG à l'aide d'Aspose.PDF pour .NET, tout en activant les indications de police. L’indication de polices est une technique qui améliore la lisibilité des petites polices. En suivant les étapes ci-dessous, vous pourrez convertir chaque page du PDF en image PNG avec des indications de police.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Ouverture du document PDF source
Dans cette étape, nous ouvrirons le fichier PDF source à l'aide d'Aspose.PDF pour .NET. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouve votre fichier PDF.

## Étape 2 : Activer l'indication de police
Après avoir ouvert le fichier PDF, nous activerons l’indication de police à l’aide des options de rendu. Utilisez le code suivant :

```csharp
// Créer des options de rendu pour activer les indications de police
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## Étape 3 : Convertir en images PNG
Nous allons maintenant convertir chaque page du PDF en une image PNG avec des indications de police. Utilisez le code suivant :

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Créer un objet PNGDevice avec les attributs spécifiés
         // Largeur, hauteur, résolution, qualité
         // Qualité [0-100], 100 est le maximum
         // Créer un objet Résolution
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         // Définir des options de rendu prédéfinies
         pngDevice.RenderingOptions = opts;

         // Convertissez une page spécifique et enregistrez l'image dans le flux
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         // Fermer le flux
         imageStream.Close();
     }
}
```

Le code ci-dessus convertit chaque page du PDF en une image PNG avec des indications de police et enregistre chaque image dans un fichier PNG distinct.

### Exemple de code source pour PDF vers PNGFont Hinting à l'aide d'Aspose.PDF pour .NET

```csharp
try
{
	
	// Le chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ouvrir le document
	Document pdfDocument = new Document(dataDir + "input.pdf");
	// Créez Aspose.Pdf.RenderingOptions pour activer les indications de police
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			// Créer un périphérique PNG avec les attributs spécifiés
			// Largeur, hauteur, résolution, qualité
			// Qualité [0-100], 100 est maximum
			// Créer un objet Résolution
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			// Définir des options de rendu prédéfinies
			pngDevice.RenderingOptions = opts;

			//Convertissez une page particulière et enregistrez l'image pour diffuser
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
Dans ce didacticiel, nous avons couvert le processus étape par étape de conversion d'images PDF en PNG avec des indications de police à l'aide d'Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant pouvoir convertir chaque page du PDF en une image PNG avec des indications de police. Cette fonctionnalité est utile lorsque vous souhaitez conserver la lisibilité des petites polices lors de la conversion en images PNG.

### FAQ

#### Q : Qu'est-ce que l'indication de police et pourquoi est-elle importante lors de la conversion d'un PDF en PNG ?

R : Les indices de police sont une technique utilisée pour améliorer la lisibilité des petites polices en ajustant leur forme et leur positionnement. Lors de la conversion d'images PDF en images PNG, l'activation de l'indication de police garantit que le texte des images PNG résultantes reste lisible et clair, en particulier pour les petites tailles de police. Ceci est important pour maintenir la qualité et la lisibilité du texte lors de la conversion de documents PDF en images.

#### Q : Comment les indications de police affectent-elles le processus de conversion PNG ?

R : Les indications de police affectent la façon dont le texte est rendu dans les images PNG résultantes pendant le processus de conversion PDF en PNG. En activant les indications de police, la bibliothèque Aspose.PDF ajuste le rendu des polices pour garantir que les petites polices conservent leur clarté et leur lisibilité, rendant les images PNG plus attrayantes et lisibles.

#### Q : Puis-je ajuster les paramètres d’indication de police pour personnaliser la conversion PNG ?

 R : Oui, la bibliothèque Aspose.PDF pour .NET propose des options pour personnaliser le processus de conversion PNG, y compris les paramètres d'indication de police. Dans l'exemple de code fourni, le`UseFontHinting` propriété du`RenderingOptions` l'objet est défini sur`true` pour activer l'indication de police. Vous pouvez affiner davantage le processus de conversion en ajustant d'autres propriétés dans le`RenderingOptions` classe selon vos besoins.

#### Q : Comment les images PNG sont-elles enregistrées lors du processus de conversion PNG ?

R : Dans l'exemple de code fourni, chaque page du document PDF est convertie en une image PNG distincte. Les images PNG sont enregistrées sous forme de fichiers individuels avec des noms de fichiers suivant le modèle "image{pageCount}_ out.png", où`{pageCount}` est le numéro de la page en cours de conversion. Chaque image PNG représente une page du document PDF original.
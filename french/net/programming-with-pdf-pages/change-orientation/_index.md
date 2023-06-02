---
title: Changer d'orientation
linktitle: Changer d'orientation
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour changer l'orientation de la page d'un PDF avec Aspose.PDF pour .NET. Facile à suivre et à mettre en œuvre dans vos projets.
type: docs
weight: 10
url: /fr/net/programming-with-pdf-pages/change-orientation/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le processus de modification de l'orientation de la page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous saurez comment modifier l'orientation de la page de vos documents PDF à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d'abord, vous devez définir le chemin d'accès à votre répertoire de documents. Il s'agit de l'emplacement où se trouve votre fichier PDF d'entrée et où vous souhaitez enregistrer votre fichier PDF de sortie modifié. Remplacez "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Chargez le document PDF
 Ensuite, vous pouvez charger le document PDF à partir du fichier d'entrée à l'aide de la`Document` classe de Aspose.PDF. Assurez-vous de spécifier le chemin d'accès correct au fichier PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 3 : Modifier l'orientation de la page
Nous allons maintenant parcourir chaque page du document et changer son orientation. Pour chaque page, nous modifions les dimensions de la boîte média (`MediaBox`) en échangeant la largeur et la hauteur, puis nous ajustons les coordonnées de la boîte média pour maintenir la position de la page. Enfin, nous définissons la rotation de la page à 90 degrés.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Étape 4 : Enregistrez le document PDF modifié
 Enfin, vous pouvez enregistrer le document PDF modifié dans un fichier de sortie à l'aide de la`Save()` méthode de la`Document` classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour le changement d'orientation à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Nous devons déplacer la page vers le haut afin de compenser la modification de la taille de la page
	// (le bord inférieur de la page est 0,0 et les informations sont généralement placées à partir du
	// Haut de la page. C'est pourquoi nous déplaçons le bord de l'amant vers le haut sur la différence entre
	// Hauteur ancienne et nouvelle.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Parfois, nous devons également définir CropBox (s'il a été défini dans le fichier d'origine)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Réglage de l'angle de rotation de la page
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Enregistrer le fichier de sortie
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Conclusion
Dans ce didacticiel, nous avons appris à modifier l'orientation de la page d'un document PDF à l'aide d'Aspose.PDF pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez facilement implémenter cette fonctionnalité dans vos propres projets. N'hésitez pas à explorer davantage la documentation Aspose.PDF pour découvrir d'autres fonctionnalités utiles pour travailler avec des fichiers PDF.
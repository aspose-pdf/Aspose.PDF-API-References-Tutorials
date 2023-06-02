---
title: Orientation de la page selon les dimensions de l'image
linktitle: Orientation de la page selon les dimensions de l'image
second_title: Référence de l'API Aspose.PDF pour .NET
description: Guide étape par étape pour définir l'orientation de la page en fonction des dimensions de l'image avec Aspose.PDF pour .NET.
type: docs
weight: 80
url: /fr/net/document-conversion/page-orientation-according-image-dimensions/
---

Dans ce didacticiel, nous vous expliquerons le processus de définition de l'orientation de la page en fonction des dimensions d'une image à l'aide de Aspose.PDF pour .NET. Nous parcourrons une liste d'images JPG dans un répertoire donné et ajusterons automatiquement l'orientation de la page en fonction de la largeur de chaque image. Suivez les étapes ci-dessous pour y parvenir.

## Conditions préalables
Avant de commencer, assurez-vous de remplir les conditions préalables suivantes :

- Connaissance de base du langage de programmation C#.
- Bibliothèque Aspose.PDF pour .NET installée sur votre système.
- Un environnement de développement tel que Visual Studio.

## Étape 1 : Parcourir les images JPG
A cette étape, nous allons parcourir toutes les images JPG dans un répertoire donné. Suivez le code ci-dessous :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Créer un nouveau document PDF
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//Récupérer les noms de tous les fichiers JPG dans un répertoire particulier
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire réel où se trouvent vos images JPG.

## Etape 2 : Création de la page et de l'image
Après avoir parcouru les fichiers JPG, nous allons créer une page et une image pour chaque fichier. Utilisez le code suivant :

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
// Créer un objet Page
Aspose.Pdf.Page page = doc.Pages.Add();

// Créer un objet Image
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## Étape 3 : Vérification des dimensions de l'image
Vérifions maintenant les dimensions de chaque image pour déterminer l'orientation de la page. Utilisez le code suivant :

```csharp
// Créer un objet BitMap pour obtenir des informations à partir du fichier image
Bitmap myimage = new Bitmap(fileEntries[counter]);

// Vérifiez si la largeur de l'image est supérieure à la largeur de la page ou non
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
// Si la largeur de l'image est inférieure à la largeur de la page, définissez l'orientation de la page sur portrait
page.PageInfo.IsLandscape = false;
```

## Étape 4 : Ajouter l'image au document PDF
Après avoir vérifié les dimensions de l'image, nous ajouterons l'image à la collection de paragraphes du document PDF. Utilisez le code suivant :

```csharp
//Ajouter l'image à la collection de paragraphes du document PDF
page.Paragraphs.Add(image1);
```

## Étape 5 : Enregistrer le fichier PDF
Une fois que nous avons ajouté toutes les images au document PDF, nous pouvons maintenant enregistrer le fichier PDF résultant. Voici la dernière étape :

```csharp
// Enregistrez le fichier PDF
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le répertoire souhaité dans lequel vous souhaitez enregistrer le fichier PDF de sortie.

### Exemple de code source pour l'orientation de la page en fonction des dimensions de l'image à l'aide de Aspose.Words pour .NET

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// Récupérer les noms de tous les fichiers JPG dans un répertoire particulier
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	// Créer un objet de page
	Aspose.Pdf.Page page = doc.Pages.Add();

	// Créer un objet image
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	// Créer un objet BitMap afin d'obtenir les informations du fichier image
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	// Vérifiez si la largeur du fichier image est supérieure à la largeur de la page ou non
	if (myimage.Width > page.PageInfo.Width)
		// Si la largeur de l'image est supérieure à la largeur de la page, définissez l'orientation de la page sur Paysage
		page.PageInfo.IsLandscape = true;
	else
		// Si la largeur de l'image est inférieure à la largeur de la page, définissez l'orientation de la page sur Portrait
		page.PageInfo.IsLandscape = false;
	// Ajouter l'image à la collection de paragraphes du document PDF
	page.Paragraphs.Add(image1);
}
// Enregistrez le fichier Pdf
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## Conclusion
Dans ce didacticiel, nous avons couvert le processus étape par étape de définition de l'orientation de la page en fonction des dimensions d'une image à l'aide de Aspose.PDF pour .NET. En suivant les instructions décrites ci-dessus, vous devriez maintenant être en mesure de créer un document PDF avec l'orientation de page correcte pour chaque image. Cette fonctionnalité est utile lorsque vous avez des images de tailles différentes et que vous souhaitez les intégrer dans un document PDF.
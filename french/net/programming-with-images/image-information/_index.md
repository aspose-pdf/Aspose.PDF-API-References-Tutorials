---
title: Informations sur les images
linktitle: Informations sur les images
second_title: Référence de l'API Aspose.PDF pour .NET
description: Extrayez les informations d'image dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 160
url: /fr/net/programming-with-images/image-information/
---

Ce guide vous expliquera étape par étape comment extraire des informations sur les images dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Assurez-vous de définir le répertoire de documents correct. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le fichier PDF source

 Dans cette étape, nous allons charger le fichier PDF source en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Étape 3 : Définir la résolution par défaut

Dans cette étape, nous allons définir la résolution par défaut des images. Dans l'exemple, la résolution par défaut est définie sur 72.

```csharp
int defaultResolution = 72;
```

## Étape 4 : Initialiser les objets et les compteurs

Dans cette étape, nous allons initialiser les objets et les compteurs nécessaires pour récupérer les informations de l'image.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Étape 5 : Parcourir les opérateurs sur la première page du document

Dans cette étape, nous allons parcourir les opérateurs sur la première page du document pour identifier les opérations liées à l'image.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Étape 6 : Gérer les opérateurs et extraire les informations d'image

Dans cette étape, nous allons gérer les différents types d'opérateurs et extraire les informations sur les images.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//Gérer les opérations GSave et GRestore pour les transformations
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// Gérer l'opération ConcatenateMatrix pour les transformations
else if (opCtm != null)
{
     // Appliquer la matrice de transformation
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// Gérer l'opération Do pour les images
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // Récupérer l'image
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // Récupérer les dimensions de l'image
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // Calculez la résolution en fonction des informations ci-dessus
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // Afficher les informations sur l'image
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### Exemple de code source pour les informations d'image à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le fichier PDF source
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Définir la résolution par défaut de l'image
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Définissez un objet de liste de tableau qui contiendra les noms d'image
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Insérer un objet à empiler
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Obtenir tous les opérateurs sur la première page du document
foreach (Operator op in doc.Pages[1].Contents)
{
	// Utilisez les opérateurs GSave/GRestore pour rétablir les transformations définies précédemment
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Instanciez l'objet ConcatenateMatrix tel qu'il définit la matrice de transformation actuelle.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Créer un opérateur Do qui dessine des objets à partir de ressources. Il dessine des objets Form et des objets Image
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Enregistrer l'état précédent et pousser l'état actuel vers le haut de la pile
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Jeter l'état actuel et restaurer le précédent
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// Multiplier la matrice actuelle avec la matrice d'état
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Dans le cas où il s'agit d'un opérateur de dessin d'image
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Créer un objet XImage pour contenir les images de la première page pdf
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// Obtenir les dimensions de l'image
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// Obtenir des informations sur la hauteur et la largeur de l'image
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// Calculer la résolution en fonction des informations ci-dessus
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// Afficher les informations de dimension et de résolution de chaque image
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## Conclusion

Félicitation ! Vous avez maintenant appris à extraire des informations d'image dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez utiliser ces informations pour diverses tâches de traitement d'image dans vos applications.
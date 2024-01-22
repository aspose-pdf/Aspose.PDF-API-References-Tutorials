---
title: Informations sur l'image dans le fichier PDF
linktitle: Informations sur l'image dans le fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Extrayez les informations de l'image dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 160
url: /fr/net/programming-with-images/image-information/
---
Ce guide vous expliquera étape par étape comment extraire des informations sur les images dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Assurez-vous de définir le répertoire de documents correct. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Chargez le fichier PDF source

 Dans cette étape, nous allons charger le fichier PDF source à l'aide du`Document` classe d’Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d’accès au document PDF.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## Étape 3 : Définir la résolution par défaut

Dans cette étape, nous définirons la résolution par défaut des images. Dans l'exemple, la résolution par défaut est définie sur 72.

```csharp
int defaultResolution = 72;
```

## Étape 4 : Initialiser les objets et les compteurs

Dans cette étape, nous initialiserons les objets et les compteurs nécessaires pour récupérer les informations de l'image.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## Étape 5 : Parcourez les opérateurs sur la première page du document

Dans cette étape, nous passerons en revue les opérateurs sur la première page du document pour identifier les opérations liées à l'image.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## Étape 6 : Gérer les opérateurs et extraire les informations sur l'image

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

### Exemple de code source pour les informations sur l'image à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le fichier PDF source
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// Définir la résolution par défaut de l'image
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// Définir un objet de liste de tableaux qui contiendra les noms d'images
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// Insérer un objet à empiler
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// Obtenez tous les opérateurs sur la première page du document
foreach (Operator op in doc.Pages[1].Contents)
{
	// Utilisez les opérateurs GSave/GRestore pour rétablir les transformations définies précédemment.
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// Instancier l'objet ConcatenateMatrix car il définit la matrice de transformation actuelle.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// Opérateur Create Do qui dessine des objets à partir de ressources. Il dessine des objets Form et des objets Image
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//Enregistrer l'état précédent et pousser l'état actuel en haut de la pile
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// Supprimer l'état actuel et restaurer le précédent
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
		// Multiplier la matrice actuelle par la matrice d'état
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// Dans le cas où il s'agit d'un opérateur de dessin d'image
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// Créer un objet XImage pour contenir les images de la première page PDF
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
			// Afficher les informations sur les dimensions et la résolution de chaque image
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

### FAQ pour les informations sur les images dans un fichier PDF

#### Q : Quel est le but d'extraire des informations sur l'image d'un document PDF à l'aide d'Aspose.PDF pour .NET ?

R : L'extraction d'informations sur les images d'un document PDF fournit des informations sur les dimensions, la résolution et d'autres attributs des images contenues dans le document. Ces informations peuvent être utilisées pour des tâches de traitement d’image, d’analyse ou d’optimisation.

#### Q : Comment Aspose.PDF pour .NET aide-t-il à extraire les informations d'image d'un document PDF ?

R : Aspose.PDF pour .NET fournit des outils pour accéder et analyser le contenu d'un document PDF, y compris ses images. Le code fourni montre comment extraire et afficher des informations sur l'image à l'aide de divers opérateurs.

#### Q : Quels types d’informations sur les images peuvent être extraites à l’aide de cette méthode ?

R : Cette méthode vous permet d'extraire et d'afficher des informations telles que les dimensions mises à l'échelle, la résolution et les noms d'images dans un document PDF.

#### Q : Comment le code identifie-t-il et traite-t-il les opérateurs liés aux images dans un document PDF ?

R : Le code parcourt les opérateurs sur une page spécifiée du document PDF. Il identifie et traite les opérateurs liés aux opérations, aux transformations et au rendu des images.

#### Q : Quelle est l’importance de la résolution par défaut et comment est-elle utilisée dans le code ?

R : La résolution par défaut est utilisée comme point de référence pour calculer la résolution réelle des images. Le code calcule la résolution de chaque image en fonction de ses dimensions et du paramètre de résolution par défaut.

#### Q : Comment les informations d’image extraites peuvent-elles être utilisées dans des scénarios réels ?

R : Les informations d'image extraites peuvent être utilisées pour des tâches telles que l'évaluation de la qualité de l'image, l'optimisation de l'image, la génération de vignettes d'image et la facilitation des processus de prise de décision liés aux images.

#### Q : Puis-je modifier le code pour extraire des attributs supplémentaires liés à l'image ?

R : Oui, vous pouvez personnaliser le code pour extraire des attributs supplémentaires des images, tels que l'espace colorimétrique, la profondeur de pixels ou le type d'image.

#### Q : Le processus d'extraction des informations sur les images est-il gourmand en ressources ou prend-il du temps ?

R : Le processus d'extraction des informations d'image est efficace et optimisé pour les performances, garantissant un impact minimal sur l'utilisation des ressources et le temps de traitement.

#### Q : Comment les développeurs peuvent-ils bénéficier de l'identification et de l'extraction d'informations sur les images à partir de documents PDF ?

R : Les développeurs peuvent obtenir des informations sur les caractéristiques des images dans les documents PDF, ce qui leur permet de prendre des décisions éclairées concernant la manipulation, le traitement et l'optimisation des images.

#### Q : Cette méthode peut-elle être utilisée pour le traitement par lots de documents PDF contenant des images ?

R : Oui, cette méthode peut être étendue au traitement par lots en parcourant plusieurs pages ou documents, en extrayant des informations sur l'image et en effectuant des tâches liées à l'image.
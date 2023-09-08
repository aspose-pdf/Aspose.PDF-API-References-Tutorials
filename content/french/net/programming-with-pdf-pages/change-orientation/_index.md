---
title: Changer l'orientation
linktitle: Changer l'orientation
second_title: Aspose.PDF pour la référence de l'API .NET
description: Guide étape par étape pour modifier l'orientation de la page d'un PDF avec Aspose.PDF pour .NET. Facile à suivre et à mettre en œuvre dans vos projets.
type: docs
weight: 10
url: /fr/net/programming-with-pdf-pages/change-orientation/
---
Dans ce didacticiel, nous vous guiderons pas à pas à travers le processus permettant de modifier l'orientation de la page d'un document PDF à l'aide d'Aspose.PDF pour .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. A la fin de ce tutoriel, vous saurez comment changer l'orientation de la page de vos documents PDF à l'aide d'Aspose.PDF pour .NET.

## Conditions préalables
Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Une connaissance de base du langage de programmation C#
- Aspose.PDF pour .NET installé dans votre environnement de développement

## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. Il s'agit de l'emplacement où se trouve votre fichier PDF d'entrée et où vous souhaitez enregistrer votre fichier PDF de sortie modifié. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Charger le document PDF
 Ensuite, vous pouvez charger le document PDF à partir du fichier d'entrée en utilisant le`Document` classe d’Aspose.PDF. Assurez-vous de spécifier le chemin correct vers le fichier PDF.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Étape 3 : Modifier l'orientation de la page
Nous allons maintenant parcourir chaque page du document et changer son orientation. Pour chaque page, nous modifions les dimensions de la boîte média (`MediaBox`) en échangeant la largeur et la hauteur, puis nous ajustons les coordonnées de la boîte média pour conserver la position de la page. Enfin, nous définissons la rotation de la page à 90 degrés.

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

## Étape 4 : Enregistrez le document PDF modifié
 Enfin, vous pouvez enregistrer le document PDF modifié dans un fichier de sortie à l'aide du`Save()` méthode du`Document`classe. Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Exemple de code source pour l'orientation du changement à l'aide d'Aspose.PDF pour .NET 

```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Il faut déplacer la page vers le haut afin de compenser le changement de taille de la page
	// (le bord inférieur de la page est 0,0 et les informations sont généralement placées à partir du
	// Haut de la page. C'est pourquoi nous déplaçons le bord amoureux vers le haut en fonction de la différence entre
	// Ancienne et nouvelle hauteur.
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

### FAQ

#### Q : Quel est le but de modifier l’orientation de la page dans un document PDF ?

: Changer l'orientation de la page dans un document PDF vous permet de faire pivoter le contenu de la page de 90 degrés. Cela peut être utile dans les scénarios où le contenu original doit être affiché ou imprimé dans une orientation différente, comme par exemple passer du mode portrait au mode paysage ou vice versa.

#### Q : Puis-je modifier l’orientation de pages spécifiques dans le document PDF ?

 R : Oui, vous pouvez modifier l'orientation de pages spécifiques dans le document PDF. Dans le code source C# fourni, le`foreach` La boucle permet de parcourir chaque page du document et de changer son orientation. Si vous souhaitez uniquement modifier l'orientation de pages spécifiques, vous pouvez modifier la boucle pour cibler ces pages en fonction de leurs numéros de page ou d'autres critères.

#### Q : La modification de l'orientation de la page affecte-t-elle la disposition du contenu sur la page ?

R : Oui, la modification de l'orientation de la page affectera la disposition du contenu sur la page. Le contenu sera pivoté de 90 degrés et la largeur et la hauteur de la page seront inversées. En conséquence, l'emplacement et l'alignement du contenu sur la page peuvent changer.

#### Q : Puis-je faire pivoter la page selon un angle autre que 90 degrés ?

 R : Dans le code source C# fourni, la rotation de la page est définie sur 90 degrés à l'aide de`page.Rotate = Rotate.on90;` . Cependant, vous pouvez modifier l'angle de rotation avec d'autres valeurs si nécessaire. Par exemple, vous pouvez utiliser`Rotate.on180` pour faire pivoter la page de 180 degrés ou`Rotate.on270` pour le faire pivoter de 270 degrés.

#### Q : Comment gérer le contenu de la page qui déborde après un changement d'orientation ?

R : Lorsque vous modifiez l'orientation de la page, les dimensions de la page peuvent changer, ce qui peut entraîner un débordement de contenu. Pour gérer cela, vous devrez peut-être ajuster la mise en page et le formatage du contenu de la page. Vous pouvez utiliser les fonctionnalités fournies par Aspose.PDF pour .NET, telles que le redimensionnement des éléments, l'ajustement des marges ou la réorganisation du contenu, pour garantir que le contenu de la page s'adapte correctement après le changement d'orientation.
---
title: Ajouter une image
linktitle: Ajouter une image
second_title: Référence de l'API Aspose.PDF pour .NET
description: Ajoutez facilement une image à un document PDF en utilisant Aspose.PDF pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-images/add-image/
---

Ce guide vous expliquera étape par étape comment ajouter une image à un document PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le répertoire correct pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre document PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe de Aspose.PDF. Utilisez le`Document` constructeur et transmettez le chemin d'accès au document PDF.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Étape 3 : Définir les coordonnées de l'image

 Définissez les coordonnées de l'image que vous souhaitez ajouter. Les variables`lowerLeftX`, `lowerLeftY`, `upperRightX` et`upperRightY` représentent respectivement les coordonnées du coin inférieur gauche et du coin supérieur droit de l'image.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## Étape 4 : Obtenir la page où l'image doit être ajoutée

Pour ajouter l'image à une page spécifique du document PDF, nous devons d'abord récupérer cette page. Dans cet exemple, nous ajoutons l'image à la deuxième page (index 1) du document.

```csharp
Page page = pdfDocument.Pages[1];
```

## Étape 5 : Charger l'image à partir d'un flux

Nous allons maintenant charger l'image que nous voulons ajouter au document PDF. Cet exemple suppose que vous avez un fichier image nommé`aspose-logo.jpg` dans le même répertoire que votre document. Remplacez le nom du fichier si nécessaire.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## Étape 6 : Ajouter l'image aux ressources de la page

Pour utiliser l'image dans le document PDF, nous devons l'ajouter à la collection d'images de ressources de la page.

```csharp
page.Resources.Images.Add(imageStream);
```

## Étape 7 : Enregistrer l'état actuel des graphiques

 Avant de dessiner l'image, nous devons enregistrer l'état graphique actuel à l'aide de la`GSave` opérateur. Cela garantit que les modifications apportées à l'état des graphiques peuvent être annulées ultérieurement.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## Étape 8 : Créer des objets Rectangle et Matrice

 Nous allons maintenant créer un`Rectangle` objet et un`Matrix` objet. Le rectangle représente la position et la taille de l'image, tandis que la matrice définit comment l'image doit être placée.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## Étape 9 : Concaténer la matrice pour le placement de l'image

 Pour spécifier comment l'image doit être placée dans le rectangle, nous utilisons le`ConcatenateMatrix`opérateur. Cet opérateur définit la matrice de transformation qui mappe l'espace de coordonnées de l'image à l'espace de coordonnées de la page.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## Étape 10 : dessinez l'image

 Dans cette étape, nous allons dessiner l'image sur la page en utilisant le`Do` opérateur. Le`Do` L'opérateur prend le nom de l'image dans les ressources et le dessine sur la page.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## Étape 11 : Restaurer l'état des graphiques

 Après avoir dessiné l'image, nous devons restaurer l'état graphique précédent en utilisant le`GRestore` opérateur.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## Étape 12 : Enregistrer le document mis à jour

 Enfin, nous enregistrerons le document mis à jour dans un nouveau fichier. Mettre à jour le`dataDir` variable avec le répertoire de sortie et le nom de fichier souhaités.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### Exemple de code source pour Ajouter une image à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// Définir les coordonnées
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
// Obtenir la page où l'image doit être ajoutée
Page page = pdfDocument.Pages[1];
// Charger l'image dans le flux
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// Ajouter une image à la collection d'images des ressources de page
page.Resources.Images.Add(imageStream);
// Utilisation de l'opérateur GSave : cet opérateur enregistre l'état actuel des graphiques
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Créer des objets Rectangle et Matrix
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
//Utilisation de l'opérateur ConcatenateMatrix (matrice de concaténation): définit comment l'image doit être placée
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Utilisation de l'opérateur Do : cet opérateur dessine l'image
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// Utilisation de l'opérateur GRestore : cet opérateur restaure l'état graphique
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## Conclusion

Dans ce didacticiel, nous avons appris à ajouter une image à un document PDF à l'aide d'Aspose.PDF pour .NET. Nous avons couvert chaque étape en détail, de l'ouverture du document à l'enregistrement de la version mise à jour. En suivant ce guide, vous devriez maintenant être en mesure d'intégrer des images dans vos fichiers PDF par programmation à l'aide de C# et Aspose.PDF.
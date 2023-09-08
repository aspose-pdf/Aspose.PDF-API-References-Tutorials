---
title: Convertir le flux d'images en fichier PDF
linktitle: Convertir le flux d'images en fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Convertissez facilement un flux d'images en fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 70
url: /fr/net/programming-with-images/convert-image-stream-to-pdf/
---
Ce guide vous expliquera étape par étape comment convertir un flux d'images en fichier PDF à l'aide d'Aspose.PDF pour .NET. Assurez-vous d'avoir déjà configuré votre environnement et suivez les étapes ci-dessous :

## Étape 1 : Définir le répertoire des documents

 Avant de commencer, assurez-vous de définir le bon répertoire pour les documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le code avec le chemin d'accès au répertoire où se trouve votre image.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Instancier un objet Document

 Dans cette étape, nous allons instancier un`Document` objet utilisant le constructeur vide du`Aspose.Pdf.Document` classe.

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## Étape 3 : Ajouter une page au document PDF

 Ajoutez une page au document PDF à l'aide du`Add` méthode du`Pages` objet de`pdf1`.

```csharp
Aspose.Pdf.Page sec = pdf1.Pages.Add();
```

## Étape 4 : Lire le flux d'images

 Dans cette étape, nous allons créer un`FileStream` objet pour lire le fichier image à partir du flux.

```csharp
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
```

## Étape 5 : Lire l'image dans un tableau d'octets

 Lisez l'image du flux et stockez-la dans un tableau d'octets à l'aide du`Read` méthode du`fs` objet.

```csharp
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
```

## Étape 6 : Créer un objet MemoryStream à partir du tableau d'octets

 Créer un`MemoryStream` objet du tableau d’octets contenant l’image.

```csharp
MemoryStream ms = new MemoryStream(data);
```

## Étape 7 : Créer un objet image

 Dans cette étape, nous allons créer un`Image` objet à l'aide du`Aspose.Pdf.Image` classe. Spécifiez le flux de l'image à l'aide du`ImageStream` propriété et passer le`ms` objet que nous avons créé plus tôt.

```csharp
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
imageht. ImageStream = ms;
```

## Étape 8 : ajouter l'objet Image à la collection Paragraphs

 Ajouter le`imageht` s'opposer à la`Paragraphs` collecte des`sec` section.

```csharp
sec.Paragraphs.Add(imageht);
```

## Étape 9 : Enregistrez le document PDF

 Enregistrez le document PDF à l'aide du`Save` méthode du`pdf1` objet. Spécifiez le chemin de sortie du fichier PDF.

```csharp
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
```

## Étape 10 : Fermez l'objet MemoryStream

 Fermer la`ms` objet à l'aide du`Close` méthode pour libérer les ressources.

```csharp
ms. Close();
```

### Exemple de code source pour convertir un flux d'images en PDF à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//Instancier l'instance de document en appelant son constructeur vide
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// Ajouter une page dans le document pdf
Aspose.Pdf.Page sec = pdf1.Pages.Add();
// Créez un objet FileStream pour lire le fichier image
FileStream fs = File.OpenRead(dataDir + "aspose.jpg");
// Lire l'image dans un tableau d'octets
byte[] data = new byte[fs.Length];
fs.Read(data, 0, data.Length);
// Créer un objet MemoryStream à partir d'un tableau d'octets d'image
MemoryStream ms = new MemoryStream(data);
// Créer un objet image
Aspose.Pdf.Image imageht = new Aspose.Pdf.Image();
// Spécifiez la source de l'image comme MemoryStream
imageht.ImageStream = ms;
// Ajouter un objet image dans la collection Paragraphs de la section
sec.Paragraphs.Add(imageht);
// Enregistrez le PDF
pdf1.Save(dataDir + "ConvertMemoryStreamImageToPdf_out.pdf");
// Fermez l'objet MemoryStream
ms.Close();
```

## Conclusion

Félicitation ! Vous avez réussi à convertir un flux d'images en fichier PDF à l'aide d'Aspose.PDF pour .NET. Le fichier PDF généré est enregistré dans le répertoire spécifié. Vous pouvez désormais utiliser ce fichier PDF dans vos projets ou applications.

### FAQ

#### Q : Quel est le but de convertir un flux d'images en fichier PDF à l'aide d'Aspose.PDF pour .NET ?

R : La conversion d'un flux d'images en fichier PDF peut être utile pour incorporer des images dans des documents PDF, créer des PDF basés sur des images ou intégrer des images dans du contenu textuel.

#### Q : Comment Aspose.PDF pour .NET aide-t-il à la conversion d'un flux d'images en fichier PDF ?

R : Aspose.PDF pour .NET fournit un processus pratique et étape par étape pour créer un document PDF, lire un flux d'images et intégrer l'image dans le fichier PDF.

#### Q : Pourquoi la définition du répertoire de documents est-elle importante dans le processus de conversion du flux d'images en PDF ?

R : La spécification du répertoire du document garantit que le flux d'images et le fichier PDF résultant sont correctement situés dans le chemin de sortie souhaité.

#### Q : Comment créer un document PDF à l'aide d'Aspose.PDF pour .NET dans le processus de conversion du flux d'images en PDF ?

 R : Instancier un`Document` objet à l'aide du`Aspose.Pdf.Document` constructeur vide de la classe pour créer le document PDF.

####  Q : Quel est le rôle du`Pages` object in the image stream to PDF conversion process?

 R : Le`Pages` L'objet vous permet d'ajouter des pages au document PDF et de gérer son contenu.

#### Q : Comment le flux d'images est-il lu et traité dans le processus de conversion du flux d'images en PDF ?

 R : Le flux d'images est lu à l'aide d'un`FileStream` objet, et son contenu est stocké dans un tableau d’octets. Le tableau d'octets est ensuite utilisé pour créer un`MemoryStream` objet, qui est ensuite utilisé pour créer un`Image` objet.

#### Q : Comment l'image est-elle intégrée dans le document PDF pendant le processus de conversion ?

 R : Un`Image` l'objet est créé à l'aide du`Aspose.Pdf.Image` classe, et le flux d’images est affecté à la`ImageStream` propriété. Le`Image` l'objet est ensuite ajouté au`Paragraphs` collection du document PDF.

#### Q : Puis-je personnaliser la position, la taille ou d'autres attributs de l'image dans le fichier PDF résultant ?

 R : Oui, vous pouvez modifier la position, la taille et d'autres attributs de l'image en ajustant les propriétés du`Image` objet avant de l'ajouter au`Paragraphs` collection.

#### Q : Quelle est la dernière étape du processus de conversion du flux d’images en PDF ?

 R : Le document PDF est enregistré à l'aide du`Save` méthode du`Document` objet, et le`MemoryStream` l'objet est fermé à l'aide de la`Close` méthode pour libérer des ressources.
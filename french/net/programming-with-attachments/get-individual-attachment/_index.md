---
title: Obtenir une pièce jointe individuelle
linktitle: Obtenir une pièce jointe individuelle
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à obtenir une pièce jointe individuelle dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 60
url: /fr/net/programming-with-attachments/get-individual-attachment/
---
Dans ce didacticiel, nous vous guiderons pas à pas dans le code source C # suivant pour obtenir une pièce jointe individuelle d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

### Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire où se trouve le fichier PDF à partir duquel vous souhaitez obtenir la pièce jointe individuelle. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Étape 2 : Ouvrez le document PDF existant

Nous ouvrons le document PDF existant en utilisant le chemin spécifié.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### Étape 3 : Obtention d'une pièce jointe spécifique

Nous récupérons une pièce jointe spécifique à partir de la collection de pièces jointes du document. Dans cet exemple, nous obtenons la première pièce jointe en utilisant l'index 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Étape 4 : Obtenir les propriétés du fichier

Nous affichons les propriétés des pièces jointes telles que le nom, la description, le type MIME, le hachage de contrôle, la date de création, la date de modification et la taille.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Vérifier si les paramètres d'objet contiennent des informations supplémentaires
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Étape 5 : Récupérez la pièce jointe et enregistrez-la dans un fichier

Nous récupérons le contenu de la pièce jointe et l'enregistrons dans un fichier texte. Dans cet exemple, le fichier est enregistré sous le nom "test_out.txt".

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Exemple de code source pour obtenir une pièce jointe individuelle à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// Obtenir un fichier intégré particulier
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Obtenir les propriétés du fichier
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
// Vérifier si l'objet de paramètre contient les paramètres
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
// Obtenir la pièce jointe et écrire dans un fichier ou un flux
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment obtenir une pièce jointe individuelle à partir d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour extraire et enregistrer les pièces jointes de vos fichiers PDF.

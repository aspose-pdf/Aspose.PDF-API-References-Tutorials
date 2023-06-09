---
title: Obtenir toutes les pièces jointes
linktitle: Obtenir toutes les pièces jointes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à obtenir toutes les pièces jointes d'un fichier PDF avec Aspose.PDF pour .NET. Guide étape par étape pour une manipulation facile.
type: docs
weight: 40
url: /fr/net/programming-with-attachments/get-all-the-attachments/
---
Dans ce didacticiel, nous vous guiderons pas à pas dans le code source C # suivant pour obtenir toutes les pièces jointes d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

### Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire où se trouve le fichier PDF à partir duquel vous souhaitez obtenir les pièces jointes. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Étape 2 : Ouvrez le document PDF existant

Nous ouvrons le document PDF existant en utilisant le chemin spécifié.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Étape 3 : Obtention de la collection de pièces jointes

Nous obtenons la collection de pièces jointes du document.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Étape 4 : Récupération des pièces jointes

Nous parcourons la collection pour obtenir toutes les pièces jointes et afficher leurs informations. Nous enregistrons également les pièces jointes dans des fichiers individuels.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Vérifier si les paramètres d'objet contiennent des informations supplémentaires
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Récupérer la pièce jointe et l'enregistrer dans un fichier
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Exemple de code source pour obtenir toutes les pièces jointes à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Obtenir la collection de fichiers intégrés
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Obtenir le nombre de fichiers intégrés
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Parcourez la collection pour obtenir toutes les pièces jointes
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment obtenir toutes les pièces jointes d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant utiliser ces connaissances pour extraire et manipuler les pièces jointes de vos fichiers PDF.
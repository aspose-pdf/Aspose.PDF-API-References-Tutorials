---
title: Désactiver la compression des fichiers
linktitle: Désactiver la compression des fichiers
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à désactiver la compression de fichier dans un fichier PDF avec Aspose.PDF pour .NET. Guide étape par étape pour une manipulation facile.
type: docs
weight: 30
url: /fr/net/programming-with-attachments/disable-files-compression/
---
Dans ce didacticiel, nous vous expliquerons étape par étape le code source C # suivant pour désactiver la compression de fichiers dans un PDF à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

### Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire où se trouve le fichier PDF que vous souhaitez désactiver la compression de fichier. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Étape 2 : Ouvrez le document PDF existant

Nous ouvrons le document PDF existant en utilisant le chemin spécifié.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Étape 3 : Configuration du nouveau fichier à ajouter en tant que pièce jointe

Nous configurons le nouveau fichier que nous voulons ajouter en pièce jointe. Dans cet exemple, nous ajoutons un fichier texte avec le nom "test_out.txt" et une description "Example text file".

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### Étape 4 : Désactiver la compression de fichiers

Nous désactivons la compression de fichier en définissant la propriété Encoding de l'objet FileSpecification sur FileEncoding.None.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### Étape 5 : Ajout de la pièce jointe à la collection de pièces jointes du document

Nous ajoutons la pièce jointe à la collection de pièces jointes du document.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Étape 6 : Enregistrez le nouveau fichier de sortie

Enfin, nous enregistrons le nouveau fichier PDF résultant avec le nom "DisableFilesCompression_out.pdf" dans le répertoire spécifié.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Exemple de code source pour désactiver la compression des fichiers à l'aide d'Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Configurer un nouveau fichier à ajouter en pièce jointe
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Spécifiez la propriété d'encodage en la définissant sur FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
// Ajouter une pièce jointe à la collection de pièces jointes du document
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Enregistrer la nouvelle sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment désactiver la compression de fichiers dans un PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant utiliser ces connaissances pour maintenir l'intégrité des fichiers joints sans compression.
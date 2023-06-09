---
title: Ajouter une pièce jointe
linktitle: Ajouter une pièce jointe
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter des pièces jointes à vos fichiers PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape pour une manipulation facile.
type: docs
weight: 10
url: /fr/net/programming-with-attachments/add-attachment/
---

Dans ce didacticiel, nous vous guiderons pas à pas dans le code source C # suivant pour ajouter une pièce jointe à un fichier PDF à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

### Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire où se trouve le fichier PDF auquel vous souhaitez ajouter la pièce jointe. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Étape 2 : Ouvrez le document PDF existant

Nous ouvrons le document PDF existant en utilisant le chemin spécifié.

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### Étape 3 : Configuration du nouveau fichier à ajouter en tant que pièce jointe

Nous configurons le nouveau fichier que nous voulons ajouter en pièce jointe. Dans cet exemple, nous ajoutons un fichier texte avec le nom "test.txt" et une description "Example text file".

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### Étape 4 : Ajout de la pièce jointe à la collection de pièces jointes du document

Nous ajoutons la pièce jointe à la collection de pièces jointes du document.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Étape 5 : Enregistrer le nouveau fichier de sortie

Enfin, nous enregistrons le nouveau fichier PDF résultant avec le nom "AddAttachment_out.pdf" dans le répertoire spécifié.

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### Exemple de code source pour Ajouter une pièce jointe à l'aide d'Aspose.PDF pour .NET
 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// Configurer un nouveau fichier à ajouter en pièce jointe
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// Ajouter une pièce jointe à la collection de pièces jointes du document
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// Enregistrer la nouvelle sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment ajouter une pièce jointe à un fichier PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant utiliser ces connaissances pour ajouter des fichiers supplémentaires en tant que pièces jointes à vos documents PDF.

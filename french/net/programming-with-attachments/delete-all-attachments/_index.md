---
title: Supprimer toutes les pièces jointes
linktitle: Supprimer toutes les pièces jointes
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à supprimer toutes les pièces jointes d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape pour une manipulation facile.
type: docs
weight: 20
url: /fr/net/programming-with-attachments/delete-all-attachments/
---
Dans ce didacticiel, nous vous guiderons pas à pas dans le code source C # suivant pour supprimer toutes les pièces jointes d'un fichier PDF à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

### Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire où se trouve le fichier PDF dont vous souhaitez supprimer les pièces jointes. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Étape 2 : Ouvrez le document PDF existant

Nous ouvrons le document PDF existant en utilisant le chemin spécifié.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### Étape 3 : Supprimez toutes les pièces jointes

Nous supprimons toutes les pièces jointes du document.

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### Étape 4 : Enregistrer le fichier mis à jour

Enfin, nous enregistrons le fichier PDF mis à jour sous le nom "DeleteAllAttachments_out.pdf" dans le répertoire spécifié.

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### Exemple de code source pour supprimer toutes les pièces jointes à l'aide d'Aspose.PDF pour .NET 

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
// Supprimer toutes les pièces jointes
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
// Enregistrer le fichier mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment supprimer toutes les pièces jointes d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant utiliser ces connaissances pour nettoyer vos documents PDF en supprimant toutes les pièces jointes indésirables.

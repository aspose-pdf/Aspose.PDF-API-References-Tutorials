---
title: Supprimer tout le texte
linktitle: Supprimer tout le texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à supprimer tout le texte d'un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 280
url: /fr/net/programming-with-text/remove-all-text/
---

Dans ce didacticiel, nous expliquerons comment supprimer tout le texte d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Nous allons passer par le processus étape par étape d'ouverture d'un PDF, de sélection et de suppression de texte de chaque page, et d'enregistrement du PDF modifié à l'aide du code source C# fourni.

## Exigences

Avant de commencer, assurez-vous que vous disposez des éléments suivants :

- La bibliothèque Aspose.PDF pour .NET installée.
- Une compréhension de base de la programmation C#.

## Étape 1 : Configurer le répertoire de documents

 Tout d'abord, vous devez définir le chemin d'accès au répertoire où se trouvent vos fichiers PDF. Remplacer`"YOUR DOCUMENT DIRECTORY"` dans le`dataDir` variable avec le chemin d'accès à vos fichiers PDF.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Ouvrez le document PDF

 Ensuite, nous ouvrons le document PDF en utilisant le`Document` classe de la bibliothèque Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Étape 3 : Supprimer le texte de chaque page

 Nous parcourons toutes les pages du document PDF et utilisons un`OperatorSelector` pour sélectionner tout le texte de chaque page. Ensuite, nous supprimons le texte sélectionné.

```csharp
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
     Page page = pdfDocument.Pages[i];
     OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
     page.Contents.Accept(operatorSelector);
     page.Contents.Delete(operatorSelector.Selected);
}
```

## Étape 4 : Enregistrer le PDF modifié

Enfin, nous enregistrons le document PDF modifié dans le fichier de sortie spécifié.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Exemple de code source pour Supprimer tout le texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Parcourez toutes les pages du document PDF
for (int i = 1; i <= pdfDocument.Pages.Count; i++)
{
	Page page = pdfDocument.Pages[i];
	OperatorSelector operatorSelector = new OperatorSelector(new Aspose.Pdf.Operators.TextShowOperator());
	// Sélectionner tout le texte de la page
	page.Contents.Accept(operatorSelector);
	// Supprimer tout le texte
	page.Contents.Delete(operatorSelector.Selected);
}
// Enregistrer le document
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Conclusion

Dans ce didacticiel, vous avez appris à supprimer tout le texte d'un document PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. En suivant le guide étape par étape et en exécutant le code C# fourni, vous pouvez ouvrir un PDF, sélectionner et supprimer du texte de chaque page et enregistrer le PDF modifié.
---
title: Rectangle de contrôle Ordre Z
linktitle: Rectangle de contrôle Ordre Z
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à contrôler l'ordre Z des rectangles dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 40
url: /fr/net/programming-with-graphs/control-rectangle-z-order/
---

Dans ce didacticiel, nous vous guiderons pas à pas dans le code source C # suivant pour contrôler l'ordre Z des rectangles à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

## Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF résultant. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : instanciation d'un objet document et ajout d'une page

Nous créons une instance de la classe Document et ajoutons une page à ce document.

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## Étape 3 : Configurer la taille de la page

Nous définissons la taille de la page PDF à l'aide de la méthode SetPageSize.

```csharp
page1.SetPageSize(375, 300);
```

## Étape 4 : Définition des marges de page

Nous pouvons configurer les marges de la page en utilisant les propriétés de l'objet PageInfo.

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## Étape 5 : Ajouter des rectangles avec l'ordre Z spécifié

Nous créons et ajoutons des rectangles à la page avec différentes couleurs et des ordres Z spécifiés.

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## Étape 6 : Enregistrer le fichier PDF résultant

Enfin, nous enregistrons le fichier PDF résultant sous le nom "ControlRectangleZOrder_out.pdf" dans le répertoire spécifié.

```csharp
doc1.Save(dataDir);
```
### Exemple de code source pour Control Rectangle Z Order utilisant Aspose.PDF pour .NET 

```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Instancier l'objet de classe Document
Document doc1 = new Document();
/// Ajouter une page à la collection de pages du fichier PDF
Aspose.Pdf.Page page1 = doc1.Pages.Add();
// Définir la taille de la page PDF
page1.SetPageSize(375, 300);
//Définir la marge de gauche pour l'objet de la page sur 0
page1.PageInfo.Margin.Left = 0;
// Définir la marge supérieure de l'objet de la page sur 0
page1.PageInfo.Margin.Top = 0;
// Créez un nouveau rectangle avec la couleur comme rouge, l'ordre Z comme 0 et certaines dimensions
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
// Créez un nouveau rectangle avec la couleur comme bleu, l'ordre Z comme 0 et certaines dimensions
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
// Créez un nouveau rectangle avec la couleur comme vert, l'ordre Z comme 0 et certaines dimensions
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
// Enregistrer le fichier PDF résultant
doc1.Save(dataDir);

```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment contrôler l'ordre Z des rectangles à l'aide d'Aspose.PDF pour .NET. Vous pouvez maintenant utiliser ces connaissances pour organiser et superposer des rectangles dans vos fichiers PDF avec précision.

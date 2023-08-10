---
title: Appliquer le style de numéro dans le fichier PDF
linktitle: Appliquer le style de numéro dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à appliquer un style de numérotation aux en-têtes d'un fichier PDF à l'aide d'Aspose.PDF pour .NET. Guide étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-headings/apply-number-style/
---
Dans ce didacticiel, nous vous guiderons pas à pas dans le code source C # suivant pour appliquer le style de numérotation dans un fichier PDF à l'aide d'Aspose.PDF pour .NET.

Assurez-vous d'avoir installé la bibliothèque Aspose.PDF et configuré votre environnement de développement avant de commencer. Avoir également des connaissances de base en programmation C#.

### Étape 1 : configuration du répertoire de documents

Dans le code source fourni, vous devez spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré. Remplacez la variable "dataDir" par le répertoire souhaité.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Étape 2 : Création du document PDF

Nous créons un nouveau document PDF avec des dimensions et des marges spécifiées.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### Étape 3 : Création d'une page et d'un conteneur flottant

Nous ajoutons une page au document et créons un conteneur flottant pour organiser le contenu.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### Étape 4 : Ajouter des titres avec numérotation

Nous créons des en-têtes avec des numérotations spécifiées et les ajoutons au conteneur flottant.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### Étape 5 : Enregistrer le document PDF

Nous enregistrons le document PDF généré dans le répertoire spécifié.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### Exemple de code source pour Apply Number Style à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment appliquer un style de numérotation aux en-têtes d'un document PDF à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais utiliser ces connaissances pour créer des documents PDF avec des numérotations personnalisées pour les en-têtes.

### FAQ pour appliquer le style de nombre dans le fichier PDF

#### Q : Qu'est-ce que le style de numérotation dans un document PDF ?

R : Le style de numérotation fait référence au format dans lequel les titres ou les sections sont numérotés dans un document PDF. Il peut inclure des chiffres, des lettres ou d'autres caractères pour fournir une structure hiérarchique.

#### Q : Pourquoi devrais-je appliquer un style de numérotation aux titres d'un document PDF ?

: L'application d'un style de numérotation aux titres améliore la lisibilité et l'organisation de votre document PDF. Il aide les lecteurs à naviguer facilement et à comprendre la structure hiérarchique du contenu.

#### Q : Qu'est-ce qu'Aspose.PDF pour .NET ?

R : Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de travailler avec des fichiers PDF par programmation dans des applications .NET. Il fournit un large éventail de fonctionnalités pour créer, éditer, convertir et manipuler des documents PDF.

#### Q : Comment importer les bibliothèques requises pour mon projet C# ?

R : Pour importer les bibliothèques nécessaires à votre projet C#, incluez les directives d'importation suivantes :

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

Ces directives vous permettent d'accéder aux classes et aux méthodes nécessaires pour travailler avec des documents PDF et appliquer des styles de numérotation.

#### Q : Comment spécifier le répertoire d'enregistrement du fichier PDF généré ?

R : Dans le code source fourni, modifiez la variable "dataDir" pour spécifier le répertoire dans lequel vous souhaitez enregistrer le fichier PDF généré.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin du répertoire réel.

#### Q : Comment créer un document PDF avec des dimensions et des marges spécifiées ?

R : Pour créer un document PDF avec des dimensions et des marges spécifiées, utilisez le code suivant :

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### : Comment puis-je ajouter des titres avec un style de numérotation au document PDF ?

R : Pour ajouter des titres avec un style de numérotation au document PDF, utilisez les exemples de code fournis pour créer des titres et personnaliser leurs styles de numérotation. Ajustez les propriétés telles que le texte, le style de numérotation, le numéro de début et la séquence automatique selon vos besoins.

#### Q : Comment enregistrer le document PDF généré ?

 R : Pour enregistrer le document PDF généré, utilisez le`Save` méthode de la`pdfDoc` objet:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### Q : Comment puis-je confirmer que le style de numérotation a été appliqué ?

R : Ouvrez le fichier PDF généré pour vérifier que le style de numérotation spécifié a été appliqué aux titres.

#### Q : Puis-je personnaliser davantage le style de numérotation ?

 R : Oui, vous pouvez personnaliser davantage le style de numérotation en ajustant les propriétés du`Heading` objets, tels que le type de style de numérotation, le numéro de départ et la séquence automatique.

#### Q : Puis-je appliquer différents styles de numérotation à différentes sections du document ?

 : Oui, vous pouvez appliquer différents styles de numérotation à différentes sections du document en créant plusieurs`Heading` objets avec différents styles et séquences.
---
title: Zone de texte
linktitle: Zone de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à créer un champ de texte dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 290
url: /fr/net/programming-with-forms/text-box/
---

Dans ce guide, nous expliquerons étape par étape comment utiliser la bibliothèque Aspose.PDF pour .NET pour créer un champ de texte dans un document PDF. Nous vous montrerons comment ouvrir le document, créer le champ de texte, personnaliser ses propriétés et enregistrer le PDF modifié.

## Etape 1 : Configuration du répertoire de documents

 La première étape consiste à configurer le répertoire de documents dans lequel se trouve le fichier PDF sur lequel vous souhaitez travailler. Vous pouvez utiliser le`dataDir`variable pour spécifier le chemin du répertoire.

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin d'accès réel à votre répertoire de documents.

## Étape 2 : Ouvrir le document PDF

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document`classe de Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Assurez-vous que le fichier PDF est présent dans le répertoire de documents spécifié.

## Étape 3 : création du champ de texte

 Nous allons créer un champ de texte en utilisant le`TextBoxField` classe. Vous pouvez spécifier les coordonnées de la position et la taille du champ à l'aide de la`Rectangle` classe.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Personnalisez les coordonnées, la taille, le nom partiel et la valeur du champ de texte selon vos besoins.

## Étape 4 : Personnalisez les propriétés du champ de texte

Dans cette étape, nous personnaliserons les propriétés du champ de texte telles que la bordure, la couleur, etc.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Personnalisez les propriétés du champ de texte selon vos préférences.

## Étape 5 : Ajouter le champ au document

Maintenant que nous avons créé et configuré le champ de texte, nous pouvons l'ajouter au document PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Étape 6 : Enregistrer le PDF modifié

 Enfin, nous pouvons enregistrer le PDF modifié en utilisant le`Save` méthode de la`Document` classe.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Assurez-vous de spécifier le chemin d'accès complet et le nom de fichier du PDF modifié.

### Exemple de code source pour la zone de texte utilisant Aspose.PDF pour .NET 
```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "TextField.pdf");
// Créer un champ
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
// TextBoxField.Border = nouvelle bordure(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
// Ajouter un champ au document
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
// Enregistrer le PDF modifié
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce guide, nous avons appris à utiliser la bibliothèque Aspose.PDF pour .NET pour créer un champ de texte dans un document PDF. En suivant les étapes décrites, vous pouvez personnaliser les propriétés du champ de texte et l'ajouter au document si nécessaire. N'hésitez pas à explorer davantage les fonctionnalités d'Aspose.PDF pour .NET afin d'élargir les possibilités de manipulation des fichiers PDF.
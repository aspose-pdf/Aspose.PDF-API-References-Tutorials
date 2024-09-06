---
title: Zone de texte
linktitle: Zone de texte
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment créer un champ de texte dans un document PDF à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 290
url: /fr/net/programming-with-forms/text-box/
---
Dans ce guide, nous vous expliquerons étape par étape comment utiliser la bibliothèque Aspose.PDF pour .NET pour créer un champ de texte dans un document PDF. Nous vous montrerons comment ouvrir le document, créer le champ de texte, personnaliser ses propriétés et enregistrer le PDF modifié.

## Étape 1 : Configuration du répertoire de documents

 La première étape consiste à configurer le répertoire de documents dans lequel se trouve le fichier PDF sur lequel vous souhaitez travailler. Vous pouvez utiliser l'`dataDir` variable pour spécifier le chemin du répertoire.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Assurez-vous de remplacer`"YOUR DOCUMENTS DIRECTORY"` avec le chemin réel vers votre répertoire de documents.

## Étape 2 : Ouverture du document PDF

 Dans cette étape, nous allons ouvrir le document PDF en utilisant le`Document` classe d'Aspose.PDF.

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

Assurez-vous que le fichier PDF est présent dans le répertoire de documents spécifié.

## Étape 3 : Création du champ de texte

 Nous allons créer un champ de texte en utilisant le`TextBoxField` classe. Vous pouvez spécifier les coordonnées de position et la taille du champ à l'aide de la`Rectangle` classe.

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

Personnalisez les coordonnées, la taille, le nom partiel et la valeur du champ de texte selon vos besoins.

## Étape 4 : Personnaliser les propriétés du champ de texte

Dans cette étape, nous allons personnaliser les propriétés du champ de texte telles que la bordure, la couleur, etc.

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

Personnalisez les propriétés du champ de texte selon vos préférences.

## Étape 5 : Ajout du champ au document

Maintenant que nous avons créé et configuré le champ de texte, nous pouvons l'ajouter au document PDF.

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## Étape 6 : enregistrement du PDF modifié

 Enfin, nous pouvons enregistrer le PDF modifié en utilisant le`Save` méthode de la`Document` classe.

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

Assurez-vous de spécifier le chemin complet et le nom de fichier du PDF modifié.

### Exemple de code source pour la zone de texte à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//Créer un champ
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

Dans ce guide, nous avons appris à utiliser la bibliothèque Aspose.PDF pour .NET pour créer un champ de texte dans un document PDF. En suivant les étapes décrites, vous pouvez personnaliser les propriétés du champ de texte et l'ajouter au document selon vos besoins. N'hésitez pas à explorer davantage les fonctionnalités d'Aspose.PDF pour .NET pour étendre les possibilités de manipulation des fichiers PDF.

### FAQ

#### Q : Puis-je utiliser Aspose.PDF pour .NET pour créer plusieurs champs de texte dans un seul document PDF ?

R : Oui, vous pouvez créer plusieurs champs de texte dans un seul document PDF à l'aide d'Aspose.PDF pour .NET. Répétez simplement le processus de création et de personnalisation des champs de texte pour chaque emplacement souhaité dans le document.

#### Q : Comment puis-je personnaliser l’apparence du champ de texte, comme la taille et la couleur de la police ?

R : Vous pouvez personnaliser l'apparence du champ de texte en modifiant ses propriétés, telles que la taille de la police, le style de police, la couleur, le style de bordure, la couleur d'arrière-plan, etc. Dans l'exemple de code source fourni, la largeur de la bordure, le motif de tiret de la bordure et la couleur du texte sont personnalisés.

#### Q : Est-il possible d’extraire le texte saisi par l’utilisateur à partir du champ de texte créé ?

R : Oui, vous pouvez extraire le texte saisi par l'utilisateur à partir du champ de texte créé. Une fois que les utilisateurs ont rempli le champ de texte dans le document PDF, vous pouvez récupérer la valeur du champ par programmation à l'aide d'Aspose.PDF pour .NET.

#### Q : Puis-je ajouter des champs de texte à un document PDF existant sans en créer un nouveau ?

R : Oui, vous pouvez ajouter des champs de texte à un document PDF existant sans en créer un nouveau. Aspose.PDF pour .NET offre la possibilité de modifier des documents PDF existants, notamment en ajoutant des champs de texte, des cases à cocher et d'autres éléments de formulaire.

#### Q : Aspose.PDF pour .NET prend-il en charge d’autres types de champs de formulaire, tels que les cases à cocher et les boutons radio ?

R : Oui, Aspose.PDF pour .NET prend en charge différents types de champs de formulaire, notamment les cases à cocher, les boutons radio, les listes déroulantes, etc. Vous pouvez utiliser la bibliothèque pour travailler avec différents types d'éléments de formulaire dans les documents PDF.
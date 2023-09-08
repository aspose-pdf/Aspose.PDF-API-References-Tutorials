---
title: Remplissage de texte arabe
linktitle: Remplissage de texte arabe
second_title: Aspose.PDF pour la référence de l'API .NET
description: Remplissez facilement les champs du formulaire PDF avec du texte arabe à l'aide d'Aspose.PDF pour .NET.
type: docs
weight: 20
url: /fr/net/programming-with-forms/arabic-text-filling/
---
Dans ce didacticiel, nous allons apprendre à remplir un champ de formulaire PDF avec du texte arabe à l'aide d'Aspose.PDF pour .NET. Aspose.PDF est une bibliothèque puissante qui permet aux développeurs de manipuler des documents PDF par programme. Nous vous guiderons pas à pas tout au long du processus, en vous expliquant le code source C# requis pour accomplir cette tâche.

## Étape 1 : Charger le contenu du formulaire PDF

Tout d’abord, nous devons charger le formulaire PDF contenant le champ que nous voulons remplir. On commence par définir le chemin vers le répertoire où se trouve le formulaire :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ensuite, nous créons un`FileStream` objet pour lire et écrire le fichier formulaire :

```csharp
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
```

 Ensuite, nous instancions un`Document` objet utilisant le flux qui contient le fichier formulaire :

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
```

## Étape 2 : Accédez au champ TextBoxField

 Pour remplir le champ du formulaire avec du texte arabe, nous devons accéder au`TextBoxField` champ que nous voulons remplir. Dans cet exemple, nous supposons que le nom du champ est « textbox1 ». Nous pouvons récupérer la référence du champ en utilisant le`Form` propriété du`pdfDocument` objet:

```csharp
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
```

## Étape 3 : Remplissez le champ du formulaire avec du texte arabe

 Maintenant que nous avons le`TextBoxField` référence, nous pouvons attribuer le texte arabe à sa`Value` propriété:

```csharp
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
```

## Étape 4 : Enregistrez le document mis à jour

Enfin, nous enregistrons le document mis à jour dans un nouveau fichier :

```csharp
dataDir = dataDir + "ArabicTextFilling_out.pdf";
pdfDocument.Save(dataDir);
```

Nous affichons également un message pour indiquer la réussite du remplissage du texte arabe :

```csharp
Console.WriteLine("\nArabic text successfully filled in the form field.\nFile saved in the following location: " + dataDir);
```

### Exemple de code source pour le remplissage de texte arabe à l'aide d'Aspose.PDF pour .NET 
```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Charger le contenu du formulaire PDF
FileStream fs = new FileStream(dataDir + "FillFormField.pdf", FileMode.Open, FileAccess.ReadWrite);
//Instancier une instance de document avec un fichier de formulaire contenant un flux
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(fs);
// Obtenir la référence d'un TextBoxField particulier
TextBoxField txtFld = pdfDocument.Form["textbox1"] as TextBoxField;
// Remplissez le champ du formulaire avec du texte arabe
txtFld.Value = "يولد جميع الناس أحراراً متساوين في";
dataDir = dataDir + "ArabicTextFilling_out.pdf";
// Enregistrer le document mis à jour
pdfDocument.Save(dataDir);
Console.WriteLine("\nArabic text filled successfully in form field.\nFile saved at " + dataDir);
```

## Conclusion

Dans ce didacticiel, nous avons exploré comment remplir un champ de formulaire PDF avec du texte arabe à l'aide d'Aspose.PDF pour .NET. Nous avons parcouru le processus étape par étape et expliqué le code source C# pertinent. En suivant ces instructions, vous pouvez facilement intégrer la fonctionnalité de remplissage de texte arabe dans vos applications .NET. Si vous avez d'autres questions ou avez besoin de plus d'informations, n'hésitez pas à contacter l'équipe d'assistance Aspose.PDF ou à consulter les ressources supplémentaires ci-dessous.

### FAQ

#### Q : Puis-je remplir d'autres types de champs de formulaire avec du texte arabe à l'aide d'Aspose.PDF pour .NET ?

 R : Oui, vous pouvez utiliser Aspose.PDF pour .NET pour remplir d'autres types de champs de formulaire avec du texte arabe, tels que des cases à cocher, des boutons radio, des zones de liste déroulante, etc. Le processus est similaire au remplissage d'un`TextBoxField` . Accédez simplement au champ spécifique en utilisant son nom ou son identifiant et définissez son`Value` propriété au texte arabe souhaité.

#### Q : Aspose.PDF pour .NET est-il compatible avec le texte arabe et l'écriture de droite à gauche (RTL) ?

R : Oui, Aspose.PDF pour .NET prend entièrement en charge le texte arabe et l'écriture RTL. Il gère correctement les caractères arabes et l'alignement du texte, garantissant que les documents PDF générés conservent la présentation visuelle correcte pour les langues s'écrivant de droite à gauche.

#### Q : Puis-je utiliser Aspose.PDF pour .NET pour extraire du texte arabe à partir de fichiers PDF existants ?

R : Oui, Aspose.PDF pour .NET fournit des fonctionnalités d'extraction de texte, vous permettant d'extraire du texte arabe à partir de fichiers PDF existants. Vous pouvez extraire par programme du texte de pages spécifiques ou de l'intégralité du document, y compris le texte arabe, à l'aide de la bibliothèque.

#### Q : Puis-je personnaliser l'apparence du texte arabe rempli dans le champ du formulaire ?

: Oui, vous pouvez personnaliser l'apparence du texte arabe rempli dans le champ du formulaire à l'aide d'Aspose.PDF pour .NET. Vous contrôlez les styles de police, les tailles, les couleurs et d’autres options de formatage du texte. Vous pouvez vous assurer que le texte arabe rempli correspond à l'apparence souhaitée dans le formulaire PDF.

#### Q : Comment puis-je obtenir de l'aide ou trouver des ressources supplémentaires pour Aspose.PDF pour .NET ?

R : Vous pouvez obtenir de l'aide pour Aspose.PDF pour .NET en visitant le forum d'assistance officiel d'Aspose ou en contactant directement leur équipe d'assistance. De plus, vous pouvez trouver une documentation utile, des exemples et des références API sur le site Web Aspose pour vous aider à mettre en œuvre diverses tâches liées aux PDF.
---
title: Créer une deuxième approche PDF multicouche
linktitle: Créer une deuxième approche PDF multicouche
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à créer un PDF multicouche à l'aide d'Aspose.PDF pour .NET. Guide étape par étape avec code source pour créer des PDF dynamiques avec du texte et des images.
type: docs
weight: 80
url: /fr/net/programming-with-document/createmultilayerpdfsecondapproach/
---

Dans ce didacticiel, nous allons explorer comment créer un PDF multicouche en utilisant la deuxième approche dans Aspose.PDF pour .NET. Nous fournirons un guide étape par étape avec des explications détaillées et inclurons le code source complet. En suivant ce didacticiel, vous serez en mesure de générer des documents PDF à plusieurs couches à l'aide de la bibliothèque Aspose.PDF dans vos applications .NET.

Commençons maintenant avec le guide étape par étape.

## Étape 1 : Configurer l'environnement

Pour commencer, ouvrez Visual Studio et créez un nouveau projet C#. Assurez-vous d'avoir référencé la bibliothèque Aspose.PDF dans votre projet. Une fois que vous avez configuré l'environnement, vous êtes prêt à passer à l'étape suivante.

## Étape 2 : Initialiser les variables

Dans cette étape, nous allons initialiser les variables nécessaires. Nous devons définir le chemin d'accès au répertoire du document et définir les variables de couleur pour les calques PDF. Voici l'extrait de code :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## Étape 3 : créer un document PDF

Ensuite, nous allons créer une nouvelle instance de la classe Aspose.Pdf.Document, qui représente un document PDF. Voici l'extrait de code :

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Étape 4 : Ajouter une page au document

Dans cette étape, nous ajouterons une nouvelle page au document PDF. Voici l'extrait de code :

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Étape 5 : Ajouter du texte à la page

Maintenant, nous allons ajouter un fragment de texte à la page. Le texte sera affiché sous la forme d'un segment de paragraphe 3 avec une couleur rouge. Voici l'extrait de code :

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## Étape 6 : Ajouter une image à la page

Dans cette étape, nous ajouterons une image à la page. L'image sera positionnée comme une boîte flottante avec une taille spécifique. Voici l'extrait de code :

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## Étape 7 : Enregistrez le PDF

Dans cette étape, nous allons enregistrer le PDF dans un fichier.

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### Exemple de code source pour la création d'une deuxième approche PDF multicouche à l'aide d'Aspose.PDF pour .NET.

```csharp

            
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
            
        
```

## Conclusion

Dans cet article, nous avons appris à créer un PDF multicouche en utilisant la deuxième approche d'Aspose.PDF pour .NET. Nous vous avons fourni des instructions étape par étape et le code source complet requis pour créer un PDF multicouche.
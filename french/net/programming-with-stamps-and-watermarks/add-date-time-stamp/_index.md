---
title: Ajouter un horodatage dans un fichier PDF
linktitle: Ajouter un horodatage dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Apprenez à ajouter facilement un horodatage dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
Dans cet article, nous vous expliquerons étape par étape comment ajouter un horodatage dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous vous montrerons comment utiliser le code source C# fourni pour ajouter un horodatage à un fichier PDF existant.

## Exigences

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 1 : Configurer l'environnement

Avant de pouvoir ajouter un horodatage à un document PDF, vous devez configurer votre environnement de développement. Voici les étapes à suivre :

1. Ouvrez votre IDE préféré (environnement de développement intégré).
2. Créez un nouveau projet C#.
3. Assurez-vous d'avoir ajouté une référence à la bibliothèque Aspose.PDF pour .NET.

## Étape 2 : Ajout de la bibliothèque Aspose.PDF

La bibliothèque Aspose.PDF pour .NET est nécessaire pour travailler avec des documents PDF dans votre projet.

## Étape 3 : Chargement du document PDF

La première étape pour ajouter un horodatage consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 4 : Création de l'horodatage

Maintenant que vous avez téléchargé le document

  PDF, vous pouvez créer l'horodatage à ajouter. Voici comment procéder :

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// Créer un tampon de texte
TextStamp textStamp = new TextStamp(annotationText);
```

Le code ci-dessus crée un nouveau tampon de texte contenant la date et l'heure actuelles.

## Étape 5 : Configurer les propriétés du tampon

Avant d'ajouter le tampon au document PDF, vous pouvez configurer diverses propriétés du tampon, telles que la marge, l'alignement horizontal et vertical, etc. Voici comment :

```csharp
// Définir les propriétés du tampon
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

Vous pouvez ajuster ces propriétés en fonction de vos besoins.

## Étape 6 : Ajouter un tampon au PDF

Maintenant que l'horodatage est prêt, vous pouvez l'ajouter à une page spécifique du document PDF. Voici comment:

```csharp
// Ajouter le tampon à la collection de tampons de la page
pdfDocument.Pages[1].AddStamp(textStamp);
```

Le code ci-dessus ajoute le tampon à la première page du document PDF. Vous pouvez spécifier une autre page si nécessaire.

## Étape 7 : Enregistrer le document de sortie

Une fois que vous avez ajouté la date et l'heure, vous pouvez enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour Ajouter un horodatage à l'aide d'Aspose.PDF pour .NET 
```csharp

// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// Créer un tampon de texte
TextStamp textStamp = new TextStamp(annotationText);

// Définir les propriétés du tampon
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// Ajout de tampon sur la collection de timbres
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## Conclusion

Félicitation ! Vous avez appris à ajouter un horodatage à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances à vos propres projets pour ajouter des horodatages aux documents PDF.

### FAQ pour ajouter un horodatage dans un fichier PDF

#### Q : Quel est le but d'ajouter un horodatage à un document PDF en utilisant Aspose.PDF pour .NET ?

: L'ajout d'un horodatage à un document PDF améliore sa valeur informative en indiquant quand le document a été modifié ou créé. Cette fonctionnalité est utile pour suivre les modifications apportées au document et fournir un point de référence pour l'historique du document.

#### Q : Puis-je personnaliser le format de l'horodatage pour répondre à des exigences spécifiques ?

 R : Oui, vous pouvez personnaliser le format de l'horodatage selon vos préférences. Le code source C# fourni utilise le`DateTime.Now.ToString()` méthode pour générer l'horodatage dans un format spécifique. Vous pouvez modifier ce code pour formater l'horodatage selon vos besoins.

#### Q : Est-il possible d'ajouter la date et l'heure à un emplacement spécifique sur une page PDF ?

 R : Absolument, vous pouvez ajuster l'emplacement de l'horodatage sur la page PDF en modifiant les propriétés du`TextStamp` objet. Le code fourni dans le didacticiel montre comment définir des propriétés telles que la marge, l'alignement et le positionnement vertical.

#### : Puis-je ajouter plusieurs horodatages sur différentes pages du même document PDF ?

 R : Oui, vous pouvez ajouter plusieurs horodatages sur différentes pages du même document PDF. Répétez simplement le processus de création d'un`TextStamp` objet et en configurant ses propriétés pour chaque page souhaitée.

#### Q : Comment puis-je modifier la police, la taille ou la couleur du texte de l'horodatage ?

 R : Pour modifier la police, la taille ou la couleur du texte de l'horodatage, vous pouvez personnaliser les propriétés du`DefaultAppearance` objet utilisé pour créer le`TextStamp`. Ajustez le nom, la taille et les valeurs de couleur de la police pour obtenir l'apparence souhaitée.

#### Q : Est-il possible d'ajouter d'autres types d'annotations ou de tampons à un document PDF à l'aide d'Aspose.PDF pour .NET ?

R : Oui, Aspose.PDF pour .NET fournit une large gamme de types d'annotations que vous pouvez ajouter aux documents PDF, notamment des annotations de texte, des tampons, des lignes, des formes, etc. Vous pouvez explorer la documentation Aspose.PDF pour plus de détails sur l'utilisation des annotations.

#### Q : Existe-t-il des limitations ou des considérations lors de l'ajout d'un horodatage à un document PDF ?

R : Bien que l'ajout d'un horodatage soit simple, tenez compte de facteurs tels que la mise en page du document et le contenu existant. Assurez-vous que l'emplacement du tampon ne cache pas d'informations importantes ou n'affecte pas la lisibilité du document.

#### Q : Comment puis-je intégrer cette méthode dans mes propres projets pour ajouter des horodatages aux documents PDF ?

R : Pour intégrer cette méthode, suivez les étapes fournies et ajustez le code en fonction de la structure de votre projet. Vous pouvez ajouter des horodatages aux documents PDF existants pour améliorer leur utilité et fournir une chronologie claire des modifications.

#### Q : Puis-je automatiser le processus d'ajout d'horodatages à plusieurs documents PDF ?

R : Oui, vous pouvez automatiser le processus d'ajout d'horodatages à plusieurs documents PDF en créant un script ou un programme qui parcourt une liste de documents et applique le même processus d'horodatage à chacun d'eux.
---
title: Ajouter un tampon de texte dans un fichier PDF
linktitle: Ajouter un tampon de texte dans un fichier PDF
second_title: Aspose.PDF pour la référence de l'API .NET
description: Découvrez comment ajouter facilement un tampon de texte dans un fichier PDF avec Aspose.PDF pour .NET.
type: docs
weight: 50
url: /fr/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
Dans ce didacticiel, nous vous expliquerons étape par étape comment ajouter un tampon de texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET. Nous allons vous montrer comment utiliser le code source C# fourni pour ajouter un tampon de texte personnalisé à une page spécifique du fichier PDF.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Chargement du document PDF

La première étape consiste à charger le document PDF existant dans votre projet. Voici comment:

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin d'accès réel au répertoire où se trouve votre document PDF.

## Étape 3 : Création du tampon de texte

Maintenant que vous avez téléchargé le document PDF, vous pouvez créer le tampon de texte à ajouter. Voici comment procéder :

```csharp
// Créer le tampon de texte
TextStamp textStamp = new TextStamp("Example Stamp");
```

Le code ci-dessus crée un nouveau tampon de texte contenant le texte spécifié.

## Étape 4 : configuration des propriétés du tampon de texte

Avant d'ajouter le tampon de texte au document PDF, vous pouvez configurer diverses propriétés du tampon, telles que l'arrière-plan, la position, la rotation, la police, la taille, etc. Voici comment procéder :

```csharp
// Configurer les propriétés du tampon de texte
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

Vous pouvez ajuster ces propriétés en fonction de vos besoins.

## Étape 5 : Ajouter un tampon de texte au PDF

Maintenant que le tampon texte est prêt, vous pouvez l'ajouter à une page spécifique du document PDF. Voici comment:

```csharp
//Ajouter un tampon de texte à une page spécifique
pdfDocument.Pages[1].AddStamp(textStamp);
```

Le code ci-dessus ajoute le tampon de texte à la première page du document PDF. Vous pouvez spécifier une autre page si nécessaire.

## Étape 6 : Enregistrez le document de sortie

Une fois que vous avez ajouté le tampon de texte, vous pouvez enregistrer le document PDF modifié. Voici comment:

```csharp
// Enregistrez le document de sortie
pdfDocument.Save(dataDir);
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour Ajouter un tampon de texte à l'aide d'Aspose.PDF pour .NET 
```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Ouvrir le document
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// Créer un tampon de texte
TextStamp textStamp = new TextStamp("Sample Stamp");

// Définir si le tampon est en arrière-plan
textStamp.Background = true;

// Définir l'origine
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Faire pivoter le tampon
textStamp.Rotate = Rotation.on90;

// Définir les propriétés du texte
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// Ajouter un tampon à une page particulière
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## Conclusion

Félicitation ! Vous avez appris à ajouter un tampon de texte à l'aide d'Aspose.PDF pour .NET. Vous pouvez désormais appliquer ces connaissances à vos propres projets pour ajouter des tampons de texte personnalisés aux documents PDF.

### FAQ pour ajouter un tampon de texte dans un fichier PDF

#### Q : Quel est le but d'ajouter un tampon de texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET ?

: L'ajout d'un tampon de texte vous permet de placer du texte personnalisé sur une page spécifique d'un document PDF. Cette fonctionnalité est utile pour ajouter des étiquettes, des commentaires, des filigranes ou toute autre information textuelle afin d'améliorer le contenu du document et de fournir un contexte supplémentaire.

#### Q : Puis-je personnaliser l’apparence du tampon de texte, comme la police, la taille, la couleur et la rotation ?

 R : Oui, vous pouvez entièrement personnaliser l’apparence du tampon de texte. Le code source C# fourni montre comment définir diverses propriétés du`TextStamp` objet, y compris la police, la taille de la police, le style de police, la couleur du texte, la couleur d'arrière-plan et la rotation.

#### Q : Est-il possible d'ajouter plusieurs tampons de texte sur différentes pages du même document PDF ?

R : Absolument, vous pouvez ajouter plusieurs tampons de texte sur différentes pages du même document PDF. Le code fourni par le didacticiel vous permet de spécifier la page cible pour ajouter le tampon de texte, ce qui le rend polyvalent pour différentes pages du document.

#### Q : Comment puis-je spécifier la position du cachet de texte dans le document PDF ?

 R : Vous pouvez personnaliser la position du cachet de texte en modifiant le`XIndent` et`YIndent` propriétés du`TextStamp` objet. Ces propriétés définissent les coordonnées du coin supérieur gauche du tampon par rapport à l'origine de la page.

#### Q : Puis-je appliquer cette méthode à des documents PDF existants pour ajouter des tampons de texte ?

R : Oui, vous pouvez appliquer cette méthode aux documents PDF existants pour ajouter des tampons de texte. Le code fourni dans le didacticiel montre comment charger un document PDF existant et ajouter un tampon de texte à une page spécifique.

#### Q : Puis-je ajouter des couleurs d’arrière-plan et de premier plan au tampon de texte ?

 R : Oui, vous pouvez ajouter des couleurs d’arrière-plan et de premier plan au tampon de texte. En définissant le`Background` propriété à`true` , vous pouvez fournir un arrière-plan coloré pour le tampon de texte. De plus, vous pouvez définir le`TextState.ForegroundColor` propriété pour spécifier la couleur du texte lui-même.

#### Q : Comment puis-je m'assurer que le cachet de texte ne masque pas le contenu sous-jacent du document PDF ?

 R : Lorsque vous ajoutez un cachet de texte, faites attention à son emplacement pour vous assurer qu'il n'obstrue pas les informations critiques ou n'affecte pas négativement la lisibilité du document. Vous pouvez ajuster le`XIndent` et`YIndent` propriétés pour positionner le tampon de texte de manière appropriée.

#### Q : Puis-je utiliser cette méthode pour ajouter des tampons autres que du texte, tels que des images ou des logos ?

R : Ce didacticiel spécifique se concentre sur l'ajout de tampons de texte, mais vous pouvez également ajouter d'autres types de tampons, tels que des images ou des logos, à l'aide d'Aspose.PDF pour .NET. Le processus implique la création de l'objet tampon approprié et la configuration de ses propriétés.

#### Q : Comment puis-je automatiser le processus d'ajout de tampons de texte à plusieurs documents PDF ?

R : Vous pouvez automatiser le processus d'ajout de tampons de texte à plusieurs documents PDF en créant un script ou un programme qui parcourt une liste de documents et applique le même processus de tamponnage de texte à chacun d'eux.
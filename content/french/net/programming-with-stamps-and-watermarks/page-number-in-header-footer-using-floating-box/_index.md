---
title: Numéro de page dans l'en-tête et le pied de page à l'aide d'une boîte flottante
linktitle: Numéro de page dans l'en-tête et le pied de page à l'aide d'une boîte flottante
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter le numéro de page dans l'en-tête et le pied de page d'un document PDF avec Aspose.PDF pour .NET.
type: docs
weight: 150
url: /fr/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
Dans ce tutoriel, nous vous expliquerons étape par étape comment ajouter un numéro de page dans l'en-tête et le pied de page d'un document PDF à l'aide de FloatingBox avec Aspose.PDF pour .NET. Nous utiliserons le code source C# fourni pour créer un document PDF, ajouter une page, créer une FloatingBox, définir sa position et y ajouter le numéro de page, puis enregistrer le document PDF modifié.

## Étape 1 : Configuration de l'environnement

Avant de commencer, assurez-vous de disposer des éléments suivants :

- Un environnement de développement .NET installé.
- La bibliothèque Aspose.PDF pour .NET téléchargée et référencée dans votre projet.

## Étape 2 : Création du document PDF et ajout d'une page

La première étape consiste à créer une instance du document PDF et à y ajouter une page. Voici comment procéder :

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Instancier le document PDF
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Ajouter une page au document PDF
Aspose.Pdf.Page page = pdf.Pages.Add();
```

Assurez-vous de remplacer « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin réel vers le répertoire dans lequel vous souhaitez enregistrer le document PDF.

## Étape 3 : création de la FloatingBox et ajout du numéro de page

Maintenant que la page est ajoutée au document PDF, nous pouvons créer une FloatingBox, définir sa position et y ajouter le numéro de page. Voici comment procéder :

```csharp
// Créez une FloatingBox avec une largeur de 140 et une hauteur de 80
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Définir la position gauche du paragraphe
box1. Left = 2;

// Définir la position supérieure du paragraphe
box1. Top = 10;

// Ajoutez le numéro de page à la FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Ajoutez la FloatingBox à la page
page.Paragraphs.Add(box1);
```

Le code ci-dessus crée une FloatingBox d'une largeur de 140 et d'une hauteur de 80. Ensuite, nous définissons sa position en spécifiant les valeurs left et top. Enfin, nous ajoutons le numéro de page à la FloatingBox à l'aide d'un TextFragment contenant la syntaxe "($p/ $P )" qui sera remplacée par le numéro de page actuel et le nombre total de pages.

## Étape 4 : enregistrement du document PDF modifié

Une fois le numéro de page ajouté à l'en-tête ou au pied de page à l'aide de FloatingBox, nous pouvons enregistrer le document PDF modifié. Voici comment procéder :

```csharp
// Enregistrer le document PDF modifié
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

Le code ci-dessus enregistre le document PDF modifié dans le répertoire spécifié.

### Exemple de code source pour le numéro de page dans l'en-tête et le pied de page à l'aide d'une boîte flottante avec Aspose.PDF pour .NET 
```csharp

// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Instancier l'instance de document
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// Ajouter une page dans le document PDF
Aspose.Pdf.Page page = pdf.Pages.Add();

// Initialise une nouvelle instance de la classe FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// Valeur flottante indiquant la position gauche du paragraphe
box1.Left = 2;

// Valeur flottante indiquant la position supérieure du paragraphe
box1.Top = 10;

// Ajoutez les macros à la collection de paragraphes de la FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// Ajouter une boîte flottante à la page
page.Paragraphs.Add(box1);

// Enregistrer le document
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## Conclusion

Félicitations ! Vous avez appris à ajouter un numéro de page dans l'en-tête et le pied de page d'un document PDF à l'aide de FloatingBox avec Aspose.PDF pour .NET. Vous pouvez désormais personnaliser vos en-têtes et pieds de page en ajoutant des informations dynamiques telles que le numéro de page.

### FAQ

#### Q : Qu'est-ce qu'une FloatingBox et comment est-elle utilisée pour ajouter des numéros de page dans l'en-tête ou le pied de page d'un document PDF ?

R : Une FloatingBox est un élément de mise en page polyvalent dans Aspose.PDF qui peut contenir divers contenus, notamment du texte et des images. Dans ce didacticiel, il est utilisé pour créer un conteneur pour le numéro de page, vous permettant d'insérer dynamiquement le numéro de page actuel et le nombre total de pages dans l'en-tête ou le pied de page.

#### Q : Comment le code source C# fourni permet-il d’ajouter des numéros de page à l’aide d’un FloatingBox ?

R : L'extrait de code montre comment créer un document PDF, ajouter une page, créer une FloatingBox, définir sa position dans la page et insérer le numéro de page à l'aide d'un TextFragment. La syntaxe « ($p/ $P ) » dans le TextFragment est remplacée par le numéro de page actuel et le nombre total de pages.

#### Q : Puis-je personnaliser l’apparence et la mise en forme du numéro de page ajouté à l’aide de FloatingBox ?

R : Oui, vous pouvez personnaliser l'apparence du numéro de page en modifiant les propriétés du TextFragment dans le FloatingBox. Vous pouvez modifier la taille de la police, la couleur, le style, l'alignement et d'autres options de formatage.

#### Q : Est-il possible d’ajouter différents éléments dynamiques, tels que la date et l’heure, à l’en-tête ou au pied de page en utilisant une approche similaire ?

R : Absolument, vous pouvez ajouter différents éléments dynamiques comme la date, l'heure, les métadonnées du document ou le texte personnalisé en modifiant le contenu du TextFragment dans la FloatingBox. Vous pouvez utiliser des macros comme « ($p/ $P ) » pour les numéros de page ou « ($date) » pour la date du jour.

#### Q : Comment spécifier la position du FloatingBox dans la section d'en-tête ou de pied de page ?
 A : Le code fourni définit la position de la FloatingBox à l'aide de`Left` et`Top` propriétés. Vous pouvez ajuster ces valeurs pour positionner la FloatingBox comme vous le souhaitez dans la section d'en-tête ou de pied de page.

#### Q : Puis-je utiliser une police ou un style différent pour le numéro de page dans l’en-tête ou le pied de page ?

R : Oui, vous pouvez personnaliser la police, le style et d’autres propriétés de formatage du texte du numéro de page en modifiant les propriétés TextFragment dans FloatingBox.

#### Q : Que se passe-t-il si le contenu de la FloatingBox dépasse ses dimensions ?

R : Si le contenu de la FloatingBox dépasse ses dimensions, il peut être coupé ou des problèmes de mise en page peuvent survenir. Assurez-vous que les dimensions de la FloatingBox sont adaptées au contenu et envisagez d'ajuster la mise en page si nécessaire.

#### Q : Est-il possible d'ajouter plusieurs FloatingBoxes avec un contenu différent à l'en-tête ou au pied de page de la même page ?

R : Oui, vous pouvez ajouter plusieurs FloatingBox avec un contenu différent à l'en-tête ou au pied de page de la même page en créant des instances FloatingBox distinctes et en les ajoutant à la collection Paragraphs de la page.

#### Q : Puis-je utiliser l’approche FloatingBox pour ajouter du contenu à d’autres sections du document PDF, comme le corps ou les marges ?

R : Bien que les FloatingBoxes soient couramment utilisées pour les en-têtes et les pieds de page, vous pouvez également les utiliser pour ajouter du contenu à d’autres sections du document PDF, telles que le corps ou les marges, en les positionnant en conséquence dans la page.
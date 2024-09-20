---
title: Ajouter une info-bulle au texte dans un fichier PDF
linktitle: Ajouter une info-bulle au texte dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter des info-bulles au texte des fichiers PDF à l'aide d'Aspose.PDF pour .NET. Améliorez vos PDF avec des textes de survol informatifs sans effort.
type: docs
weight: 90
url: /fr/net/programming-with-text/add-tooltip-to-text/
---
## Introduction

Pour créer des PDF attrayants et interactifs, les info-bulles peuvent s'avérer très utiles. Vous connaissez ces petites fenêtres contextuelles qui vous donnent des informations supplémentaires lorsque vous passez la souris sur quelque chose ? Elles peuvent fournir un contexte, des descriptions ou même des conseils sans encombrer votre document. Dans ce didacticiel, nous vous expliquerons comment ajouter des info-bulles au texte d'un fichier PDF à l'aide de la bibliothèque Aspose.PDF pour .NET. Que vous soyez un développeur chevronné ou que vous débutiez dans le monde des PDF, vous êtes au bon endroit ! Alors, plongeons-nous dans le vif du sujet !

## Prérequis

Avant de passer à la partie codage, assurons-nous que vous disposez de tout ce dont vous avez besoin pour suivre le cours en douceur.

### Visual Studio installé
Il est essentiel que Visual Studio soit installé sur votre machine, car il sera votre environnement de développement principal pour les applications .NET.

### Bibliothèque Aspose.PDF pour .NET
 Vous aurez également besoin de disposer de la bibliothèque Aspose.PDF. Vous pouvez[téléchargez-le ici](https://releases.aspose.com/pdf/net/)Assurez-vous de l'inclure dans vos références de projet.

### Connaissances de base de C#
Une connaissance du langage C# sera d'une grande aide, car nous coderons dans ce langage. Mais ne vous inquiétez pas, je vous guiderai à chaque étape !

### Un document PDF avec lequel travailler
Vous pouvez commencer avec un document PDF vierge, comme nous le faisons dans cet exemple, ou utiliser un document existant si vous préférez.

Maintenant, passons à la partie codage !

## Paquets d'importation 

 La première étape de notre aventure de codage consiste à importer les packages nécessaires. Ouvrez votre projet Visual Studio et, en haut de votre fichier C#, vous souhaiterez ajouter ce qui suit`using` directives:

```csharp
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

Ces packages vous donnent accès à toutes les classes et fonctionnalités dont vous avez besoin pour créer et manipuler des documents PDF.

## Étape 1 : Configurez votre répertoire de documents

Tout d'abord, nous devons définir le chemin où vous allez enregistrer vos documents. Considérez cela comme la recherche d'un endroit confortable dans votre système de fichiers où toutes vos créations résideront.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
```

 Assurez-vous de remplacer`YOUR DOCUMENT DIRECTORY` avec le chemin réel sur votre machine.

## Étape 2 : Créer un exemple de document PDF

Ensuite, il est temps de créer un PDF simple avec du texte. C'est ici que nous lançons notre processus créatif !

```csharp
//Créer un exemple de document avec du texte
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

Dans cette étape, nous créons un document, ajoutons deux fragments de texte et l’enregistrons dans le chemin précédemment spécifié.

## Étape 3 : Ouvrir le document pour le traitement

Maintenant que notre document est créé, ouvrons-le pour pouvoir travailler sur ces info-bulles !

```csharp
// Ouvrir un document avec du texte
Document document = new Document(outputFile);
```

Ici, nous chargeons simplement le document que nous venons de créer.

## Étape 4 : Créer un absorbeur de texte pour rechercher des fragments de texte

Nous devons trouver les fragments de texte dans lesquels nous souhaitons ajouter les infobulles. C'est comme utiliser une loupe pour mettre en évidence une partie spécifique d'une grande carte ! 

```csharp
// Créez un objet TextAbsorber pour trouver toutes les phrases correspondant à l'expression régulière
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorber);
```

## Étape 5 : Extraire des fragments de texte

Ensuite, nous extrayons les fragments de texte que nous avons trouvés à l’étape précédente.

```csharp
// Obtenir les fragments de texte extraits
TextFragmentCollection textFragments = absorber.TextFragments;
```

Cet extrait nous permet de conserver les références des fragments de texte qui nous intéressent.

## Étape 6 : Parcourez les fragments et ajoutez des info-bulles

Vient maintenant la partie amusante ! Nous allons parcourir chacun des fragments de texte et ajouter une info-bulle à chacun d'eux. Imaginez que vous emballez de petits cadeaux (info-bulles) autour d'éléments spécifiques (fragments de texte).

```csharp
// Boucle à travers les fragments
foreach (TextFragment fragment in textFragments)
{
	// Créer un bouton invisible sur la position du fragment de texte
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// La valeur AlternateName sera affichée sous forme d'info-bulle par une application de visualisation
	field.AlternateName = "Tooltip for text.";
	// Ajouter un champ de bouton au document
	document.Form.Add(field);
}
```

À chaque itération, nous créons un champ de bouton qui correspond à la position du fragment de texte et lui attribuons le texte de l'info-bulle.

## Étape 7 : Répétez l'opération pour les infobulles longues

Tout comme nous avons ajouté une simple info-bulle, nous pouvons faire la même chose pour un texte plus long. Élargissons notre créativité !

```csharp
// Ensuite, nous verrons un exemple d'info-bulle très longue
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	// Définir un texte très long
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
```

Ici, nous faisons le même genre de travail que précédemment, mais avec une info-bulle beaucoup plus étendue.

## Étape 8 : Enregistrez votre document

L’étape finale consiste à enregistrer votre document avec toutes ces nouvelles info-bulles brillantes. 

```csharp
// Enregistrer le document
document.Save(outputFile);
```

Et voilà, c'est fait ! Vous avez ajouté des info-bulles à votre PDF, le rendant ainsi plus convivial et interactif.

## Conclusion

Et voilà, un guide facile à suivre pour ajouter des info-bulles au texte des fichiers PDF à l'aide d'Aspose.PDF pour .NET. Cette technique peut améliorer considérablement l'expérience utilisateur, en rendant vos documents plus informatifs sans submerger le lecteur avec trop de texte à la fois. 

En passant simplement la souris sur un mot ou une phrase, le lecteur obtient des informations pertinentes qui ajoutent de la valeur sans encombrer le contenu. Alors, retroussez vos manches et essayez ! En un rien de temps, vous pourriez créer toutes sortes de documents attrayants qui se démarquent.

## FAQ

### Qu'est-ce qu'Aspose.PDF pour .NET ?
Aspose.PDF pour .NET est une bibliothèque qui permet aux développeurs de créer, manipuler et convertir des documents PDF dans des applications .NET.

### Puis-je utiliser Aspose.PDF gratuitement ?
 Oui, Aspose propose un essai gratuit pour vous permettre d'explorer ses fonctionnalités ! Vous pouvez le trouver[ici](https://releases.aspose.com/).

### Existe-t-il des options de licence disponibles pour Aspose.PDF ?
Oui, vous pouvez acheter une licence ou obtenir une licence temporaire. Découvrez les options[ici](https://purchase.aspose.com/).

### Puis-je ajouter des éléments interactifs autres que des info-bulles à l'aide d'Aspose.PDF ?
Absolument ! Aspose.PDF permet d'ajouter divers éléments interactifs tels que des hyperliens, des boutons et des formulaires.

### Où puis-je trouver plus de documentation sur Aspose.PDF ?
 Vous pouvez consulter la documentation[ici](https://reference.aspose.com/pdf/net/) pour des conseils plus approfondis.
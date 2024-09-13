---
title: Ajouter un tampon de texte dans un fichier PDF
linktitle: Ajouter un tampon de texte dans un fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment ajouter un tampon de texte dans un fichier PDF à l'aide d'Aspose.PDF pour .NET avec notre guide étape par étape et améliorez vos présentations de documents.
type: docs
weight: 50
url: /fr/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
## Introduction

À l'ère du numérique, les PDF sont un format courant pour le partage et la diffusion de documents. Que vous soyez un développeur, un créateur de contenu ou simplement quelqu'un qui cherche à améliorer ses fichiers PDF, savoir comment manipuler les PDF par programmation peut changer la donne. Une fonctionnalité intéressante que vous pourriez vouloir utiliser est la possibilité d'ajouter des tampons de texte dans vos fichiers PDF. L'ajout d'un tampon de texte peut donner à vos documents une touche professionnelle ou transmettre des informations importantes, telles que « Exemple », « Confidentiel » ou même un filigrane.

## Prérequis

Avant de passer au code, il y a quelques prérequis pour s'assurer que tout est correctement configuré. Voici ce dont vous aurez besoin :

1.  Aspose.PDF pour .NET : assurez-vous que la bibliothèque Aspose.PDF est installée dans votre projet. Si vous ne l'avez pas encore fait, vous pouvez la télécharger à partir du[Site Web d'Aspose](https://releases.aspose.com/pdf/net/).
2. Visual Studio ou IDE compatible : vous aurez besoin d'un environnement de développement pour écrire et exécuter votre code .NET. Visual Studio est le choix le plus courant parmi les développeurs.
3. Connaissances de base de C# : une familiarité avec C# et les principes de programmation orientée objet vous aidera à mieux comprendre les exemples.
4. Exemple de fichier PDF : vous devez disposer d'un fichier PDF prêt à l'emploi. Vous pouvez créer un fichier PDF de base ou utiliser n'importe quel fichier PDF existant pour tester la fonctionnalité.

Une fois ces prérequis réglés, nous pouvons passer au codage !

## Paquets d'importation

Maintenant, importons les packages nécessaires. Cette étape est cruciale car elle rend les classes et méthodes de la bibliothèque Aspose disponibles dans votre projet.

### Importer l'assemblage Aspose.PDF

Pour commencer, vous devez importer l'espace de noms Aspose.PDF. En haut de votre fichier C#, ajoutez la directive using suivante :

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Cela vous permettra d'accéder à des cours essentiels à la création et à la manipulation de documents PDF.

Passons maintenant au cœur du didacticiel. Nous allons décomposer le processus en étapes claires et concises. Chaque étape vous guidera à travers le code pour ajouter un tampon de texte à un fichier PDF.

## Étape 1 : Configurer le répertoire de documents

Tout d'abord, vous devez définir le répertoire dans lequel votre document PDF est stocké. Cela signifie que votre code doit savoir où trouver le fichier PDF que vous souhaitez modifier.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Explication : Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel où se trouve votre fichier PDF (`AddTextStamp.pdf`) est stocké. Ce chemin est utilisé ultérieurement pour ouvrir et enregistrer le PDF modifié.

## Étape 2 : Ouvrir le document PDF

 Ensuite, nous allons ouvrir le document PDF en utilisant le`Document` classe de l'espace de noms Aspose.PDF.

```csharp
// Ouvrir le document
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

 Explication : Ici, nous créons une instance de`Document` classe et en passant le chemin vers notre fichier PDF. Cela chargera le PDF afin que nous puissions le manipuler.

## Étape 3 : Créer un tampon de texte

Nous allons maintenant créer un tampon de texte que nous appliquerons plus tard à notre document PDF.

```csharp
// Créer un tampon de texte
TextStamp textStamp = new TextStamp("Sample Stamp");
```

 Explication : Le`TextStamp` L'objet est créé avec le texte que vous souhaitez afficher. Dans ce cas, nous utilisons « Sample Stamp » comme texte pour notre tampon.

## Étape 4 : définir les propriétés du tampon

Pour personnaliser votre tampon, nous pouvons définir diverses propriétés telles que la couleur d'arrière-plan, la position et la rotation. Faisons-le maintenant :

```csharp
// Définir si le tampon est en arrière-plan
textStamp.Background = true;

// Définir l'origine
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// Faire pivoter le timbre
textStamp.Rotate = Rotation.on90;
```

Explication:
- Contexte : définir ceci sur`true` signifie que le tampon apparaîtra derrière le contenu du PDF.
- XIndent et YIndent : ces propriétés déterminent la position du tampon sur la page. Dans cet exemple, le tampon sera placé à 100 unités des bords gauche et supérieur de la page.
- Rotation : cette option fait pivoter le tampon de 90 degrés. Vous pouvez choisir différentes options de rotation en fonction de vos exigences de conception.

## Étape 5 : Personnaliser les propriétés du texte

Ensuite, faisons preuve de créativité en personnalisant l’apparence du texte dans notre tampon :

```csharp
// Définir les propriétés du texte
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(Color.Aqua);
```

Explication:
- Police : Nous utilisons la police Arial et la mettons en gras et en italique.
- Taille de police : elle est définie sur 14 points.
- Couleur de premier plan : utilisez RVB pour définir la couleur du texte sur Aqua. N'hésitez pas à modifier la couleur pour l'adapter à vos besoins en matière de marque ou de conception !

## Étape 6 : ajouter un tampon à la page PDF

Il est maintenant temps d'ajouter le tampon à une page spécifique du document PDF.

```csharp
// Ajouter un tampon à une page particulière
pdfDocument.Pages[1].AddStamp(textStamp);
```

Explication : Dans cet exemple, le tampon est ajouté à la première page du PDF (les pages sont indexées à 1). Ajustez le numéro de page selon les besoins de votre document.

## Étape 7 : Enregistrer le PDF modifié

Enfin, enregistrons le document avec le tampon de texte nouvellement ajouté.

```csharp
dataDir = dataDir + "AddTextStamp_out.pdf";

// Enregistrer le document de sortie
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);
```

Explication : Nous définissons un nouveau chemin pour le fichier de sortie, puis enregistrons le document modifié. Après l'enregistrement, le chemin est imprimé sur la console, confirmant la réussite de l'opération.

## Conclusion

Félicitations ! Vous avez ajouté avec succès un tampon de texte à un fichier PDF à l'aide d'Aspose.PDF pour .NET. Cette méthode vous permet d'annoter vos documents de manière efficace, améliorant ainsi leur professionnalisme et leur facilité d'utilisation. Que vous ajoutiez des filigranes, des signatures ou de simples notes, la bibliothèque Aspose fournit des outils puissants pour manipuler vos PDF en toute simplicité.

## FAQ

### Qu'est-ce qu'un tampon de texte dans un PDF ?
Un tampon de texte est une superposition graphique contenant du texte qui peut être placé sur un document PDF, souvent utilisé pour des annotations ou des filigranes.

### Puis-je personnaliser le tampon avec des images ?
Oui, Aspose.PDF prend également en charge l'ajout de tampons d'image, offrant ainsi une plus grande flexibilité de conception.

### Quels langages de programmation puis-je utiliser avec Aspose.PDF ?
Aspose.PDF est principalement axé sur .NET, mais il existe des versions disponibles pour d'autres langages comme Java et Python.

### Comment obtenir une licence temporaire pour Aspose.PDF ?
 Vous pouvez demander une licence temporaire en visitant le[lien d'achat](https://purchase.aspose.com/temporary-license/) sur leur site internet.

### Où puis-je trouver de l'aide pour Aspose.PDF ?
 Le support pour Aspose.PDF est disponible sur leur[Forum de soutien](https://forum.aspose.com/c/pdf/10).
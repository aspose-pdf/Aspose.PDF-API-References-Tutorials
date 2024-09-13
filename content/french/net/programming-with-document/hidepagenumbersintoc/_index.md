---
title: Masquer les numéros de page dans la table des matières
linktitle: Masquer les numéros de page dans la table des matières
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment masquer les numéros de page dans la table des matières à l'aide d'Aspose.PDF pour .NET. Suivez ce guide détaillé avec des exemples de code pour créer des PDF professionnels.
type: docs
weight: 220
url: /fr/net/programming-with-document/hidepagenumbersintoc/
---
## Introduction

Lorsque vous travaillez avec des fichiers PDF, vous souhaiterez peut-être parfois générer une table des matières (TOC) tout en masquant les numéros de page pour une présentation plus soignée. Peut-être que le document s'en sort mieux sans eux, ou peut-être s'agit-il d'un choix esthétique. Quelle que soit votre raison, si vous travaillez avec Aspose.PDF pour .NET, ce didacticiel vous montrera exactement comment masquer les numéros de page dans votre table des matières.

## Prérequis

Avant de commencer, vous devez mettre en place quelques éléments. Voici une liste de contrôle rapide :

- Visual Studio installé : vous aurez besoin d’une version fonctionnelle de Visual Studio pour coder.
- Bibliothèque Aspose.PDF pour .NET : assurez-vous d'avoir installé la bibliothèque Aspose.PDF pour .NET.
  -  Lien de téléchargement :[Aspose.PDF pour .NET](https://releases.aspose.com/pdf/net/)
- Licence temporaire : si vous testez les fonctionnalités, il est utile de disposer d'une licence temporaire.
  -  Licence temporaire :[Obtenez-le ici](https://purchase.aspose.com/temporary-license/)

## Paquets d'importation

Avant de vous lancer dans le code, assurez-vous d'importer les espaces de noms suivants dans votre projet C#. Ceux-ci fourniront les classes et méthodes nécessaires pour travailler avec des documents PDF et créer votre table des matières (TOC).

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

Maintenant que votre environnement est prêt et que les packages sont importés, décomposons chaque étape du processus. Nous couvrirons chaque partie du code pour garantir la clarté, afin que vous puissiez suivre facilement.

## Étape 1 : Initialisez votre document PDF

La première chose que nous devons faire est de créer un nouveau document PDF et d’ajouter une page pour la table des matières (TOC).


```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "HiddenPageNumbers_out.pdf";
Document doc = new Document();
Page tocPage = doc.Pages.Add();
```

- dataDir : il s’agit du répertoire dans lequel votre fichier de sortie sera enregistré.
- Document() : Initialise un nouveau document PDF.
- Pages.Add() : ajoute une nouvelle page vierge au document, qui contiendra plus tard votre table des matières.

## Étape 2 : Configurer les informations et le titre de la table des matières

Ensuite, nous définirons les informations de la table des matières, y compris la définition du titre qui apparaîtra en haut de la table des matières.

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

- TocInfo : cet objet contient toutes les informations sur la table des matières.
- TextFragment : représente le texte du titre de la table des matières, ici nous le définissons comme « Table des matières ».
- FontStyle : nous stylisons le titre de la table des matières en définissant sa taille sur 20 et en le mettant en gras.
- tocPage.TocInfo : Nous attribuons les informations de la table des matières à la page qui affichera la table des matières.

## Étape 3 : masquer les numéros de page dans la table des matières

Passons maintenant à la partie amusante ! C'est ici que nous configurons la table des matières pour masquer les numéros de page.

```csharp
tocInfo.IsShowPageNumbers = false;
tocInfo.FormatArrayLength = 4;
```

-  IsShowPageNumbers : il s'agit du commutateur magique qui masque les numéros de page. Réglez-le sur`false`, et les numéros de page n'apparaîtront pas dans la table des matières.
- FormatArrayLength : nous définissons cette valeur sur 4, indiquant que nous souhaitons définir la mise en forme pour quatre niveaux de titres de table des matières.

## Étape 4 : Personnaliser le formatage de la table des matières

Pour ajouter plus de style à votre table des matières, nous allons maintenant définir la mise en forme pour différents niveaux de titres.

```csharp
tocInfo.FormatArray[0].Margin.Right = 0;
tocInfo.FormatArray[0].TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
tocInfo.FormatArray[1].Margin.Left = 30;
tocInfo.FormatArray[1].TextState.Underline = true;
tocInfo.FormatArray[1].TextState.FontSize = 10;
tocInfo.FormatArray[2].TextState.FontStyle = FontStyles.Bold;
tocInfo.FormatArray[3].TextState.FontStyle = FontStyles.Bold;
```

- FormatArray : ce tableau contrôle la mise en forme des entrées de la table des matières. Chaque index représente un niveau de titre différent.
- Marge et style de texte : nous définissons des marges et appliquons des styles de police tels que gras, italique et souligné pour chaque niveau de titre.

## Étape 5 : Ajouter des titres au document

Enfin, ajoutons les titres réels qui feront partie de la table des matières.

```csharp
Page page = doc.Pages.Add();
for (int Level = 1; Level != 5; Level++)
{ 
    Heading heading2 = new Heading(Level); 
    TextSegment segment2 = new TextSegment(); 
    heading2.TocPage = tocPage; 
    heading2.Segments.Add(segment2); 
    heading2.IsAutoSequence = true; 
    segment2.Text = "this is heading of level " + Level; 
    heading2.IsInList = true; 
    page.Paragraphs.Add(heading2); 
}
```

- Titre et segment de texte : ils représentent les titres qui apparaîtront dans votre table des matières. Chaque niveau possède son propre titre.
- IsAutoSequence : numérote automatiquement les titres.
- IsInList : garantit que chaque titre apparaît dans la table des matières.

## Étape 6 : Enregistrer le document

Une fois que tout est défini, enregistrez le document PDF dans votre fichier de sortie spécifié.

```csharp
doc.Save(outFile);
```

Et voilà ! Vous avez réussi à créer un PDF avec une table des matières et les numéros de page sont masqués !

## Conclusion

Créer une table des matières dans un PDF et masquer les numéros de page peut sembler compliqué, mais avec Aspose.PDF pour .NET, c'est un jeu d'enfant. En suivant ce guide étape par étape, vous avez appris à personnaliser le format de la table des matières, à masquer les numéros de page et à appliquer différents styles à vos titres. Vous pouvez désormais créer des PDF professionnels adaptés à vos besoins précis.

## FAQ

### Puis-je afficher les numéros de page pour des titres spécifiques dans la table des matières ?
Non, Aspose.PDF masque ou affiche les numéros de page pour l'ensemble de la table des matières. Vous ne pouvez pas les masquer de manière sélective pour des entrées spécifiques.

### Est-il possible d'ajouter plus de niveaux à la table des matières ?
 Oui, vous pouvez augmenter le`FormatArrayLength` pour définir davantage de niveaux de titres de table des matières.

### Comment puis-je changer la police de toutes les entrées de la table des matières ?
 Vous pouvez changer la police en modifiant le`TextState.Font` propriété pour chaque niveau dans le`FormatArray`.

### Puis-je insérer des hyperliens dans la table des matières ?
 Oui, vous pouvez lier chaque entrée de la table des matières à une section spécifique du document à l'aide de l'`Heading.TocPage` propriété.

### Ai-je besoin d'une licence pour Aspose.PDF ?
Oui, une licence valide est requise pour une utilisation en production. Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/) pour tester les fonctionnalités.
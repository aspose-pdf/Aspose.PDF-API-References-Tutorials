---
title: Spécifier l'espacement des lignes dans le fichier PDF
linktitle: Spécifier l'espacement des lignes dans le fichier PDF
second_title: Référence de l'API Aspose.PDF pour .NET
description: Découvrez comment spécifier l'espacement des lignes dans un PDF à l'aide d'Aspose.PDF pour .NET grâce à ce guide étape par étape. Idéal pour les développeurs à la recherche d'une mise en forme de texte précise.
type: docs
weight: 510
url: /fr/net/programming-with-text/specify-line-spacing/
---
## Introduction

Avez-vous déjà eu du mal à contrôler l'espacement des lignes dans un fichier PDF ? Peut-être avez-vous eu du texte qui semble trop chargé ou qui n'est tout simplement pas aussi soigné que vous le souhaiteriez. Dans ce didacticiel, nous allons vous expliquer comment spécifier facilement l'espacement des lignes dans un PDF à l'aide d'Aspose.PDF pour .NET. Nous utiliserons un guide simple, étape par étape, pour vous faire passer d'un PDF vierge à un PDF incluant un espacement de ligne personnalisé. C'est parfait si vous avez besoin de précision dans la mise en page de votre texte pour des documents tels que des rapports, des factures ou des certificats.

## Prérequis

Avant de passer au code, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1.  Aspose.PDF pour .NET est installé. Si vous ne l'avez pas, récupérez-le à partir du[Page de téléchargement d'Aspose.PDF](https://releases.aspose.com/pdf/net/).
2. Un environnement de développement .NET (comme Visual Studio).
3. Un fichier de police TrueType (`.ttf` ) que nous utiliserons dans l'exemple. Vous pouvez utiliser n'importe quelle police, mais pour ce guide, nous utiliserons la`HPSimplified.TTF` fonte.
4. Connaissances de base de C# et de manipulation PDF.

Si vous êtes prêt, passons à l’importation des packages nécessaires.

## Paquets d'importation

Dans votre projet C#, vous devrez importer les espaces de noms Aspose.PDF pour utiliser les fonctionnalités PDF. Voici comment procéder :

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

Ces espaces de noms vous permettent de créer et de manipuler des documents PDF, ainsi que de travailler avec des options de formatage de texte et de police.

Nous allons décomposer ce processus en étapes simples, afin que vous puissiez le suivre facilement. Chaque étape se concentrera sur une partie clé du processus, de la configuration de votre PDF à la spécification de l'espacement des lignes.

## Étape 1 : Configurez votre projet et définissez le répertoire des documents

La première chose à faire est de définir où se trouvent nos fichiers. Cela permet au programme de savoir où trouver la police et où enregistrer le PDF obtenu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 Dans cette étape, vous remplacerez`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel vers lequel vous stockez vos fichiers. C'est là que vous placerez votre fichier de police (`HPSimplified.TTF`) et où le PDF sera enregistré.

## Étape 2 : charger un document PDF

Maintenant, nous devons créer un nouveau document PDF. Pour ce guide, nous commencerons avec un document vierge, mais vous pouvez également charger un PDF existant si nécessaire.

```csharp
Document doc = new Document();
```

Cela crée un nouveau document PDF vide. Facile, non ?

## Étape 3 : définir les options de formatage du texte

 C'est ici que la magie opère. Nous allons spécifier le mode d'espacement des lignes pour le texte que nous voulons ajouter au PDF. Aspose.PDF nous offre plusieurs options, mais dans ce guide, nous utiliserons`LineSpacingMode.FullSize`, ce qui garantit que l'interligne est entièrement respecté.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 Ce code définit le mode d'espacement des lignes sur`FullSize` , garantissant que le texte sera affiché avec un espacement approprié. Il existe d'autres options comme`Proportional` si vous voulez des comportements d'espacement différents, mais pour l'instant, restons-en à`FullSize`.

## Étape 4 : Créer un fragment de texte

Nous allons maintenant créer le texte qui sera placé dans le PDF. Ce texte respectera l'interligne que nous avons défini.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 Nous avons créé un fragment de texte avec la chaîne`"Hello world"`Vous pouvez, bien sûr, personnaliser ce texte comme bon vous semble.

## Étape 5 : charger et appliquer une police personnalisée

Pour faire ressortir le texte, nous allons charger une police TrueType personnalisée à partir d'un fichier. Cette étape est facultative, mais elle peut ajouter une touche professionnelle à vos PDF.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

Ici, nous chargeons le fichier de police et l'appliquons au fragment de texte. Si le chemin du fichier est valide, la police est utilisée. Sinon, la police par défaut est appliquée.

## Étape 6 : définir la position et la mise en forme du texte

Ensuite, nous devons positionner le texte sur le PDF. Nous appliquerons également les options de formatage que nous avons créées précédemment.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 Le`Position` La méthode définit les coordonnées où le texte apparaîtra sur la page (dans ce cas, 100 unités à partir de la gauche et 600 unités à partir du bas). Les options de formatage, y compris le mode d'espacement des lignes, sont appliquées ici.

## Étape 7 : ajouter du texte à la page PDF

Maintenant que notre texte est formaté et positionné, il est temps de l'ajouter au document PDF.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

Ce code crée une nouvelle page dans le document PDF et y ajoute le fragment de texte.

## Étape 8 : Enregistrez le PDF

Nous avons atteint l'étape finale ! Maintenant que tout est configuré, enregistrons le PDF.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

Cela enregistre le PDF avec l’espacement des lignes spécifié et votre fichier est prêt !

## Conclusion

Et voilà ! Vous venez de créer un document PDF avec un espacement de ligne personnalisé à l'aide d'Aspose.PDF pour .NET. Il s'agit d'un outil puissant qui vous permet de contrôler tous les aspects de vos fichiers PDF, et ce n'est qu'un exemple de ce que vous pouvez réaliser. Du placement du texte au formatage, les possibilités sont infinies.

Si vous souhaitez approfondir la manipulation des PDF, Aspose.PDF propose une multitude de fonctionnalités à explorer. N'hésitez pas à expérimenter et à repousser les limites de ce que vous pouvez faire avec vos documents !

## FAQ

### Puis-je ajuster l'espacement des lignes à d'autres modes ?  
 Oui, vous pouvez utiliser d'autres modes comme`Proportional` ou`Fixed` selon vos besoins.

### Est-il possible de charger des polices depuis le système au lieu d'un fichier ?  
 Oui, vous pouvez charger les polices installées sur le système à l'aide de l'`FontRepository`.

### Puis-je utiliser Aspose.PDF pour .NET avec d’autres formats de fichiers ?  
Absolument ! Aspose.PDF pour .NET prend en charge une variété de formats tels que XML, HTML, etc.

### Ai-je besoin d'une licence pour utiliser Aspose.PDF pour .NET ?  
Oui, pour bénéficier de toutes les fonctionnalités, vous aurez besoin d'une licence, que vous pouvez obtenir[ici](https://purchase.aspose.com/buy).

### Comment définir l'interligne pour plusieurs paragraphes ?  
 Vous pouvez postuler`TextFormattingOptions` à chacun`TextFragment` ou`TextParagraph` pour contrôler l'espacement de plusieurs lignes ou paragraphes.